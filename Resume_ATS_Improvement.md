# Rewrite a resume for better ATS Results

## Run this prompt with your Resume and Job Description to help enhance your resume for applications

#### Prepare 2 files before starting, one that includes the title "Resume" and the other that includes the title "Job"
#### Recommend after completing your resume, you check it for watermarks (https://github.com/ptop20/Prompt_Examples/blob/main/Check_for_Watermarks.md)

```text
Role: A high-level recruiter and editor with a strong understanding of optimizing resumes for ATS scoring

Task: Review a resume against a job description to see how likely it would pass an initial ATS scoring and 1st round of reviews

Inputs:
- Job posting will be provided in <job_description></job_description> tags
- Resume will be provided in <resume></resume> tags
- If either is missing, truncated, or incomplete, say so explicitly rather than inferring missing content

Before starting the instructions: Ask the user, "Who is the intended audience or company for this resume?" and "If the ATS system known"?

Instructions:
- Compare the documents, then review for commonality in this order:
  - Details
  - Qualifications
  - Skills
  - Soft Skill Traits
  
- Based on the comparison, determine the ATS Score. 
    - Check the web to determine if the company has stated what ATS it uses. If so, use the known weighted average for that system. If not, use what is stated in the output. 
- Determine the top skills/requirements in the job description and compare each to the resume
- Identify acronyms in either document and determine whether they map to a stated requirement; flag any that are ambiguous or unmapped
- Treat clear synonyms or abbreviations (e.g., "JS" vs "JavaScript," "PM" vs "Product Manager") as partial matches, and note them separately from exact matches
- Check the resume for ATS parseability issues: tables, columns, text boxes, images, headers/footers, non-standard fonts, or other formatting that could cause parsing errors
- Based on what you know about the hiring company, do an analysis to find key strengths and weaknesses in the resume that could enhance the results
- Do a second pass and refine the analysis for accuracy before finalizing output

Clarification: 
- Ask questions during the review if you are unclear about any part of the instructions

Guardrails:
- Do not invent facts or add any assumptions to either document
- If the job posting or resume text is truncated/incomplete, say so rather than inferring missing content
- If uncertain, say “Uncertain” and bound the claim.
- Flag any assumptions explicitly

Scoring:
- Produce an overall ATS Score from 0–100 (100 = best match)
- Use a known platform-specific weighting if the ATS platform is known and its weighting behavior is well-established; otherwise default to:
  - Skills: 40%
  - Qualifications: 30%
  - Keywords/Details: 20%
  - Soft Skills/Formatting: 10%
- State which weighting was used and why

Output:
- Overall summary with the ATS Score and weighting method used
- Matches and misses for Details, Qualifications, Skills, Soft Skills Traits
- Assumed required or knockout attributes
- Note which of the top skills have explicit evidence provided in the "Resume" document
- Note which of the top skills do NOT have explicit evidence provided in the "Resume" document
- List of the top 5 keywords
- 5 recommendations to improve the resume, each labeled as based on: (a) job posting text, or (b) inferred company/platform knowledge

Format:
- Create a section with bullet points for each output
- Keep each section to under 1000 words each

After providing the output, ask the user: "Would you like me to (a) clarify anything, or (b) revise the analysis based on your feedback?"
```

## In the SAME Session, run this prompt to request an updated resume based on the results

#### This prompt will use the provided Job and Resume provided in the last prompt

```text
Role: A high-level recruiter and editor with a strong understanding of optimizing resumes for ATS scoring

Task: Take the previous prompt's results and rebuild the "Resume" to create an improved chance of a higher ATS score and passing the 1st review

Instructions:
- Resumes cannot be longer than 2 printed 8"x11" pages using standard font and font size of 12. 
- Take the results from the previous prompt
- Use the "Resume" file
  - Revise the resume to provide a better ATS Score based on industry standards
  - Create a second version using the improved resume; update it so it matches the identified company's preferred language and style (if not known, ask a clarification question)

- Using the same method from the previous prompt:
- For both generated resumes, determine the ATS Scorecard it would most likely generate
- Review each draft and do a refinement pass to make any possible improvements. 
- Based on the revised resumes, determine the ATS Scorecard it would most likely generate

Clarification: 
- Ask questions during the review if you are unclear about any part of the instructions, including for ATS Style

Scoring:
- Produce an overall ATS Score from 0–100 (100 = best match)
- Use a known platform-specific weighting if the ATS platform is known and its weighting behavior is well-established; otherwise default to:
  - Skills: 40%
  - Qualifications: 30%
  - Keywords/Details: 20%
  - Soft Skills/Formatting: 10%
- State which weighting was used and why

Guardrails:
- You may reword, reorganize, and incorporate keywords from the job posting only where they reflect experience already present in the original resume. Do not add skills, tools, titles, metrics, or experience   not evidenced in the original resume.
- Do not add in related job search results to this analysis
- Flag any assumptions explicitly
- Any keyword or phrase added that wasn't in the original resume must be marked inline (e.g., [added: X]) or listed separately under 'Insertions for review.

Output:
- Updated Resume in an accepted ATS style, and the Resume rewritten in an ATS-approved way in the provided audience's style
- Summary of the ATS scores of the two new resumes compared to the Resume in the previous prompt
- Bullet List of the top 5 keywords
- 5 Bullet points of potential improvements for the resume

After providing the output, ask the user: "Would you like me to (a) clarify anything, or (b) revise the resumes based on your feedback?"
