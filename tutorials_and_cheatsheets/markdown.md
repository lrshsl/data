# Markdown Example

### Introduction

This is a basic markdown file using all the important features of markdown with the github syntax. For more information I'd recommend to read the [GitHub Documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).


### Table of Contents

* [Introduction](#introduction)
* [Examples](#examples)
    * [Very, Very Basic Example](#very-very-basic)
    * [README for a Project](#readme-for-a-project)
    * [Notes from a Lecture](#notes-from-a-lecture)
* [Main Sections](#content)
    * [Headers](#headers)
    * [Text Styling](#text-styling)
    * [Listings](#listings)
    * [Tables](#tables)
    * [Links](#links)
    * [Images](#images)
    * [Code](#code)


### Examples

#### Very, Very Basic

```
# Title

## Introduction

- List item 1
- Item 2
    - Sub item 1

It is __important__ that the text is formatted in a way that makes it _easy to read_.

```

#### README for a project

```
# Important project 1

## Introduction
This tool can simply _everything_ that you need.

## Table of Contents

- [Introduction](#introduction)
- [Progress](#progress)
- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Usage](#usage)


## Progress

[X] Basic structure
[ ] Make usable
    [ ] CLI?
[ ] Make it easy
    [ ] Add GUI

## Getting Started

### Prerequisites

Before you begin, make sure you have the following installed on your system:
- [Git](https://git-scm.com/)
    - If you don't, you can get it from [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Python](https://www.python.org/)
- [Numpy](https://numpy.org/) (you can install it with `pip install numpy`)

### Installation

On a Unix Based system:
\`\`\`bash
# Clone the repo
git clone tool_url
cd tool_name
\`\`\`

You can Run it with this command:
\`\`\`bash
python main.py
\`\`\`


```

#### Notes from a Lecture

```
# AI and its future

## Introduction

Important:
- AI
    - .. is everywhere
        - YT-Algorithm
        - Voice-Recognition software
        - ...
    - Can do amazing things
        - Image classification
        - [chatGPT](https://chat.openai.com/)
    - Can be dangerous
        - Case Facebook: Built to stay on site -> Radicalisation (You only see what you want to see)
        - Interesting article: `https://medium.com/swlh/facebook-ai-algorithm-one-of-the-most-destructive-technologies-ever-invented-f44196e25d3f#:~:text=The%20Facebook%20Artificial%20Intelligence%2Dpowered,That%20sounds%20great%2C%20right%3F`

## How does it work?

### In general



### Example Image Recognition

\`\`\`python
import tensorflow as tf
import numpy as np

# Load the data
mnist = tf.keras.datasets.mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()

# Create a model with some layers
model = tf.keras.models.Sequential([
  tf.keras.layers.Flatten(input_shape=(28, 28)),
  tf.keras.layers.Pooling2D(2, 2),
  tf.keras.layers.Dense(64, activation='relu'),
  tf.keras.layers.Dense(128, activation='relu'),
  tf.keras.layers.Dense(10, activation='softmax')
])

[..]
\`\`\`

Explanations for the code:
- Loads images from mnist dataset
- Flattens the image into a 1D array
- Creates a model:
    - Preparation of data
        - Flattening: [28, 28] (2D array) -> [784] (1D array)
        - Pooling
            - Takes 2x2 window
            - Takes the maximum value
            - Produces a new image with reduced size ( --> faster processing)
    - 2 hidden layers
        - One with 64 neurons
        - One with 128 neurons
        - Both use [relu](#relu-vs-sigmoid) activation
    - Another layer with 10 neurons (= Output layer)
- Then the model would be compiled and trained


### Relu vs Sigmoid

> They are __mathematical functions__ that make the output of another function easier to work with.

ReLU stands for _R_ectified _L_inear _U_nit. It sets all negative values to zero, and keeps the positive ones as is.

Sigmoid on the other hand sets all values between -1 and 1.

[..]

```



### Content

#### Headers

```
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
```

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6


#### Text Styling

##### Emphasis

```
This is a paragraph with some *italic*, _more italic_, **bold** and __more bold__ text.
You can also ~~strike a word~~ through using two tilde signs.
```

This is a paragraph with some *italic*, _more italic_, **bold** and __more bold__ text.
You can also ~~strike a word~~ through using two tilde signs.

#### Annotations or Comments

```
> This is a note or comment.
>
> Works for multiline blocks too

> This is separate from the previous paragraph.
```

> This is a note or comment block.
> 
> Works for multiline blocks too

> This is separate from the previous paragraph.


#### Listings

#### Unordered Lists

```
- Item 1
- Item 2
- Item 3
    - Sub Item 1
    - Sub Item 2
```

- Item 1
- Item 2
- Item 3
    - Sub Item 1
    - Sub Item 2

```
* Item 1
* Item 2
* Item 3
    * Sub Item 1
    * Sub Item 2
```

* Item 1
* Item 2
* Item 3
    * Sub Item 1
    * Sub Item 2


#### Ordered Lists

```
1. Item 1
2. Item 2
3. Item 3
    1. Sub Item 1
    2. Sub Item 2
```

1. Item 1
2. Item 2
3. Item 3
    1. Sub Item 1
    2. Sub Item 2


#### Checkboxes

```
[ ] Unchecked Item
[x] Checked Item
[ ] Anothe unchecked Item
    [x] Checked Subitem
```

[ ] Unchecked Item
[x] Checked Item
[ ] Anothe unchecked Item
    [x] Checked Subitem


#### Tables

```
| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Row1 1   | Row1 2   | Row1 3   |
| Row2 1   | Row2 2   | Row2 3   |
```

| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Row1 1   | Row1 2   | Row1 3   |
| Row2 1   | Row2 2   | Row2 3   |


#### Links

```
[GitHub](https://github.com)
```

[GitHub](https://github.com)

There's a shorthand if the text to be displayed is the link itself.
In this case, you can use backticks like \`https://github.com/\` and it will be rendered like that: `https://github.com/`


##### Relative Links

```
Link to [another file](examplefile.md) in the same repo
Link to [another section](#code) in the same file*
```

Link to [another file](examplefile.md) in the same repo
Link to [another section](#code) in the same file*


> Important: If you link to a section in the same file, you need to use lowercase and replace all spaces with dashes (`-`).
> For instance, If you need to link to section 'Complicated Section', use `[Complicated Section](#complicated-section)` for the link.



#### Images

```
![alt text](image.gif)
```

![alt text](image.gif)

> Note: You can also use a url in the parenthesis () to reference an image from the web.


#### Code

##### Inline
```
You can use single backticks to render single `words` as `code` in a paragraph.
```

You can use single backticks to render single `words` as `code` in a paragraph.

> Note: You can use the same technique to render color codes
> \`#44ff22\`: `#44ff22`
> \`rgb(0, 255, 34)\`: `rgb(0, 255, 34)`
> \`rgba(0, 255, 34, 0.5)\`: `rgba(0, 255, 34, 0.5)`


##### Code blocks

For Code Blocks, use three backticks:
\`\`\`
Code in a code block
\`\`\`

```
Code in a code block
```

You can also specify the syntax:
\`\`\`python
# This is python code with python syntax highlighting
print("Hello World")
\`\`\`

```python
# This is python code with python syntax highlighting
print("Hello World")
```









