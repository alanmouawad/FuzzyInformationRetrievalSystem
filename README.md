# Fuzzy Information Retrieval System
An Arabic Information Retrieval desktop app in C# using Fuzzy Logic to rank Word documents on marketing. It features an Arabic stemmer, custom Stop Words filtering (e.g., prepositions), and a smart caching system for instant re-search results. Files are ranked based on title match, term frequency, and proximity to the document's beginning.

### High-Performance Desktop Application for Marketing Document Indexing & Retrieval

## 📌 About the Project
This project is an advanced, high-performance **C# Desktop Application** designed for intelligent Information Retrieval (IR) from Arabic Microsoft Word (.docx) documents specializing in the marketing domain. 

Unlike traditional keyword-matching search engines, this system merges **Arabic Natural Language Processing (NLP)** with a custom **Fuzzy Inference System (FIS)**. It evaluates semantic relevance through approximate reasoning, matching words based on linguistic roots rather than literal text. The system features semantic stop-words filtering, structural text analysis, and an optimized caching engine ensuring sub-millisecond retrieval times for previously queried terms.
## 🚀 Key Features

* **Advanced Arabic Stemming (NLP):** Integrates a morphological analyzer that strips search queries and document content down to their core Arabic roots (e.g., *تسويق*, *مسوّق*, *سوقنا* all map back to the root *س و ق*). This maximizes recall and handles the complex derivational nature of the Arabic language.
* **Fuzzy Inference Engine (FIS):** Instead of binary (Yes/No) matching, the system calculates a dynamic **Relevance Weight (Score)** for each document using 3 key linguistic variables (Fuzzy Inputs):
    1. **Title Match:** Evaluates if the stemmed keyword exists in the document's main title (Full, Partial, or No Match).
    2. **Term Frequency (TF):** Measures the density of the root word within the text (Low, Medium, High).
    3. **Proximity to Beginning:** Measures how close the keyword is to the top of the file (Very Close, Medium, Far), leveraging the fact that abstracts, executive summaries, and introduction headings carry the highest thematic weight.
* **Stop Words & Functional Particles Filter:** Automatically screens queries. If the input is a preposition, article, or particles of negation/accusation (e.g., *لا، كم، لن، لم، في، على*), the system rejects the query and guides the user to input a domain-specific marketing keyword, preventing misleading structural weights.
* **Smart Result Caching:** Implements an in-memory caching system (`O(1)` response time). When a keyword is searched, its calculated and ranked results are cached. Subsequent searches for the same term bypass text parsing and fuzzy calculations completely, drastically reducing CPU overhead.
* **Professional High-Contrast UI:** Built with a clean, high-contrast desktop user interface tailored for fast interaction, robust validation, and ordered results presentation.

---

## 🛠 Tech Stack

* **Language:** C# (.NET Core / .NET Framework)
* **Application Type:** Windows Desktop Application (WPF / WinForms)
* **Document Processing:** OpenXML / DocX or Microsoft Office Interop (for extraction of Word headings and body text)
* **Core Algorithms:** Custom Rule-Based Fuzzy Inference Engine & Arabic Light Stemmer

---

## 📐 System Architecture & Workflow
[ User Input Query ]
│
▼
[ Stop Words Filtering ] ───► (Is Stop Word?) ───► [ Alert: Invalid Query ]
│ (Valid Semantic Word)
▼
[ Arabic Root Stemming ]
│
▼
[ Cache Lookup Check ] ─────► (Hit / Found)  ───► [ Instant O(1) Display ]
│ (Miss / New Root)
▼
[ Read & Parse Word Files ]
│
▼
[ Fuzzy Logic Engine ]
├── 1. Title Match Analytics
├── 2. Term Frequency (TF) Calculation
└── 3. Document Proximity Scoring
│
▼
[ Defuzzification & Ranking ] (Sorted Highest Weight to Lowest)
│
▼
[ Store in Cache + Render to UI ]

