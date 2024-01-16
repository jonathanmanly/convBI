## How It Works

This approach makes use of the OpenAI api (running the 3.5-turbo model), and leverages function calling.
Function calling lets an application let the LLM know what functions it can request to be run on the host computer, 
and what parameters to extract in order to make such a request. Functions are defined in a JSON package, and supplied 
as part of the context in the chat request to the API. When the LLM detects that it is appropriate to ask for a function call, 
rather than respond directly, it reponds with a specific function call response, and provides a JSON package of the parameters. 
ConvBI then runs the appropriate function, and returns the output to the LLM to get the final response for the chatbot.

Create your api key at [openai.com](https://openai.com/), and save a text file in your local directory with this code called config.ini in the format below:

[DEFAULT]
openai_api_key = <...>

