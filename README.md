# Overview

A 'library' for adding line numbers to code stylized using Highlight.js in a Reveal.js presentation.

# Dependencies

This library depends on using Highlight.js in your Reveal.js presentation.

# File placement
Relative to the root of your Reveal.js presentation:

* place line-numbers.css into '/lib/css/'
* place line-numbers.js into '/lib/js/'

# Adding library to presentation
To use this library in a Reveal.js presentation, you need to add the 'line-numbers.js' to the list of dependencies in 'Reveal.initialize'.

```javascript
Reveal.initialize({
  dependencies: [
    {src: 'lib/js/line-numbers.js'}
  ]
})
```

# Adding line numbers to code blocks
To add line numbers to a code block, just add the class 'line-numbers' to the <code> element

```html
<pre><code class="line-numbers">
/**
 * Example Code.
 */
function my_example_code($line_numbers = TRUE) {
  $message = 'This example code does';
  $message .= ($line_numbers ? '' : ' not');
  $message .= ' have line numbers.';

  return $message;
}

print my_example_code(TRUE);
</code></pre>
```
