# Chess Bot

The aim of this project is to develop a neural network capable of evaluating chess positions. The project is still in its infancy and is currently under development.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Exemples](#examples)
- [Future](#future)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/simonriou/chess.git
    cd chess
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Download and install [Stockfish](https://stockfishchess.org/download/) (or use the .zip provided here)

## Current Features

Data formatting has been solved. Each input feature is a 8x8x12 matrix. (8x8 is the chessboard, 12 is 1 channel / piece, 1 if there's a piece, 0 else). My first try is a CNN + 2 Dense layers network. Still in the process of testing it on different datasets. Will update when I come up with something.

## Usage

1. Clean a PGN file:
    ```python
    from utils import clean_pgn

    cleaned_pgn_path = clean_pgn('path/to/your/file.pgn')
    print(f"Cleaned PGN file saved to: {cleaned_pgn_path}")
    ```

2. Process a PGN file and export features and labels:
    ```python
    from data_process import process_file

    process_file('path/to/your/file.pgn', 'path/to/stockfish', 'dataset_name')
    ```

3. Split a PGN file into smaller files:
    ```python
    from utils import split_pgn

    split_files = split_pgn('path/to/your/file.pgn', num_files=10)
    print(f"Split files: {split_files}")
    ```

4. Convert FEN to matrix and normalize evaluations:
    ```python
    from utils import fen_to_matrix, normalize_evaluation

    fen = "rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR w KQkq - 0 1"
    matrix = fen_to_matrix(fen)
    print(matrix)

    evaluation = {"type": "centipawn", "value": 34}
    normalized_value = normalize_evaluation(evaluation)
    print(normalized_value)
    ```

## Examples

The `processed/` directory contains the processed versions of the `datasets/classical_2000_0124.pgn` and `datasets/test_double.pgn` files. The first one contains all the classical games of 2000+ rated players played on Lichess during January 2024. The second one is just a sample of that file that I used for tests.

It took approximately 20 minutes to process a bit more than 1000 games using 4 workers. It is still relatively slow, but keep in mind that this process will be needed once for each dataset.

## Future

I am currently processing a lot of data and games, so that I have sufficient positions to train the network and try different network architectures. I would like to
- Find a way to include game context in the training (ATM, data is flatten and the network only gets a plain list of FENs)
- Decide on a network architecture that works well
- Find a way to speed up the data processing computations

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License.
