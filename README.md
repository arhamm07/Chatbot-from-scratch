# Intelligent Chatbot from Scratch 🤖

A lightweight, neural network-based chatbot built from scratch using PyTorch, designed for intent classification and response generation without relying on large language models.

## Features

- 🧠 Custom neural network architecture
- 🔍 Intent classification using bag-of-words
- 🛠️ Easy to extend with new intents
- 📊 Function mapping for dynamic responses

## Prerequisites

- Python 3.7+
- PyTorch
- NLTK
- NumPy

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/chatbot-from-scratch.git
   cd chatbot-from-scratch
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download NLTK data:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('wordnet')
   ```

## Usage

### Training the Model

1. Edit `intents.json` to add your custom intents and patterns
2. Uncomment and run the training code in `chatbot.py`:
   ```python
   assistant = ChatbotAssistant('intents.json')
   assistant.parse_intents()
   assistant.prepare_data()
   assistant.train_model(batch_size=8, lr=0.001, epochs=100)
   assistant.save_model('chatbot_model.pth', 'dimensions.json')
   ```

### Running the Chatbot

```bash
python chatbot.py
```

Interact with the chatbot in the terminal. Type `/quit` to exit.

## Customization

### Adding New Intents

1. Add a new intent block to `intents.json`:
   ```json
   {
       "tag": "your_intent",
       "patterns": ["sample pattern 1", "sample pattern 2"],
       "responses": ["Response 1", "Response 2"]
   }
   ```

2. Retrain the model to include the new intents

### Adding Function Mappings

1. Define your function in `chatbot.py`:
   ```python
   def your_function():
       # Your code here
       return "Function executed!"
   ```

2. Add it to the function mappings when initializing the chatbot:
   ```python
   assistant = ChatbotAssistant('intents.json', function_mappings={
       'your_intent': your_function
   })
   ```

## Project Structure

- `chatbot.py` - Main chatbot implementation
- `intents.json` - Training data and responses
- `logger.py` - Logging configuration

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
