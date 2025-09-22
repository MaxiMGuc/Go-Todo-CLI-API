Go-Todo-CLI-API
A simple command-line interface (CLI) todo application written in Go. It lets a user manage todo items via text commands, with persistent storage in a JSON file. It supports adding, editing, deleting, listing, toggling completion status, etc.

Features
-Create new todo items with a title
-Edit existing todo items
-Delete todo items
-Mark todo items as completed / toggle completion status
-List all todos, with their status (completed / not completed)
-Persist data between runs in a todos.json file
-Simple text-based command parsing

Usage
After you build or install the application, you run it via the terminal. The application supports several commands/options that a user can input. When the application is run, it loads existing todos from todos.json (if exists), performs the requested command, then saves updates.
Below are the supported user commands / flags and what they do.

Project Structure
Here are the key files:
File	Purpose:
- main.go	Entry point. Loads storage, parses commands, executes requested operations, saves storage.
- todos.json	JSON file used for storing the todo items persistently.
- todo.go	Definition of the Todo type (title, completed flag, timestamps) and operations on the list (add, delete, toggle, edit, etc.).
- storage.go	Handling load/save to JSON file.
- command.go	Parsing of command-line flags / commands, mapping user input to todo operations.
- go.mod / go.sum	Module definition and dependencies.

- Commands / Flags / Text Inputs
Here are each of the command-line inputs the user can supply, and what they do:
<img width="776" height="398" alt="Снимок экрана 2025-09-22 в 1 33 01 PM" src="https://github.com/user-attachments/assets/d3f7f6b3-1a55-48b8-99e6-dfe3de1fefbf" />
