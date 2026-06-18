---
name: Developers Assistant
nested_agents:
  - Github Reader
  - Readme Creator
  - Merge Request Creator
orchestrator_instruction: >-
  Follow the workflow in this exact order: Github Reader -> Readme Creator -> Merge Request Creator.
  The Github Reader gathers repository facts from the codebase, the Readme Creator turns those facts into
  a complete README.md, and the Merge Request Creator prepares the final change for review.
---

# quiz-cli

## Project Overview

`quiz-cli` is a Node.js command-line quiz game located in `test-app/`. It presents an interactive terminal experience where users can choose a quiz category, answer multiple-choice questions, and review their results at the end.

The application is built with Node.js ES modules and uses only built-in Node.js APIs. Its source code is organized into a small CLI entrypoint, reusable input helpers, quiz logic, terminal color helpers, and a JSON question bank.

## Features

- Interactive terminal quiz experience
- Category-based question selection
- Choice of question count per quiz
- Randomized question order
- Progress display during the quiz
- Immediate feedback for correct and incorrect answers
- Explanations shown after each question when available
- Final score summary with performance messages
- Review of incorrect answers after completion
- Play-again loop for continuous sessions
- ANSI-based terminal color formatting without external dependencies

## Technologies and Tools

- **Language:** JavaScript
- **Runtime:** Node.js `>=18.0.0`
- **Module system:** ES Modules (`"type": "module"`)
- **Built-in Node.js modules used:**
  - `node:fs/promises`
  - `node:url`
  - `node:path`
  - `node:readline`
- **CLI execution:** Node.js command-line runtime
- **Testing script:** `node --test` as defined in `package.json`

## Project Structure

```text
test-app/
├── data/
│   └── questions.json
├── index.js
├── package.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File responsibilities

- **`test-app/index.js`**  
  Main CLI entrypoint. Loads quiz data, renders the banner, coordinates category and question-count selection, runs the quiz loop, and handles top-level errors.

- **`test-app/src/quiz.js`**  
  Contains the `Quiz` class, including question shuffling, answer tracking, progress rendering, result display, and incorrect-answer review.

- **`test-app/src/input.js`**  
  Provides readline-based helpers for prompting, selection, confirmation, and pause/continue behavior.

- **`test-app/src/colors.js`**  
  Provides ANSI color utilities for terminal styling.

- **`test-app/data/questions.json`**  
  Stores the quiz content grouped into categories.

- **`test-app/package.json`**  
  Defines project metadata, runtime requirements, and npm scripts.

## Prerequisites

- Node.js `18.0.0` or newer
- A terminal capable of displaying ANSI escape codes

No external npm dependencies are declared in `package.json`.

## Setup Instructions

1. Clone the repository.
2. Change into the application directory:
   ```bash
   cd test-app
   ```
3. Ensure you are using Node.js 18 or newer.
4. Run the application with the provided npm script or directly with Node.js.

## Getting Started

### Run the quiz

From inside `test-app/`:

```bash
npm start
```

This runs:

```bash
node index.js
```

You can also start the app directly:

```bash
node index.js
```

### Run the test script

The project defines a test script in `package.json`:

```bash
npm test
```

This uses Node’s built-in test runner:

```bash
node --test
```

## Usage Examples

### Start the quiz

```bash
cd test-app
npm start
```

### Run the entrypoint directly

```bash
cd test-app
node index.js
```

### Run tests

```bash
cd test-app
npm test
```

### Typical gameplay flow

1. Launch the app.
2. Choose a category.
3. Choose how many questions to answer.
4. Answer each multiple-choice question by entering the option number.
5. Review your score and any incorrect answers.
6. Decide whether to play again.

## Configuration

The main configuration lives in the repository files themselves:

- **`package.json`**
  - `main`: `index.js`
  - `type`: `module`
  - `scripts.start`: `node index.js`
  - `scripts.test`: `node --test`
  - `engines.node`: `>=18.0.0`

- **`data/questions.json`**
  - Stores all quiz categories and questions.
  - Each question includes:
    - `question`
    - `options`
    - `answer`
    - `explanation`

There are no environment variables or external configuration files referenced in the source.

## Error Handling and Troubleshooting

### Error handling behavior

The CLI includes top-level error handling in `index.js`:

- Application logic is wrapped in a `try/catch`
- Failures are printed with a styled error message
- The process exits with code `1` on fatal errors
- The `readline` interface is always closed in a `finally` block

### Input validation

The input helper rejects invalid menu selections and prompts again until the user enters a valid number.

### Common troubleshooting tips

- **“Cannot find module” or syntax issues:** make sure you are running Node.js 18+.
- **Quiz does not start:** confirm you are executing the app from inside `test-app/`.
- **Terminal colors look odd:** your terminal may not fully support ANSI escape codes.
- **JSON parsing errors:** verify that `data/questions.json` remains valid JSON.

## Future Improvements

Potential enhancements suggested by the current codebase:

- Add more quiz categories and questions
- Add persistent score history
- Support custom quiz lengths beyond the current preset options
- Allow random category selection
- Add automated tests for quiz behavior and input handling
- Improve accessibility for non-ANSI terminals
- Add packaging for easier global CLI installation
- Persist user progress or best scores between sessions

## Orchestrator Workflow

This repository documentation is intended to be produced through the following agent workflow:

1. **Github Reader**  
   Reads the repository contents and extracts only facts supported by the code.

2. **Readme Creator**  
   Converts those facts into a complete, professional `README.md`.

3. **Merge Request Creator**  
   Packages the README changes for review and submission.

The required order is:

**Github Reader -> Readme Creator -> Merge Request Creator**

This order should be followed exactly to ensure the README is based on repository evidence before any final submission is prepared.