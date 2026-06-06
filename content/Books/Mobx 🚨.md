---
publish: true
created: 2026-05-29T08:57:35.757+05:30
modified: 2026-06-06T09:39:48.706+05:30
---

> Mobx is a reactive [^2] state management library.

## Introduction

The UI is always representation of the state. State is the term used for client-data.
Hence, `UI = fn(state);`

`State ---> UI  ---> Action ----> State`

A component should have one single responsibility, with this it becomes more easier to main the UI based on the state. - Referring to SingleResponsibilituPrinciple [^1]

## Observables

These are the state values.

To add observability to primitive types, functions and class-objects use `observable.box`
For array, map and object `observable` can be used. There are also specialized functions to these as well. `observale.array([])`, `observable.map()` & `observable.object({})`

We should use `toJS` function to convert the observable types into normal JS objects.

`observables` support shallow and deep observability.
By default when observale.object or array of map is used it's deep observability. If we want shallow observability we have to say so.
Example

```js
const arr = observale.array([], {deep: false});
const map = observale.array(value, {deep: false});
const obj = observale.array(value, decorator ,{deep: false});
```

mobx also supports decorators, `@observable` is the decorator. Here also by default it's deep observability. `decorators` are only used within classes

```js
@observable.shallow items = [];
@observable modified = {};
```

## Actions

The observable state should be modified only within the `action` function.
To enforce the use of action to modify observable we can config by adding

```ts
import { configure } from 'mobx';
configure({
	enforceActions: true
});
```

`@action` this is the decorator for action.  Within the class we use `@action.bound` to bind `this` to the respective class property.

```ts
class Cart {
	@action.bound
	removeItem(name:string){
		/*
		*...
		*/
	}
}
```

Other way of binding `this` is by using arrow function to bind the method to the class and make the method the property of the class

```js
class Cart {
	@action removeItem = (name:string) => {
		/*
		*...
		*/
	};
}

```

## Reactions

Mobx provides 3 different ways to express this.

### **1. autorun** ^53b126

It's a long running function, which takes in the effect-function and run till autorun is cancelled.

```js
autorun(() => {console.log(`continue to print`, item.count)});
```

To cancel the long run of autorun, we can use the disposer.
`autorun` return a disposer value which can be used to cancel out the autorun in the future when required.

```js
let disposer = null;

disposer = autorun(() => {/*....*/});

disposer(); // This prevents further autorun
```

### 2. **reaction**

This is similar to [[#^53b126|autorun]], in this case it waits for the observables to change before executing

Signature of `reaction`

```
reaction(tracker-function, effect-function): disposer-function;

tracker-function: () => data;
effect-function:  (data) => {};
```

tracker-function is where all the observables are tracked.
This gives more control over when we can run. `reaction` run only when the data/return value returned from `tracker-function` is different from it's previous value.
`reaction` also return a disposer-function which can be used to cancel the future reactions.

```
class PanelExtension{

	let reactionDisposer = null;

	construction(){
		this.reactionDisposer = reaction(this.tracerFunction, this.effectFunction);
	}

	@computed
	get tracerFunction(){
		/*
		...
		*/
		return data;
	}
	
	effectFunction(data){
		/*
		.
		*/
	}

	disposer(){
		this.reactionDisposer();
	}

}
```

The `observer` decorator which gets imported from `mobx-react` is a reaction.

```
import { observer } from 'mobx-react';

const observedComponent = observer(normalReactComponent);

```

The `tracker-function`'s are the observables used within the component
The `effect-function` is the react-component.

### 3. **when**

`when` only executes the `effect-function` when the condition is met and automatically disposes the side-effect after that.
`when` is a one time side-effect, than the other 2 reaction methods.

**Signature**

```
when(predicate-function, effect-function): disposer-function;

predicate-function: () => boolean;

effect-function: () => {};
```

`predicate-function` returns Boolean values. when it becomes `true` then the `effect-function` runs and when is automatically disposed.

---

## Code sample

```jsx
<Provider uiStore={ui} experienceStore={exp}>
	<App />
</Provider>


@inject('uiStore')
@observer
class App extends React.Component {
	render(){
		const {uiStore} = this.props;

		return (
		<>
			...
		</>
		)
	}
}
```

---

> [!tip] `@observable` is a shorter form or an alias of `@observable.deep`, which is the default decorator. It applies deep observability at all levels of objects, arrays, and maps. However, the deep observation stops at places where the object has a constructor or a prototype . Such objects are usually instances of classes and are expected to have their own observable properties. MobX chooses to skip such objects during deep observation.

```syntax
observable(properties, decorators, options)
```

---

## Links/References

- https://packt-mobx.surge.sh/ch02/when#/
- https://github.com/PacktPublishing/MobX-Quick-Start-Guide/tree/master

> **Principle**
>
> Anything that can be derived from the application state, should be derived. Automatically

- JSON-patch - RFC-6902

---

## Footnotes

[^1]:  Single Responsibility Principle - SRP
Which basically means, the class/object/module should have only one reason to change.

[^2]: Reactivity is a paradigm, which is closely associated with functional programming.
