# Project 1: Zero-Shot & Few-Shot Data Extraction using Prompt Engineering

## Project Overview

This project demonstrates how Prompt Engineering can transform messy, unstructured text into structured JSON output. The prompt follows deterministic prompting techniques by using clear instructions, delimiters, and few-shot examples to ensure consistent and accurate results.

---

## Objective

Design a prompt that:

- Extracts Name, Email, Phone, and City from unstructured text.
- Uses delimiters (`"""`) to separate instructions from input.
- Includes few-shot examples.
- Returns only valid JSON.
- Uses `null` for missing fields.
- Produces deterministic output.

---

## Concepts Used

- Zero-Shot Prompting
- Few-Shot Prompting
- Delimiters
- JSON Formatting
- Deterministic Prompting
- Temperature = 0

---

# Master Prompt

```text
You are an expert Data Extraction AI.

Rules:

1. Extract only these fields:
   - name
   - email
   - phone
   - city

2. Return ONLY valid JSON.

3. Do NOT include explanations, greetings, markdown, or extra text.

4. If any field is missing, return null.

5. Preserve all values exactly as provided.

6. Output must contain exactly these keys:
   - name
   - email
   - phone
   - city

Example 1

Input:

"""
Zara Sabri
Email: zarasabri572@gmail.com
Phone: 0327 6572000
City: Kasur
"""

Output:

{
  "name": "Zara Sabri",
  "email": "zarasabri572@gmail.com",
  "phone": "0327 6572000",
  "city": "Kasur"
}

Example 2

Input:

"""
Zareen Sabri
Phone: 0328 6572000
City: Kasur
"""

Output:

{
  "name": "Zareen Sabri",
  "email": null,
  "phone": "0328 6572000",
  "city": "Kasur"
}

Example 3

Input:

"""
Zakki Hassan Sabri
Email: zakkihsabri@gmail.com
"""

Output:

{
  "name": "Zakki Hassan Sabri",
  "email": "zakkihsabri@gmail.com",
  "phone": null,
  "city": null
}

Now process the following input.

Input:

"""
Zara Sabri
Email: zarasabri572@gmail.com
Phone: 0327 6572000
City: Kasur
"""
```

---

## Expected Output

```json
{
  "name": "Zara Sabri",
  "email": "zarasabri572@gmail.com",
  "phone": "0327 6572000",
  "city": "Kasur"
}
```

---

## Temperature

```
Temperature = 0
```

Using Temperature = 0 ensures deterministic, consistent, and reliable JSON output.

---

## Technologies Used

- ChatGPT
- Prompt Engineering
- JSON
- Markdown

---

## Conclusion

This project successfully demonstrates Zero-Shot and Few-Shot Prompt Engineering techniques for extracting structured information from unstructured text. The use of delimiters, strict instructions, and multiple examples ensures deterministic and accurate JSON output suitable for automation systems.
