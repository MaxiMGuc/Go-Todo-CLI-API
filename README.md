Go-Todo-CLI-API

A simple command-line interface (CLI) todo application written in Go. It lets a user manage todo items via text commands, with persistent storage in a JSON file. It supports adding, editing, deleting, listing, toggling completion status, etc.

Features

Create new todo items with a title

Edit existing todo items

Delete todo items

Mark todo items as completed / toggle completion status

List all todos, with their status (completed / not completed)

Persist data between runs in a todos.json file

Simple text-based command parsing

Project Structure

Here are the key files:

File	Purpose
main.go	Entry point. Loads storage, parses commands, executes requested operations, saves storage.
todos.json	JSON file used for storing the todo items persistently.
todo.go	Definition of the Todo type (title, completed flag, timestamps) and operations on the list (add, delete, toggle, edit, etc.).
storage.go	Handling load/save to JSON file.
command.go	Parsing of command-line flags / commands, mapping user input to todo operations.
go.mod / go.sum	Module definition and dependencies.
Usage

After you build or install the application, you run it via the terminal. The application supports several commands/options that a user can input. When the application is run, it loads existing todos from todos.json (if exists), performs the requested command, then saves updates.

Below are the supported user commands / flags and what they do.

Commands / Flags / Text Inputs

Here are each of the command-line inputs the user can supply, and what they do:

Command / Flag	Description
--add or -add (or similar) + title	Add a new todo item with the given title. Example: appname --add "Buy groceries" creates a new todo.
--edit + index : new_title	Edit an existing todo: change its title. The user specifies the index (or ID) of the todo and the new title. Example: --edit 2:"Walk the dog" changes todo #2.
--del + index	Delete the todo with the given index. Example: --del 1 removes the first todo.
--toggle + index	Toggle the completion status of the given todo (if not completed → mark completed; if completed → mark back as not completed). Example: --toggle 3.
--list (or no other flag)	List all todos, showing their indices, titles, whether they’re completed, and timestamps (when created, maybe when completed). If the user doesn’t pass any other command/flag, list may be the default.
