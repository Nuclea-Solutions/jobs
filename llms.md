# LLMS Challenge

Objective: The challenge involves developing a multi-agent system using LLMs (using [langraph](https://langchain-ai.github.io/langgraph)) to operate as an interactive bot communicating with users via WhatsApp (using [whatsapp-web.js](https://github.com/pedroslopez/whatsapp-web.js)). This system will manage tasks, where each task must have **at least** a name and a date.

**Assistant Capabilities**:

The graph must consist of **at least** three nodes (agents). That work together to handle the various functions of the bot.

**Agent 1: Intention Classifier**

- **Function**: This agent is responsible for identifying the user's intention and directing the interaction to the appropriate agent. It’s essential for deciding whether the user wants to create a task, query existing tasks, or perform another action.
- **Input**: User message.
- **Output**: Redirects to the appropriate agent (Task Creator, Task Consultant, etc.).

**Agent 2: Task Creator**

- **Function**: This agent handles task creation. It should prompt and confirm details such as the task name, date and time. Finally, it saves the task to the database.
- **Input**: Instruction to create a new task (e.g., "Add dentist appointment tomorrow at 2 PM").
- **Output**: Confirmation of the task created and saved to the database.

**Agent 3: Task Consultant**

- **Function**: This agent is responsible for answering user queries about stored tasks. It can display pending tasks filter them by date, etc.
- **Input**: User query about their tasks (e.g., "What tasks do I have pending this week?").
- **Output**: A list of tasks matching the user’s query.


Remember: If you consider it necessary, feel free to add more agents for proper operation, or if you want to add any other functionality, you might need more nodes in the graph.

---

**Language and Technology**: You must use Langraph to coordinate the agents and whatsapp-web.js to communicate with users via WhatsApp.

---

**Data Storage**: All messages and relevant information exchanged with the assistant (such as tasks and their details) should be saved to a database. You can choose any database you prefer (SQL, NoSQL, etc.), but ensure it’s easy to set up and query.

---

**Project Run Instructions**: Provide clear instructions for setting up and running your project, including any dependencies and technologies that need to be installed. Docker is an excellent option to simplify setup and ensure the development environment is consistent for all evaluators.

---

**Demo Video**: Include a video (on Loom or YouTube) that demonstrates your project’s functionality. Make sure to show how the assistant interacts with the user via WhatsApp, performing tasks like creating, querying, and managing tasks.

---

**Hints**
- If this is your first time using LangGraph, it might be a good idea to review LangChain and its ecosystem. The documentation and the community are quite good, and there are plenty of tutorials available on the internet.
- Consider how to integrate both systems, whether through APIs, web services, or local scripts. Python would be ideal for managing Langraph, while JavaScript or Node.js would be best for interacting with WhatsApp.
- There are many LLMs out there that you can run locally [example](https://ollama.com/). Also there are some providers that offers generous [free tier](https://console.groq.com). Or you can use OpenAI, Claude, etc.
- You can use more than one LLM thats the power of Langchain.

---


### Example
This example is the chat with the user. Behind the scenes langgraph and the agents would have many more interactions

```txt
// example 1
user: Agrega ir al dentista para mañana a las 14
bot: Perfecto, tu tarea "ir al dentista" ha sido añadida para 14 de septiembre de 2024 a las 14:00 hrs

// example 2
user: recuerdame comprar leche
bot: agregaré "comprar leche" a la lista, ¿Qué fecha deberia usar?
user: pasado mañana
bot: Entiendo, ¿alguna hora?
user: 2pm
bot: Perfecto, tu tarea "comprar leche" ha sido añadida para 9 de agosto de 2024 a las 14:00 hrs

// example 3
user: Qué tareas pendientes tengo para esta semana
bot: Tienes 3 tareas pendientes: [Listado]

// example 4
user: Cuantas personas hay en el mundo
bot: Esa funcionalidad esta fuera de mis capacidades
```

The examples are demonstrative; the tone and format of the messages may vary. It is important to save the data for tasks in the database.

---

## Bonus

Any other functionality that you believe could enhance your project is welcome, such as:

- Add functionality for users to mark tasks as completed.
- Smart notifications.
- You can add extra fields like priority (high, medium, low), tags, or a more detailed description of the task for advanced task management.
- Allow users to attach files.
- Allow users to use voice messages as input or even as output for increased system flexibility.
- If you feel comfortable, you can add Retrieval-Augmented Generation (RAG) to enhance responses based on data or contextual information (there are many models to generate embeddings).


The above are just suggestions; any other functionality you can think of that might improve the interaction is welcome