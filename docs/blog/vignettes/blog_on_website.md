# Writing a Blog Post for the SAE4Health Website

This vignette provides guidance for writing a blog post for the SAE4Health website. The general Markdown or R Markdown syntax applies. 

---

## Front Matter (Header)

Each post should begin with a YAML header that specifies metadata for the post. You can customize the `categories` field or choose from existing ones such as `"Software Updates"` or `"Resources"`.

```yaml
---
date:
  created: 2025-03-15
authors: [yunhanwu]
readtime: 1
categories:
  - Software Updates
---
```

---

## Headers

Use `##` for section headings and `###` for subheadings. Avoid using `#` for the title; it's handled by the page layout automatically.

---

## Formulas

Use standard LaTeX syntax for equations and **Avoid** custom math shortcuts or macros.

---

## Figures

Figures can be inserted using standard Markdown syntax:

```markdown
![Participants of the SAE4Health Workshop in Kigali, Rwanda](../figs/Rwanda_workshop.jpg)
*Participants of the regional SAE4Health workshop in Kigali, Rwanda, June 2024. Source: [@WHORwanda](https://x.com/WHORwanda/status/1803155257301561593)*
```

Don't worry about the file paths. Just send me the image files, and I will place them in the correct folder.

---

## Citations

This is slightly different from Latex. Use citation keys with square brackets and an `@` symbol, like so:

```markdown
..., as described in Rao and Molina (2015) [@rao:molina:15].
```

Please also include the BibTeX entry for any references at the end of your post (you do not need to create a separate `.bib` file). For example:

```bibtex
@book{rao:molina:15,
  Address = {New York},
  Author = {J.N.K. Rao and I. Molina},
  Publisher = {John Wiley},
  Title = {Small Area Estimation, Second Edition},
  Year = {2015}
}
```

---