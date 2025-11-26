# AI Query Generation and Evaluation Pipeline

This project contains a set of scripts to generate AI queries, translate them, generate responses using an LLM, and evaluate the responses for safety.

## Project Structure

The project is organized as follows:

- `dataset/`: Directory containing all data files.
  - `build_prompt/`: Contains Excel files used for prompt generation (`aiscenario.xlsx`, `aicos.xlsx`).
  - `queries/`: Contains generated query JSON files (`all_ai_queries.json`, `all_ai_queries_en.json`, `merged_queries.json`).
  - `response/`: Contains generated responses (`responses.json`).
  - `evaluations/`: Contains evaluation results (`evaluation_keywords.json`, `evaluation_llm.json`).
- `create_excel_files.py`: Generates the initial Excel files from hardcoded data.
- `generate_prompts.py`: Generates queries based on the Excel files.
- `translate_queries.py`: Translates the generated queries to English.
- `merge_jsons.py`: Merges all query JSON files.
- `generate_responses.py`: Generates responses for the merged queries (currently using a placeholder LLM).
- `evaluate_keywords.py`: Evaluates responses based on keywords in `warning.txt`.
- `evaluate_llm_safety.py`: Evaluates responses for safety using an LLM (currently using a placeholder).
- `warning.txt`: List of keywords used for keyword-based evaluation.

## Usage

Follow these steps to run the entire pipeline:

### 1. Generate Excel Files
Generate `dataset/build_prompt/aiscenario.xlsx` and `dataset/build_prompt/aicos.xlsx`.
```bash
python3 create_excel_files.py
```

### 2. Generate Queries
Generate `dataset/queries/all_ai_queries.json` based on the Excel files.
```bash
python3 generate_prompts.py
```

### 3. Translate Queries
Translate the queries to English and save to `dataset/queries/all_ai_queries_en.json`.
```bash
python3 translate_queries.py
```

### 4. Merge Queries
Merge all query JSON files in `dataset/queries/` into `dataset/queries/merged_queries.json`.
```bash
python3 merge_jsons.py
```

### 5. Generate Responses
Generate responses for the merged queries and save to `dataset/response/responses.json`.
```bash
python3 generate_responses.py
```

### 6. Evaluate Responses (Keywords)
Evaluate the responses based on keywords in `warning.txt` and save to `dataset/evaluations/evaluation_keywords.json`.
```bash
python3 evaluate_keywords.py
```

### 7. Evaluate Responses (LLM Safety)
Evaluate the responses for safety using an LLM and save to `dataset/evaluations/evaluation_llm.json`.
```bash
python3 evaluate_llm_safety.py
```

## Dependencies

- `pandas`
- `openpyxl`
- `googletrans==4.0.0-rc1`

Install dependencies:
```bash
pip install pandas openpyxl googletrans==4.0.0-rc1
```
