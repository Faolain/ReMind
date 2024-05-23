# reMind - Your Local Artificial Memory Assistant

Welcome to reMind! This application captures and indexes your digital activities, transcribing and summarizing them for easy recall. reMind uses advanced AI models to provide detailed summaries of your daily activities and to answer questions based on your digital history. It is at its first version , a more optimal and runnable version will be uploaded on mid June 2024.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Capture Digital Activities**: Records screenshots, audio, and other digital activities.
- **Text Transcription**: Transcribes text from captured screenshots.
- **Indexing**: Uses vector databases to index and retrieve documents.
- **Summarization**: Provides detailed summaries of daily activities.
- **Interactive Chat**: Interact with the application using a chat interface to query your digital history.

## Installation

To get started with reMind, follow these steps:

1. **Clone the Repository**
    ```sh
    git clone https://github.com/DonTizi/reMind.git
    cd reMind
    ```

2. **Set Up a Virtual Environment**
    ```sh
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Dependencies**
    ```sh
    pip install -r requirements.txt
    ```

4. **Install Node.js and npm** (for the Electron app)
    Download and install Node.js from [nodejs.org](https://nodejs.org/).

5. **Set Up the Electron App**
    ```sh
    npm install
    ```

6. **Install Ollama and Set Up the LLM**

    After installing Ollama, follow these steps to set up the LLM:

    ```sh
    ollama run llama3
    ollama run nomic-embed-text
    ollama create recallAI
    ```

    Use the following system prompt for your LLM:

    ```plaintext
    You are RecallAI, an advanced artificial memory assistant. Your primary function is to capture, index, and summarize digital activities for easy recall. You provide detailed summaries of daily activities and answer questions based on the user's digital history. Your responses should be concise, accurate, and helpful.
    ```



## Usage

1. **Start the Flask Server**
    ```sh
    python main.py
    ```

2. **Start the Electron App**
    ```sh
    npm run start
    ```

3. **Interact with the Application**
    - Use the chat interface to query your digital history or ask for summaries of your activities.

## API Endpoints

### `/`
- **Description**: Checks if the application is running.
- **Method**: GET
- **Response**: "Chat application is running!"

### `send_message`
- **Description**: Handles incoming messages and generates responses.
- **Method**: SocketIO Event
- **Data**: JSON object containing the user message.
- **Response**: Stream of messages generated by the AI model.

## Configuration

- **JSON File**: Ensure `all_texts.json` is present in the `memory_capture/vectore` directory. If the file does not exist, it will be created with sample data.
- **Persist Directory**: The vector database is stored in `memory_capture/vectore/vectoreDB`.

## Contributing

We welcome contributions from the community! To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or support, please open an issue in the GitHub repository or contact me at [elyes.melbouci@gmail.com](mailto:elyes.melbouci@gmail.com).

---

Thank you for using reMind! We hope it helps you manage and recall your digital activities effortlessly. By making reMind open-source, we aim to foster a collaborative environment where developers can contribute to and improve this innovative application. Happy coding!
