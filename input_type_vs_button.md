
# HTML Form Buttons: `<input type="submit">` vs `<button type="submit">`

When creating submission buttons in HTML forms, you can use either:
- `<input type="submit">`
- `<button type="submit">`

Understanding the **differences** between these two helps you design better forms and user interfaces.

---

## 1. `<input type="submit">`

- Creates a submit button.
- Uses the **`value`** attribute to set the button's text.
- **Cannot contain HTML elements** such as images or icons—only plain text.

**Example:**

```
<form>
  <input type="submit" value="Send Form" />
</form>
```

**Result:**  
A button displaying the text “Send Form.”

---

## 2. `<button type="submit">`

- Also creates a submit button for a form.
- Content between `<button> ... </button>` can include text, **HTML elements, images, and icons**.
- Offers **greater flexibility for design and styling**.

**Example (with text and image):**

```
<form>
  <button type="submit">
    <img src="send-icon.png" alt="Send" width="16" height="16"> Send Form
  </button>
</form>
```

**Result:**  
A button displaying both the send icon and the “Send Form” text.

---

## Adding HTML Markup Inside `<button>`

The `<button>` tag allows you to **add HTML markup inside the button**, letting you create more visually appealing and flexible buttons.

**Example: Button with formatted text and an icon**

```
<button type="submit">
  <img src="send.png" alt="Send" width="16" height="16">
  <span style="color: blue; font-weight: bold;">Send Message</span>
</button>
```

- The `<img>` tag displays an icon.
- The `<span>` tag styles the button text (blue and bold).

**Example – Button with mixed formatting:**

```
<button type="button">
  <b>Send</b> <i>Now!</i>
</button>
```

- "Send" will appear in bold.
- "Now!" will appear in italics.

**You can include:**  
- Images 
- Different styles using `<b>`, `<i>`, `<u>`, `<span>`, etc.
- Even line breaks and more complex formatting

---

## Summary Table

| Feature                      | `<input type="submit">`           | `<button type="submit">`                            |
|------------------------------|-----------------------------------|-----------------------------------------------------|
| Allows custom text           | Yes (`value` attribute)           | Yes (inner HTML content)                            |
| Allows images/icons          | **No**                            | **Yes**                                             |
| Contains HTML elements       | No                                | Yes                                                 |
| Tag structure                | Self-closing (`<input />`)        | Opening/closing tag (`<button></button>`)           |
| Styling flexibility          | Limited                           | Greater (supports HTML, CSS, classes, icons, etc.)  |

---

## When to Use Each

- Use **`<input type="submit">`** for simple forms or when only plain text is needed on the button.
- Use **`<button type="submit">`** if you want to:
  - Add images or icons
  - Use HTML markup inside the button
  - Apply advanced styling and effects

---

**In summary:**  
- `<input type="submit">` is limited to plain text via the value attribute.
- `<button type="submit">` allows for much richer content and customization, including embedding images and adding any HTML markup.

