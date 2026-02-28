# AGENTS.md

## Cursor Cloud specific instructions

### Repository overview

This repository contains 5 student/academic projects stored as ZIP archives at the repo root. There is no top-level build system, package manager, or CI/CD configuration.

| ZIP Archive | Project | Technology | Runnable |
|---|---|---|---|
| `calculator-*.zip` | Java Swing Calculator | Java (NetBeans) | Yes — JDK only |
| `Diary1-*.zip` | Diary Application | Java (Eclipse) | Yes — JDK only |
| `TempConverter-*.zip` | Temperature Converter | Java (NetBeans) | No — empty src |
| `CBIR Complete Major Project-*.zip` | Content-Based Image Retrieval | Python (OpenCV, sklearn) | Partial — see note |
| `A secure and dynamic multi-keyword ranked search scheme...zip` | Encrypted Cloud Data Search | ASP.NET / C# | No — requires IIS/Windows |

### Running the Java Calculator (primary demo)

```bash
# Extract and compile
unzip -o "calculator-20190812T185424Z-001.zip" -d /tmp/extracted/calculator/
mkdir -p /tmp/calc_build
javac -d /tmp/calc_build /tmp/extracted/calculator/calculator/src/calculation/calculator.java
# Run (requires DISPLAY)
DISPLAY=:1 java -cp /tmp/calc_build calculation.calculator
```

### CBIR Python project notes

- The CBIR project uses `greycomatrix` / `greycoprops` from scikit-image, which were removed in scikit-image >= 0.21. These old function names are incompatible with Python 3.12+. Core functionality (image loading, histograms, KMeans clustering) works with current packages.
- Python dependencies: `pip3 install opencv-python-headless numpy scipy scikit-learn scikit-image matplotlib glob2`

### Lint / Test / Build

There are no lint configurations, automated tests, or build scripts in this repository. The projects are standalone academic archives. Verification is done by compiling and running individual projects.
