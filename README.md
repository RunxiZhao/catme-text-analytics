# Text Analytics for CATME Peer Evaluation — System Write-Up

> **This is a write-up, not a code release.** The production code for this project is not mine to publish. This repo describes the system, what I built, and the outcome, so reviewers can understand the work without the source.

## What it does and why

CATME is a Purdue-developed platform used at hundreds of universities for team-based peer assessment. Students write self-reflections and peer comments, but instructors get little insight from that free text at scale.

We built an NLP system that classifies that text so instructors and students get AI-driven feedback on reflection and peer evaluation. The system was adopted at 10+ universities.

## What I built

I led a 4-person software engineering team (Head of Software Engineering Team) to design and deploy the system:

- Designed the text classification pipeline in Python and exposed it as a production REST API backend
- Implemented a Support Vector Machine (SVM) classifier for text classification
- Benchmarked the SVM against neural network baselines built in TensorFlow/Keras, and selected the SVM based on results
- Achieved 90% text classification accuracy with the selected model (per project evaluation)

## Prompting / modeling approach

This was a classical ML system, not an LLM prompting system: text preprocessing, feature extraction, then a supervised classifier (SVM), with neural baselines for comparison. Model selection was empirical — we kept the approach that performed best on held-out evaluation, rather than defaulting to the more complex neural model.

## Outcome

- Deployed NLP model adopted across 10+ universities for use within CATME
- Enabled AI-driven self-reflection and peer evaluation feedback that was not previously available from the raw comment text

## What I would do differently now

- Add a small, reproducible public demo on synthetic / public-domain peer comments, so the pipeline can be run without the original private data
- Compare the SVM baseline against a modern transformer / LLM classifier and report precision/recall per class, not just overall accuracy

---

*Author: Runxi (Audrey) Zhao — NYU Tandon, BS Computer Science, May 2026. Role: Head of Software Engineering Team, 4-person team.*
