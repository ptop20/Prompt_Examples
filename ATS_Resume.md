# Rewrite a resume for better ATS Results

## Run this prompt with your Resume and Job Description to help enhance your resume for applications

#### Prepare 2 files before starting, one that includes the title "Resume" and the other that includes the title "Job"

```text
Role: A high-level recruiter and editor with a strong understanding of optimizing resumes for ATS scoring

Task: Review a resume against a job description that is more likely to pass an initial ATS scoring and 1st round of reviews

Before starting the instructions: Ask who the intended audience or company will be for this resume

Instructions:
- Compare the documents, then review for commonality in this order:
  - Details
  - Qualifications
  - Skills
  - Personality Traits
- Based on the comparison, determine the ATS Scorecard it would most likely generate based on what you know about the provided audience's ATS system
- Determine the top skills in the "Job" document and compare it to the "Resume" document
- Based on what you know about the hiring company, do an analysis to find key strengths and weaknesses in the resume that could enhance the results

- Do a second pass and make any updates to improve the results

Clarification: 
- Ask questions during the review if you are unclear about any part of the instructions

Guardrails:
- Do not invent facts or add any assumptions to either document
- Do not add in related job search results to this analysis
- If uncertain, say “Uncertain” and bound the claim.
- Flag any assumptions explicitly

Output:
- Overall summary with the assumed ATS Scorecard
- List the matches and misses for Details, Qualifications, Skills, Personality Traits
- List of the assumed required or knockout attributes
- Note which of the top skills have explicit evidence provided in the "Resume" document
- Note which of the top skills do NOT have explicit evidence provided in the "Resume" document
- List of the top 5 keywords
- List of 5 recommendations based on knowledge of the hiring company that could improve the Resume

Format:
- Create a section with bullet points for each output
- Keep each section to under 1000 words each

After providing the output, ask "Did you understand the output?"
"If no, do I need to rerun the prompt?"
If yes to rerun the prompt, delete results and restart from the beginning. 
```

## In the SAME Session, run this prompt to request an updated resume based on the results

#### Prepare 2 files before starting, one that includes the title "Resume" and the other that includes the title "Job"

```text
Role: A high-level recruiter and editor with a strong understanding of optimizing resumes for ATS scoring

Task: Take the previous prompt's results and rebuild the "Resume" to create an improved chance of a higher ATS score and passing the 1st review

Instructions:
- Resumes cannot be longer than 2 printed 8"x11" pages. 
- Take the results from the previous prompt
- Use the "Resume" file to improve the resume to create a resume with a better ATS Score 
- Create a second version, using the improved resume, and update it so it matches the provided audience's from the last prompt preferred style 

- Using the same method from the previous prompt:
- For both generated resumes, determine the ATS Scorecard it would most likely generate based on what you know about the provided audience's ATS system 

- Based on the results, do a second pass and make any updates to improve the results. 
- Based on the revised resumes, determine the ATS Scorecard it would most likely generate based on what you know about the provided audience's ATS system 

Clarification: 
- Ask questions during the review if you are unclear about any part of the instructions

Guardrails:
- Do not invent facts or add any assumptions to either document
- Do not add in related job search results to this analysis
- Flag any assumptions explicitly

Output:
- Updated Resume in an accepted ATS style, and the Resume rewritten in an ATS-approved way in the provided audience's style
- Summary of the ATS scores of the two new resumes compared to the Resume in the previous prompt
- Bullet List of the top 5 keywords
- 5 Bullet points of potential improvements for the resume
