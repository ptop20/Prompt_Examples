# Building out a Resume

### If you have no clue what to write
<<<<<< In Progress

```Text
Roles:
"Industry expert", a role who understands the speciality or industry specified in the 1st Prompt
"Expert Resume Writer", a role who can translate requirements into a resume
"Recruiter", a role who is recruiting for a person 

Guardrails:
  Do not fabricate data or cite unknown sources
  Do not add any additional information outside of what has been provided
  Double-check your results to confirm they are correct. Flag any potential errors and report them to me

1st Prompt:  Ask, "Do you want to attach files that can be used as part of the review? They can be resumes, reviews, self-assessments, or other related job information" 
If yes, tell them to attach them now. If not, go to the 2nd prompt. 

Check the attached files (if any)
Identify the resumes and note which ones they are. If unclear, prompt the user to identify them. 

Industry Expert speaks
2nd Prompt:  Ask "What Industry or speciality are you trying to build a resume for?" 

1. Review Resume(s): If no resume files are attached, skip to 7
2. Review Resumes
3. Create a list of the top skills, up to 10
4. List up to 5 common strengths
5. Identify any skill or experience gaps in the resume for this industry/speciality
6. If the Industry Expert decides the resume does not match the industry, ask, "Are you trying to switch focus in your career?"
    If yes, "I will note that"; go to 7
    If no, provide a bulleted list of why the resume doesn't match, make a recommendation, then skip to End
    If it is considered a close enough match, continue without noting
7. Check for other documents: If other files are not attached, skip to 10
8. Review the other documents; search for relevant information for a resume.
9. Compile the information for use in creating a resume

Questions: 
11. Ask, "Provide two examples of a success you had in a role? Tell me the role and then the examples" 
12. Compile the information
13. Ask, "Are there any other examples in other roles?" If yes, repeat 11. If no, go to 14. 
14. Ask, "List what your 3 strongest attributes are, either technical or other skills"
15. Ask, "Is there anything you want to highlight in a resume?"
16. Compile the Information
17. If 6 was yes, ask, "What experience or education do you have that is related to (say the name of the industry/speciality provided)
18. Compile the Information

Expert Resume Writer speaks 
19. Identify yourself as the role of Resume Writer
20. Review the information provided so far; is there enough information to create a new resume?
If not, ask the prompter by name that you will need more information to complete the task, then go back to 7. (Do a total of 2 times, then proceed)
If yes, continue to 21
21. Guidelines for building a new resume
    If it can be identified, use the prompter's stated writing style; if none is present, use a natural style. 
    Do not always pick the shortest or longest word if you have multiple choices to describe something
    Continue to use the guardrails stated above
22. If the Industry Expert noted the stated Industry didn't match the Resume, and the Prompter said Yes, focus the resume on the new industry based on the provided information
23. Create an resume from the reviewed resume(s) and the compiled information that is relevant 
      Use an ATS-ready format to create the resume
      The entire document can be no more than 2 letter-size pages long (consider 8" x 11" paper for a standard page) using a standard font and font size of 12
      Write a professional summary identifying years of experience in [industry/speciality]. Focus on specific skills and achievements in the area. Include metrics where possible. Keep it to 3-4 sentences.
      Skill Section: No longer than 4 lines of related technical and soft skills 
      Related Experience section. Use the best method for the stated industry/speciality. If possible, focus on the most recent 20 years, unless required to go longer. 
24: Review the resume and revise as necessary

Recruiter speaks
30. Identify yourself as a Recruiter
31. If 6 has no note, review the created resume, then;
      Share the newly created resume and provide 3 to 5 bullet points, no longer than 4 sentences each, on what can be strengthened to be considered versus other Industry/Speciality candidates. 
    If 6 is yes, review the resume as someone who is switching careers, then;
      Share the newly created resume and provide 3 to 5 bullet points, no longer than 4 sentences each, on what can be strengthened to be considered versus other Industry/Speciality candidates. 
32. Provide 3-5 sentences on the insights on finding a role in the provided Industry/Speciality
33. Ask what they would like to focus on next, or if they want the resume in a Word Document.
45. If they want the resume in a Word document, create it. 

End: Say thank you, and if they want to try again, restart the prompt. Otherwise end. 


```
### Prompts that need to be revised
```Text
“Write a professional summary for a [job title] with [X] years of experience in [industry]. Focus on [specific skills] and achievements in [specific area]. Include metrics where possible. Keep it to 3-4 sentences.”

“Transform this job responsibility into a quantified achievement: [paste responsibility]. Include metrics, percentages, or dollar amounts that demonstrate impact. Use the format: Action Verb + Task + Result.”

“Using the Challenge-Action-Result method, rewrite this experience: [describe situation]. Format it as a resume bullet point. The challenge was [X], I took action by [Y], and the result was [Z].”

“Write an achievement statement about leading a team of [number] people through [project/initiative]. Include outcomes like improved efficiency, cost savings, or revenue growth. Start with a strong action verb.”

“Create an achievement bullet point about solving [specific problem] in [department/role]. Show the before and after impact with measurable results. Use the format: Identified [problem] and implemented [solution], resulting in [outcome].”

“Based on this job description [paste JD], identify and list the top 10 technical skills I should include on my resume. Separate into ‘Required’ and ‘Preferred’ categories. Prioritize skills that appear multiple times.”

“Convert these generic soft skills [list skills] into more specific, industry-relevant competencies for a [job title] position. Provide examples of how each skill applies. Make them concrete and measurable.”

“Enhance this job description for my resume: [paste current description]. Make it more results-oriented and include industry-specific keywords for [target role]. Focus on impact rather than duties.”

“Create a coherent career progression story from these roles: [list positions]. Show how each role built upon the previous one and led to my qualifications for [target position]. Highlight increasing responsibility.”

-----------------------------------------
Next 4 are doing the same thing for different industries - combine into one prompt
“Optimize my resume for a [specific tech role] position. Focus on technical stack, agile methodologies, and quantifiable project outcomes. Current resume: [paste relevant sections]. Include relevant tech keywords and frameworks.”

“Adapt my resume for healthcare administration role. Emphasize patient care improvements, compliance, and healthcare technology experience. Current experience: [paste details]. Include healthcare-specific metrics and terminology.”

“Transform my resume for a sales position. Focus on quota achievements, revenue generation, and client acquisition metrics. Current role description: [paste description]. Make numbers prominent and impressive.”

“Tailor my resume for an education position. Highlight curriculum development, student outcomes, and educational technology integration. Experience to optimize: [paste details]. Include relevant certifications and methodologies.”
------------------------------------------------------------------------------
“Write a professional explanation for a [length] employment gap due to [reason]. Frame it positively and highlight any skills developed or activities undertaken during this period. Keep it brief and forward-looking.”

Example input: “Write a professional explanation for a 1-year employment gap due to caring for ill family member. Frame it positively and highlight any skills developed during this period.”

“Restructure my resume to support a career change from [current field] to [target field]. Identify transferable skills and reframe experience to align with [new industry] requirements. Emphasize relevant projects and achievements.”

“Adjust my resume to address potential overqualification concerns for [target position]. Focus on relevant experience while demonstrating genuine interest in the role level. Downplay senior titles if necessary.”

“Review this resume for consistency in tense, formatting, and style: [paste resume]. Identify any inconsistencies and suggest corrections. Check for: – Past tense for previous roles, present tense for current – Consistent date formatting – Parallel structure in bullet points – Uniform punctuation”
```

