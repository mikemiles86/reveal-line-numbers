# Reveal.js Code block Line Numbers

## Overview

A 'library' for adding line numbers to code stylized using [highlight.js](http://softwaremaniacs.org/soft/highlight/en/) in a [Reveal.js](https://github.com/hakimel/reveal.js) presentation.

See a [live example](https://mikemiles86.github.io/reveal-line-numbers/#/)

To learn more about this library, [read my blog post](http://www.mike-miles.com/blog/displaying-line-numbers-code-examples-revealjs-presentations) about writing it.

## Dependencies

This library depends on using Highlight.js in your Reveal.js presentation.

## File placement

Place these files into 'plugin/line-numbers/';

### Adding library to presentation
To use this library in a Reveal.js presentation, you need to add the 'line-numbers.js' to the list of dependencies in 'Reveal.initialize'.

```javascript
Reveal.initialize({
  dependencies: [
   // ...
    {src: 'plugin/line-numbers/line-numbers.js'}
    // ...
  ]
})
```

## Usage

### Adding line numbers to code blocks
To add line numbers to a code block, just add the class 'line-numbers' to the &lt;code> element

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

### Highlighting line numbers.

To highlight particular line numbers in a code block, add the attribute 'data-highlight-lines' to the &lt;code> element.
* Seperate the lines you would like to highlight with a comma(,).
* Specifcy a group of lines to highlight by seperating the start line and end line with a dash(-).

_Example: to highlight the lines 1,2,3:_
```html
<pre><code class="line-numbers" data-highlight-lines="1,2,3">
/**
 * Example Code.
 */
function my_example_code($line_numbers = TRUE) {
  $message = 'This example code does';
  $message .= 'Will have line numbers';
  $message .= 'and will have highlighed line numbers.';

  return $message;
}

print my_example_code(TRUE);
</code></pre>
```

_Example: To highlight the lines 4 to 10:_
```html
<pre><code class="line-numbers" data-highlight-lines="4-10">
/**
 * Example Code.
 */
function my_example_code($line_numbers = TRUE) {
  $message = 'This example code does';
  $message .= 'Will have line numbers';
  $message .= 'and will have highlighed line numbers.';

  return $message;
}

print my_example_code(TRUE);
</code></pre>
```

_Example: highlighting lines 1 to 3 and 5,7,9:_

```html
<pre><code class="line-numbers" data-highlight-lines="1-3,5,7,9">
/**
 * Example Code.
 */
function my_example_code($line_numbers = TRUE) {
  $message = 'This example code does';
  $message .= 'Will have line numbers';
  $message .= 'and will have highlighed line numbers.';

  return $message;
}

print my_example_code(TRUE);
</code></pre>
```
