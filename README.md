# 🧠 Smart Course Selector AI Agent

## Project Architecture

The Course Recommendation System uses a multi-agent architecture to provide personalized academic guidance to students:

### Core Components

**Supervisor Agent:** Central coordinator that orchestrates the entire workflow, receiving user queries and returning finalized responses.
**Decision Agent:** Analyzes user queries to determine their intent (recommendation, inquiry, or clarification needed).
**Specialized Response Agents:**

**Recommendation Agent:** Provides personalized course recommendations based on career goals
**General Inquiry Agent:** Answers specific questions about individual courses
**Clarification Agent:** Helps users articulate their needs when queries are vague


### Database Components
PostgreSQL database with pgvector extension for semantic search

#### Tables include: 
1. Student Profiles
2. Completed Courses
3. and Course Details

### Workflow

Step 1: User submits a query to the Supervisor Agent
Step 2: The Supervisor routes the query to the Decision Agent
Step 3: Decision Agent classifies query intent:
   a. For recommendation requests: System fetches relevant courses using collaborative filetring from the database via semantic search, then passes to Recommendation Agent
   b. For inquiry requests: System fetches specific course details or general queries, then passes to General Inquiry Agent
   c. For clarification needed: Query is passed directly to Clarification Agent
Step 4: Specialized agent processes the query and returns a response
Step 5: Supervisor delivers the finalized response to the user in structurized format

This architecture ensures that each query is handled by the most appropriate agent, providing users with relevant, personalized information while abstracting away the complex backend processes.
