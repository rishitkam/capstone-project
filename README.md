Template for creating and submitting MAT496 capstone project.

# Overview of MAT496

In this course, we have primarily learned Langgraph. This is helpful tool to build apps which can process unstructured `text`, find information we are looking for, and present the format we choose. Some specific topics we have covered are:

- Prompting
- Structured Output 
- Semantic Search
- Retreaval Augmented Generation (RAG)
- Tool calling LLMs & MCP
- Langgraph: State, Nodes, Graph

We also learned that Langsmith is a nice tool for debugging Langgraph codes.

------

# Capstone Project objective

The first purpose of the capstone project is to give a chance to revise all the major above listed topics. The second purpose of the capstone is to show your creativity. Think about all the problems which you can not have solved earlier, but are not possible to solve with the concepts learned in this course. For example, We can use LLM to analyse all kinds of news: sports news, financial news, political news. Another example, we can use LLMs to build a legal assistant. Pretty much anything which requires lots of reading, can be outsourced to LLMs. Let your imagination run free.



-------------------------

# Project report Template

## Title: Privacy Policy Analyzer

## Overview

This tool reads any privacy policy or terms-of-service text and instantly tells you the important stuff like what data the service collects, who they share it with, what permissions are risky, how long they keep data, and whether there are any obvious compliance or privacy-red-flag issues. You paste or upload a policy (PDF/text), and it returns a clean, easy-to-scan JSON report plus a plain-English summary and quick suggestions for users.

It’s built to be practical: not a legal opinion, just a fast, structured way to understand the privacy tradeoffs so people don’t have to slog through pages of legalese.
## Reason for picking up this project

I picked this project because it’s something that actually solves a real problem — nobody reads privacy policies, and most of them hide shady data collection or confusing wording. Instead of pretending to read 20 pages of legal text, this tool can instantly show the important parts, highlight risks, and tell you what’s going on in a simple way.

This project lines up with everything we learned in this course. The core of the Privacy Policy Analyzer is about taking unstructured, messy legal text and turning it into clean, structured information which directly uses prompting, JSON structured outputs, and controlled generation. The policy text is chunked and embedded so we can run semantic search and retrieval, which covers RAG, embeddings, chunking, and retrieval concepts we studied. Each stage of the pipeline works like a node in a LangGraph-style workflow, passing state forward step by step, exactly like the “nodes, state, graph” idea from class. The analyzer also uses tool like components such as a “risk classifier,” “permissions extractor,” or “summary generator,”. We can store user privacy preferences (for example, how sensitive they are about location or camera access), which naturally demonstrates stateful memory. The debugging and tracing ideas from LangSmith also apply cleanly here because the pipeline is easy to inspect and track. Basically, every major concept — prompting, structured output, semantic search, embeddings, RAG, tool-calling, node-based workflow, state, memory, evaluation — fits neatly into this one project.

## Plan

I plan to excecute these steps to complete my project.

- [DONE] Step 1 : Set up the Core infrastructure, which involves Project foundation with all dependencies, environment and Api config.
- [TODO] Step 2 : Setup Visualising and monitoring by adding tracing through Langsmith/LangGraph
- [TODO] Step 3 : Creating data models for policy analysis
- [TODO] Step 4 : Set up the document processing,including the text chunking system, vector store with FAISS, and pdf processing
- [TODO] Step 5 : Set up RAG & Vector Search, enable the AI to search the document for specific clauses.
- [TODO] Step 6 : Set up the AI Engine which includes, LLM integration with structured output, and prompt templates
- [TODO] Step 7 : build the reputation system by adding a tavily integration tool and building an advanced/enhanced analyser.
- [TODO] Step 8 : Define the langgraph nodes, and compile them to make the langgraph and display the graph strucute using mermaid.
- [TODO] Step 9 : Define the Main analyzer, which includes the core analyser and the result formatting system
- [TODO] Step 10 : Setup a UI interface, using gradio,  where user can upload the pdf/ copy paste the text to demonstrate the bot and host it


## Conclusion:

I had planned to achieve {this this}. I think I have/have-not achieved the conclusion satisfactorily. The reason for your satisfaction/unsatisfaction.

----------

# Added instructions:

- This is a `solo assignment`. Each of you will work alone. You are free to talk, discuss with chatgpt, but you are responsible for what you submit. Some students may be called for viva. You should be able to each and every line of work submitted by you.

- `commit` History maintenance.
  - Fork this respository and build on top of that.
  - For every step in your plan, there has to be a commit.
  - Change [TODO] to [DONE] in the plan, before you commit after that step. 
  - The commit history should show decent amount of work spread into minimum two dates. 
  - **All the commits done in one day will be rejected**. Even if you are capable of doing the whole thing in one day, refine it in two days.  
 
 - Deadline: Nov 30, Sunday 11:59 pm


# Grading: total 25 marks

- Coverage of most of topics in this class: 20
- Creativity: 5
  
