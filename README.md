 # structred output for the stream of thoughts
This project uses Groq's LLaMA3-70B model to transform unstructured stream-of-thoughts journal entries into structured .

## What It Does
Given a raw, free-form journal input, this script classifies and organizes the content under the following categories:

Health & Well-being

Family & Relationships

Work Stress

Community & Meaningful Work

Emotional State

Habits & Patterns

Each category includes entries with titles and lists of summarized thoughts. Only relevant categories are included in the output.


## Example
Input:

```vbnet
I barely slept last night. My back hurts again. I miss talking to my sister. I'm dreading the Zoom call tomorrow.
```
Output:
```python
[
  {
    "category": "Health & Well-being",
    "entries": [
      {
        "entry": 1,
        "title": "Sleep & Pain",
        "thoughts": [
          "Had trouble sleeping.",
          "Experienced recurring back pain."
        ]
      }
    ]
  },
  {
    "category": "Family & Relationships",
    "entries": [
      {
        "entry": 1,
        "title": "Missing Family",
        "thoughts": [
          "Misses talking to sister."
        ]
      }
    ]
  },
  {
    "category": "Work Stress",
    "entries": [
      {
        "entry": 1,
        "title": "Zoom Anxiety",
        "thoughts": [
          "Dreading tomorrow's Zoom meeting."
        ]
      }
    ]
  }
]
```

## How It Works
Sets up a Groq LLaMA3-70B chat model.

Sends a system prompt instructing the LLM to return structured, categorized JSON.

Parses and prints the JSON output for clear readability.

Handles JSON formatting issues gracefully.

Install Python
Make sure Python 3.8+ is installed. Check by running:

```bash
python --version
```
Set Up a Virtual Environment (Optional but Recommended)
Create and activate a virtual environment:

Windows:
```bash
python -m venv .venv
.venv\Scripts\activate
```

## setting up the environment 
1. Clone the Repository
```python
git clone https://github.com/vishal320/Structured_json.git
cd Structured_json
```
2. Install Dependencies
```python
pip install groq python-dotenv
```
3. Set Your API Key
Create a .env file in the root directory and add:
```python
GROQ_API_KEY=your_actual_groq_api_key_here
```
4. Run the Program
```python
python main.py
```
Enter your journal-style text when prompted.
## Expected error
 Error code: 400 - {'error': {'message': "Failed to generate JSON. Please adjust your prompt
Why does this happen?
The instructions to the model might be unclear
## How to fix or avoid it?
Simplify and clarify your prompt

## Notes
Make sure your Groq API key is active and has sufficient quota.

The output strictly follows the requested JSON structure—ideal for downstream automation.

