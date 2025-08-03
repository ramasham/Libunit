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

## ✅ Key Features

- 🧩 **Modular Design**: Easily integrate with multiple functions (e.g., `ft_strlen`, `ft_atoi`, etc.)
- 🔒 **Process Isolation**: Ensures crashes in one test do not affect others
- ⚠️ **Signal Detection**: Handles segmentation faults, bus errors, aborts, timeouts, and more
- 📋 **Detailed Output**: Displays per-test result and summary report
- 🧱 **Reusability**: Designed to serve multiple test sets by just changing the test launcher
- 🧑‍🎓 **42-Compliant**: Only uses allowed functions (e.g., `malloc`, `fork`, `wait`, `write`, `signal`, etc.)

---

## 🔍 Typical Use Case

LibUnit is commonly used in 42 projects to validate implementations of functions such as:
- `ft_strlen`
- `ft_atoi`
- `ft_strncmp`
- Custom algorithms or sorting logic

Each test can validate correct outputs, boundary cases, and intentional errors, providing a **robust safety net** before peer evaluations.

---

## 🔒 Allowed Functions

LibUnit strictly adheres to the functions permitted by the 42 subject:

- `malloc`, `free`
- `write`, `exit`
- `fork`, `wait`, `waitpid`, `kill`
- `signal`, `alarm`
- `setitimer`, `gettimeofday`

Functions like `printf`, `sleep`, or standard libraries like `assert.h` or `string.h` are intentionally **excluded** to meet project norms.

---
## 👥 Authors
This project was developed as part of the 42 School curriculum by:  
🧑‍💻 [@ramasham](https://github.com/ramasham)  
🧑‍💻 [@maemran](https://github.com/maemran)






