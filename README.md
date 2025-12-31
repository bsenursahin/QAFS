# QAFS (Quiz App For School)

QAFS is a native Android application developed to facilitate English vocabulary practice for primary school students. The project focuses on interactive learning through category-based quizzes covering Numbers, Colors, and Animals.

**Note:** This project was developed as part of the "Mobile Systems" undergraduate coursework. The primary objective was to implement native Android architecture patterns, manage the Activity lifecycle, and optimize resource usage without external database dependencies.

## Project Overview

The application provides a straightforward user interface where students can select a topic and answer multiple-choice questions. The system evaluates answers in real-time, providing immediate visual feedback and tracking the user's score throughout the session.

## Technical Implementation

This project demonstrates fundamental software engineering concepts within the Android ecosystem, focusing on algorithm design and state management.

### 1. Data Management & Parsing
To maintain a lightweight footprint, the application utilizes **Android String Resources** instead of a heavy local database (SQLite/Room).
* **Implementation:** Vocabulary data is stored in `strings.xml` arrays in a raw format (e.g., `Turkish-English`).
* **Runtime Parsing:** The application parses these string arrays at runtime, splitting the data to separate the question (Source Language) from the answer (Target Language).

### 2. Randomized Distractor Algorithm
A custom algorithm was implemented to generate multiple-choice options dynamically.
* **Logic:** The system selects one correct answer and generates three "distractor" (wrong) answers.
* **Validation:** A duplicate-check mechanism ensures that the distractors are unique and distinct from the correct answer, preventing logical errors in the quiz options.

### 3. Asynchronous UI Handling
The application manages UI thread operations to enhance user experience.
* **Implementation:** A `Handler` with `postDelayed` is used to introduce a timed delay after an answer is selected. This allows the user to perceive the color-coded feedback (Green/Red) before the UI refreshes for the next question, ensuring a smooth transition.

### 4. Navigation & State Passing
* **Explicit Intents:** Used for secure navigation between the Dashboard (`MainActivity`) and the Quiz Interface (`MainActivity2`).
* **State Management:** Key-value pairs are passed via `Intent` extras to determine the selected category context, allowing a single Activity to serve multiple quiz types (Reusability).

## Technologies & Tools

* **Language:** Java
* **UI Framework:** Android XML Layouts
* **IDE:** Android Studio
* **Build System:** Gradle
* **Architecture Pattern:** MVC (Model-View-Controller)

## Installation & Setup

1. Clone the repository:
   ```bash
   git clone [https://github.com/busenrsahn/QAFS.git](https://github.com/busenrsahn/QAFS.git)



   Buse Nur Şahin

   Linkedin: www.linkedin.com/in/busenursahin
