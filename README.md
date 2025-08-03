# 🧪 LibUnit

> A lightweight C unit testing framework for 42 projects that safely isolates and reports function behavior.

---

## 📖 Description

**LibUnit** is a custom unit-testing framework built for the **42 School curriculum**, aiming to test C functions in a safe and modular way. The framework is designed to:
- Execute each test in a **separate process** using `fork()`, allowing for clean failure handling.
- Detect and report unexpected behaviors like **segmentation faults**, **bus errors**, or **infinite loops**.
- Provide **clean and readable output** summarizing which tests passed, failed, or crashed.
- Be **reusable**, **extensible**, and **fully compliant** with the restrictions of 42 projects.

---

## 🧠 How It Works

- Tests are added to a list using `load_test()`, giving each one a name and function pointer.
- The list is passed to `launch_tests()`, which:
  - Runs each test using `fork()`.
  - Captures and interprets exit codes and signals.
  - Displays the results in a clear format.
- Your real logic (like `ft_atoi`, `ft_strlen`, etc.) is tested without crashing the whole test suite.

---

## 📂 Project Structure
```
libunit/
├── framework/
│ ├── launcher.c # launch_tests, test loop
│ ├── loader.c # load_test function
│ ├── tester.c # logic for forking/waiting
│ ├── utils.c # helper functions (e.g., signal interpretation)
│ └── libunit.h # all framework declarations
│
├── tests/
│ ├── 00_launcher.c # test launcher per function
│ ├── 01_basic_test.c # individual test files
│ └── ...
│
├── Makefile
└── README.md
```

---

## ⚙️ Usage

### 🔧 Compile

```bash
make
This builds the libunit.a static library and compiles the test launchers.
🧪 Run Tests
Run the compiled test launcher:
./tests/launcher_atoi



