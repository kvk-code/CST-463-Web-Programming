# Inline vs Block-level Elements in HTML

Understanding HTML structure starts with recognizing the difference between **block-level** and **inline** elements. This distinction is fundamental to designing and styling web pages.

---

## Block-level Elements

- **Always start on a new line**—browser inserts a line break before and after.
- **Expand to fill the available width** of their parent container by default.
- **Can contain**:  
  - Other block-level elements  
  - Inline elements
- **Purpose**: Structure and group large sections of content.
- **Examples**: `<div>`, `<p>`, `<h1>`, `<ul>`, `<li>`, `<form>`, `<table>`

**Example:**
```
<div>
  <p>This is a paragraph inside a div.</p>
  <span>And here is a span inside the div.</span>
</div>
```

---

## Inline Elements

- **Do NOT start on a new line**—they sit within the flow of the current line or paragraph.
- Take up **only the width needed** for their content.
- **Can contain**:  
  - Other inline elements (typically not block-level elements)
- **Purpose**: Mark or style small parts of content without changing overall structure.
- **Examples**: `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<input>`

**Example:**
```
<p>This is <span style="color: red;">red text</span> in a sentence.</p>
```

---

## Summary Table: Block-level vs Inline Elements

| Property                   | Block-level Elements             | Inline Elements                   |
|----------------------------|----------------------------------|-----------------------------------|
| Starts on new line         | Yes                              | No                                |
| Uses full container width  | Yes (by default)                 | No (just content width)           |
| Contains                   | Block + Inline elements          | Inline elements                   |
| Used for                   | Structure, layout, grouping      | Styling or marking small sections |

---

# Difference Between `<div>` and `<span>` Tags

Once you understand inline vs block-level, it’s easy to see the difference between the commonly used `<div>` and `<span>` tags:

---

## `<div>` Tag

- **Type:** Block-level element
- **Behavior:** 
  - Starts on a new line
  - Fills full parent width
- **Use Case:** 
  - Grouping larger sections (paragraphs, images, forms, navigation, etc.)
- **Ideal For:** 
  - Webpage layout and structural organization

**Example:**
```
<div>
  <p>This is inside a div.</p>
  <img src="photo.jpg" alt="Sample Image">
</div>
```

---

## `<span>` Tag

- **Type:** Inline element
- **Behavior:** 
  - Does not start on a new line
  - Only as wide as its content
  - Stays within the flow of the text
- **Use Case:** 
  - Styling or highlighting small portions of text
- **Ideal For:** 
  - Emphasizing or applying styles inline

**Example:**
```
<p>This is a <span style="color: red;">red word</span> in a sentence.</p>
```
Only "red word" is colored; rest of the text flows naturally.

---

## Summary Table: `<div>` vs `<span>`

| Feature               | `<div>` (Block-level)               | `<span>` (Inline)                      |
|-----------------------|-------------------------------------|-----------------------------------------|
| Starts on new line    | **Yes**                             | **No**                                  |
| Takes full width      | **Yes**                             | **No** (only as wide as content)        |
| Used for              | Grouping large sections/containers  | Styling small, inline content           |
| Typical content       | Paragraphs, images, lists, forms    | Words, phrases, parts of sentences      |
| Affects layout/flow   | Creates new blocks in the document  | Does not break or disrupt text flow     |

---

## Key Points

- **Block-level elements:** Start on a new line, take full width, and can contain both block and inline elements—used for structuring pages.
- **Inline elements:** Stay within a line, only as wide as their content, and can contain other inline elements—used for fine-grained styling.
- `<div>` = block-level, for structure/layout; `<span>` = inline, for in-line styling/highlighting.

**In summary:**
- Use `<div>` for organizing and grouping large sections or blocks of content.
- Use `<span>` for styling or marking up small parts of content inline—without interrupting text flow.
