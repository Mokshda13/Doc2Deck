

# Doc2Deck

**Doc2Deck** is an AI-powered document-to-presentation pipeline that automates the conversion of unstructured Microsoft Word documents into structured, professionally formatted PowerPoint slides. Designed for analysts, consultants, educators, and business professionals, it streamlines the traditionally manual and repetitive slide creation process using modern language models and document parsers.

## Key Features

* **Structured Extraction**: Parses .docx files to extract paragraphs, images, and tables using LlamaParse.
* **LLM-Driven Slide Generation**: Generates titles, bullet points, and layout suggestions via Claude and GPT APIs.
* **Intelligent Image Mapping**: Uses captioning and similarity scoring to associate images with relevant slide content.
* **Table Rendering Support**: Extracts and formats structured and Markdown-style tables into PowerPoint slides.
* **Design Consistency**: Maintains uniform fonts, spacing, and visual hierarchy using a predefined template.
* **Pipeline Orchestration**: Modular code for parsing, prompt generation, layout logic, and output rendering.
* **Error Handling & Logging**: Includes fallback logic for API failures, schema mismatches, and layout inconsistencies.

## How It Works

1. **Document Parsing**

   * Extracts text, images, and tables from Word documents using LlamaParse.
   * Renames visual assets using contextual metadata for traceability.

2. **Topic-Aware Chunking**

   * GPT-based segmentation divides text into semantically coherent sections for slide generation.

3. **Content Enrichment**

   * Structured slide JSON is generated using Claude or GPT-4 based on each text chunk.
   * A refinement pass corrects formatting and ensures consistency.

4. **Image Captioning and Mapping**

   * GPT-4 Turbo generates captions for each image.
   * Semantic similarity scores match captions with slide text for intelligent placement.

5. **Table Insertion**

   * Tables are rendered with dynamic sizing, bolded headers, and layout adaptations.
   * Supports fallback Markdown parsing when structured tables are missing.

6. **PowerPoint Rendering**

   * Generates slides with python-pptx using the enriched JSON.
   * Final slides include text, visuals, and a custom “Thank You” slide.

## Technology Stack

* **Python 3.10+**
* **LlamaParse (LlamaIndex API)** – Document parsing
* **Claude (Anthropic API)** – Slide generation and enrichment
* **GPT-4 / GPT-4 Turbo (OpenAI API)** – Topic chunking, image captioning, and layout refinement
* **python-docx** – Legacy Word parsing
* **python-pptx** – PowerPoint file generation
* **FuzzyWuzzy / difflib** – Similarity scoring for redundancy checks and image mapping


## Known Challenges

* JSON format inconsistencies from LLMs
* Image-slide mismatches due to poor caption relevance
* Table layout instability with wide or complex structures
* API rate limits and token constraints on long documents

## Future Roadmap

* Interactive web-based presentation exports
* Embedding-based visual mapping
* Diagram generation via Mermaid or Graphviz
* Enterprise-grade testing and CI/CD integration

## Contributors

* Deepak Saini – [saini50@purdue.edu](mailto:saini50@purdue.edu)
* Mokshda Sharma – [sharm879@purdue.edu](mailto:sharm879@purdue.edu)

