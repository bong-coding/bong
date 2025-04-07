---
title: Mini Compiler
date: 2025-03-29
---

### 🔗 https://github.com/bong-coding/Compiler

# ⚙️ Lex-Based Mini C Compiler

This project implements a mini C compiler using **Lex**, focusing on **tokenizing basic data types, operators**, and **complex constructs like nested comments and range operators** (`..`).

---

## 🔍 Key Features

### 🧩 Nested Comment Support

Supports **nested multi-line comments** using Lex's `start conditions`.

| Pattern | Action |
|---------|--------|
| `/*`    | Enter `Comment` mode and increase `depth` counter |
| `*/`    | Decrease `depth`; exit `Comment` mode if `depth == 0` |
| Other   | Ignored in `Comment` mode |

- Compiler starts in `Normal` mode: `BEGIN Normal;`
- Nested comments are tracked accurately using a `depth` counter
- Only `/*` and `*/` are meaningful inside `Comment` mode

---

### 🔁 Range Operator (`..`)

Handles `..` as a **range operator**, distinguishing it from floating-point literals.

- Example: `1..5` is tokenized as `INT`, `RANGE_OP`, `INT`
- Utilizes Lex **lookahead** (`/` operator) to differentiate from cases like `1.5`

---

## 📥 Example Input

```c
/************************
/* nested comments */
************************/
struct _point {
  float x, y, z;
  int color;
} point[20];

struct _line {
  struct _point *p[2];
  int color;
  float meter = 0.5;
} line[20];
1..50

```
## 📤 Output

For each token, the compiler outputs:

- **Token Type** (e.g., KEY, ID, OP, INT, FLOAT)
- **Lexeme** (the actual text of the token)

---

## Run

**Execution**
   ```bash
   ./subc.l test.c
```

