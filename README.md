# NDTkit UT - API Examples & SDKs

Welcome to the central hub for automation and control examples regarding TESTIA's **[NDTkit](https://www.testia.com/product/ndtkit-ut/)** software.

This repository aggregates projects, SDKs, and code samples designed to interact with the NDTkit API. It is tailored for NDT engineers and developers looking to integrate NDTkit into custom toolchains, automate acquisition workflows, or extend the software's capabilities.

## 🧠 Core Concepts: Two Ways to Interact

Before diving into the code, it is essential to understand that NDTkit supports **two distinct interaction modes** depending on the language and use case:

### 1\. External Automation (TCP Sockets)

Used by **C++** and Standard **Python**.

- **How it works:** Your code runs as a separate process (outside NDTkit) and communicates with NDTkit via a TCP Socket Server.
- **Use case:** Remote control, integrating NDTkit into a larger factory pipeline, headless automation, high-performance external processing or new feature adding.

### 2\. Internal Scripting (Menus & Plugins)

Used by **Jython** and **Java**.

- **How it works:** Your code runs _inside_ NDTkit's Java Virtual Machine (JVM).
- **Deployment:** Scripts are placed in the user's configuration folder (e.g., `.ndtkit/Conf_4.1/scripts`).
- **Use case:** Creating **custom menus** directly inside the NDTkit GUI, accessing internal objects without serialization overhead, and seamless workflow extensions.

---

## 📂 Project Structure

This repository acts as a container for multiple **Git submodules**, separating examples by language and approach:

| Language   | Directory                                                                                                       | Description                                   | Interaction Mode       |
| :--------- | :-------------------------------------------------------------------------------------------------------------- | :-------------------------------------------- | :--------------------- |
| **Python** | [`ndtkit-python-api-examples/`](https://github.com/cedric-bertrand-testia/ndtkit-python-api-examples/tree/main) | Examples using the `ndtkit-api` PyPI library. | 🔌 **External Socket** |
| **C++**    | [`ndtkit-cpp-api-examples/`](https://github.com/cedric-bertrand-testia/ndtkit-cpp-api-examples)                 | C++ Client implementation (`NDTKitClient`).   | 🔌 **External Socket** |
| **Jython** | [`ndtkit-jython-api-examples/`](https://github.com/cedric-bertrand-testia/ndtkit-jython-api-examples)           | Scripts to create custom NDTkit menus.        | 📑 **Internal Menu**   |
| **Java**   | _(Coming Soon)_                                                                                                 | Compiled plugins for NDTkit.                  | 📑 **Internal Menu**   |

---

## 🚀 Installation & Cloning

Because this repository uses Git submodules, a standard clone will result in empty folders.

### Recommended Method (One-liner)

To clone the repository and automatically download the content for the submodules:

```bash
git clone --recurse-submodules https://github.com/YOUR-USERNAME/ndtkit-api-examples.git
```

### If you have already cloned the repository

If the folders are empty, run the following command at the root of the project to fetch the submodules:

```bash
git submodule update --init --recursive
```

---

## 🔌 External Automation Examples

These languages communicate with NDTkit over a network port (Default: 32146). NDTkit must be running with the Server option enabled.

### 🐍 Python (Standard)

The Python submodule demonstrates how to use the official wrapper library.

- **Library:** Uses `ndtkit-api` from PyPI.
- **Features:** Automatic connection management, loading `.nkc` files, and manipulating C-Scan data using a Pythonic interface.
- 👉 **[Browse Python Examples](https://github.com/cedric-bertrand-testia/ndtkit-python-api-examples)**

### ⚙️ C++

The C++ submodule provides a high-performance, low-level integration.

- **Library:** Includes a custom `NDTKitClient` header-only library.
- **Features:** Direct implementation of the binary protocol (Header + Length + JSON Payload). Ideal for embedding NDTkit control into C++ industrial applications.
- 👉 **[Browse C++ Examples](https://github.com/cedric-bertrand-testia/ndtkit-cpp-api-examples)**

---

## 📑 Internal Scripting Examples

These languages run directly within the NDTkit process to extend the User Interface.

### ☕ Jython & Java

_Note: Specific examples for Jython/Java are being added to this repository._

Unlike the socket-based examples, Jython scripts and Java JARs are not executed from a terminal. Instead, they are recognized by NDTkit at startup to **generate new menu items** in the application toolbar.

- **Deployment Path:** Files must be copied to:
  `C:/Users/<USERNAME>/.ndtkit/Conf_<VERSION>/scripts`
- **Behavior:**
  1.  NDTkit scans this folder upon launch.
  2.  It creates a new menu entry (e.g., "My Custom Script").
  3.  When clicked, the script executes within the NDTkit context, having direct access to the currently open data without network transfer.

---

## 🔗 Prerequisites

To run any of these examples, you must have:

1.  **NDTkit UT 4.1+** installed and licensed.
2.  For Socket examples (Python/C++): NDTkit must be launched.
3.  For Menu examples (Jython/Java): NDTkit must be restarted after adding the scripts.

## 🤝 Contributing

Contributions are welcome\! If you have developed a wrapper for another language (C\#, MATLAB, LabVIEW, etc.) or have additional examples:

1.  Fork this repository.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes.
4.  Push to the branch.
5.  Open a Pull Request.

## 📄 License

This project is distributed under the MIT License (unless stated otherwise in the specific submodules). See the [LICENSE](https://www.google.com/search?q=LICENSE) file for more information.
