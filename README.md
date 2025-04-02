# Introduction

I'm trying to contribute to Webpack for GSOC, so I'm following along on a talk by [Ronen Amiel](https://www.youtube.com/watch?v=Gc9-7PBqOC8&list=TLPQMjAwMzIwMjVrMcK1VArxJA&index=3)

## Implementation details

- Parse a single file and extract it's dependencies
- Recursively build a dependency graph
- Package everything into a single file

## File Structure

![alt text](image.png)

## Dependencies

### Global Dependencies

- JS beautify - `npm i -g js-beautify`
- highlight - `npm i -g highlight`
