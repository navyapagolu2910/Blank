# quiz-cli

## Project Overview

`quiz-cli` is an interactive command-line quiz game built with Node.js for learning JavaScript. It presents a shuffled set of questions from a JSON question bank, tracks the user's score, shows progress during the quiz, provides explanations, and displays a final results review.

The application is organized as an ES module-based CLI app and uses terminal input/output to deliver a lightweight learning experience directly in the console.

## Features

- Interactive command-line quiz experience
- Question shuffling for varied playthroughs
- Score tracking throughout the quiz
- Progress bar-style feedback during gameplay
- Answer explanations after each question
- Final results summary and review
- ANSI terminal colors for improved readability
- Input validation for user responses
- Robust `try/catch`-based error handling
- JSON-driven question bank
- Topic coverage including:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming

## Technologies and Tools

- **JavaScript**
- **Node.js** `>=18.0.0`
- **ES Modules** (`type: module`)
- **Node.js built-in `readline` interface** for terminal input
- **JSON** for quiz data storage
- **ANSI escape codes / terminal colors**
- **Node.js built-in test runner** via `node --test`

No third-party dependencies are listed in the repository’s `package.json`.

## Project Structure

```text
test-app/
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Overview

- **`test-app/index.js`**  
  Entry point for the CLI application.

- **`test-app/package.json`**  
  Project metadata, scripts, module type, and Node.js engine requirement.

- **`test-app/data/questions.json`**  
  Question bank used by the quiz application.

- **`test-app/src/colors.js`**  
  Terminal color utilities for styled console output.

- **`test-app/src/input.js`**  
  Input handling logic built around terminal interaction.

- **`test-app/src/quiz.js`**  
  Core quiz logic, including question flow, scoring, progress, and result handling.

## Prerequisites

- **Node.js 18.0.0 or later**

The repository does not list any external dependencies, so no additional packages are required beyond Node.js itself.

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Blank/test-app
   ```

2. **Verify your Node.js version**
   ```bash
   node --version
   ```
   Make sure the version is `18.0.0` or later.

3. **Install dependencies**

   There are no external dependencies declared in `package.json`, so there is nothing additional to install. If you prefer to initialize the project in the usual Node workflow, you may still run:
   ```bash
   npm install
   ```
   This will only create local project metadata if needed.

## Getting Started

### Run the quiz

From the `test-app/` directory:

```bash
npm start
```

This runs the application using the configured start script:

```bash
node index.js
```

### Run tests

If you want to execute the Node.js test runner script configured in `package.json`:

```bash
npm test
```

This uses:

```bash
node --test
```

## Usage Examples

### Start the quiz

```bash
cd test-app
npm start
```

### Run the test suite

```bash
cd test-app
npm test
```

### Typical quiz flow

- The app displays a question
- You enter an answer in the terminal
- The app validates the input
- The app shows whether the answer is correct
- An explanation is displayed
- Progress and score are updated
- A final summary is shown at the end

## Configuration

### `package.json`

Key configuration values:

- **Name:** `quiz-cli`
- **Version:** `1.0.0`
- **Description:** `An interactive command-line quiz game for learning JavaScript`
- **Module system:** ES modules (`"type": "module"`)
- **Start script:** `node index.js`
- **Test script:** `node --test`
- **Engine requirement:** Node.js `>=18.0.0`
- **License:** MIT

### Question data

The quiz content is stored in:

```text
test-app/data/questions.json
```

This file contains the question bank used by the application, organized into categories such as:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

## Error Handling and Troubleshooting

### Error handling overview

The application includes:

- **Input validation** to handle invalid user responses
- **`try/catch` error handling** to prevent crashes during runtime
- **Graceful CLI behavior** for terminal-based interaction

### Common troubleshooting tips

- **Node version issues**  
  If the app does not run, confirm that your Node.js version is at least `18.0.0`.

- **Running from the wrong directory**  
  The scripts are defined inside `test-app/`, so run `npm start` and `npm test` from that directory.

- **Invalid input during a quiz**  
  The quiz validates answers and prompts appropriately, so re-enter your response if the input is rejected.

## Future Improvements

Potential enhancements for the project could include:

- Additional quiz categories and question sets
- Difficulty levels
- Timed questions
- Persistent high scores
- Randomized answer ordering
- Quiz session statistics
- User-selectable quiz length
- Expanded test coverage for quiz flow and input validation