# Murder in Westeros --- Game of Thrones Murder Mystery

An AI-powered, full-stack murder mystery game set in the world of *Game
of Thrones*. Each investigation presents a crime, five suspects, and a
sequence of clues. Examine the evidence, narrow down the suspects, and
identify the killer.

> **Note:** This is a fan-made, non-commercial project inspired by the
> fictional world of *Game of Thrones*. It is not affiliated with or
> endorsed by HBO or the rights holders.



## Features

-   **AI-generated mysteries:** Claude Sonnet 4 generates murder
    scenarios, motives, suspects, and clues.
-   **Interactive investigations:** Review the crime scene and examine
    clues one at a time.
-   **Suspect elimination:** Use the evidence to work out who committed
    the murder.
-   **Guess submission:** Submit your accusation and receive the game's
    result.
-   **Replayability:** Start a new investigation to receive another
    mystery.

## Tech Stack

  Layer            Technology
  ---------------- ----------------------------------------
  Backend          Python, FastAPI
  Frontend         React 18, Vite
  AI integration   Anthropic Claude API (Claude Sonnet 4)
  Communication    REST API

## Project Structure

``` text
got_murder_mystery/
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   └── .env                 # Create locally; do not commit
├── frontend/
│   ├── index.html
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.js
│   └── src/
│       ├── App.jsx
│       └── main.jsx
├── docs/
│   └── screenshots/
└── README.md
```

## Getting Started

### Prerequisites

-   Python 3.9+ (use the version supported by your dependencies)
-   Node.js and npm
-   An Anthropic API key

### 1. Clone the repository

``` bash
git clone https://github.com/vaishnavimukala/got-murder-mystery.git
cd got-murder-mystery
```

### 2. Configure the backend

``` bash
cd backend
python -m venv venv
```

Activate the virtual environment:

**Windows PowerShell**

``` powershell
.\venv\Scripts\Activate.ps1
```

**macOS / Linux**

``` bash
source venv/bin/activate
```

Install dependencies:

``` bash
pip install -r requirements.txt
```

Create a `.env` file inside `backend/` and add your Anthropic API key
using the environment-variable name expected by `backend/main.py`. For
example:

``` env
ANTHROPIC_API_KEY=your_anthropic_api_key
```

If your code uses a different variable name, use that exact name
instead. Keep `.env` out of Git.

Start the backend:

``` bash
uvicorn main:app --reload --port 8000
```

Backend: `http://localhost:8000`\
API documentation: `http://localhost:8000/docs`

### 3. Configure the frontend

Open a second terminal:

``` bash
cd frontend
npm install
npm run dev
```

Frontend: `http://localhost:3000` (if configured on port 3000 in
`vite.config.js`).

## API Endpoints

  Method   Endpoint      Purpose
  -------- ------------- -------------------------------
  `POST`   `/new-game`   Generate a new murder mystery
  `POST`   `/guess`      Submit a guess for the killer
  `GET`    `/health`     Check backend health

## How to Play

1.  Open the game in your browser.
2.  Begin a new investigation.
3.  Read the crime details, including the victim, location, and method.
4.  Review the clues as they are revealed.
5.  Compare the clues with the suspects and their motives.
6.  Submit your guess for the killer.
7.  Review the outcome or start another investigation.

## Configuration and Security

-   Store the Anthropic API key in a local environment file.
-   Never commit `.env`, API keys, access tokens, or other credentials.
-   Keep `backend/.env` and other environment files excluded through
    `.gitignore`.
-   If an API key has previously been committed or exposed, revoke it
    and create a replacement.

## Future Enhancements

-   Add difficulty levels and optional hints.
-   Track investigation history and player scores.
-   Add richer character profiles and evidence presentation.
-   Deploy the frontend and backend so the game can be played online.

## Author

**Vaishnavi Mukala**

GitHub: [@vaishnavimukala](https://github.com/vaishnavimukala)

------------------------------------------------------------------------

If you enjoy the project, feel free to explore the code and share
feedback.
