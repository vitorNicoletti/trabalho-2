
# Simple Database in C

This project is a simple database implemented in C. It comprises three programs:

1. **Generator:** Reads a `.txt` file containing all the database information, stores it in a structure sorted by ID, and exports it into a `.bin` archive.
   
2. **Editor:** Takes the binary archive, stores it in memory, and allows users to perform alterations on the database (such as adding, editing, removing, and printing data).

3. **Exporter:** Converts the binary archive back to text, incorporating any alterations made by the second program.

This project utilizes dynamic memory allocation and structs to store the database in memory, enabling easy manipulation. The example database in this project consists of books. However, the code can be easily modified to handle other types of data (as long as it can be stored in a text archive).

## Usage

1. **Compilation:**
   ```bash
   gcc -o generator gerador.c funcoes_gerador.c
   gcc -o editor Editor.c funcoes_editor.c
   gcc -o exporter exportador.c funcoes_exportador.c
   ```

2. **Executing:**
   ```bash
   ./generator texto-base.txt output.bin
   ./editor output.bin output-edited.bin
   ./exporter output-edited.bin final-db.txt
   ```

## Functionality

- **Program 1:**
  - Reads data from `texto-base.txt`.
  - Stores data in a structured format sorted by ID.
  - Exports the data into `output.bin`.

- **Program 2:**
  - Loads data from `input.bin` into memory.
  - Provides options to add, edit, remove, or print data.
  - Saves any changes made back to `input.bin`.

- **Program 3:**
  - Converts `input.bin` back to a text format.
  - Incorporates any changes made by Program 2.
  - Outputs the updated data to `output.txt`.

## Example Database Structure

- **Book Structure:**
  ```c
  struct Livro {
    int id;
    char titulo[MAX];
    Livro *proximo;
  };
  ```

## Modifying the Code

To adapt this project to handle different types of data, follow these steps:

1. Modify the structure definition in the code (`struct Book` in this case) to match the structure of the new data.
2. Ensure the input and output file formats are compatible with the new data structure.
3. Adjust any data processing or manipulation functions as needed.

Note:
the `.h` archives are very redundant.
