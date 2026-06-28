Here is a clean **Obsidian Markdown note** for the most useful Emmet shortcuts.

```
# Emmet Cheat Sheet> Press `Tab` after typing an Emmet abbreviation to expand it. Emmet is built into VS Code and many editors. :contentReference[oaicite:0]{index=0}---# 1. Basic Structure## HTML Boilerplate```html!
```

Output:

```
<!DOCTYPE html><html lang="en"><head>    <meta charset="UTF-8">    <meta name="viewport" content="width=device-width, initial-scale=1.0">    <title>Document</title></head><body></body></html>
```

---

# 2. Elements

## Single Element

```
div
```

Output:

```
<div></div>
```

---

# 3. Child Operator (>)

Create nested elements.

```
nav>ul>li
```

Output:

```
<nav>    <ul>        <li></li>    </ul></nav>
```

---

# 4. Sibling Operator (+)

Create elements on the same level.

```
header+main+footer
```

Output:

```
<header></header><main></main><footer></footer>
```

---

# 5. Climb Up (^)

Move one level up.

```
div>p>span^a
```

Output:

```
<div>    <p>        <span></span>    </p>    <a href=""></a></div>
```

---

# 6. Multiplication (*)

Repeat elements.

```
ul>li*5
```

Output:

```
<ul>    <li></li>    <li></li>    <li></li>    <li></li>    <li></li></ul>
```

---

# 7. ID (#)

```
div#container
```

Output:

```
<div id="container"></div>
```

---

# 8. Class (.)

```
div.card
```

Output:

```
<div class="card"></div>
```

Multiple Classes:

```
div.card.shadow.rounded
```

Output:

```
<div class="card shadow rounded"></div>
```

---

# 9. Attributes ([])

```
input[type=text]
```

Output:

```
<input type="text">
```

Multiple Attributes:

```
a[href="#"][target="_blank"]
```

Output:

```
<a href="#" target="_blank"></a>
```

---

# 10. Text Content ({})

```
h1{Welcome}
```

Output:

```
<h1>Welcome</h1>
```

---

# 11. Numbering ($)

```
ul>li.item$*5
```

Output:

```
<ul>    <li class="item1"></li>    <li class="item2"></li>    <li class="item3"></li>    <li class="item4"></li>    <li class="item5"></li></ul>
```

---

# 12. Grouping (())

```
(div>h2+p)+(footer>p)
```

Output:

```
<div>    <h2></h2>    <p></p></div><footer>    <p></p></footer>
```

---

# 13. Common Shortcuts

## Navbar

```
nav>ul>li*5>a
```

---

## Card

```
div.card>img+h3+p+button
```

---

## Table

```
table>tr*3>td*4
```

---

## Form

```
form>input[type=text]+input[type=email]+button
```

---

## Image

```
img
```

Output:

```
<img src="" alt="">
```

---

## Link

```
a
```

Output:

```
<a href=""></a>
```

---

# 14. Lorem Ipsum Generator

10 Words

```
lorem10
```

50 Words

```
lorem50
```

Paragraphs

```
p>lorem30
```

---

# 15. CSS Emmet Shortcuts

## Margin

```
m10
```

Output:

```
margin: 10px;
```

## Padding

```
p20
```

Output:

```
padding: 20px;
```

## Width

```
w100
```

Output:

```
width: 100px;
```

## Height

```
h100
```

Output:

```
height: 100px;
```

## Display Flex

```
df
```

Output:

```
display: flex;
```

## Justify Content Center

```
jcc
```

Output:

```
justify-content: center;
```

## Align Items Center

```
aic
```

Output:

```
align-items: center;
```

## Position Relative

```
pos:r
```

Output:

```
position: relative;
```

## Position Absolute

```
pos:a
```

Output:

```
position: absolute;
```

---

# 16. Most Used Real-World Combinations

## Flex Center Container

```
div.container
```

```
dfaicjcch100vh
```

---

## Product Card

```
div.card>img+h2+p+button{Buy Now}
```

---

## Navigation Menu

```
nav>ul>li*5>a{Menu $}
```

---

## Hero Section

```
section.hero>h1+p+button
```

---

# Must Memorize

```
>+^*#.[]{}$()!
```

These 11 symbols are responsible for about 90% of daily Emmet usage.

```
If you're learning MERN and frontend development, mastering just the "Must Memorize" section will already make you significantly faster in VS Code.::contentReference[oaicite:2]{index=2}
```