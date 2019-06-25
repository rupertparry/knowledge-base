# Lit-HTML

Lit-Element & Lit-HTML are my new go-to ways to build websites. Why? They’re small (<2KB), they are really simple and straightforward to use, and they just boil down to regular old web components. Really, apart from LitHTML which does some clever updating, it’s just syntactic sugar on top of a Custom Element declaration.

[This example](https://www.evernote.com/l/AYjC62NBIIFKoaRyRnA0XI58q4HoA77qPDA) shows a lit-element vs. a vanilla web-components implementation of the same custom element.

## Here are some resources:

- https://lit-element.polymer-project.org/guide/styles

## Useful Snippets

### Firing a custom event

```js
class MyElement extends LitElement {
  render() {
    return html`<div>Hello World</div>`;
  }
  firstUpdated(changedProperties) {
    let event = new CustomEvent('my-event', {
      detail: {
        message: 'Something important happened'
      }
    });
    this.dispatchEvent(event);
  }
}
```

You can then listen to this event using the `@` attribute:

```js
function myListener() { /* ... */ }
html`<my-element @my-event=${myListener}></my-element>`;
```
