# Study Bank MVP

Simple personal web platform:
- Question bank
- Error bank
- Notes
- Exam generator
- JSON import/export
- Admin-only user management
- Login/session authentication
- SQLite by default

## Run locally

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
uvicorn app.main:app --reload
```

Open http://127.0.0.1:8000

The initial admin account is configured in `.env`. Change SECRET_KEY before public deployment.

## JSON import format

Question example:

```json
[
  {
    "type": "mcq",
    "subject": "English",
    "topic": "Unit 1",
    "difficulty": 5,
    "question": "Question text",
    "choices": ["A", "B", "C", "D"],
    "answer": "B",
    "explanation": "Optional explanation"
  },
  {
    "type": "essay",
    "subject": "History",
    "topic": "Unit 2",
    "difficulty": 6,
    "question": "Explain ...",
    "answer": "Model answer"
  }
]
```

## Production note

For a public deployment, use PostgreSQL instead of SQLite and put secrets in the host's environment variables.
