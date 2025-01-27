# LangGraph Stategraph ReadMe

## Overview
This project implements a LangGraph stategraph that dynamically selects between a Retrieval-Augmented Generation (RAG) node and an LLM call node based on a topic selection function. The decision process leverages a conditional edge, a Pydantic parser, and a chain to fetch attributes for determining the appropriate action.

### Key Features
1. **Dynamic Decision Making**:
   - The stategraph evaluates whether to call the RAG function or the LLM call function based on the input topic.

2. **Nodes**:
   - **Agent Node**: The entry point for the stategraph.
   - **RAG Node**: Handles retrieval-augmented generation for relevant topics.
   - **LLM Call Node**: Directly queries a language model for topics not suited for RAG.

3. **Conditional Edge**:
   - Dynamically routes input to either the RAG or LLM node based on the topic selection function.

4. **Pydantic Parser**:
   - Extracts attributes from the input to feed into the decision chain.

---

## Structure
![image](https://github.com/user-attachments/assets/ef5be0fa-e456-4bdc-bcb7-ba739a96c217)

### Nodes
- **Agent Node**: Initiates the process and passes the input to the topic selection function.
- **RAG Node**: Executes a retrieval-augmented generation task.
- **LLM Call Node**: Executes a standard call to the language model.

### Conditional Edge
- Evaluates the topic based on extracted attributes and routes to the appropriate node.

### Topic Selection Function
- A chain function that:
  1. Utilizes a Pydantic parser to extract attributes from the input.
  2. Decides the relevance of the topic for RAG or LLM based on predefined criteria.

---

## Usage
### Running the Stategraph
1. Open the provided Jupyter Notebook (`agent-decide-RAG vs LLM call.ipynb`).
2. Execute the cells step-by-step to:
   - Initialize the nodes and edges.
   - Configure the topic selection function.
   - Run sample inputs through the stategraph.
3. Review the output at each node to verify functionality.




