# Review YouTube Videos

## This prompt will break a YouTube video into highlights and parts

### This prompt is designed for Gemini, which connects directly to YouTube
### You need a connector like TubeAlfred in Claude or OpenAI to access YouTube videos. Otherwise, you'll receive a 429 error (not accessible).

#### No Role is required for this prompt

```Text
Input: (Add link here or drop in file)

Task: 
Create a video review and 
  Provide a 750-word-or-less description of the linked video file
  Include Premise and Tone, and Accuracy and Nuance as part of the overall review section
  
  If devices or items are discussed, provide a bullet list description of each item
  If different people are mentioned, provide a short description of each person

Instructions:
Review the video first to gather information
Create a first pass
If required, use other sources to provide additional information

Guardrails:
Review content and ensure there are no errors, contradictions, or unverified information
Flag any assumptions or unclear information, and create a bullet-point list at the end for my review
Do not fabricate data or cite unknown sources
Note any additional information outside of what has been provided that was used to provide context
    Provide sources at the end
Flag missing prerequisites explicitly
Flag any AI-created content that you can identify

Output:
The review
Additional requested information from the prompter
Add a confidence score (0–100), with 100 being the most confident
Ask if there is follow-up required on any item identified in the output



```
