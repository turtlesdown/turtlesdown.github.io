---
title: "Placeholder: a field guide to formatting"
date: 2026-11-02
description: Every element a post can use, so you can see how each one is styled.
---

This post exists to show the typography. Body text is set in Newsreader at a
comfortable reading size, with [links underlined in green](/about/), *italics*,
**bold**, and `inline code`.

## Headings look like this

A second-level heading opens a section. Use them sparingly; most posts need
two or three.

### Third-level headings

These are for the rare post that needs a second tier.

## Lists

- Unordered lists use a plain marker.
- Items sit close together.
- Keep them short.

1. Ordered lists are for real sequences.
2. Such as steps you'd follow in order.

## Quotations

> A block quotation is set in italics with a green rule on the left. Use it
> for someone else's words, not for emphasis.

## Code

```go
// Stack returns the turtles beneath t, nearest first.
func Stack(t *Turtle) []*Turtle {
	var below []*Turtle
	for t.Below != nil {
		t = t.Below
		below = append(below, t)
	}
	return below
}
```

```sh
hugo new content posts/my-next-post.md
hugo server --buildDrafts
```

## Tables

| Layer          | Stands on      | Changes   |
| -------------- | -------------- | --------- |
| Application    | Platform       | Weekly    |
| Platform       | Cloud provider | Quarterly |
| Cloud provider | Turtles        | Rarely    |

---

A horizontal rule marks a change of subject or a closing note.
