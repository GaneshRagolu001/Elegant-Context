Here’s a **professional GitHub README.md** for your project — clear, well-structured, and beginner-friendly. It highlights your goal of learning **React Context and useReducer**, explains the structure, and adds setup instructions.

---

```markdown
# 🛒 React Shopping Cart — useReducer & Context API Practice

This project is a **React-based Shopping Cart** application built to practice **state management** using the **Context API** and **useReducer()** hook. It demonstrates how to share state efficiently across multiple components without prop drilling.

---

## 🚀 Features

- 🧠 **Global State Management** using `React Context` and `useReducer`
- 🛍️ Add items to the shopping cart
- 🔁 Update item quantities (increment/decrement)
- 🧹 Remove items when quantity reaches zero
- 🧩 Modular component structure (`Header`, `Shop`, `Cart`)
- 💡 Demonstrates real-world use of `useReducer()` for handling complex state logic

---

## 🧱 Tech Stack

- **React 18+**
- **JavaScript (ES6+)**
- **Context API**
- **useReducer Hook**
- **React Portals**

---

## 📂 Project Structure
```

src/
│
├── components/
│ ├── Header.jsx # Displays app title and cart button
│ ├── Shop.jsx # Displays available products
│ ├── Cart.jsx # Shows items added to cart
│ ├── CartModal.jsx # Modal using React Portal for cart UI
│
├── store/
│ └── CartContextStore.jsx # Context + Reducer logic for global cart state
│
├── dummy-products.js # Sample product data
│
└── App.jsx # Root component that wraps everything with CartContextProvider

````

---

## ⚙️ How It Works

1. `CartContextStore.jsx` creates a context that stores all cart data.
2. The reducer function handles two actions:
   - `ADD_ITEMS`: Adds a new product or increases quantity if it exists.
   - `UPDATE_ITEMS`: Updates quantity or removes product if quantity ≤ 0.
3. `CartContextProvider` provides these functions and the current cart state to the entire app.
4. Components like `Shop` and `Cart` use this context to add or update items dynamically.

---

## 🧰 Installation & Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
````

2. Install dependencies:

   ```bash
   npm install
   ```

3. Run the development server:

   ```bash
   npm run dev
   ```

4. Open in browser:

   ```
   http://localhost:5173/
   ```

---

## 🧩 Example Reducer Logic

```js
if (action.type === "ADD_ITEMS") {
  const updatedItems = [...state.items];
  const existingIndex = updatedItems.findIndex(
    (item) => item.id === action.payload
  );

  if (existingIndex !== -1) {
    updatedItems[existingIndex].quantity += 1;
  } else {
    const product = DUMMY_PRODUCTS.find((p) => p.id === action.payload);
    updatedItems.push({
      id: product.id,
      name: product.title,
      price: product.price,
      quantity: 1,
    });
  }

  return { items: updatedItems };
}
```

---

## 🧠 What I Learned

- How to use **Context API** for global state sharing
- How `useReducer()` can simplify state updates for complex objects
- How to use **React Portals** to render modals outside the root hierarchy
- How to organize and manage a scalable React app structure

---


## 📸 Preview

![App Preview](public/preview.png)

---

## 💡 Future Improvements

- Add total price calculation
- Persist cart data using `localStorage`
- Add checkout and payment simulation
- Add responsive design with Tailwind CSS or CSS Modules

---

## 🧑‍💻 Author

**Ganesh Ragolu**

- 🌐 [GitHub](https://github.com/GaneshRagolu001/Elegant-Context.git)
- 💬 Built this project to practice React state management and reducer patterns.

---
 