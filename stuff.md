I can highlight text, and now copy to the clipboard. However I also need to be able to select text/

### Highlight matching text in JavaScript

#### How does it work?

- There's an $input, and some $text on the page.
- input some text that is within the $text
- the $text element text will be highlighted

pros:
The app works as expected however there are some features that I would add or change,
such as making the regular expression search more strict. If you type in the $string: `web`.
It will match ['Web', 'web', 'websites'] in this example.

cons:

```js
/* * selecting elements in the DOM* /
const $box = document.getElementById("box");
const $search = document.getElementById("search");

$search.addEventListener("input", (event) => {
  const searchText = event.target.value;
  const regex = new RegExp(searchText, "gi");

  let text = $box.innerHTML;
  text = text.replace(/(<mark class="highlight">|<\/mark>)/gim, "");

  const newText = text.replace(regex, '<mark class="highlight">$&</mark>');
  $box.innerHTML = newText;
});
```
