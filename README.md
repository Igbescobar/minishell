# minishell

This project is a custom implementation of a basic command-line shell, similar to `bash`. It is designed to parse user input, manage environment variables, and execute commands within a persistent loop. The shell features a dynamic prompt that displays the current user, hostname, and working directory.

## Features

-   **Interactive Prompt:** Displays a dynamic prompt with the format `user@hostname:path$`, updating with the current context.
-   **Command History:** Utilizes the `readline` library to maintain a history of commands, accessible via arrow keys.
-   **Environment Variable Management:** Copies the system's environment variables upon startup and provides functions to access them.
-   **Basic Parsing:** The input is tokenized, with initial support for splitting commands by the pipe (`|`) character.

## Prerequisites

To compile and run this project, you will need:
-   A C compiler (e.g., `gcc`)
-   The `make` utility
-   The `readline` library. On Debian/Ubuntu, you can install it with `sudo apt-get install libreadline-dev`.

## Compilation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/Igbescobar/minishell.git
    cd minishell
    ```

2.  **Build the project using the Makefile:**
    ```sh
    make
    ```
    This will compile the source files and create the `minishell` executable in the root directory.

## Usage

To start the shell, run the compiled executable from the project's root directory:
```sh
./minishell
```
You can then start typing commands into the prompt. To exit the shell, press `Ctrl+D`.

### Makefile Commands

-   `make` or `make all`: Compiles the project.
-   `make clean`: Removes the intermediate object files.
-   `make fclean`: Removes all compiled files, including the final executable.
-   `make re`: Forces a full recompilation of the project.

## Project Structure

```
.
├── includes/         # Header files
│   ├── env.h
│   └── minishell.h
├── libft/            # Custom C utility library
│   ├── get_next_line/
│   ├── printf/
│   └── standard/
├── src/              # Source code for the shell
│   ├── env.c
│   ├── main.c
│   └── shell_loop.c
└── Makefile          # Main makefile for compilation
```

-   **`src/`**: Contains the core logic of the minishell.
    -   `main.c`: The entry point of the program. It initializes the environment and starts the shell loop.
    -   `shell_loop.c`: Manages the main interactive loop, constructs the prompt, and reads user input.
    -   `env.c`: Handles copying, accessing, and freeing environment variables.
-   **`includes/`**: Contains the header files for the project, defining data structures and function prototypes.
-   **`libft/`**: A personal library of standard and utility C functions used throughout the project, including a custom `printf` and `get_next_line`.
