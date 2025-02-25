---
title: Understanding Function Calls in the OpenAI Assistants API
subtitle: What I've learned about function/tool calls in the OpenAI Assistants API
date: 2025-02-21
layout: post
permalink: /post/openai-assistant-function-calls
redirect_from:
    - /openai-assistant-function-calls
---
Are you building with the OpenAI Assistants API and struggling to grasp how tool/function calls work? Here's what I've learned.

TL;DR: function calls change prompt parsing, not runtime behavior.

When you define a function in the Assistants API, you're enhancing prompt parsing, not altering runtime execution. Unlike traditional function calls, where execution happens inline, function calls in the Assistants API work more like callbacks (or native functions in Java, FFIs in Ruby, NIFs in Erlang, etc.).

Here's how it works:

1. The Assistant Determines the Need for a Function Call
- Based on your function definition and the natural language of a prompt, the assistant decides whether a function needs to be invoked.
- The assistant does not execute the function itself. Instead, it signals that it requires external input.
2. You Handle the Function Call Externally
- The assistant enters a special waiting state called `requires_action` that indicates the "callback."
- While in this state, you can inspect the assistant's run to find the function name it is awaiting and parameters it has extracted from the prompt.
- This all happens on the API client side.
3. Executing the Function and Injecting the Result
- Once you identify the function and its parameters, you manually execute the required operation.
- After completing the operation, you return the result to the assistant, allowing it to continue processing.

In this context, "function calls" don't refer to executable code. Instead, they serve as a mechanism for structuring assistant interactions with external resources. Think of it as a callback with two key elements:
- A function name that you define
- A set of named parameters parsed from the prompt

This design gives you control over how a function is implemented, and defers the if and when to the LLM.

<a href="https://gist.github.com/mnadel/65b3de4888dc9355d7fbc5af36bbc13d">This gist</a> demonstrates how to interact with the API when defining an assistant that fetches content from a URL. It walks through:
- Invoking the assistant with your prompt
- Detecting when the assistant enters requires_action
- Extracting function parameters (the name is ignored, as there's only one function defined)
- Calling the function externally and returning results to the assistant
- Pulling the final response out of the assistant

Keep shipping! 🚀