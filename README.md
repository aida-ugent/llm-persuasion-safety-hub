

## Adding a new resource

To add a new item on the Resources page, edit:

- `src/pages/resources/index.astro`

Find the `resources` array and add a new object.

### Resource template

```ts
{
  title: "",
  year: "",
  authors: [],
  description: "",
  paper: "",
  studyWebsite: null,
  dataset: {
    url: "",
    description: "",
  },
  code: {
    url: "",
    description: "",
  },
}
```

### Field notes

- `title`: full study/resource title.
- `year`: publication year (string, e.g. `"2025"`).
- `authors`: list of author names (displayed in short form as first author surname + `et al.` when multiple).
- `description`: optional text shown under the metadata row (can be empty).
- `paper`: paper URL, or `null` if unavailable.
- `studyWebsite`: project/study website URL, or `null` if unavailable.
- `dataset`: dataset link + short description, or `null` if unavailable.
- `code`: code link + short description, or `null` if unavailable.

### Null vs value

- Use `null` for missing optional links (`paper`, `studyWebsite`, `dataset`, `code`).
- Use an object for `dataset` and `code` when present, including both `url` and `description`.
- `studyWebsite` can be a plain URL string (no description required).
