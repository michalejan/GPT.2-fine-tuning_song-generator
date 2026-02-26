NLP Song Lyrics Generator 🎶

This repository contains a Google Colab notebook designed to generate rhyming blues song lyrics using a fine-tuned GPT-2 model. It leverages Low-Rank Adaptation (LoRA) for efficient fine-tuning on a specialized dataset.

1. Features
GPT-2 Fine-tuning: Uses the gpt-2 small model as a base.

Efficient Adaptation: Implements LoRA (via the peft library) to train only a small subset of parameters, making it faster and less memory-intensive.

Prompt-Based Generation: Generates lyrics based on specific topics (e.g., romantic, violence, sadness) and emotional "feels" (e.g., energetic, sad, danceable).

Automated Rhyming: Includes logic to search for phonetic rhymes and construct four-line lyric chunks.

Profanity Filtering: Uses the better_profanity library to censor inappropriate content in the final output.

2. Technical Stack
Language: Python

Libraries: transformers, peft, datasets, syllapy, g2p_en, better_profanity

Dataset: A filtered CSV of song lyrics, focused on the blues genre and refined by descriptive keywords.

3. How It Works
Preparation: Installs necessary NLP libraries and loads the base GPT-2 model.

Dataset Processing: Downloads a lyric dataset, filters it for the "blues" genre, and converts rows into formatted prompts.

Training: Applies LoRA configuration to the model and runs the Trainer for several epochs, saving checkpoints to Google Drive.

Inference:

Creates a custom prompt based on a chosen topic and keywords.

Generates a base line of lyrics.

Finds phonetic rhymes from subsequent generated text to build a cohesive verse.

Censors the output for a clean final result.

4. Evaluation

The notebook includes a comparison between the Raw GPT-2 Small model and the Fine-tuned version. While the raw model often produces generic text or unrelated snippets, the fine-tuned model generates structured, genre-appropriate blues lyrics with consistent rhyming schemes.
