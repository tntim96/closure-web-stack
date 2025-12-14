# Closure Web Stack

This repository packages a small, reproducible toolchain for building
Closure-style JavaScript applications.

It bundles:

- **Closure Compiler**
- **Closure Library**
- **Closure Templates (Soy) JavaScript runtime**
- **Incremental DOM**

The output is a single ZIP intended for use by build scripts or CI systems,
not as a runtime dependency.

---

## Contents

The assembled ZIP contains the following structure:

```
closure-web-stack-<version>/
├── compiler/
│ └── closure-compiler-<version>.jar
├── closure-library/
│ └── closure/
│ └── goog/...
├── closure-templates/
│ └── javascript/
│ ├── soyutils_usegoog.js
│ ├── soyutils_idom.js
│ └── required_by_soy.js
└── incremental-dom/
└── incremental-dom.js
```

Only the JavaScript runtime components needed for Closure + Soy + Incremental
DOM are included. Server-side Soy (Java/Python), examples, tests, and
documentation are intentionally excluded from the distribution.

---

## Building the ZIP

From the repository root:

```bash
mvn clean package
```

The resulting archive will be written to:

target/closure-web-stack-<version>.zip