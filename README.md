# LangChain Document Loaders

A collection of examples demonstrating how to use different document loaders in LangChain to load data from various sources.

## Prerequisites

- Python 3.8+
- Google API Key (for examples using Google Generative AI)

## Installation

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd LangChain-Document-Loaders
```

### Step 2: Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Linux/Mac
# or
venv\Scripts\activate  # On Windows
```

### Step 3: Install Dependencies

```bash
pip install langchain langchain-community langchain-google-genai python-dotenv pypdf beautifulsoup4
```

### Step 4: Set Up Environment Variables

Create a `.env` file in the project root:

```bash
GOOGLE_API_KEY=your_google_api_key_here
```

## Document Loaders

### 1. Text Loader

**File:** `text_loader.py`

Loads plain text files and processes them with LangChain.

```bash
python text_loader.py
```

**What it does:**
- Loads `cricket.txt` using `TextLoader`
- Creates a summarization chain using Google Generative AI
- Outputs a summary of the text content

---

### 2. CSV Loader

**File:** `csv_loader.py`

Loads CSV files where each row becomes a separate document.

```bash
python csv_loader.py
```

**What it does:**
- Loads `Social_Network_Ads.csv` using `CSVLoader`
- Each row in the CSV becomes a separate document
- Prints the total number of documents and sample content

---

### 3. PDF Loader

**File:** `pdf_loader.py`

Loads PDF files where each page becomes a separate document.

```bash
python pdf_loader.py
```

**What it does:**
- Loads a PDF file using `PyPDFLoader`
- Each page of the PDF becomes a separate document
- Prints page content and metadata

**Note:** Ensure you have a PDF file (e.g., `dl-curriculum.pdf`) in the project directory.

---

### 4. Directory Loader

**File:** `directory_loader.py`

Loads multiple files from a directory using glob patterns.

```bash
python directory_loader.py
```

**What it does:**
- Loads all PDF files from the `books/` directory
- Uses `lazy_load()` for memory-efficient loading
- Prints metadata for each loaded document

**Note:** Place PDF files in the `books/` folder before running.

---

### 5. Web Base Loader

**File:** `webbase_loader.py`

Loads content from web pages.

```bash
python webbase_loader.py
```

**What it does:**
- Fetches content from a specified URL
- Creates a Q&A chain using Google Generative AI
- Answers questions based on the web page content

---

## Project Structure

```
LangChain-Document-Loaders/
├── README.md
├── .env                    # Environment variables (create this)
├── cricket.txt             # Sample text file
├── Social_Network_Ads.csv  # Sample CSV file
├── text_loader.py          # Text file loader example
├── csv_loader.py           # CSV file loader example
├── pdf_loader.py           # PDF file loader example
├── directory_loader.py     # Directory loader example
├── webbase_loader.py       # Web page loader example
└── books/                  # Directory for PDF files
    └── readme.md
```

## Key Concepts

| Loader | Use Case | Output |
|--------|----------|--------|
| `TextLoader` | Plain text files (.txt) | Single document |
| `CSVLoader` | CSV files | One document per row |
| `PyPDFLoader` | PDF files | One document per page |
| `DirectoryLoader` | Multiple files in a directory | Multiple documents |
| `WebBaseLoader` | Web pages | Single document per URL |

## Tips

- Use `lazy_load()` for large files or directories to save memory
- Always specify `encoding='utf-8'` for text files to avoid encoding issues
- The `glob` parameter in `DirectoryLoader` supports patterns like `*.pdf`, `**/*.txt`

## License

MIT License
