## The Speech to Markdown script

### How it works:
 - The script will search for all the files in the provided path, and look for all mp4, wav, and txt files.
 - The full processing pipeline: mp4 video => wav (via ffmpeg) => txt (via Whisper) => Markdown (Via Gemini Pro)
 - The input could be mp4 video or wav audio, txt files are also accepted. If the input directory is a txt file, it will be organized into Markdown right away.
 - The Markdown (.md) file will be uploaded to HackMD for easy browsing and sharing, however the title naming issue from the HackMD api was still under work at the moment.

### Requirments
 - get Google AI Studio API key for gemini pro model
 - get HackMD api key for uploading to HackMD
 - pip install the following libraries:
~~~
!pip install python-dotenv
!pip install whisper
!pip install ffmpeg-python
!pip install google-generativeai
!pip install PyHackMD
!pip install tqdm
~~~

### Note
 - The code was onl tested working in Windows and Visual Studio Code environment.
 - Do not leak your API keys, set up a ".env" file to store your API keys and add ".env" to ".gitignore" to not publish your API keys.
 - You can tweak the parameters of the function as you wish, please reference to the documentations below:
    - [Gemini API generation configuration](https://ai.google.dev/tutorials/python_quickstart#generation_configuration)
    - [Google AI Studio and fetch API keys](https://aistudio.google.com/app/prompts/new_chat/?utm_source=agd&utm_medium=referral&utm_campaign=core-cta&utm_content=)
    - [Google generative AI](https://pypi.org/project/google-generativeai/)
    - [Whisper model](https://pypi.org/project/openai-whisper/)
    - [PyHackMD api](https://pypi.org/project/PyHackMD/)
