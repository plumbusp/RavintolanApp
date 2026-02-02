# 🍽️ Restaurant App

A Unity-based interactive restaurant application built with C#. The app handles order creation, menu item filtering, and stores orders in .txt files on the local machine.
It has dynamic UI updates, event-driven design and modular structure. It persists application state between sessions.

---

### 📌 The project extensively applies OOP, including:

- **Inheritance** to share common behavior and enable polymorphism (e.g all shop items inheriting logic from the ShopItem class)
- **Abstraction** to define flexible interfaces (e.g. how DataObject class handles new info addition about current ShopItems)
- **Encapsulation** to isolate implementation details (can be found throughout all scripts)

### 📌 Design Patterns used:
- **Factory** – for controlled creation of menu items (e.g in ShopItemViewFactory)
- **Observer** – for reacting to state and UI changes (e.g. in CartItemView/Item objects)

Design Patter usage example:
The project uses **ScriptableObject-based factories** to create UI elements dynamically:
- 'CartItemViewFactory' creates fully initialized 'CartItemView' instances for the shopping cart.
- 'ShopItemViewFactory' creates 'ShopItemView' instances for menu items.
- Each factory encapsulates object creation and initialization, so client code only needs to call Get(item, parent) without worrying about Instantiate or Initialize.
- This approach improves modularity, reusability, and maintainability.

### 📌 Persistence & Initialization
The application maintains its state between sessions using a **local data provider**:
- 'DataObject' stores order and customer information.
- 'PersistantData' acts as a container for the current session.
- 'LocalDataProvider' handles saving and loading orders as .txt files, ensuring unique file naming and order counting.

The scene is bootstrapped by 'StoreBootstrap', which:
- Initializes the **shop**, **cart**, and **personal info controller** with shared 'PersistantData'.
- Subscribes to events such as order completion to reset the session.
- Demonstrates **dependency injection**, **observer pattern**, and **MVC-like separation** of data and UI logic.
---

## 🛠️ Technologies Used

- **C#**
- **Unity Engine**
- **Git & GitHub**
