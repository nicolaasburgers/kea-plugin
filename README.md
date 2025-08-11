# Kea Plug-in
Information about the Kea plug-in for Grasshopper (Rhinoceros 3D).

<img width="200" height="196" alt="KeaLogo3-01" src="https://github.com/user-attachments/assets/6a313a58-8837-4244-a1fa-701a01e87c29" />

After installing the plug-in using the Package Manager (with "include pre-releases" box ticked) and restarting Rhino, you'll find a new option in the top-level View Menu: AI Script Assistant (Kea). Select that to launch the Kea window.

You'll need at least one set of API keys for one of these AI platforms:
- OpenAI
- Anthropic
- Deepseek

When you have an API key, go to the Settings page of the Kea window, insert the API key in the appropriate box and press Save.

You can then go to the Chat tab, and select the model to use, and start using natural language to request new or changed C# and Python scripts.

### Model selection
Each platform provides many models to choose from, and while some have already been filtered out (like the test and image-generation-only ones), there are many more models than you might expect. 

The popular, well-known models on the above platforms generally know C# and Python quite well but there could be models in the list that aren't as good. If you're unsure, find the one whose name most closely resembles the one you use in your regular web chats.

### How it works
With every request you make, Kea informs these models of the Grasshopper context and how to respond such that Kea can enact the changes. As a result, the AI models return information in a format that Kea can parse into:
- the text response to display on the screen
- a set of information Kea uses to create or update script objects

The kinds of chat requests it expects and knows best how to handle are ones like:
- "Create a Python script which has __ as inputs and outputs __"
- "Can you explain what this script does?"
- "Add an new input of ___ and incorporate it into the calculations by ___"

When you first ask it to create a script, if you don't specify a language, it will assume Python. Once the script object is created, the language is fixed.

Kea will maintain a chat history *per script object*.

### Limitations
These limitations exist at the time of writing but might be improved or changed over time. So at this point, Kea cannot:
- change the language of a script component once it's been created
- see the input values, output values or bugs in the script component
- see anything else on the canvas except for the contents of the selected script, its input and output meta data
