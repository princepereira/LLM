## Install streamlit ##

```
pip install streamlit
```

## Sample Code ##

```
import streamlit as st

# Set page title
st.set_page_config(page_title="Simple Chat App", page_icon="💬")

st.title("💬 Simple Chat App")

# Initialize session state for messages
if "messages" not in st.session_state:
    st.session_state.messages = []

# Display chat history
for msg in st.session_state.messages:
    with st.chat_message(msg["role"]):
        st.markdown(msg["content"])

# User input
user_input = st.chat_input("Type a message...")

if user_input:
    # Save user message
    st.session_state.messages.append({"role": "user", "content": user_input})
    with st.chat_message("user"):
        st.markdown(user_input)

    # Dummy bot response (echo or replace with real logic)
    bot_response = f"You said: {user_input}"

    # Save bot message
    st.session_state.messages.append({"role": "assistant", "content": bot_response})
    with st.chat_message("assistant"):
        st.markdown(bot_response)

```

## How to run ##

```

streamlit run chat_app.py

```
