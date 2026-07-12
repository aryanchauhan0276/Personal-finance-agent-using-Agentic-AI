# Personal Finance Categorizer & Query Agent
A small agentic AI project built with LangChain and Groq that answers questions about personal spending — like "how much did I spend on Rent in 2020?" — and can categorize new transactions on the fly.
# What it does
You ask it a normal question in plain English. It figures out on its own whether it needs to look up numbers from your transaction history, guess a category for something new, or both — then gives you a real answer using actual data, not a guess.
# How it works

 Dataset:
A cleaned personal finance CSV (Date, Category, Amount, Type) with ~1,500 real transactions from 2020–2024.
 Categorization tool: 
Takes a transaction description and classifies it into one of 10 categories (Entertainment, Food & Drink, Health & Fitness, Investment, Other, Rent, Salary, Shopping, Travel, Utilities) using an LLM, with a fallback so it never returns something outside that list.
 Query tool:
Filters the dataset by year, month, category, and type (Income/Expense), and returns the total amount — or a clear "no transactions found" message if nothing matches.
 The agent:
Built with LangChain's create_agent, running on Groq's llama-3.1-8b-instant. It reads your question, decides which tool(s) to call, runs them, and replies in plain language.
