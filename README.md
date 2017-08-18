# Picostyle

> Most lightweight CSS in JS library ever.

[![323 gzip][gzip-badge]][bundlesize]

[gzip-badge]: https://img.shields.io/badge/minified%20&%20gzipped-323%20B-brightgreen.svg
[bundlesize]: https://github.com/siddharthkp/bundlesize

<div align="center">
  <a href="https://github.com/morishitter/picostyle">
    <img width="360px" src="http://morishitter.github.io/picostyle.svg">
  </a>
</div>
<br>

[Try it Online](https://codepen.io/morishitter/pen/qXaPYQ?editors=0010)

## Features

- **🚀 Most lightweight CSS in JS library ever**: Only 0.3 KB (minified & gzipped)
- **👏 Zero dependency**: Picostyle has no dependencies
- **💅 Styled components**: Returns styled components like [styled-components](https://www.styled-components.com/) that everyone loves :)
- **❤️ For HyperApp**: [HyperApp](https://github.com/hyperapp/hyperapp) is a JavaScript library for building frontend applications
- **❤️ For Picodom**: [Picodom](https://github.com/picodom/picodom) is just 1 KB Virtual DOM builder and patch algorithm

## Installation

```
$ npm install picostyle
```

## How to use

Picostyle works well with Media Queries (`@media`), Pseudo-element and Pseudo-classes (`:hover`).

### Use with HyperApp

```js
import { h, app } from "hyperapp"
import picostyle from "picostyle"

const ps = picostyle(h)

app({
  state: {
    text: "Picostyle"
  },
  view: (state) => {
    const keyColor = "#f07";

    const Text = ps("h1")({
      fontSize: "64px",
      cursor: "pointer",
      color: "#fff",
      padding: "0.4em",
      transition: "all .2s ease-in-out",
      ":hover": {
        transform: "scale(1.3)",
      },
      "@media (max-width: 450px)": {
        fontSize: "32px",
      },
    })

    const Wrapper = ps("div")({
      display: "flex",
      justifyContent: "center",
      alignItems: "center",
      width: "100vw",
      height: "100vh",
      backgroundColor: keyColor,
    })

    return (
      <Wrapper>
        <Text>Hello, {state.text}</Text>
      </Wrapper>
    )
  }
})
```

Perfect example with HyperApp and webpack is [here](https://github.com/morishitter/picostyle/tree/master/examples/hyperapp).

### Use with Picodom

```js
import picodom from "picodom"
import picostyle from "picostyle"

const ps = picostyle(picodom.h)

const Text = ps("h1")({
  fontSize: "64px",
  cursor: "pointer",
  color: "#fff",
  padding: "0.4em",
  transition: "all .2s ease-in-out",
  ":hover": {
    transform: "scale(1.3)",
  },
  "@media (max-width: 450px)": {
    fontSize: "32px",
  },
})

const Wrapper = ps("div")({
  display: "flex",
  justifyContent: "center",
  alignItems: "center",
  width: "100vw",
  height: "100vh",
  backgroundColor: keyColor,
})

return (
  <Wrapper>
    <Text>{state.trim() === "" ? ":)" : state}</Text>
  </Wrapper>
)
```

Perfect example with Picodom and webpack is [here](https://github.com/morishitter/picostyle/tree/master/examples/picodom).
