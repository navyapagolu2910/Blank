---
name: Developers Assistant
nested_agents:
  - Github Reader
  - Readme Creator
  - Merge Request Creator
orchestrator_instruction: >
  1) Github Reader reads the repository content from the provided repository URL and branch,
  2) Readme Creator generates a complete README.md from that repository information,
  3) Merge Request Creator creates a new branch, commits README.md, and opens a pull request.
---

# Quiz CLI

## Project Overview

Quiz CLI is an interactive command-line quiz game built with Node.js. It lets users choose a category, select how many questions to answer, and receive immediate feedback along with a final score summary.

The application is designed as a learning-focused terminal project and demonstrates core JavaScript and Node.js concepts such as ES modules, async/await, file system access, classes, and user input handling.

> Note: The application source lives in the `test-app/` directory.

## Features

- Interactive terminal-based quiz experience
- Category selection from a JSON question bank
- Choice of quiz length based on available questions
- Randomized question order using a shuffle algorithm
- Immediate correctness feedback after each answer
- Optional question explanations
- Final score summary with performance-based messaging
- Review section for incorrect answers
- Styled terminal output using ANSI colors
- Graceful error handling with readable console output

## Technologies and Tools

- **JavaScript (ES Modules)**
- **Node.js 18+**
- **Built-in Node.js APIs**
  - `node:fs/promises` for loading quiz data
  - `node:path` and `node:url` for resolving file paths in ES modules
  - `node:readline` for interactive terminal input
- **npm** for package management and scripts
- **ANSI escape codes** for terminal text styling

## Project Structure

```text
.
├── README.md
└── test-app/
    ├── index.js
    ├── package.json
    ├── data/
    │   └── questions.json
    └── src/
        ├── colors.js
        ├── input.js
        └── quiz.js
```

### Important Files

- `test-app/index.js` - Application entry point and main game loop
- `test-app/package.json` - Project metadata, scripts, and Node.js engine requirement
- `test-app/data/questions.json` - Quiz categories, questions, answers, and explanations
- `test-app/src/input.js` - Reusable terminal input helpers
- `test-app/src/colors.js` - ANSI color utilities for terminal output
- `test-app/src/quiz.js` - Quiz logic, scoring, progress display, and results output

## Prerequisites

Before running the application, make sure you have:

- **Node.js 18.0.0 or later**
- **npm** (included with Node.js)

## Setup Instructions

1. Clone or download the repository.
2. Open a terminal in the repository root.
3. Change into the application directory:

   ```bash
   cd test-app
   ```

4. Install dependencies:

   ```bash
   npm install
   ```

## Getting Started

### Run the Quiz

From the `test-app/` directory, start the application with:

```bash
npm start
```

This launches the interactive quiz in your terminal.

### Run Tests

The project includes a test script that uses Node's built-in test runner:

```bash
npm test
```

## Usage Examples

### Start the application

```bash
cd test-app
npm start
```

### Typical quiz flow

- Choose a category such as JavaScript Basics, Node.js Fundamentals, or General Programming
- Select how many questions to answer
- Enter the number corresponding to your answer choice
- Review your score and incorrect answers at the end
- Decide whether to play again

### Example interaction

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions
```

## Configuration

### `package.json`

The `test-app/package.json` file defines:

- `start` script: `node index.js`
- `test` script: `node --test`
- `type: module` to enable ES module syntax
- `engines.node: >=18.0.0`

### Quiz Data

All quiz content is stored in `test-app/data/questions.json`. Each category contains:

- A category name
- A list of questions
- Multiple-choice options
- The correct answer index
- Optional explanations

To expand the quiz, add new categories or questions in that file using the same structure.

## Error Handling and Troubleshooting

### Built-in Error Handling

The application wraps startup and execution logic in a `try/catch` block. If something goes wrong, it:

- Prints a readable error message
- Outputs the stack trace for debugging
- Exits with a non-zero status code

### Input Validation

The input helpers validate user selections and keep prompting until a valid option number is entered. This helps prevent crashes caused by invalid menu input.

### Common Troubleshooting Tips

- **`node: command not found`**
  - Install Node.js 18 or later and confirm it is available on your PATH.

- **Invalid module or syntax errors**
  - Make sure you are running the app from `test-app/` and using a supported Node.js version.

- **Questions not loading**
  - Check that `test-app/data/questions.json` exists and contains valid JSON.

## Future Improvements

Potential enhancements for this project include:

- Adding more quiz categories and questions
- Supporting custom quiz creation from the terminal
- Tracking high scores between sessions
- Adding timed questions
- Introducing difficulty levels
- Writing automated tests for quiz logic and input helpers
- Improving accessibility and keyboard navigation
- Persisting results to a local file or database
