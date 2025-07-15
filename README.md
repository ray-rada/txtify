# txtify
# 📄 txtify

<p align="center">
  <a href="https://pypi.org/project/txtify/">
    <img src="https://img.shields.io/pypi/v/txtify.svg" alt="PyPI Version">
  </a>
  <a href="https://pypi.org/project/txtify/">
    <img src="https://img.shields.io/pypi/pyversions/txtify.svg" alt="PyPI - Python Version">
  </a>
    <a href="https://github.com/ray-rada/txtify/blob/main/LICENSE.txt">
    <img src="https://img.shields.io/pypi/l/txtify.svg" alt="PyPI - License">
  </a>
</p>

**txtify** is a simple yet powerful command-line tool and Python library designed to effortlessly convert various document formats (PowerPoint, Word, PDF, and Excel) into clean, plain text files.  
It's ideal for extracting content for analysis, archiving, or providing crucial context to AI assistants like GitHub Copilot and Amazon CodeWhisperer, allowing them to better understand your project's domain knowledge, requirements, and existing documentation.

---

## 📚 Table of Contents

- [✨ Features](#-features)
- [🤖 Providing Context to AI Code Assistants](#-providing-context-to-ai-code-assistants)
- [🚀 Installation](#-installation)
- [💡 Usage (Command Line Interface)](#-usage-command-line-interface)
  - [Convert a Single File](#convert-a-single-file)
  - [Convert Multiple Files](#convert-multiple-files)
  - [Convert an Entire Directory](#convert-an-entire-directory)
  - [Specify an Output Directory](#specify-an-output-directory)
- [📂 Supported File Formats](#-supported-file-formats)
- [🗄️ Output](#-output)
- [📜 License](#-license)

---

## ✨ Features

✅ **Multi-Format Support**: Converts `.pptx` (PowerPoint), `.docx` (Word), `.pdf` (Portable Document Format), and `.xlsx` (Excel) files.  
✅ **Batch Processing**: Convert multiple files or entire directories at once.  
✅ **Clean Text Output**: Extracts core textual content, making documents easily searchable and readable for both humans and AI.  
✅ **Intuitive CLI**: Simple command-line interface for quick and easy conversions.  
✅ **Preserves Structure**: When converting directories, the original folder structure is replicated in the output.

---

## 🤖 Providing Context to AI Code Assistants

One of the most powerful use cases for **txtify** is to prepare your project's non-code documentation (e.g., design documents, requirement specifications, meeting notes, data dictionaries) for consumption by AI code generation tools like GitHub Copilot, Amazon CodeWhisperer, or similar LLM-based assistants.

### Why this is useful

- **Expand AI's Knowledge Base**: Let the AI "read" and understand domain-specific terminology, project goals, architectural decisions, and detailed requirements that might otherwise be locked away in binary formats.
- **Improve Code Relevance**: The AI can generate more relevant and accurate code suggestions, function names, and comments by leveraging the textual context.
- **Reduce Hallucinations**: With more accurate information, the AI is less likely to "hallucinate" or generate incorrect assumptions.
- **Seamless Integration**: Place the converted `.txt` files in a directory accessible to your IDE, and they can often automatically index and use this information.

### Example Workflow

1. Convert your documentation:
   ```bash
   txtify ./docs_and_requirements/ -o ./ai_context/
   ```

2. Integrate with your project: Place the `ai_context/` folder directly within your main project repository.
3. Let your AI assistant learn: Your assistant will now have access to the wealth of information contained in these plain text files, enabling more intelligent and context-aware code suggestions.

---

## 🚀 Installation

You can install **txtify** directly from PyPI using pip:

```bash
pip install txtify
```

---

## 💡 Usage (Command Line Interface)

**txtify** can be used directly from your terminal.

### Convert a Single File

Pass the path to your document as an argument:

```bash
txtify my_project_spec.docx
```

This will create a plain text file named `my_project_spec.txt` inside a new `output/` directory by default.

---

### Convert Multiple Files

Specify several files at once:

```bash
txtify requirements.pdf architecture.pptx data_schema.xlsx
```

This will convert the specified files to `.txt` versions in the `output/` directory.

---

### Convert an Entire Directory

Provide the path to a directory, and **txtify** will scan it (and its subdirectories) for all supported document types:

```bash
txtify project_documentation/
```

All convertible files will be processed. The original directory structure will be mirrored in the `output/` folder.
For example:

```
project_documentation/meetings/q1_notes.pptx
```

becomes:

```
output/project_documentation/meetings/q1_notes.txt
```

---

### Specify an Output Directory

Use the `-o` or `--output` option to choose a different location for your converted files:

```bash
txtify legacy_reports/ -o contextual_data/
```

This saves all converted text files into the `contextual_data/` directory.

---

## 📂 Supported File Formats

**txtify** currently supports conversion for the following file types:

* PowerPoint Presentations: `.pptx`
* Word Documents: `.docx`
* PDF Documents: `.pdf`
* Excel Workbooks: `.xlsx`
  *(converted to a CSV-like plain text format, useful for data extraction)*

---

## 🗄️ Output

Converted files will always have a `.txt` extension.
By default, they are saved to a directory named `output/` in your current working directory.
You can customize this using the `-o` or `--output` option.

If converting an entire directory, the relative path from the input directory is preserved in the output.

---

## 📜 License

**txtify** is distributed under the terms of the MIT License.
