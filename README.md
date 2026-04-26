# Job Seeker Prompt Generator

**Two ways to generate AI prompts for your job applications:**

## 🎯 What It Does

This tool takes your:
- **Excel file** with company names and job descriptions
- **Resume** (full text)
- **Professional summary** (2-3 sentences)

And generates **5 tailored AI prompts** for each job application:
1. Company Culture & Intel
2. Hidden Job Requirements
3. Gap Analysis
4. Tailored Resume Summary
5. Rubric Evaluation

## 🚀 Quick Start

### Option 1: Web Interface (Recommended)

```bash
# Install dependencies
pip install -r requirements.txt

# Run the web app locally
python app.py
# or
python run_web.py

# Open http://localhost:5000 in your browser
```

Or deploy the Flask app to a Python-friendly host like PythonAnywhere.
I currently run a free account at:

https://leonardjohnsonjr.pythonanywhere.com/

## 📊 Excel File Format

Your Excel file must have these exact column headers:
- **Company**: The company name
- **Job_Description**: The full job description text
- **Run** (optional): If present, only rows with a truthy value in this column will be processed.

Accepted truthy values for the optional **Run** column include: `yes`, `y`, `true`, `1`, `x`, `run`, or `go`.

Example:
| Company | Job_Description | Run |
|---------|----------------|-----|
| Google | We are looking for a software engineer... | yes |
| Microsoft | Join our team as a product manager... | no |

If the **Run** column is omitted, all rows are processed.

**Try it out:** Use the included `sample_jobs.xlsx` file to test!

## 📝 Input Methods

### Web Version
- **Upload files**: Drag & drop Excel, resume (.txt/.md), and summary files
- **Paste text**: Directly input resume and summary content
- **Tabbed interface**: Switch between file upload and text input

### Command Line Version
- **File paths**: Configure paths in `config.json`
- **Command line flags**: Override config with `--excel`, `--resume`, etc.

## 🎨 Web Version Features

- **Responsive design** that works on desktop and mobile
- **Tabbed interface** for easy input switching
- **Copy-to-clipboard** functionality for each prompt
- **Download options** for individual or bulk markdown files
- **Professional styling** with modern UI
- **No external APIs** - everything runs locally

## 🔧 Technical Details

- **Backend**: Flask (Python)
- **Frontend**: HTML5, CSS3, JavaScript
- **Dependencies**: Flask, openpyxl, Werkzeug
- **No external APIs** required - everything runs locally

## 📋 Quality Rubric

Every AI response should meet these 5 rules:
1. **Specificity** - References specific details from job/company/resume
2. **Actionability** - Includes concrete, actionable takeaways
3. **Completeness** - Fully addresses the question asked
4. **Candidate-Centric Framing** - Focused on helping you prepare
5. **Professional Tone** - Clear, professional, no filler phrases

## 🤝 Contributing

Feel free to submit issues or pull requests to improve the application!

## 📄 License

This project is open source and available under the MIT License.
| `resume_summary.txt` | A 2-3 sentence professional summary used in the tailored summary prompt |

File paths are resolved in this order:

1. CLI flags (`--resume`, `--resume-summary`)
2. `config.json` (`"resume"`, `"resume_summary"` keys)
3. Error with a helpful message if neither is provided

---

## Quality Rubric

Each generated prompt file includes a built-in quality rubric with 5 rules that AI responses should meet:

1. **Specificity** — References specific details from the job description, company, or resume
2. **Actionability** — Includes concrete, actionable takeaways
3. **Completeness** — Fully addresses the question without leaving gaps
4. **Candidate-Centric Framing** — Framed from the job seeker's perspective
5. **Professional Tone** — Clear, professional language without fluff

Use the 5th prompt ("Rubric Evaluation") to have the AI self-evaluate its own responses.

---

---

## Generated Prompts

The script generates five prompts for each job application:

| # | Prompt | Purpose |
|---|---|---|
| 1 | **Company Culture & Intel** | Summarize the company's culture, challenges, recent news, and suggest a smart interview question |
| 2 | **Hidden Job Requirements** | Uncover unstated priorities and personality traits behind the formal job description |
| 3 | **Gap Analysis** | Identify where your background is weakest for this role, with suggestions to address gaps |
| 4 | **Tailored Resume Summary** | Rewrite your resume summary to mirror the language and priorities of the job description |
| 5 | **Rubric Evaluation** | Evaluate AI responses against the 5 quality rules (use this after getting responses from prompts 1-4) |

Each prompt is saved in a clean Markdown file with fenced code blocks for easy copying and pasting into AI interfaces.

---

## .gitignore Recommendations

```gitignore
# Generated prompt files
reports/
prompts/

# Personal resume files (optional — omit if you want them versioned)
resume.txt
resume_summary.txt

# Excel files with personal data
jobs_data.xlsx
```

# macOS / editor artifacts
.DS_Store
__pycache__/
*.pyc
```

---

## License

MIT License. See [LICENSE](LICENSE) for details.
