# Retromer Lit Scanner GPT

AI-powered literature review automation tool that reduces scientific literature triage time by 75%.

## Problem

In fast-paced drug discovery research, staying current with scientific literature is critical but time-consuming. This daily grind took mental energy away from actual lab work.

## Solution

An automated tool that uses GPT-4 to extract and organize key findings from scientific literature.

**Input:** Search terms or PubMed IDs  
**Process:** Queries PubMed API → Sends abstracts to GPT-4 → Extracts structured data  
**Output:** Organized summaries with disease area, pathway, intervention, model organism, key findings, and study type

## Technology Stack

- **AI Model:** GPT-4 via OpenAI API
- **Language:** Python 3.9+
- **Data Source:** PubMed API (NCBI Entrez)
- **Development:** Cursor AI for rapid prototyping
- **Key Libraries:** `requests`, `openai`, `json`

## Features

- Structured extraction of key experimental findings
- Standardized output format for easy comparison across papers
- Thematic grouping by mechanism, model system, or therapeutic approach
- Slide-ready tabular format for presentations
- Version history maintained for reproducibility

## Impact

- **Time reduction:** 75% (from 25 hours/week to 6 hours/week for team)
- **Annual savings:** ~950 hours for 5-person team
- **Adoption:** Used daily by entire research team
- **Measured rigorously:** Stopwatch tracking across 10+ sessions

## How It Works

1. User inputs search terms (e.g., "Retromer AND neurodegeneration")
2. Script queries PubMed API for recent papers
3. Abstracts are sent to GPT-4 with structured prompts
4. GPT-4 extracts key fields in JSON format
5. Results are organized and formatted for review
6. Output delivered in ~10 minutes vs 60+ minutes manually

## Key Learning: Prompt Engineering

The hardest part was designing prompts that consistently extracted actionable information. Five iterations were required:

**Iteration 1:** "Summarize this paper" → Vague, generic responses  
**Iteration 5:** "Extract key experimental result with specific metrics" → Consistent, actionable data

This taught me that specificity in prompts dramatically improves AI output quality.

## Installation & Usage
```bash
# Clone repository
git clone https://github.com/[your-username]/retromer-lit-scanner.git

# Install dependencies
pip install -r requirements.txt

# Set OpenAI API key
export OPENAI_API_KEY='your-key-here'

# Run tool
python lit_scanner.py
```

## Example Output
```
Paper: "Retromer deficiency in Alzheimer's disease" (PMID: 12345678)
Disease: Alzheimer's disease
Pathway: Retromer-mediated protein trafficking
Intervention: VPS35 overexpression
Model: APP/PS1 transgenic mice
Key Result: VPS35 overexpression reduced amyloid-beta levels by 40% (p<0.01)
Study Type: In vivo
Relevance: 5/5
```

## Limitations & Design Decisions

- GPT-4 occasionally misinterprets technical terminology
- Solution: Tool includes confidence indicators and links to original text
- Humans validate outputs rather than assuming 100% accuracy
- Designed workflows that leverage AI strengths while accounting for limitations

## Future Improvements

- PDF upload support (currently abstracts only)
- Automated weekly digest emails
- Citation relationship mapping
- Multi-paper synthesis for literature review generation

## Project Context

Built during my work as a research scientist at MD Anderson Cancer Center's Neurodegeneration Consortium. The tool emerged from observing a daily pain point my team faced and using modern AI tools (Cursor AI + GPT-4) to rapidly prototype and deploy a solution.

This project taught me that effective product development requires observing real problems, shipping quickly, measuring impact rigorously, and iterating based on actual usage.

## License

MIT License - feel free to adapt for your own research needs

## Contact

For questions or collaboration: [Your email or LinkedIn]

---

**Note:** This tool was built for internal research use. OpenAI API key required (not included in repository).
```

---

**To add this README:**
1. In your GitHub repo, click "Add file" → "Create new file"
2. Name it `README.md`
3. Paste the markdown above
4. Replace `[your-username]` with your GitHub username
5. Add your contact info at bottom
6. Click "Commit new file"

---

### **STEP 5: Create requirements.txt (2 minutes)**

**Create a file called `requirements.txt` with this content:**
```
openai>=1.0.0
requests>=2.31.0
