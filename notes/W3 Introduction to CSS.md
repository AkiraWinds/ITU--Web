# Introduction to CSS

CSS instead defines **style** formatting of web pages 

- Design and layout: colors, borders, fonts, backgrounds, positions, etc.

- Variations in display for different devices and screen sizes.

CSS saves a Lot of Work

- CSS can control the layout of multiple web pages all at once.
- One website can support multiple styles ( https://www.w3schools.com/css/css_intro.asp)

## CSS rules

A CSS rule groups a set of CSS properties together and applies all properties to the HTML elements matched by the CSS rule.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2016.36.36.png" alt="截屏2024-02-13 16.36.36" style="zoom:50%;" />

```css
<div style="border: 1px solid black; font-size: 18px;">
	Some text 
</div>
```

- The CSS **selector** determines what HTML elements to target with the CSS rule.
- The CSS **properties** specifies what to style of the targeted HTML elements.

## CSS selectors

A common scenario in web development <u>where multiple elements on a web page require the same styling attributes</u>. CSS addresses this problem by allowing developers to <u>define a set of styles that can be applied to multiple HTML elements</u>, thus avoiding repetition. CSS achieves this through <u>selectors</u> that can target multiple elements at once. 

CSS selectors are used to **"find" (or select) the HTML elements** you want to style.

### 5 categories:

1. **Simple selectors**: (select elements based on name, id, class) 
2. **Combinator selectors**: (select elements based on a specific relationship between them) 
3. **Pseudo-class selectors**: (select elements based on a certain state) 
4. **Pseudo-elements selectors**: (select and style a part of an element)
5. **Attribute selectors**: (select elements based on an attribute or attribute value

#### 1. Sample selectors

Every HTML element can have **"id" and "class"** attributes.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2016.49.56.png" alt="截屏2024-02-13 16.49.56" style="zoom:50%;" />

#### Relationship and Key Difference between _id_ and _class_

- **Purpose:** The `id` attribute is meant for identifying a single unique element, whereas the `class` attribute is designed for defining common styles across multiple elements.
- **Specificity:** An `id` selector has a higher specificity than a class selector in CSS, making it a stronger hook for styling in cases of conflict.
- **Multiplicity:** An element can have only one `id` value but can have multiple `class` values, allowing it to inherit styles from multiple class definitions.

#### 2. CSS combinators selectors

explains the relationship between the selectors.

A CSS selector can <u>contain more than one simple selector.</u>

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2017.08.22.png" alt="截屏2024-02-13 17.08.22" style="zoom:50%;" />

#### 邻接兄弟选择器（`+`）的作用

`+`选择器在CSS中是用来选择一个元素的直接邻接兄弟，这个兄弟元素必须跟它在同一层级（也就是说它们共享同一个父元素）。`+`选择器常用于设计中需要对元素的位置敏感的样式调整，例如，当一个元素直接跟在另一个特定元素后时，你可能想为它应用特殊的样式。

#### 3. CSS Pseudo-classes selectors

Pseudo class designates **a special state** of an element. 

- when a user mouses is over an element 
- visited and unvisited links 
- when an element gets focus

**syntax**:

<img src="/Users/akira/Library/Application Support/typora-user-images/截屏2024-02-13 17.20.11.png" alt="截屏2024-02-13 17.20.11" style="zoom:40%;" /><img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2017.56.55.png" alt="截屏2024-02-13 17.56.55" style="zoom:50%;" />

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2017.20.46.png" alt="截屏2024-02-13 17.20.46" style="zoom:50%;" />

#### 4. CSS Pseudo-elements selectors

used to style **specified parts** of an element.

- Style the first letter, or line, of an element 
- Insert content before, or after, the content of an element

**syntax**:<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2017.59.25.png" alt="截屏2024-02-13 17.59.25" style="zoom:50%;" />

Example: <img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2018.00.12.png" alt="截屏2024-02-13 18.00.12" style="zoom:50%;" />



<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2018.01.19.png" alt="截屏2024-02-13 18.01.19" style="zoom:50%;" />

#### 5. CSS attribute selectors

Used to style HTML elements that **have specific attributes or attribute values**

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2018.26.44.png" alt="截屏2024-02-13 18.26.44" style="zoom:50%;" />

## How To Add CSS in HTML document

### 3 ways:

- inline CSS
- internal CSS
- external CSS

### 1. Inline CSS

Use the ***style attribute*** to apply a unique style for a single element. The style attribute <u>can contain any CSS property</u>

Example:

```css
<h1 style="color:blue;text-align:center;">This is a heading</h1> <p style="color:red;">This is a paragraph.</p>
```

### 2. Internal CSS

can be used if <u>one single HTML page has a unique style</u>

inside the **<style> element**, inside the **head section**.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2018.32.24.png" alt="截屏2024-02-13 18.32.24" style="zoom:40%;" />

### 3. External CSS

The style sheet is **defined in a sepaarfte file**.

Each HTML page must include a **reference** to the external style sheet file inside the **<link> element**, inside the **head section**.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-13%2018.35.32.png" alt="截屏2024-02-13 18.35.32" style="zoom:50%;" />

## Resolution of conflicts

Resolved by rules:

- Cascade
- Specificity
- Inheritance

### 1. Cascades 级联 - priority order:

1. Inline style (inside an HTML element)
2. External and internal style sheets(in the head section)
3. Browser default 浏览器默认值

### 2. Specificity 特异性 

Specificity is a measure of **how specific a selector is**. The more specific a selector, the higher its priority in the cascade. Specificity is calculated based on several factors:

1. **IDs (or inline)** - An ID is the most specific reference (aside from inline styles.
2. **Classes, attributes, and pseudo-classes** - These are less specific than IDs but more specific than element and pseudo-element selectors.
3. **Elements and pseudo-elements** - These have the lowest specificity.

If multiple rules could apply to an element, the rule with the most specific selector takes precedence.

### 3. Inheritance 继承性 

Some CSS property values set on parent elements are inherited by their child elements, and some aren't. This depends on the specific properties.

Example:

CSS:

```css
/* 父元素设置的样式 */
body {
    color: green;
}

/* 直接设置在元素上的样式 */
p {
    color: blue;
}
```

HTML:

```html
<body>
    <div>
        <p>这段文本是蓝色的。</p>
        <span>这段文本是绿色的，因为它继承了body的颜色。</span>
    </div>
</body>

```

所以<p>文本是蓝色的（直接设置在CSS文件里）， <span> 文件是绿色的（没有直接设置在<span> 里所以继承父元素<body> 的颜色。

### 4. Multiple style sheets

If some properties have been defined for the same selector (element) in different style sheets, **the value from the last read style sheet** will be used.

## CSS properties

CSS specification divided into modules to manage the complexity

covery:

- Text, fonts, colors and backgrounds
- box model
- layout 
- positioning
- flexbox
- responsive web design

### 1. Text styling

#### a. Set **color** and **background-color** using:

- **Predefined color names**, such as "red".
- **HEX values**, like "#ff0000" which is also red.
- **RGB values**, like "rgb(255, 0, 0)" which is again red.

```css
p {
    color: red; /* text color is red */
    background-color: #ff0000; /* background color is red (same as text) */
}
```

#### b. Text-align

4 types: left aligned, right aligned, centered,  justified(两端对齐)

```css
h1{text-align: center;}
h2{text-align: left;}
```

#### c. Font 

The `font` property is a shorthand for several font-related properties:

- **font-family**类型: Specifies the font type, like "Arial", "serif", "sans-serif", etc.
- **font-size/line-height**字号行高: Specifies the size of the font and the line height.
- **font-style**样式: Specifies the style of the font, such as "normal", "italic", or "oblique".
- **font-variant**大小写: Specifies whether the text is displayed in a small-caps font.
- **font-weight**是否加粗: Specifies the weight (thickness) of the font, such as "normal", "bold", "bolder", etc.

<u>The font-size and font-family values are required!</u>

```css
p.a {font: 20px Arial, sans-serif;}
p.b {font: italic small-caps bold 12/30px Georgia, serif}
```

- `12/30px`：指定字体大小为 12 像素，行高为 30 像素。
- `Georgia, serif`：指定字体系列为 Georgia，如果系统中不存在 Georgia 字体，则回退到 serif 字体族。

### 2. CSS box model

It defines how each HTML element is rendered on the screen. According to the box model, every element is treated as a box with the following properties:

- **Content**: the actual text, image, or other media content inside the element.

- **Padding**填充: This clears an area around the content. The padding is <u>inside the border and is transparent.</u>

- **Border**边框: This surrounds the padding (if any) and content. It can be styled in <u>various widths, colors, and styles.</u>

- **Margin**边距: This clears an area outside the border. The margin is also transparent and is used to create space between elements.

  Height, Width – relates to the content area only!

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-14%2010.25.03.png" alt="截屏2024-02-14 10.25.03" style="zoom:50%;" />

##### Values of height, width, padding, border and margin

The values for the box model properties can be set using various units:

- **auto**: Default. The browser calculates the size <u>automatically.</u>
- **length**: Defines the value in px, cm etc.
- **%**: Defines the size in percentage relative to the containing block.
- **initial**: Sets the default value.
- **inherit**: Inherits the value from its parent element.

Example:

```css
div { 
  height: 200px; 
  width: 50%; 
  margin: 10px; 
}
```

### 3. Layout 

The `display`, `position`, and `float` properties are pivotal for changing the normal flow of document layout. 

- The `display` property: specifies if or how an element is displayed on the page. 

  Values: `none`, `inline`, `block-inline`, `block`

  - `display: none` will **remove** the element completely from the document layout. This means it **won't take up any space as if it doesn't exist.**
  - `display: inline` allows elements to be displayed as inline elements, meaning they **sit on the same line as adjacent content, like words in a sentence.**
  - `display: inline-block` is a mix between block and inline behavior. Elements will be **laid out like inline elements but calculate space as block**.
  - `display: block` makes elements behave like block-level elements, meaning they will **start on a new line and occupy the full width available**.

- Distinction between `display: none` and `visibility: hidden`: 

  `display: none` removes the element from the layout entirely.

  `visibility: hidden` merely makes the element invisible, but it still **occupies space in the layout** as if it were visible.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2016.40.33.png" alt="截屏2024-02-16 16.40.33" style="zoom:50%;" />







### 4. Positioning

Set how an element is **positioned** in a document. 

5 different position values:

1. `Static`: The default value, where elements are positioned according to the **normal flow of the document**.
2. `Relative`: The element is **positioned relative to its normal position**, allowing you to **move it** with offset properties like `top`, `right`, `bottom`, and `left`.
3. `Absolute`: The element is **removed from the normal document flow and positioned relative to its nearest positioned ancestor** (an ancestor with a position other than `static`).
4. `Fixed`: The element is **removed** from the normal document flow and positioned **relative to the viewport**, which means it stays in the same place even if the page is scrolled.
5. `Sticky`: **A hybrid of relative and fixed positioning**. The element is treated as `relative` until it crosses a specified threshold within the viewport, at which point it becomes `fixed`.

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2016.46.13.png" alt="截屏2024-02-16 16.46.13" style="zoom:50%;" />



### 5. Flexbox

Based on **flex container (parent)** and **flex items (parent's direct children)**

To use Flexbox, set `display: flex` on the container element.

The flex layout is based on “flex-flow directions”

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2018.07.30.png" alt="截屏2024-02-16 18.07.30" style="zoom:50%;" />

Source: https://css-tricks.com/snippets/css/a-guide-to-flexbox/

#### Flex container properties

##### 1. Flex-direction

```css
.container{
  flex-direction: row | row-reverse | column | column-reverse;
}
```

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2018.11.21.png" alt="截屏2024-02-16 18.11.21" style="zoom:50%;" />

##### 2. Flex-wrap

```css
.container{
  flex-direction: row | row-reverse | column | column-reverse;
}
```

##### 1+2: these two can be shortened as flex-flow

```css
.container{flex-flow: column weap;}
```

Source: https://css-tricks.com/snippets/css/a-guide-to-flexbox/

##### 3. Justify-content

```css
.container {  
  justify-content:   flex-start | flex-end | center | space-between | space-around | space-evenly ...
}
```

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2018.14.56.png" alt="截屏2024-02-16 18.14.56" style="zoom:50%;" />

##### 4. Align-items

```css
.container{
  align-items: stretch | flex-start | flex-end | center | baseline
}
```

<img src="/Users/akira/Desktop/ITU--Web/notes_image/%E6%88%AA%E5%B1%8F2024-02-16%2020.31.54.png" alt="截屏2024-02-16 20.31.54" style="zoom:50%;" />













### 6. Responsive web design

