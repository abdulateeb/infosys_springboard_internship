# EasyHire

EasyHire helps find the best person for a job! It looks at resumes and job descriptions, then makes reports to show who fits best. The reports come in a neat ZIP file!

## What It Does

- **Checks Resumes**: Looks at resumes and gives them a score (1-100).
- **Finds Strengths & Weaknesses**: Tells what a person is good at and what they can improve.
- **Makes Reports**:
  - Creates a PDF for each person.
  - Makes a CSV file with all candidate details.
- **ZIP File**: Puts all reports in one easy-to-download file.

## How to Set It Up

### What You Need

- Python 3.10 or newer
- Pip (a package manager for Python)

### Steps

1. Get the project and go to the folder:
   ```bash
   git clone <repository-url>
   cd EasyHire
   ```
2. Create and start a virtual environment:
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```
3. Install everything needed:
   ```bash
   pip install -r requirements.txt
   ```

## How to Use It

### Start the Program

1. Open the project folder.
2. Run the server:
   ```bash
   uvicorn app.main:app --reload
   ```
3. Open a web browser and go to `http://127.0.0.1:8000`.

### Upload Resumes

- **Where to Upload**: `POST /upload/`
- **What to Upload**: Resumes and job descriptions.
- **What You Get Back**: A ZIP file with:
  - PDFs for each person.
  - A CSV file with all results.

### Example Results

```json
[
  {
    "candidate_name": "John Doe",
    "score": 85,
    "strengths": "Good at coding, works well in teams",
    "weaknesses": "Needs to learn more about cloud computing",
    "analysis": "John knows a lot about software but should learn more about cloud tech."
  },
  {
    "candidate_name": "Jane Smith",
    "score": 90,
    "strengths": "Great problem-solving, knows AI",
    "weaknesses": "Should work on communication skills",
    "analysis": "Jane is very skilled in AI but should practice speaking clearly."
  }
]
```

## What's Inside the Project

```
EasyHire/
├── app/
│   ├── main.py       # Runs the program
│   ├── utils.py      # Helps make reports
│   ├── models.py     # Stores data
│   ├── static/       # Holds extra files (if needed)
│   └── templates/    # Web page templates (if needed)
├── requirements.txt  # List of needed tools
├── README.md         # Info about the project
└── tests/            # Checks if everything works
```

## Tools Used

- **FastAPI** - Helps build the web service.
- **Uvicorn** - Runs the web service.
- **FPDF** - Makes PDF reports.
- **Zipfile** - Packs everything into a ZIP file.

To install everything, run:
```bash
pip install -r requirements.txt
```

## For Developers

### Test the Code
Run tests with:
```bash
pytest
```

### Check Code Quality
Make sure the code is neat with:
```bash
flake8
```

## Want to Help?

You can improve this project! If you find problems or have ideas, feel free to share. Make sure your changes work before adding them.

## License

This project uses the MIT License. See the `LICENSE` file for details.

