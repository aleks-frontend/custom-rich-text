# custom-rich-text
Function that allows users to use rich text formatting inside spreadsheet inputs.
## Instructions
### HTML implementation
Input needs to be wrapped in a div with a `js-customRichText-src` class.

Once the function is called `js-customRichText-src` div will be hidden and `js-customRichText-target` will be appended dynamically. 
```
{{#spreadsheet.test-spreadsheet}}
<tr>
  <td>
    <div class="js-customRichText-src">{{test-item-1}}</div>
  </td>
  <td>
    <div class="js-customRichText-src">{{test-item-2}}</div>
  </td>
</tr>
{{/spreadsheet.test-spreadsheet}}
```
### Function initialization
Function call (`customRichText(mapObj);`) doesn't need to be in a `setInterval()` or Mutation Observer, since the template is refreshed 
and re-rendered each time a spreadsheet input is updated.

Another important thing is passing the **mapOb** object with all the rules:
```
 const mapObj = {
    '{b': '<strong>',
    'b}': '</strong>',
    '{i': '<i>',
    'i}': '</i>',
    '{h1': '<h1>',
    'h1}': '</h1>',
    '{h2': '<h2>',
    'h2}': '</h2>',
    '{nl}': '<br>'
  };
```
