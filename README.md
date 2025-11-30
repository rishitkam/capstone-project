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

This tool reads any privacy policy or terms of service text and instantly tells you the important stuff like what data the service collects, who they share it with, what permissions are risky, how long they keep data, and whether there are any obvious compliance or privacy red flag issues. You paste or upload a policy (PDF/text), and it returns a clean,  report plus a plain English summary and quick suggestions for users, along with a summary of the said company's reputation with previous cases of data breaches/respect of user data. on top of the report it gives a one word summary like high risk, low risk etc. It’s basically a practical, fast, and structured way to understand the privacy tradeoffs so people don’t have to slog through pages of legalese. This was the basic idea, 
now I have made a more enriched version of this bot, which uses a multi-agent set up with 4 agents(Data Scout, Risk Officer, Compliance Lawyer, and Reputation Researcher), each to perform different tasks parallelly, (which makes the process quicker) and also I have given users a chat space where user can ask the llm follow up questions on the report and the llm can use both web search tool, or the input context to answer the questions,and it also has a memory so it remembers the conversations,it works like any other professional chatbot all on a nice, aesthetic looking website.
I did keep the simple old versions of this same bot which only gives a simple summary/suggestion as mentioned in the first para, I have tried to make them like a paid and non-paid version of the same thing. The enriched version is built on top of the first bot.

## Reason for picking up this project

I picked this project because it’s something that actually solves a real problem nobody reads privacy policies (I personally have honestly never read one, I just click yes), and most of them hide shady data collection or confusing wording. Instead of pretending to read 20 pages of legal text, this tool can instantly show the important parts, highlight risks, and tell you what’s going on in a simple way.

This project lines up perfectly with everything we learned in this course. I used advanced prompt engineering by giving each agent a dedicated persona (Data Scout, Risk Officer, Compliance Lawyer, and Reputation Researcher), structured output through Pydantic models, and full RAG with embeddings + semantic search to let the model work directly with the PDF. I also used tool calling for the live reputation checks, and LangGraph to build a proper multi-agent workflow with nodes, edges, shared state, and checkpointing. All four agents run in parallel using a map-reduce pattern, and the whole system supports persistent memory so users can chat with the document over time. Basically, the project implements every major technique we covered just combined into one nice system with a nice ui website, and because the workflow is broken into clear nodes, it's easy to debug and trace step-by-step using LangSmith inspection and evaluation exactly like we did for class.


## Plan

I plan to excecute these steps to complete my project.

- [DONE] Step 1 : Set up the Core infrastructure, which involves Project foundation with all dependencies, environment and Api config.
- [DONE] Step 2 : Setup Visualising and monitoring by adding tracing through Langsmith/LangGraph
- [DONE] Step 3 : Creating data models for policy analysis
- [DONE] Step 4 : Set up the document processing,including the text chunking system, vector store with FAISS, and pdf processing
- [DONE] Step 5 : Set up RAG & Vector Search, enable the AI to search the document for specific clauses.
- [DONE] Step 6 : Set up the AI Engine which includes, LLM integration with structured output, and prompt templates
- [DONE] Step 7 : build the reputation system's base by adding a tavily integration web search tool.
- [DONE] Step 8 : Define the langgraph nodes, and compile them to make the langgraph and display the graph strucute using mermaid.
- [TODO] Step 9 : Define the Main analyzer, which includes the core analyser and the result formatting system
- [TODO] Step 10 : Setup a UI interface, using gradio,  where user can upload the pdf/ copy paste the text to demonstrate the bot and host it
- Basic Bot work is finished here, Now I will build on top of it to create an enriched 'premium' version of it, i will create a copy of this simple bot's jupyter notebook and do the following steps in it:
- [TODO] Step 11 : Import all additional libraries
- [TODO] Step 12 : Define the new and upgraded data models for policy analysis, with our new special agents
- [TODO] Step 13 : Initialize Global Tools (VectorStore & Tavily) & LLM beforehand so agents can use them.
- [TODO] Step 14 : Define the new nodes, with refined prompts, and AI experts(in a FanOut/FanIn config) and turn them into a coordinated team where they operate simultaneously within a structured, state-aware architecture
- [TODO] Step 15 : Setup the memory and context logic (to save states and msges)
- [TODO] Step 16 : Update the main PrivacyPolicyAnalyzer class to generate unique thread_ids for every user and handle the Hybrid (RAG + Web) search logic.
- [TODO] Step 17 : Setup the new chatbot window, where the user can have back and forth conversation with our bot related to the policies etc.


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
  
