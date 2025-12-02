# 📌 Minishell — 42 Project

Minishell is a simplified shell program inspired by bash.
It handles parsing user input, executing commands, managing processes, redirections, and environment variables — just like a real shell.

# 🏁 Features
## 🔹 Command Execution
    
    - Run external executable programs from PATH

    - Support for multiple pipes

    - Correct process forking & execve

## 🔹 Built-in Commands
Command     	Description

echo --->	Prints text to the terminal (-n supported)
cd --->	    Change current working directory
pwd --->	Print working directory
export --->	Set environment variables
unset --->	Remove environment variables
env --->	Display environment variables
exit  --->	Exit minishell
## 🔹 Redirections

  - < input redirection

  - > output redirection (truncate)

  - >> output append redirection

  - << heredoc with limiter

## 🔹 Other Supported Features

- $ environment variable expansion

- Single ' and double " quotes behavior respected

- Signals handling:

    - Ctrl-C → interrupt current command, keep shell running

    - Ctrl-\ → ignored

    - Ctrl-D → exit shell

- Exit status ($?) maintained

# 🚫 Unsupported (Not Required by Subject)

- Wildcards *

- &&/|| operators

- Subshell ( )

- Semicolon ;

# ⚙️ Compilation & Run

```bash
make
./minishell
```

# Clean project

```bash
make clean     # Remove object files
make fclean    # Full clean + minishell binary
make re        # Recompile from scratch
```

# 🧠 How It Works (Simplified Architecture)

```
User Input
   │
   ▼
Parser ──► Tokens ──► AST (commands & pipes)
   │
   ▼
Executor ──► Fork & exec ● Builtins ● Redirections ● Pipes
   │
   ▼
Output & status updated
```

# 🧪 Testing Commands

Try things like:
```bash
ls -la | grep minishell
echo hello > out.txt
cat < out.txt | wc -l
export TEST=42
echo $TEST
cd ..
pwd
```

# 🧑‍💻 Contributors
- @me
- [@aayad](https://github.com/abdellahayad)



# 📄 License

This project is created as part of 42 School curriculum.
Reuse allowed with attribution.
