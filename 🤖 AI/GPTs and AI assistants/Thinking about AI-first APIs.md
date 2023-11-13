> TL;DR: AI-first APIs are designed as a bridge for AI assistants to interact with other systems, either to gather data or to perform actions on behalf of the user. This text discusses the conceptual design of these APIs, focusing on making them convenient and efficient for chatbots to use. They tackle challenges like identifying specific individuals or items in conversations and include strategies for resolving uncertainties. The goal is to develop APIs that are adaptable, assistant-friendly, and adept at handling complex conversation contexts, ensuring AI assistants can effectively and accurately address user requests across various platforms.

AI-first APIs differ from traditional APIs in that they are used as tools for conversational chatbots. They need to be tailored to primarily natural language based nature of chatbots. The selection of endpoints, data structures and error handling must be tailored to the needs of the chatbot for efficient data retrieval, processing and writing. 

AI assistant chat's with the user and can occasionally call API when it feels that calling API could help fulfill user requests. There is no guarantee that assistant will call specific endpoint at specific time. We need to do as much as we can when designing API to ensure user success (through assistant's success in getting right information or being able or perform right action).

Some fundamental concepts of API design might need rethinking.

API doesn't need to be smart it has to be convenient. It has to be a good tool, a right tool for the job that the assistant is doing.

There is a particular problem for these kinds of APIs. Usually relational data is stored and connected with ids. However ids are meaningless to the user, we need to present them with actual names. In web applications ids are usually stored in frontend state and used to communicate with API, but with assistant there is no such possibility as it doesn't keep strong maps between names and ids in context. Another problem is that names usually don't guarantee uniqueness (while ids do). 
##### Possible solutions: 
- **Clarification Dialogues**: When there is ambiguity in entity names, the assistant can initiate a clarification dialogue. For example, if a user says "Schedule a meeting with John," and there are multiple Johns in the system, the assistant can ask, "Do you mean John Smith or John Doe?"
- **Alias Management**: Allow users to create aliases or tags for frequently referenced entities. These aliases can then be uniquely linked to specific IDs in the backend, simplifying future references.
- **Tagging for Disambiguation**: Implement a tagging system where entities can be tagged with additional descriptors or categories, aiding in disambiguation without relying solely on names.
- **Leveraging Past Interactions**: Analyze past interactions to infer which entity the user is likely referring to. If a user frequently interacts with a particular entity, the assistant can prioritize that entity when a name is mentioned.
- **Incremental Context Building**: Use each interaction to build and refine the context. For example, if a user mentions a name, the system should consider recent topics or previously mentioned items to narrow down the search space.
# Requirements

##### Context Tracking and Management Endpoints
- **Context Initialization**: Endpoints to initiate a new conversational context when a user starts an interaction or some optional parameter that can be filled by assistant to indicate that the value should be saved as context.
- **Context Update**: Endpoints to update the conversational context with each user interaction.  It is important to determine what data is relevant for context updates without overburdening the system with unnecessary information.
- **Context Retrieval**: Endpoints to retrieve the current context in ongoing conversations or some parameter in each response indicating context. This could also include a feature where the context can be retrieved based on certain triggers or conditions within the conversation.
- **Contextual Data Model**: Develop a comprehensive data model that includes not just the immediate user query and AI response, but also additional contextual information like the topic of conversation, sentiment, user preferences, and historical interactions.
- **Context Decay Mechanisms**: Implement context decay algorithms to gradually phase out older context data that may no longer be relevant to the current conversation.
##### Dynamic Content Injection
We cannot push messages to the assistants and we can't make them call specific endpoints as "Get Notifications". We need some way to inform assistants about the updates. We can develop a system within the API that dynamically injects relevant metadata or news into the response based on current events, updates, or specific user interests. It is important to ensure that this injection is seamless and contextually appropriate.

##### Multi-Purpose Endpoints
Design endpoints that can handle multiple types of requests, reducing the need for the assistant to call multiple endpoints for related information. Include options for the assistant to filter the data it needs, allowing for more customized and relevant responses to user queries. Care must be taken to ensure that these endpoints do not become overly complex or difficult to maintain. 

##### Simplified and Direct Access
- **Direct Access Endpoints**: Create endpoints that are straightforward and easy for the assistant to access, reducing the complexity and time needed for data retrieval.
- **Minimalistic Query Requirements**: Design the API to require minimalistic input for queries. The assistant should be able to retrieve relevant information with simple, direct requests.
##### Fallback Mechanisms
Implement fallback mechanisms in endpoints so that if one type of request fails or doesn’t return relevant data, the API can attempt an alternative approach within the same request. The goal here is to always give assistant something to work with.

##### Uniform Resource Naming
Adopt a consistent and intuitive naming convention for endpoints, resources, and methods, making the API predictable and easy to understand.

##### Standard Response Formats
Use uniform and predictable formats for all API responses, ensuring that the assistant can easily parse and understand the data.

##### Token-Based Authorization
Use token-based authorization methods where the user’s identity and permissions are encapsulated in a secure token, which the assistant uses to make requests on behalf of the user. Token should be revokable and user should be informed not to share it with anyone.

##### Error Messaging in Plain Language
Instead of technical jargon or error codes, design the API to return error messages in plain, understandable language. For example, "Sorry, I couldn’t find the information you asked for. Can you please rephrase your question or ask something else?"

##### Helpful Guidance on Failures
In case of failures or errors, include suggestions or guidance in the response to help the user or the assistant rectify the issue or explore alternative queries.

##### Cross-Platform Compatibility
Ensure the API is compatible with various AI assistant platforms and can be easily integrated into different systems.

