# data-architecture-explorer

This repository contains a series of prompt templates designed to help you design the data architecture of various platforms using Generative AI tools like ChatGPT and then create dummy data in Python to experiment with. The prompts guide you through designing the database, writing mermaid.js syntax, improving the design, and generating contextually appropriate dummy data for the platform.

## Prompt Templates

**Prompt 1:**

```
Write Mermaid syntax for an ER diagram for [database].
```
Replace `[database]` with the desired platform or project for which you want to create an ER diagram.

**Prompt 2:**

```
Improve this as a [role].
```
Replace `[role]` with your expertise, such as "senior data scientist" or "database architect", to refine and optimize the initial database design.

**Prompt 3:**
```
Write a Python program that generates [number] [entities] and dummy data based on the ER diagram. Use the OpenAI API to build prompts into the code that creates random but contextually appropriate content. Write the script to ensure that prompts don't produce very similar results.
```
Replace `[number]` with the desired number of entities and `[entities]` with the type of entities (e.g., learners, users, products) for which you want to generate dummy data.

## Sample Prompts

### Online Learning Platform

**Sample Prompt 1:**

```
Write Mermaid syntax for an ER diagram for an online learning platform's database.
```

**Sample Prompt 2:**

```
Improve this as a senior edtech data scientist.
```

**Sample Prompt 3:**

```
Write a python program that generates approximately 100 learners and dummy data based on the ER diagram. Use the OpenAI API to build prompts into the code that creates random but contextually appropriate content. Write the script to ensure that prompts don't produce very similar results.
```

## Usage

This tool is designed to be used with generative text tools like ChatGPT. Simply edit the prompts with your requirements, and the prompt will generate the Mermaid syntax for the ER diagram and Python code for dummy data.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
