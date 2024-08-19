# huffman-algorithm
# Huffman Compression and Decompression in C

This project implements a text file compressor and decompressor based on the Huffman algorithm. It uses a binary heap (min-heap) to construct a Huffman tree for encoding and decoding text files.

## Features

- **Compression**: Converts a text file into a compressed binary format using Huffman coding.
- **Decompression**: Restores the original text file from the compressed binary format.
- **Huffman Tree Construction**: Builds a Huffman tree from character frequencies.
- **Binary Encoding/Decoding**: Encodes and decodes text files using binary representations of Huffman codes.

## Files

- `main.c`: Contains the implementation of the Huffman compression and decompression algorithm.
- `texto.txt`: Input text file for compression.
- `textoC.dat`: Output compressed binary file.
- `textoD.txt`: Output decompressed text file.

## Compilation

To compile the program, use the following command:

``` gcc -o huffman main.c ```

## Usage

1. **Prepare Input File**: Ensure `texto.txt` is present in the same directory as the executable. This file will be compressed.
2. **Run the Program**:

``` ./huffman ```

3. **Output Files**:
   - `textoC.dat`: Contains the compressed binary data.
   - `textoD.txt`: Contains the decompressed text data.

## Functions

- **`HeapNodo* criaNodo(char caracter, unsigned freq)`**: Creates a new node for the Huffman tree.
- **`void printBinary(unsigned int num)`**: Prints an integer in binary format.
- **`void verificaPrioridade(Heap* heap, int idx)`**: Ensures the heap property is maintained.
- **`HeapNodo* constroiHuffman(char array_caracteres[], int array_freq[], int tamanho_freq)`**: Constructs the Huffman tree.
- **`void liberaArvoreHuffman(HeapNodo* raiz)`**: Frees memory allocated for the Huffman tree.
- **`void criaTabelaHuffman(HeapNodo* raiz, int aux[], int pai, unsigned int codigoBinarioInt[], int tamanhoBits[])`**: Creates a Huffman table with binary codes and their lengths.
- **`void printTabelaHuffman(unsigned int codigoBinario[], int tamanhoBits[256])`**: Prints the Huffman table.
- **`void descompact2(HeapNodo* raiz)`**: Decompresses the binary file and writes the output to a text file.
- **`void compacta()`**: Compresses the input text file and writes the output to a binary file.

## Example Output

```
Codigos de Huffman

Caracter: A - Codigo Binario: 1010
Tamanho em Bits: 4

Caracter: B - Codigo Binario: 0001
Tamanho em Bits: 4

Frequencia de Caracteres:

Caracter: A - Frequencia: 10 vezes
Caracter: B - Frequencia: 5 vezes
```
## Notes

- The program assumes that `texto.txt` contains plain text and is encoded in a format compatible with the Huffman coding algorithm.
- The Huffman tree is built from character frequencies calculated from the input text file.
- The compression and decompression processes handle binary data and text files respectively.
