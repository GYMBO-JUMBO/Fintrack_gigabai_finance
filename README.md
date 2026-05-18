# Fintrack_gigabai_finance

## 🛠️ Technology Stack
Programming Language: Python 3.10+

Graphical User Interface (GUI): customtkinter (A specialized extension of standard tkinter optimizing smooth, flat geometric UI rendering).

Storage Engine: Structured data persistence using Python's native json streams using safe transactional overwrites.

## 💡 Architecture & Implementation Details
Custom Theme Render Engine: To circumvent standard customtkinter rendering bugs that cause transparent container frames to unexpectedly bleed into hard white fragments when toggling the systemic appearance engine, ctk.set_appearance_mode("dark") is locked permanently. The theme layer is instead managed manually by dynamically swapping raw HEX color assignments across all elements based on the state of the active self.theme flag.

Thread-Safe Local Pipeline: State operations (adding income, dropping an expense row, updating settings strings) trigger sequential procedural calls: load_users() -> dict mutation -> save_users(). This guarantees atomic transaction writes directly into the users.json layout, eliminating the performance overhead of running an active external database server.

