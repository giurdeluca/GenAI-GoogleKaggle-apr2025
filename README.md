# The Ass1stant D — A Meal Assistant for T1D Teens

This repo contains the project (blog and code) I submitted for [GenAI Intensive Course Capstone 2025Q1](https://www.kaggle.com/competitions/gen-ai-intensive-course-capstone-2025q1).  
Submitted [Kaggle notebook](https://www.kaggle.com/code/giuraffdeluca/the-ass1stant-d-meal-assistant-for-t1d-patients).

## Overview

The Ass1stant D is a meal-planning assistant designed for people living with T1D. It doesn’t just suggest “healthy meals”—it considers glycemic load, fiber, insulin dosing, and the kind of questions a patient might ask. It aims to talk like a friend who understands their biology.

Technically, it’s an agent-powered RAG pipeline backed by nutritional advice and custom logic for T1D-specific analysis. But behind the tech, it’s simply trying to answer: “What can I eat that won’t spike my glucose later?”

## What it does

- Takes in a user profile: age, weight, insulin plan, etc.
- Parses food input (from ingredients or meals) and scores it for glycemic impact
- Suggests alternatives or confirms good choices
- Explains the reasoning in plain language

## (Some) GenAI techniques used

1. **Agents:** A multi-turn agent that uses reasoning and tools to walk through carb scoring, substitutions, and explanations.
2. **RAG:** Provides grounded answers using vector search over USDA data and hand-picked diabetes-safe recipes.
3. **Function Calling:** Offloads nutrition analysis, insulin ratio math, and glycemic estimation to Python functions.

## Example outputs
### Sample data
![image](https://github.com/user-attachments/assets/7c63cbcf-c26f-4e75-ac19-aef724d14d63)

### Recipe recommendation
![image](https://github.com/user-attachments/assets/8a9e05f7-513c-4243-b703-6895fb45314f)

### Recipes analysis
![recipe_analysis](https://github.com/user-attachments/assets/d022afee-7631-43b1-8662-991da69c3533)

![nutritional_analysis](https://github.com/user-attachments/assets/4a4cde8e-73c3-4f9d-a926-999802666391)


## Limitations

- This is just an MVP. Right now, document chunks are manually selected and injected into the vector store.
- It's not a medical device and cannot replace a clinician or registered dietitian.
- Ingredient parsing and matching are simplistic for now.
- It assumes accurate and honest input from the user.

## What’s next

- [ ] Add a carb estimator module that leverages object recognition and is based on medical checked tables for counting.
- [ ] Replace the hand-curated chunks with a full medical knowledge base—parsed, embedded, and queried with LangChain.
- [ ] Integrate CGM APIs for feedback loops based on real glucose response.
- [ ] Expose the assistant via a chat UI (and maybe voice) to make it more accessible.
- [ ] Add a caregiver view for shared decision-making.

