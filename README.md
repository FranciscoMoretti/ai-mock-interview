# 🎯 AI Mock Interview

An AI-powered interview practice platform built with our [Conversational AI SDK](https://www.npmjs.com/package/@11labs/react).

| Select Interview | Call Started | Question Feedback | Overall Feedback |
|------|--------------|----------|------------------|
| ![Home](images/home.png) | ![Call Started](images/call_started.png) | ![Feedback](images/feedback.png) | ![Overall Feedback](images/overall_feedback.png) |

## Prerequisites

- Node.js 16 or higher
- pnpm installed globally
- An [ElevenLabs](https://elevenlabs.io) account
- A [Vercel](https://vercel.com) account

## Setting up the Agent

1. Set-up a Conversational AI agent in ElevenLabs [Guide](https://elevenlabs.io/docs/conversational-ai/docs/agent-setup).
2. Enable overrides in agent Settings => Security => Enable overrides.
3. Add the following client-tools:


   1. name: `triggerName`

   - Description: When the person tells you their name, call this function to store in memory.
   - Parameter 1:
     1. Data type: String
     2. Identifier: name
     3. Description: The name of the user.

   2. name: `triggerQuestionAsked`

   - Description: When you ask a new interview question, call this function.
   - Parameter 1:
     1. Data type: String
     2. Identifier: questionId
     3. Description: A unique identifier for the question (e.g., "q1").
   - Parameter 2:
     1. Data type: String
     2. Identifier: questionText
     3. Description: The full text of the question being asked.

   3. name: `triggerAnswerFeedback`

   - Description: After getting an answer from the user, call this function.
   - Parameter 1:
     1. Data type: String
     2. Identifier: questionId
     3. Description: The ID of the question being answered.
   - Parameter 2:
     1. Data type: String
     2. Identifier: answer
     3. Description: The answer provided by the user.
   - Parameter 3:
     1. Data type: String
     2. Identifier: feedback
     3. Description: Your feedback on the answer.
   - Parameter 4:
     1. Data type: Number
     2. Identifier: score
     3. Description: A score from 1-10 for the answer.
   - Parameter 5:
     1. Data type: Array
     2. Identifier: suggestions
     3. Description: Specific suggestions for improving the answer.
     4. Array items:
        - Data type: String
        - Description: A suggestion for improving the answer.

   4. name: `triggerInterviewComplete`

   - Description: When providing the final assessment, call this function.
   - Parameter 1:
     1. Data type: Number
     2. Identifier: overallScore
     3. Description: The overall interview score (1-10).
   - Parameter 2:
     1. Data type: Array
     2. Identifier: strengths
     3. Description: Key strengths demonstrated during the interview.
     4. Array items:
        - Data type: String
        - Description: A strength demonstrated by the candidate.
   - Parameter 3:
     1. Data type: Array
     2. Identifier: areasForImprovement
     3. Description: Areas where the candidate needs improvement.
     4. Array items:
        - Data type: String
        - Description: An area where the candidate needs improvement.
   - Parameter 4:
     1. Data type: Array
     2. Identifier: nextSteps
     3. Description: Recommended next steps for preparation.
     4. Array items:
        - Data type: String
        - Description: A recommended next step for preparation.


## Setting up the Project

1. `pnpm install`
2. `cp .env.example .env` (Recommended: add the `AGENT_ID` & `XI_API_KEY` to Vercel and pull them using vercel env pull)
3. `pnpm run dev`

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. 