## Install Required Python Packages in Virtual Environment ##

```

Ensure python is installed

python -m venv openai-env

.\openai-env\Scripts\Activate.ps1

python.exe -m pip install --upgrade pip

pip install openai

pip install --upgrade openai

pip show openai

```

## Token Generation ##
```
https://platform.openai.com
```

## Token Usage ##

```
https://platform.openai.com/usage
```

## List the supported models ##

```

import os
from openai import OpenAI

API_KEY = "<API KEY>" # Generate from https://platform.openai.com

client = OpenAI(api_key=API_KEY)  # or use environment variable
models = client.models.list()
print("Supported models:")
print("===============")

for model in models.data:
    print(model.id)

```

## Make a OpenAI API call ##

```

import os
from openai import OpenAI

API_KEY = "<API KEY>" # Generate from https://platform.openai.com

response = client.chat.completions.create(
    model="gpt-4.1",  # or "gpt-3.5-turbo"
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "What is the capital of France?"}
    ]
)

print(response.choices[0].message.content)

```
