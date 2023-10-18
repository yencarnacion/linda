# linda

`linda` is a CLI tool designed to harness the power of the GPT-3.5-Turbo-Instruct model from OpenAI. The acronym **LINDA** stands for &quot;Large language model Imperfect Non-Deterministic Algorithm&quot;. With `linda`, users can:

- Query in natural language directly from the command line.
- Execute a command after querying GPT-3.5-Turbo-Instruct using natural language.
- Prompt the model in both English and Spanish.

## Prerequisites

Before you can run `linda`, you need to have `jq` installed on your system. `jq` is a lightweight and flexible command-line JSON processor.

### Installing jq

On most systems, you can install `jq` using the package manager:

- **On Debian/Ubuntu**:
  ```bash
  sudo apt-get install jq
  ```

- **On Red Hat/Fedora**:
  ```bash
  sudo yum install jq
  ```

- **On macOS** (using Homebrew):
  ```bash
  brew install jq
  ```

For other systems or methods, please refer to the [official jq documentation](https://stedolan.github.io/jq/download/).

## Motivation

The project was inspired by [pls](https://github.com/MxDkl/pls) by Max Dekel, which is licensed under the MIT License. However, there are a few distinctions between `linda` and Max's `pls`:

- **Model**: `linda` utilizes the GPT-3.5-Turbo-Instruct model, which contrasts with `pls` that uses the GPT-4 model. The GPT-3.5-Turbo-Instruct is less expensive and faster.
- **Response Type**: Besides returning commands, `linda` also allows users to get natural language responses to their queries.
- **Language Support**: `linda` supports both English and Spanish prompts.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yencarnacion/linda.git
   cd linda
   ```

2. Create a configuration file under your home directory:
   ```bash
   touch ~/.linda-config
   ```
   And add your OpenAI API key:
   ```
   api_key="<your api key>"
   ```

## Usage

```
yencarnacion@penguin:~/linda$ linda <your question>
yencarnacion@penguin:~/linda$ linda -c <your command>
yencarnacion@penguin:~/linda$ linda -c -s <tu comando en Español>
```

### Examples

1. **Command Execution**:
   ```
   yencarnacion@penguin:~/linda$ linda -c command to invoke python3 simple http server on port 8000
   python3 -m http.server 8000
   Press any button to execute, or n to cancel: <RET>
   Executing command...
   Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
   ```

2. **Natural Language Query**:
   ```
   yencarnacion@penguin:~/linda$ linda what is the command to list unique lines in a file in reverse order
   The command to list unique lines in a file in reverse order is 'sort -u -r <file>'.
   ```

## License

This project is Copyright (c) 2023 Yamir Encarnacion and is licensed under the [MIT License](./LICENSE).

---

Special thanks to [Max Dekel](https://github.com/MxDkl) for the inspiration.
