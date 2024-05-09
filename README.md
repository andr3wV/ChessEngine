# Overview

This project demonstrates how a tokenizer and a trained neural network can be combined to create a chess engine. Unlike traditional search-based engines, this no-search engine evaluates positions one move ahead and selects the best move based on a neural network's evaluation.

# Components

## Chess Engine

The chess engine evaluates a given position by generating all possible legal positions one move ahead. Each position is evaluated by a neural network, which assigns a winning probability. The steps involved are:

1. Generate all legal FEN positions one move ahead from the given position.
2. Tokenize the list of FEN positions.
3. Use the neural network to evaluate and categorize each position.
4. Select and return the position with the highest winning probability.

## Tokenizer

The tokenizer handles FEN notations, which can vary in length up to a maximum of 71 characters. Each FEN position is padded to ensure uniform length. This basic tokenizer does not consider castling information or move numbers, but future versions will include a more advanced tokenizer.

## Neural Network

The neural network categorizes each position into one of 64 classes, representing how winning the position is from the next player's perspective. A position evaluated as 0 is completely losing, while 63 is completely winning. This evaluation is consistent regardless of which player is to move next.

# How It Works

1. **Position Generation**: The engine generates all possible FEN positions from the current position.
2. **Tokenization**: The tokenizer converts the list of FEN notations into integers.
3. **Evaluation**: The neural network assigns each tokenized position a winning probability.
4. **Selection**: The engine selects the position with the highest winning chance and outputs it as the best move.

# Future Improvements

- **Advanced Tokenizer**: Implement a tokenizer that includes castling information and move numbers.
- **Enhanced Neural Network**: Train a more sophisticated neural network for better position evaluation.
- **Search Integration**: Explore integrating search techniques to evaluate deeper positions.
- **User Interface**: Develop a graphical user interface for easier interaction with the chess engine.
