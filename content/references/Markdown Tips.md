---
publish: true
created: 2026-05-19T13:55:12.126+05:30
modified: 2026-05-19T14:00:44.379+05:30
---

# Markdown Tips

Adding checkbox

```md
- [ ] Todo task
- [x] Complete Task stricked out
```

Text decoration

- Underline

```md
<span style='text-decoration: underline'>will this be stricketed out</span>
```

**Example** : <span style='text-decoration: underline'>will this be Underlied</span>

Strike out : `line-through`

<span style='text-decoration: line-through'>will this be stricketed out</span>

```
Markdown with CSS
```

<span style='color:red; font-size: 40px'>Red COlor</span>

Styling as Bold

```md
**Bold**

```

Example : **Bold**

## Adding table of contents

**Meaning**: At the start of the page, we can see list of all the sections present in the page.
Markdown inheritly doesn't support table of contents

<ins>Underline</ins>

```mixed
~~This text is struckthrough.~~ This one isn’t.
```

\~~This text is struckthrough.~~ This one isn’t.

Inserting time and date into the template

```js

{{data: DD-MM-YYYY gggg}} // moment-js format

```

```
> [!Quote]+ Quote of the Day  
> <% tp.web.daily_quote() %>
```

> [!Quote]+ Quote of the Day\
> <% tp.web.daily\_quote() %>

## Things

Install a theme called things and should get the following checkbox theming

### Basic

`- [ ] to-do`

- incomplete
- done
- canceled
- forwarded
- scheduling
- todo

### Extras

- question
- important
- star
- quote
- location
- bookmark
- information
- savings
- idea
- pros
- cons
- fire
- key
- win
- up
- down

---
