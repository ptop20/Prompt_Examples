# Review YouTube Videos

## 1 - This prompt will break a YouTube video into highlights and parts

### If the video is on YouTube, use Gemini because it connects directly
### If you are on Claude or OpenAI, you will need to access YouTube videos via a connector like TubeAlfred. Otherwise, you'll receive a 429 error (not accessible).

```Text
Input: (Add YouTube Video here)

Before starting, check whether you can actually view or transcribe the video. If you cannot access it directly, say "I can not access YouTube" and end the prompt.

Role: You are reviewing a video (linked or uploaded) and producing a structured, fact-checked analysis.

Task: 
Watch or review the video content first. Note its length, since that determines the output length (see below).
Review and verify content 
If web or Internet access is available, use other sources to add information. 
If not accessible, note that.
Length: 1000 words or less if the video is under 15 minutes, 1250 words or less if it's longer.
Finalize content

Guardrails:
Review content and ensure there are no errors, contradictions, or unverified information
Do not fabricate data or cite unknown sources

Output:
Overview – Premise, Tone, and Nuance of the video.  
List devices or items discussed; provide a bullet-list description of each item
List any people mentioned; provide a short description of each person
Flag any assumptions or unclear information, and create a bullet-point list at the end for my review
Flag missing prerequisites explicitly
Flag any AI-created content that you can identify
Provide sources at the end for any additional information outside of what has been provided that was used to provide context
Confidence Assessment – rate your confidence as High, Medium, or Low for each major claim and for the review overall, with a one-line reason for each rating (avoid numeric scores, they imply false precision).
Ask if there is follow-up required on any item identified in the output
```

## 2 - This prompt reviews a video to determine accuracy

### If the video is on YouTube, use Gemini because it connects directly
### If you are on Claude or OpenAI, you will need to access YouTube videos via a connector like TubeAlfred. Otherwise, you'll receive a 429 error (not accessible).

```Text
Role: You are reviewing a video (linked or uploaded) and producing a structured, fact-checked analysis.

Request Input: If no link or file is available, say "Please add video to be reviewed now"

Step 1: Confirm access
Before starting, check whether you can actually view or transcribe the video. If you cannot access it directly, stop and ask me for a transcript, description, or key points instead of guessing at content.

Step 2: Gather information
Watch or review the video content first. Note its length, since that determines the output length (see below).

Step 3: Draft, then verify

Create a first-pass draft of the review.
If you have web search or browsing available, use it to verify claims made in the video and add relevant context. If you do not have that capability, do not guess or invent sources. Instead, mark those claims as unverified.
Revise the draft into a final version based on that check.

Step 4: Write the review
Length: 700 words or less if the video is under 15 minutes, 1000 words or less if it's longer.

Structure the output in this exact order:

Overview – Premise, Tone, and Nuance of the video.
Items/Devices (if applicable) – bullet-point description of each item or device discussed, plus a critical review of the claims made about it.
People (if applicable) – short description of each person mentioned, plus a critical review of the claims made about or by them.
Critical Review – overall assessment of the accuracy of claims made in the video.
Assumptions and Unclear Information – bullet list of anything you had to assume or couldn't confirm.
AI-Generated Content Flags – note if any part of the video appears AI-generated.
Missing Prerequisites – flag anything needed to fully evaluate the video that wasn't provided (e.g., missing context, earlier parts of a series).
Sources – list anything used to verify claims, including outside information not in the original video.
Confidence Assessment – rate your confidence as High, Medium, or Low for each major claim and for the review overall, with a one-line reason for each rating (avoid numeric scores, they imply false precision).
Follow-up Question – ask me if I want deeper review on any specific item flagged above.

Rules:

Do not fabricate data, quotes, or sources.
Do not present unverified claims as fact.
If something can't be confirmed, say so directly rather than smoothing it over.
```
