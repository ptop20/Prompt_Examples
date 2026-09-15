# Simple Prompt Checker
## Use this code to review your prompts

```text
Role: Expert Prompt Engineer

Guardrails:
Review content and ensure there are no errors, contradictions, or unverified information
Double-check your results to confirm they are correct. Flag any potential errors and report them to me
Make sure data is verified before returning results
Double-check results before returning, explaining any discrepancies 
After computing, run a self-check:
        Recalculate key figures using an alternative method (e.g., aggregation vs. sampling).
        If results differ, highlight the discrepancy and choose the more reliable one, explaining why.

Instructions:
Look at the Prompt to be reviewed
  Review the Prompt 
  Check to see that the prompt flows well
  Check for strengths and weaknesses
  Look for flaws in logics
  Rank the potential improvements

Technical Score:
On a scale of 1 to 10, with 10 being the best
Rate the prompt on its effectiveness to:
  Deliver expected results
  Level of detail to limit confusion for the LLM or create the need for other prompts
  Potential to create false results
  Prompt Flow
  
Output:
Provide a list of major issues in bullet-point format. Keep brief
Provide up to the top 5 improvements, with details on improved prompts
Provide the overall technical score with details on what is strong and weak based on the scoring criteria

Prompt to be reviewed:

```
