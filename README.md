# Picostyle

> Most lightweight CSS in JS library ever.

[![438B gzip][gzip-badge]][bundlesize]

[gzip-badge]: https://img.shields.io/badge/gzip-438%20B-brightgreen.svg
[bundlesize]: https://github.com/siddharthkp/bundlesize

<div align="center">
  <a href="https://github.com/morishitter/picostyle">
    <img width="360px" src="http://morishitter.github.io/picostyle.svg">
  </a>
</div>
<br>

Picostyle is a 0.4 KB CSS in JS library for [Picodom](https://github.com/picodom/picodom).

## Features

- **🚀 Most lightweight CSS in JS library ever**: Only 0.4 KB (gzipped)
- **⚡️ Extreme high performance**: Optimized by Virtual CSS inspired by [Styletron](https://ryantsao.com/blog/virtual-css-with-styletron)
- **💅 Styled components**: Returns styled components like [styled-components](https://www.styled-components.com/) that everyone loves :)
- **❤️ For Picodom**: [Picodom](https://github.com/picodom/picodom) is just 1 KB Virtual DOM builder and patch algorithm

## Installation

```
$ npm install picostyle
```

## How to use

Picostyle works well with Media Queries (`@media`), Pseudo-element and Pseudo-classes (`:hover`).

```js
const Text = ps("h1")({
  fontSize: 64,
  cursor: "pointer",
  color: "#fff",
  padding: "0.4em",
  transition: "all .2s ease-in-out",
  ":hover": {
    transform: "scale(1.3)",
  },
  "@media (max-width: 450px)": {
    fontSize: 32,
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

Perfect example with Picodom and webpack is [here](https://github.com/morishitter/picostyle/tree/master/example).
