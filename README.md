<h1 align="center">
    Progressive
</h1>

<p align="center">
     <i>A customizeable, text-based progress bar generator & library for Arturo</i> 
     <br><br>
     <img src="https://img.shields.io/github/license/arturo-lang/grafito?style=for-the-badge">
    <img src="https://img.shields.io/badge/language-Arturo-orange.svg?style=for-the-badge">
</p>


<p align="center"><img width="90%" align="center" src="https://raw.githubusercontent.com/drkameleon/progressive.art/master/progressive.gif"/></p>

--- 
 
<!--ts-->

* [What does this package do?](#what-does-this-package-do)
* [How do I use it?](#how-do-i-use-it)
   - [With iterators](#with-iterators)
   - [Custom progress bars](#custom-progress-bar)
* [Option Reference](#option-reference)
   - [Styles](#styles)
   - [Common options](#common-options)
   - [More customization](#more-customization)
* [License](#license)   

<!--te-->
 
---

### What does this package do?

This package introduces ultra-customizeable terminal-based progress bars for Arturo. Simply put, whether you want to track the progress through an iteration or create a custom progress bar and play with it yourself, it's supported.

### How do I use it?

First `import` it and then... let's decide how you want to use it.

#### With iterators
Do you want to use it along with an existing iterator? That's very easy:

```arturo
import "progressive"!

progressive\loop 1..20 'x [
    processing ~"Current num: |x|"
    pause 200
]
```

> [!IMPORTANT]
> Right now, Progressive supports the following Iterator "overloads":
> - [loop](https://arturo-lang.io/documentation/library/iterators/loop/)
> - [map](https://arturo-lang.io/documentation/library/iterators/map/)
> - [select](https://arturo-lang.io/documentation/library/iterators/select/)
> - [filter](https://arturo-lang.io/documentation/library/iterators/filter/)

> [!TIP]
> By calling the magic function `processing` from inside a progressive iterator, you may pass information which will be displayed above the progress bar (as in: "what is currently being processed?")

#### Custom progress bars

If you want to create a progress bar object and manipulate it yourself, that's possible too:

```arturo
import "progressive"!

i: 0
limit: 20
progress: progressive\new limit!

while [i < 20][
    progress\increase 1
    pause 200
    i: i + 1
]
```

### Option Reference

Progressive comes with *lots* of different options so that you are able to customize your progress bars to your heart's content!

#### Styles

| Option | Description |
|----|----|
| .plain | plain style using only ASCII characters | 
| .fancy | a "fancy" progress bar | 

#### Common options

| Option | Description |
|----|----|
| .simple | make details, above the progress bar, disappear |
| .counter | counter mode (= don't show a progress bar) |
| .static | don't show animated spinner |
| .colorless | don't use colors |
| .ratioless | don't show progress as a ratio |
| .keep | keep progress bar as-is after finishing, without minimizing |
| .hide | hide progress bar completely, after finishing |

#### More customization

| Option | Type | Description | Default |
|----|----|----|----|
| .label | :string | set the main label | `"Progress:"` | 
| .message | :string | set a final message to appear as information | `""` |
| .labelColor | :color | set the main label color | `#white` |
| .detailColor | :color | set the color for the details | `#gray` |
| .onMark | :string | set character for "active" progress bar portions | `"▓"` |
| .onColor | :color | set color for "active" progress bar portions | `#white` |
| .offMark | :string | set character for "inactive" progress bar portions | `"░"` |
| .offColor | :color | set color for "inactive" progress bar portions | `#white` |
| .headMark | :string | character for the "tip" of the progress bar | `""` |
| .barBefore | :string | custom prefix, just before the progress bar | `""` |
| .barAfter | :string | custome suffix, just after the progress bar | `""` |
| .checkMark | :string | success icon | `"✔"` |
| .checkColor | :color | color for the success icon | `#green` |
| .percentColor | :color | color for the percentage | `#green` |
| .animation | :block | characters to use for the spinner | `["┤","┘","┴","└","├","┌","┬","┐"]` |

> [!TIP]
> You may pass any combination of the options above (= that's a lot!) either to an iterator, or when creating a new custom progress bar. 
> So, this:
> ```arturo
> progressive\loop .fancy .label:"Doing sth" ...
> ```
> ...is perfectly valid!

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
