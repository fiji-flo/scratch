# Some nice things for Markdown in Yari

## Smart Ref Links

We can use reference style links in markdown to replace the `jsxref` ... marcos.
There a several ways depending on how flexible we want to be.

### Option A

The straight forward solution would be having a reference like this:

```md
[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/ Global_Objects/Array (Array)
[Map]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map (Map)
...
[import]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import (import)
```

which can be used like:

```md
This points to [Array] and we can rename it, too. This [Brray][Array] also points to [Array]
```

> This points to [Array] and we can rename it, too. This [Brray][Array] also points to [Array]

The downside is that we might have collision within the reference names.

### Option B

An possible solution would be:

```md
[JS/Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array (Array)
```

And we use it the same way.

```md
This points to [JS/Array] and we can rename it, too. This [Brray][JS/Array] also points to [JS/Array]
```

> This points to [JS/Array] and we can rename it, too. This [Brray][JS/Array] also points to [JS/Array]

The downside here is that natively this renders the `JS/` prefix but we also have the `title` set to `Array` which we could use to render this in custom way for Yari.

[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array (Array)
[Map]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map (Map)
[import]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import (import)
[JS/Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array (Array)

## Notes/Warnings and the likes

One way to do notes would be to use *blockquotes* combined with an *h6*:

```md
> ###### Note
> This could be a note
```

looks like this:

> ###### Note
> This could be a note

And it can even be nested


```md
> ###### Warning
> Some important warning
>> ###### Note
>> With a nested note
```

looks like:

> ###### Warning
> Some important warning
>> ###### Note
>> With a nested note

And we can customize the look and strip the *h6* in Yari.

## Live Samples

Instead of relying on DOM hierarchy and ids we can annotate all code blocks.

````md
```css exmaple-1
.foo {
  color: red;
}
```

```html
<div class="foo">bar</div>
```
````
still renders fine:

```css exmaple-1
.foo {
  color: red;
}
```
```html
<div class="foo">bar</div>
```

But we can generate a refer to this sample via `example-1`.
