# 📚 Zenn Books Directory

The `books/` directory is used to manage **only books that are actively being written or updated**  
and are intended to be published on **Zenn**.

With Zenn’s GitHub integration, **each folder directly under `books/` is automatically recognized as one book**.

> ✅ **Completed or frozen books must be moved to `done-books/`**  
> ❌ Only books located under `books/` are deployed to Zenn

---

## 🚦 Operational Policy (Important)

- `books/`  
  → **Active books** (writing in progress / under revision)
- `done-books/`  
  → **Completed or frozen books**, archived for long-term reference

As a general rule:

> **Keep 0 or 1 book in `books/` at any given time**

This policy helps prevent:
- Accidental deployments
- Exceeding Zenn’s posting limits
- Unintended updates to completed books

---

## 📘 Current Status

At present, there are **no active books** under `books/`.

```text
books/
├ .gitkeep
└ README.md
```

- `.gitkeep` is used to keep the empty directory under Git version control
- A new folder should be added **only when starting a new book**

---

## ✍ Adding a New Book

When starting a new book, create a new folder under `books/` with the following structure:

```text
books/
└ my-new-book/
  ├ config.yaml
  ├ cover.png        # optional
  ├ 01_intro.md
  ├ 02_theory.md
  └ 03_application.md
```

---

## 📌 Zenn Book Structure Rules

### ✔ Place `.md` files directly under the book folder
- Subdirectories (e.g. `chapters/`) are **not allowed**

### ✔ Define chapter order in `config.yaml`
```yaml
chapters:
  - 01_intro
  - 02_theory
  - 03_application
```

### ✔ `cover.png` is optional
- If provided, it will be displayed as the book cover on Zenn

### ✔ GitHub → Zenn integration is repository-based
- Once `zenn-books` is linked to Zenn,  
  all books under `books/` are automatically detected and deployed

---

## 🧊 Completed Books

Once a book is completed, **always move it to `done-books/`** using the following command:

```powershell
git mv books/book-name done-books/
```

This ensures:

- The book is excluded from Zenn deployment
- Accidental rebuilds or edits are avoided
- The content is preserved as a long-term educational archive
