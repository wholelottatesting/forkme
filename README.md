# forkme

> Batteries-included utilities you'd otherwise rewrite in every project.

**A collection of really useful string, array, map, set, and math utilities — implemented in common languages like Go, Python, and more.**

`forkme` is a multi-language utility library. The same well-tested helpers you reach for every day — chunking an array, deduplicating a slice, merging maps, clamping a number — implemented idiomatically in each language, with a consistent API and behavior across all of them.

It's designed to be **highly forkable**: grab the language and the utilities you need, drop them into your project, and go.

## Why this exists

Every project ends up re-implementing the same small helpers: split a string, group a list, take the intersection of two sets, clamp a value to a range. These are easy to get subtly wrong (off-by-one bounds, empty-collection edge cases, surprising mutation). `forkme` provides a single, well-tested home for them so you don't have to write them again.

## What's inside

Utilities are organized by data type, and each is available in every supported language.

### Strings
- Case conversion: `camelCase`, `snake_case`, `kebab-case`, `Title Case`
- Trimming, padding, and truncation (with ellipsis)
- Splitting, joining, and templating
- Slugify, capitalize, reverse, and word counting

### Arrays / Slices
- `chunk`, `flatten`, `unique`, `groupBy`, `partition`
- `zip`, `unzip`, `range`
- `first`, `last`, `take`, `drop`, `compact` (remove nullish/empty values)
- `intersection`, `difference`, `union`

### Maps / Dictionaries
- `merge` (shallow and deep), `pick`, `omit`, `invert`
- `mapKeys`, `mapValues`, `filterValues`
- `getOrDefault`, `entries`, `fromEntries`

### Sets
- `union`, `intersection`, `difference`, `symmetricDifference`
- `isSubset`, `isSuperset`, `isDisjoint`

### Math
- `clamp`, `lerp`, `round` (to N decimals), `mean`, `median`, `sum`, `product`
- `gcd`, `lcm`, `factorial`
- `randomInt` / `randomFloat` within a range

## Supported languages

| Language | Status   | Location     |
| -------- | -------- | ------------ |
| Go       | Planned  | `go/`        |
| Python   | Planned  | `python/`    |

More languages (TypeScript, Rust, Ruby, …) are welcome — see [Contributing](#contributing).

## Design principles

- **Consistent behavior across languages.** A function with the same name behaves the same way everywhere; differences are limited to what's idiomatic for the language.
- **Pure and predictable.** Utilities don't mutate their inputs and have no hidden side effects, unless explicitly named otherwise.
- **Well-tested.** Every utility ships with unit tests that document its behavior, including the empty and boundary cases.
- **Forkable.** Minimal dependencies. Copy a single file or import the whole package — both work.

## Usage

Each language directory is a self-contained package with its own idiomatic install and import instructions in its local README. In general:

```sh
# Go
go get github.com/wholelottatesting/forkme/go

# Python
pip install forkme
```

## Contributing

Contributions are very welcome — especially new language implementations and additional utilities. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

When adding a utility:

1. Implement it idiomatically for the target language.
2. Keep the name and behavior consistent with the existing implementations in other languages.
3. Add unit tests that cover the empty, single-element, and boundary cases.

## License

Released under the [MIT License](LICENSE).
