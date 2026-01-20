# Handwritten Music Recognition System

## System Overview

This system converts handwritten musical notation from scanned PDFs into clean, digital sheet music. The core challenge is resolving ambiguity in handwritten symbols—determining whether a smudged mark is a quarter note or half note, distinguishing a sharp from a natural, or identifying note positions on staff lines. The system uses AI techniques to interpret ambiguous symbols, validate musical correctness, and produce polished output. This theme naturally engages multiple AI approaches: search algorithms explore interpretation possibilities, constraint satisfaction ensures musical validity, and logical reasoning validates rule compliance. The problem domain requires handling uncertainty, making decisions under ambiguity, and ensuring output correctness—all central AI challenges.

## Modules

### Module 1: Image Preprocessing and Staff Detection

**Topics:** _[To be determined - could be basic image processing or Constraint Satisfaction for staff line detection]_

**Input:** PDF file containing scanned handwritten music notation

**Output:** Preprocessed image with detected staff lines, including coordinates of each staff line and measure boundaries

**Integration:** Provides structured image data to Module 2 for symbol detection. Staff line positions are critical for determining note pitches in later modules.

**Prerequisites:** Basic image processing concepts

---

### Module 2: Symbol Detection and Initial Classification

**Topics:** _[To be determined - could involve pattern recognition or basic classification]_

**Input:** Preprocessed image with staff line coordinates from Module 1

**Output:** List of detected symbol regions, each with: bounding box coordinates, initial classification candidates (e.g., "quarter note (confidence: 0.7), half note (confidence: 0.3)"), and position relative to staff lines

**Integration:** Provides ambiguous symbol candidates to Module 3, which will resolve the ambiguity using search algorithms.

**Prerequisites:** Module 1, basic pattern recognition concepts

---

### Module 3: Ambiguous Symbol Interpretation Using Search

**Topics:** Search (Beam Search, A*)

**Input:** List of ambiguous symbol candidates from Module 2, where each symbol has multiple possible interpretations with confidence scores

**Output:** Single best interpretation sequence for all symbols, where each symbol is assigned a definitive classification (e.g., "quarter note on E line") with overall sequence score

**Integration:** Resolves ambiguity from Module 2's initial classifications. Output feeds into Module 4 for time signature validation and Module 5 for final validation.

**Prerequisites:** Module 2, Search algorithms (Beam Search, A*)

---

### Module 4: Time Signature Detection and Validation

**Topics:** _[To be determined - could use Constraint Satisfaction or Propositional Logic]_

**Input:** Interpreted symbol sequence from Module 3, including detected time signature indicators (if visible)

**Output:** Validated time signature for each measure (e.g., "4/4", "3/4") and list of measures that don't match their time signature (for error reporting)

**Integration:** Uses Module 3's interpreted symbols to determine and validate time signatures. Output informs Module 5's validation checks.

**Prerequisites:** Module 3, [topic to be determined]

---

### Module 5: Musical Validity Validation

**Topics:** Constraint Satisfaction or Propositional Logic

**Input:** Fully interpreted symbols from Module 3, time signatures from Module 4

**Output:** Validated musical notation with error flags for measures that violate constraints (e.g., measure duration doesn't match time signature, invalid note sequences)

**Integration:** Final validation step before output generation. Ensures musical correctness of Module 3's interpretations using Module 4's time signature information.

**Prerequisites:** Module 3, Module 4, Constraint Satisfaction or Propositional Logic

---

### Module 6: Digital Sheet Music Generation _(optional)_

**Topics:** _[To be determined - could be Planning for layout optimization, or basic output formatting]_

**Input:** Validated musical notation from Module 5

**Output:** Clean digital sheet music in specified format (e.g., MusicXML, LilyPond, or cleaned image)

**Integration:** Final output stage. Takes validated notation and formats it into the desired output format.

**Prerequisites:** Module 5

---

## Feasibility Study

_A timeline showing that each module's prerequisites align with the course schedule. Verify that you are not planning to implement content before it is taught._

| Module | Required Topic(s) | Topic Covered By | Checkpoint Due |
| ------ | ----------------- | ---------------- | -------------- |
| 1      |                   |                  |                |
| 2      |                   |                  |                |
| 3      |                   |                  |                |
| 4      |                   |                  |                |
| 5      |                   |                  |                |
| 6      |                   |                  |                |

## Coverage Rationale

_Brief justification for your choice of topics. Why do these topics fit your theme? What trade-offs did you consider?_
