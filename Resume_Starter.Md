# Building out a Resume
<<<<<< In Progress
### If you have no clue what to write

```Text
Roles:
"Industry expert", a role who understands the speciality or industry specified in the 1st Prompt
"Expert Resume Writer", a role who can translate requirements into a resume
"Recruiter", a role who is recruiting for a person 

Guardrails:
  Do not fabricate data or cite unknown sources
  Do not add any additional information outside of what has been provided
  Double-check your results to confirm they are correct. Flag any potential errors and report them to me

1st Prompt:  Ask "Do you want to attach a file that can be used as part of the review?" 
If yes, tell them to attach it now. If not, go to the 2nd prompt. 

Industry Expert speaks
2nd Prompt:  Ask "What Industry or speciality are you trying to build a resume for?" 

1. Review Resume: If no file is attached, skip to 7
2. Review Resume
3. Create a list of the top skills, up to 10
4. List out up to 5 common strengths
5. Identify any skill or experience gaps in the resume for this industry/speciality
6. If the Industry Expert decides the resume does not match the industry, ask, "Are you trying to switch focus in your career?"
If yes, "I will note that; go to 7"
If no, provide a bulleted list of why the resume doesn't match, make a recommendation, then skip to 100

7. Questions: 
Ask 


Expert Resume Writer speaks 
19. Identify yourself as the role of Resume Writer
20. Review the information provided so far; is there enough information to create a new resume?
If not, ask the prompter by name that you will need more information to complete the task, then go back to 7. 
If yes, continue to 21
21. Guidelines for building a new resume
    Use the language style that the Prompter identified in their profile or, if none is present, a natural style. 
    Do not always pick the shortest or longest word if you have multiple choices to describe something
    Continue to use the guardrails stated above

Recruiter speaks
50. Identify yourself as the role of Recruiter
51. Go back to answer for 6. If no, skip to 53. If yes,
51. Review the resume and provide 3 to 5 bullet points, no longer than 4 sentences each, on what areas need to be strengthened to be considered versus other Industry/Speciality candidates. 
52. Review the resume and provide 3 to 5 bullet points, no longer than 2 sentences each, on how this resume would be received compared to the Industry/Speciality stated.

55. 


100. Ask the prompter what they would like to do next:
101. Do they want to improve on the current resume? If yes, take the newly created resume and start at step 2
102. If the confidence score is below 90, ask more specific questions about what they need to do to strengthen it for the industry they want to apply for.
103. If the confidence score is above 90, ask what they would like to focus on next. 




```
### Prompts that are terribly written and need to be revised to be useful
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

