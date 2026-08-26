# Project Description

A low-level HTTP Web Server built from scratch using the Bonezegei Scripting Language (BSL) and the BSL Socket Library developed by Jofel A. Batutay. Its purpose is to explore fundamental network programming, configure a clean development environment in Visual Studio Code, maintain a public GitHub repository under the MIT License, enforce proper syntax mapping via `.gitattributes`, and implement custom HTTP route handling for `/`, `/about`, and generic `404 Not Found` responses.

---

# Installation & Setup Guide

## 1. Prerequisites

### Bonezegei Scripting Language (BSL) Runtime

- **For Windows**
  * Install **Bonezegei_Scripting_Language** directly from the Microsoft Store app in your Windows Start Menu.

- **For Linux (x86_64)**
  * Download the `.deb` installer:
    ```bash
    wget https://github.com/bonezegei/Bonezegei_Scripting_Language/raw/refs/heads/main/Release/Latest/Bonezegei-x86.deb
    ```
  * Run the installation command:
    ```bash
    sudo apt install ./Bonezegei-x86.deb
    ```

- **For Raspbian Raspberry Pi / Linux (ARM64)**
  * Download the `.deb` installer:
    ```bash
    wget https://github.com/bonezegei/Bonezegei_Scripting_Language/raw/refs/heads/main/Release/Latest/Bonezegei-arm64.deb
    ```
  * Run the installation command:
    ```bash
    sudo apt install ./Bonezegei-arm64.deb
    ```

### Development Environment (VS Code)
* Download and install [Visual Studio Code](https://code.visualstudio.com/).
* Open the project directory in VS Code.
* Configure a `.gitattributes` file in your repository root to ensure GitHub and code editors properly detect syntax for `.bzg` source files:
  ```gitattributes
  *.bzg linguist-language=C
  ```

### Verifying Installation
Open your terminal or Command Prompt to confirm the runtime is functional:

```bash
# View current version
bonezegei --version

# Test inline scripting
bonezegei -inline "print(\"Hello World\");"
```

---

## 2. Socket Library Installation

Install the official Bonezegei Socket Library package required for TCP and HTTP operations:

```bash
bzg install socket
```

Verify installed packages:

```bash
bzg -list
```

---

## 3. Running the Server

Clone the repository, switch into the project directory, and launch the server script:

```bash
# Clone the repository
git clone https://github.com/Jevoel16/my-bsl-http-server.git
cd my-bsl-http-server

# Run the server
bonezegei src/http.bzg
```

By default, the server binds to port `8080` (or your configured port) and begins listening for incoming HTTP connections.

---

# Usage Instructions

Once the server is running, open any web browser or HTTP client and navigate to the following endpoints:

| Endpoint | Target URL | Expected Status | Description |
|---|---|---|---|
| **Root** | `http://localhost:8080/` | `200 OK` | Loads the primary index landing page. |
| **About** | `http://localhost:8080/about` | `200 OK` | Displays project details, purpose, and environment info. |
| **404 Fallback** | `http://localhost:8080/anything` | `404 Not Found` | Dispatches the custom 404 error page for unregistered paths (e.g. `/home`, `/user`, `/anything`). |

---

# Screenshots Section

Visual verification assets captured from local runtime and browser tests, located in the `documentation/` folder:

## 1. Root Route (`/`)
Browser rendering the main home route.

![Root Route](documentation/home.png)

## 2. About Route (`/about`)
Browser displaying the `/about` endpoint content.

![About Route](documentation/about.png)

## 3. 404 Error Page (`/anything`)
Browser showing the 404 response for an unhandled path.

![404 Error Route](documentation/404.png)

## 4. Terminal Server Execution
Terminal output showing the server actively listening, with username and directory path clearly visible.

![Terminal Server](documentation/terminal.png)