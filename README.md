# ToDoListAgent

This is a PoC for a todolist agent, which breaks down tasks. This is a very simple PoC.

### Features:-
1. Takes in an audio or text input from user.
2. Uses Gemini Flash 1.5 to answer the prompt(if it adheres to the SMART framework).
3. Uses streamlit as an interface. 

### Usage
streamlit run Todolist.py

### Example prompts
1. I'm a 25 year old ML engineer, with 3 years experience at a computer vision startup based out of Chennai. I want to switch jobs in the next 30 days. Give me a detailed breakdown on a day/day basis on how to achieve it.
2. I want to run a 10K in 1hour, currently I run a 10K in 70mins. Give me a breakdown on training regimen, i have 1 month to my race

#### References
https://github.com/jiaaro/pydub/issues/346#issuecomment-608084856 - converting pydub.audio_segment to np.array

#### Challenges I'm currently facing

Date - 2024/06/17
I wanted to incorporate a light weight ASR model, using distilled version of whisper to transcribe audio to text. Then, send this text as an input to gemini. Realised this way i can do additional NLP preprocessing to the text instead of directly feeding the input to the model. 
1. I have a 1050Ti GPU and running this on windows, hugging face transformers library has issues with windows support (FlashAttention2)
2. I tried running this on Colab, but the model seems to not transcribe this properly. Either the text hallucinates or i don't get any text response. I'll have to come back to this and check 

Date - 2024/06/23
1. Tried using langchain framework for this, turns out to be pretty complicated to build agents with gemini. Got lots of bugs. 
2. Came across this [article](https://www.octomind.dev/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents) to get me going without langchaing 