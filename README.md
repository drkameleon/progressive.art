<h1 align="center">
    Progressive
</h1>

<p align="center">
     <i>A customizeable, text-based progress bar generator & library for Arturo</i> 
     <br><br>
     <img src="https://img.shields.io/github/license/arturo-lang/grafito?style=for-the-badge">
    <img src="https://img.shields.io/badge/language-Arturo-orange.svg?style=for-the-badge">
</p>


<p align="center"><img width="90%" align="center" src="https://raw.githubusercontent.com/drkameleon/master/demo.gif"/></p>

--- 
 
<!--ts-->

* [What does this package do?](#what-does-this-package-do)
* [How do I use it?](#how-do-i-use-it)
* [Function Reference](#function-reference)
* [License](#license)   

<!--te-->
 
---

### What does this package do?

This package introduces ultra-customizeable terminal-based progress bars for Arturo. Simply put, whether you want to track the progress through an iteration or create a custom progress bar and play with it yourself, it's supported.

### How do I use it?

Simply `import` it and use the included `recase` function:

```arturo
import "recase"!

recase.snake "This is an example"
; => "this_is_an_example"

recase.camel "Print SQL"
; => "printSQL"
```

### Function reference

#### `recase`

##### Description

convert case of given string

##### Usage

<pre>
<b>recase</b> <ins>str</ins> <i>:string</i>
</pre>

##### Attributes

| Option | Type(s) | Description |
|----|----|----|
| title |  | convert to TitleCase | 
| camel |  | convert to camelCase | 
| snake |  | convert to snake_case | 
| kebab |  | convert to kebab-case | 

##### Returns

- *:string*

<hr/>

### License

MIT License

Copyright (c) 2024 Yanis Zafirópulos

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
