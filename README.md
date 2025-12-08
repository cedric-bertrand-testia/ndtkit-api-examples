# NDTkit UT - API Examples & SDKs

Welcome to the central hub for automation and control examples regarding TESTIA's **[NDTkit](https://www.testia.com/product/ndtkit-ut/)** software.

This repository aggregates projects, SDKs, and code samples designed to interact with the NDTkit UT external API across different programming languages. It is tailored for NDT engineers and developers looking to integrate NDTkit into custom toolchains, automate acquisition workflows, or process data in real-time.

## 📂 Project Structure

This repository acts as a container for multiple **Git submodules**, separating examples by language and approach:

| Language   | Directory                                                                                             | Description                                     | Approach               |
| :--------- | :---------------------------------------------------------------------------------------------------- | :---------------------------------------------- | :--------------------- |
| **Python** | [`ndtkit-python-api-examples/`](https://github.com/cedric-bertrand-testia/ndtkit-python-api-examples) | Examples using the high-level **PyPI** library. | High-Level (Wrapper)   |
| **C++**    | [`ndtkit-cpp-api-examples/`](https://github.com/cedric-bertrand-testia/ndtkit-cpp-api-examples)       | C++ Client implementation and examples.         | Low-Level (TCP Socket) |

---

## 🚀 Installation & Cloning

Because this repository uses Git submodules, a standard clone will result in empty folders.

### Recommended Method (One-liner)

To clone the repository and automatically download the content for both Python and C++ submodules:

```bash
git clone --recurse-submodules https://github.com/YOUR-USERNAME/ndtkit-api-examples.git
```

### If you have already cloned the repository

If the `python-examples` or `cpp-examples` folders are empty, run the following command at the root of the project to fetch the submodules:

```bash
git submodule update --init --recursive
```

---

## 🐍 Python Examples

The Python submodule demonstrates how to use the official library, which significantly simplifies interactions with the software.

- **Approach:** Uses the `ndtkit-api` package available on PyPI.
- **Prerequisites:** Python 3.7+
- **Library Installation:**
  ```bash
  pip install ndtkit-api
  ```
- **Key Features Covered:**
  - Automatic server connection.
  - Loading `.nkc` files.
  - Object-Oriented manipulation of C-Scan data.
  - High-level interface for defect detection and analysis.

👉 **[Browse Python Examples](https://www.google.com/search?q=./python-examples)**

---

## ⚙️ C++ Examples

The C++ submodule provides a fundamental approach, ideal for integration into high-performance systems or environments where Python is not an option.

- **Approach:** Direct communication via **TCP Sockets**. This project includes a lightweight C++ client library (`NDTKitClient`) that implements the NDTkit binary protocol.
- **Purpose:** Demonstrates the language-agnostic nature of the API and ensures maximum performance.
- **Contents:**
  - Protocol implementation (Header + Length + JSON Payload).
  - Full example (`main.cpp`) for loading files and processing data.
  - **CMake** configuration for easy compilation.

👉 **[Browse C++ Examples](https://www.google.com/search?q=./cpp-examples)**

---

## 🔗 NDTkit Prerequisites

To run these examples, you must have a functional installation of **NDTkit UT 4.1.X** (provided by TESTIA).

## 🤝 Contributing

Contributions are welcome\! If you have developed a wrapper for another language (C\#, MATLAB, LabVIEW, etc.) or have additional examples:

1.  Fork this repository.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes.
4.  Push to the branch.
5.  Open a Pull Request.

## 📄 License

This project is distributed under the MIT License (unless stated otherwise in the specific submodules). See the [LICENSE](https://www.google.com/search?q=LICENSE) file for more information.
