# Worksheet 6
#### SYST10049 Web Development

1. Work through the material in [Exercise Set 6]()
2. Work through Class example 51. Test and document observations for each potential solution.
3. Test, observe, document, try to recreate yourself; dig deeper and research properties and values used...
   * [example06_001.html](example06_001.html) - explore text properties
   * [example06_002.html](example06_002.html) - explore text properties
   * [example06_021.html](example06_021.html) - explore different selectors
   * [example07_001.html](example07_001.html) - explore background properties
   * [example07_002.html](example07_002.html) - explore color values and units
   * [example07_003.html](example07_003.html) - explore color values and units
   * [example07_010.html](example07_010.html) - explore box model
   * [explore_font.html](explore_font.html) - explore font properties
4. Practice!

## Class Example 51
- [example51.html]()

### Description

This example has HEADER with H1 content, followed by four (4) paragraphs of Latin text, and FOOTER content in the body of an HTML5 document.
- [DOM for Example 51](dom_example51.html)

### Process

1. Start with a valid HTML5 code. (Validate your code at validator.w3.org)
2. Plan what you need to style.
3. Choose what properties and values.
4. Choose the element(s) to apply them to.

#### 1. Create and validate HTML5

#### 2. Plan what to style
 
We want to change the text and background colors, and change the padding, of the first paragraph.
 
#### 3. Choose what properties and values
 
* black background color
* yellow foreground (text) color
* 50 pixels padding at the top and bottom
* 20 pixels padding at the right and left

#### 4. Choose element(s)

We want to select the first paragraph.

### Explore potential solutions

Solution A

```css
<p style="color: yellow; 
          background-color: black; 
          padding: 50px 20px;">
...
</p>
```
inline CSS. Avoid using! hard to change (high specificity) and narrow scope (no code re-usability)
inline (specificity 1000) [6.4.3 Calculating a selector's specificity](https://www.w3.org/TR/2011/REC-CSS2-20110607/cascade.html#q6.0)

---

Solution B

```html
<style>
/* CSS rule */
p {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
</style>
</head>
```
convert to internal styles. Problem: this rule will apply to all paragraphs on the page, not just the first one.
how do you find the right (and best) selector? try, research, try different things [https://www.w3schools.com/css/css_selectors.asp](https://www.w3schools.com/css/css_selectors.asp)
specificity [https://www.w3.org/TR/selectors-3/#specificity](https://www.w3.org/TR/selectors-3/#specificity)

---

Solution C

```css
/* wrong target; first child of body is HEADER */
p:first-child {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution D

```css
/* wrong target; first child of paragraph is STRONG */
p :first-child {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution E

```css
/* add an id; not very good; high specificity 100 ; larger DOM */
#one {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution F

```css
/* over-qualified; there can be only one id="one", increases specificity 101  */
p#one {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution G

```css
/* better using classes;  specificity 010; larger DOM */
.one {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution H

```css
/* after adding div parent to paragraphs ; specificity 011 */
p:first-child {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution I

```css
/* good choice; no additional elements required; low specificity 011 */
p:nth-child(2) {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution J

```css
/* best choice; the most descriptive; low specificity 011 */
p:first-of-type {
 background-color: black;
 color: yellow; 
 padding: 50px 20px;
}
```
---

Solution ?

 any other or better choices? 


---

> Web Development @ Sheridan College

