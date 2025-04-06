Great question! The `writing-mode` property in CSS allows you to control the flow direction of text. This is especially useful for non-Latin languages like Chinese, Japanese, or Korean, which may be traditionally written vertically.

### 🔍 Difference between `vertical-rl` and `sideways-rl`:

| Property        | Flow Direction                                 | Characters Orientation      |
|-----------------|-------------------------------------------------|-----------------------------|
| `vertical-rl`   | Vertically from **top to bottom**, columns flow from **right to left** | Characters remain upright (natural for vertical languages) |
| `sideways-rl`   | Vertically like `vertical-rl`, but the characters are **rotated** 90° clockwise | Characters are rotated      |

---

### ✅ Example: HTML file using Japanese text

Let's build an example to show both:

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Writing Mode Example</title>
  <style>
    body {
      display: flex;
      gap: 50px;
      padding: 40px;
      font-size: 24px;
      height: 100vh;
    }

    .vertical-rl {
      writing-mode: vertical-rl;
      border: 2px solid #4CAF50;
      padding: 10px;
      height: 300px;
    }

    .sideways-rl {
      writing-mode: sideways-rl;
      border: 2px solid #2196F3;
      padding: 10px;
      height: 300px;
    }
  </style>
</head>
<body>
  <div class="vertical-rl">
    こんにちは。これは縦書き（vertical-rl）です。
  </div>

  <div class="sideways-rl">
    こんにちは。これは回転縦書き（sideways-rl）です。
  </div>
</body>
</html>
```

---

### 💡 What you'll observe:
- In the `.vertical-rl` block, the Japanese characters are displayed **naturally in vertical layout**, top to bottom, and the next line appears to the **left**.
- In the `.sideways-rl` block, the same text is **rotated**; characters are turned sideways, like they're lying down, but still flow top to bottom and right to left.

---

### 🈶 Why does it matter?
- Use `vertical-rl` when you want to preserve the natural reading flow of vertical East Asian scripts.
- Use `sideways-rl` for artistic effects or when dealing with Latin text that should be laid out vertically but with rotated characters.

Would you like me to generate a live preview or screenshot to help you visualize it?