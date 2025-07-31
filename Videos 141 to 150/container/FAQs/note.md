# 🧠 What is `@container` in CSS?

### ➤ Definition:
Absolutely! Let’s dive into the **`@container` query** in **CSS** in a **detailed, clear, and beginner-friendly** way. We'll cover everything step-by-step — from what it is, why it's needed, how it works, its syntax, types, examples, and real use cases.

---

# 🧠 What is `@container` in CSS?

### ➤ Definition:

A **Container Query** (`@container`) is a CSS feature that allows you to apply styles to an element **based on the size of its parent container**, rather than the size of the viewport (which is what traditional media queries do).

---

## 🤔 Why Do We Need Container Queries?

Let’s say you're building **modular components** like:

* Cards
* Widgets
* Sidebars
* Grids

These components might appear in different layouts (sidebars, full page, columns, etc.).

**Problem with media queries**:
They depend on screen width — not on the size of the component's container.

So if your card is in a **narrow container** on a **large screen**, the media query won’t help — the layout won't change even if it **should**.

**Container queries solve this** by checking the **width/height of the container**, not the viewport.

---

## ✅ Key Benefits

| Feature            | Description                                               |
| ------------------ | --------------------------------------------------------- |
| 📦 Component-based | Each component can style itself independently.            |
| 🎯 Precision       | Styles based on actual container size, not entire screen. |
| 🔄 Reusability     | One component can work in many layouts responsively.      |
| ⚙️ Better UX       | Fine-grained control over layout shifts.                  |

---

# 🧩 How Does `@container` Work?

## 🔹 Step 1: Enable Container on a Parent

To use container queries, you must first **declare a container**.

```css
.container {
  container-type: inline-size;
}
```

### Explanation:

| Property         | Meaning                                       |
| ---------------- | --------------------------------------------- |
| `container-type` | Tells browser to track size of this element.  |
| `inline-size`    | React to the **width** of the container.      |
| `size`           | React to both width and height (less common). |

---

## 🔹 Step 2: Use `@container` Query

```css
@container (min-width: 600px) {
  .child {
    font-size: 2rem;
  }
}
```

This means:

> If the nearest container is **at least 600px wide**, apply the styles inside this block.

---

# 🧰 Complete Example

### 🔸 HTML:

```html
<div class="card-container">
  <div class="card">
    <img src="user.jpg" alt="User photo">
    <div class="content">
      <h2>Jane Doe</h2>
      <p>Web Designer</p>
    </div>
  </div>
</div>
```

### 🔸 CSS:

```css
.card-container {
  container-type: inline-size;
  width: 100%;
  max-width: 700px;
  margin: auto;
  border: 2px solid #ccc;
  padding: 16px;
}

.card {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

@container (min-width: 600px) {
  .card {
    flex-direction: row; /* horizontal on large container */
  }
}
```

---

## 🔎 Parts of a Container Query

```css
@container [<name>] (<condition>) {
   /* styles here */
}
```

| Part                | Description                                | Example                                 |
| ------------------- | ------------------------------------------ | --------------------------------------- |
| `@container`        | Starts the query                           | `@container`                            |
| `<name>` (optional) | Named container (advanced)                 | `@container sidebar (min-width: 300px)` |
| `<condition>`       | Size conditions like min-width, max-height | `(min-width: 500px)`                    |
| Block               | Styles to apply                            | `{ ... }`                               |

---

## 💡 You Can Combine Conditions:

```css
@container (min-width: 400px) and (max-width: 800px) {
  .box {
    background-color: lightblue;
  }
}
```

---

## 🏷️ Container Types in Detail

| Property                                | Use case                                    |
| --------------------------------------- | ------------------------------------------- |
| `container-type: inline-size;`          | Most common; responds to **width**          |
| `container-type: block-size;`           | Responds to **height**                      |
| `container-type: size;`                 | Responds to both width & height             |
| `container-name: myContainer;`          | (Optional) name the container for targeting |
| `container: myContainer / inline-size;` | Shorthand: sets both name and type          |

---

# 📦 Example with Named Containers

### HTML:

```html
<div class="sidebar">
  <div class="menu-item">Home</div>
</div>
```

### CSS:

```css
.sidebar {
  container-type: inline-size;
  container-name: sidebar;
}

@container sidebar (max-width: 300px) {
  .menu-item {
    font-size: 0.9rem;
    padding: 4px;
  }
}
```

---

# 🌐 Browser Support

| Browser | Support |
| ------- | ------- |
| Chrome  | ✅ 105+  |
| Edge    | ✅ 105+  |
| Firefox | ✅ 110+  |
| Safari  | ✅ 16+   |
| Opera   | ✅ 91+   |

> ✅ Make sure you're using modern browser versions or test in a compatible environment.

---

# 💬 Use Cases for `@container`

| Component   | Usage                                     |
| ----------- | ----------------------------------------- |
| 🧩 Cards    | Switch layout from vertical to horizontal |
| 📊 Charts   | Change design when placed in sidebars     |
| 📰 Articles | Adjust font size based on space           |
| 📱 Sidebars | Collapse/expand depending on container    |
| 📦 Widgets  | Responsive dashboard components           |

---

# ⚠️ Limitations

* Cannot query the size of elements **not marked as a container**.
* Not yet supported in **some older browsers**.
* You need to set proper **container size** (inline-size) in parent.

---

# ✅ Summary Table

| Concept          | Description                                     |
| ---------------- | ----------------------------------------------- |
| `container-type` | Enables container tracking                      |
| `inline-size`    | Query based on width                            |
| `@container`     | Starts a container query block                  |
| Conditions       | `(min-width: 500px)` etc.                       |
| Optional name    | Add container-name to target specific container |

---

Let me know if you'd like a **live CodePen demo**, or how to integrate this into your **real portfolio or project**.

A **Container Query** (`@container`) is a CSS feature that allows you to apply styles to an element **based on the size of its parent container**, rather than the size of the viewport (which is what traditional media queries do).

---

## 🤔 Why Do We Need Container Queries?

Let’s say you're building **modular components** like:

* Cards
* Widgets
* Sidebars
* Grids

These components might appear in different layouts (sidebars, full page, columns, etc.).

**Problem with media queries**:
They depend on screen width — not on the size of the component's container.

So if your card is in a **narrow container** on a **large screen**, the media query won’t help — the layout won't change even if it **should**.

**Container queries solve this** by checking the **width/height of the container**, not the viewport.

---

## ✅ Key Benefits

| Feature            | Description                                               |
| ------------------ | --------------------------------------------------------- |
| 📦 Component-based | Each component can style itself independently.            |
| 🎯 Precision       | Styles based on actual container size, not entire screen. |
| 🔄 Reusability     | One component can work in many layouts responsively.      |
| ⚙️ Better UX       | Fine-grained control over layout shifts.                  |

---

# 🧩 How Does `@container` Work?

## 🔹 Step 1: Enable Container on a Parent

To use container queries, you must first **declare a container**.

```css
.container {
  container-type: inline-size;
}
```

### Explanation:

| Property         | Meaning                                       |
| ---------------- | --------------------------------------------- |
| `container-type` | Tells browser to track size of this element.  |
| `inline-size`    | React to the **width** of the container.      |
| `size`           | React to both width and height (less common). |

---

## 🔹 Step 2: Use `@container` Query

```css
@container (min-width: 600px) {
  .child {
    font-size: 2rem;
  }
}
```

This means:

> If the nearest container is **at least 600px wide**, apply the styles inside this block.

---

# 🧰 Complete Example

### 🔸 HTML:

```html
<div class="card-container">
  <div class="card">
    <img src="user.jpg" alt="User photo">
    <div class="content">
      <h2>Jane Doe</h2>
      <p>Web Designer</p>
    </div>
  </div>
</div>
```

### 🔸 CSS:

```css
.card-container {
  container-type: inline-size;
  width: 100%;
  max-width: 700px;
  margin: auto;
  border: 2px solid #ccc;
  padding: 16px;
}

.card {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

@container (min-width: 600px) {
  .card {
    flex-direction: row; /* horizontal on large container */
  }
}
```

---

## 🔎 Parts of a Container Query

```css
@container [<name>] (<condition>) {
   /* styles here */
}
```

| Part                | Description                                | Example                                 |
| ------------------- | ------------------------------------------ | --------------------------------------- |
| `@container`        | Starts the query                           | `@container`                            |
| `<name>` (optional) | Named container (advanced)                 | `@container sidebar (min-width: 300px)` |
| `<condition>`       | Size conditions like min-width, max-height | `(min-width: 500px)`                    |
| Block               | Styles to apply                            | `{ ... }`                               |

---

## 💡 You Can Combine Conditions:

```css
@container (min-width: 400px) and (max-width: 800px) {
  .box {
    background-color: lightblue;
  }
}
```

---

## 🏷️ Container Types in Detail

| Property                                | Use case                                    |
| --------------------------------------- | ------------------------------------------- |
| `container-type: inline-size;`          | Most common; responds to **width**          |
| `container-type: block-size;`           | Responds to **height**                      |
| `container-type: size;`                 | Responds to both width & height             |
| `container-name: myContainer;`          | (Optional) name the container for targeting |
| `container: myContainer / inline-size;` | Shorthand: sets both name and type          |

---

# 📦 Example with Named Containers

### HTML:

```html
<div class="sidebar">
  <div class="menu-item">Home</div>
</div>
```

### CSS:

```css
.sidebar {
  container-type: inline-size;
  container-name: sidebar;
}

@container sidebar (max-width: 300px) {
  .menu-item {
    font-size: 0.9rem;
    padding: 4px;
  }
}
```

---

# 🌐 Browser Support

| Browser | Support |
| ------- | ------- |
| Chrome  | ✅ 105+  |
| Edge    | ✅ 105+  |
| Firefox | ✅ 110+  |
| Safari  | ✅ 16+   |
| Opera   | ✅ 91+   |

> ✅ Make sure you're using modern browser versions or test in a compatible environment.

---

# 💬 Use Cases for `@container`

| Component   | Usage                                     |
| ----------- | ----------------------------------------- |
| 🧩 Cards    | Switch layout from vertical to horizontal |
| 📊 Charts   | Change design when placed in sidebars     |
| 📰 Articles | Adjust font size based on space           |
| 📱 Sidebars | Collapse/expand depending on container    |
| 📦 Widgets  | Responsive dashboard components           |

---

# ⚠️ Limitations

* Cannot query the size of elements **not marked as a container**.
* Not yet supported in **some older browsers**.
* You need to set proper **container size** (inline-size) in parent.

---

# ✅ Summary Table

| Concept          | Description                                     |
| ---------------- | ----------------------------------------------- |
| `container-type` | Enables container tracking                      |
| `inline-size`    | Query based on width                            |
| `@container`     | Starts a container query block                  |
| Conditions       | `(min-width: 500px)` etc.                       |
| Optional name    | Add container-name to target specific container |

---

Let me know if you'd like a **live CodePen demo**, or how to integrate this into your **real portfolio or project**.
