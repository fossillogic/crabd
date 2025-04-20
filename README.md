# **crabd** — Blue Crab Daemon

`crabd` is the central daemon responsible for hosting and managing CrabDB instances across the network. It runs as a background service, responding to commands issued by tools like `crabctl`, and provides endpoints for database synchronization, remote querying, health monitoring, and system orchestration. On startup, `crabd` loads its configuration from a TOML file, which defines server settings, security policies, node relationships, and database paths. It supports running in the foreground for debugging or as a daemon for production environments. With built-in support for SSH-based authentication, token-based security, and IP allowlists, `crabd` ensures secure communication between nodes. It listens for incoming connections, processes commands, and handles lifecycle operations such as initialization, configuration deployment, and log streaming. Its modular architecture enables clean integration with metrics collection, automation scripts, and distributed control, making it the backbone of the CrabDB infrastructure.

---

## 🔧 `crabd` Command Reference

| Command / Flag             | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| `--help`                  | Show usage instructions                                                     |
| `--version`               | Print the daemon’s version                                                  |
| `--config <file>`         | Load config from a specific `.toml` file (default: `/etc/crabd/config.toml`)|
| `--foreground`            | Run in the foreground (no daemonization)                                    |
| `--port <port>`           | Override listening port (default: `4747`)                                   |
| `--host <ip>`             | Bind to a specific IP (default: `0.0.0.0`)                                   |
| `--log <file>`            | Log to a specified file (overrides config)                                  |
| `--init-db`               | Initialize default `.crabdb` files from templates                           |
| `--dry-run`               | Validate configuration and exit without starting                            |

---

## ✅ **Prerequisites**

Ensure you have the following installed before starting:

- **Meson Build System**: This project relies on Meson. For installation instructions, visit the official [Meson website](https://mesonbuild.com/Getting-meson.html).

---

## ⚙️ **Setting Up Meson Build**

1. **Install Meson**:
    - Follow the guide on the [Meson website](https://mesonbuild.com/Getting-meson.html) for your operating system.

---

## 🚀 **Setup, Compile, Install, and Run**

1. **Clone the Repository**:

    ```sh
    git clone https://github.com/fossillogic/fossil-app.git
    cd fossil-app
    ```

2. **Configure the Build**:

    ```sh
    meson setup builddir
    ```

3. **Compile the Project**:

    ```sh
    meson compile -C builddir
    ```

4. **Install the Project**:

    ```sh
    sudo meson install -C builddir
    ```

5. **Run the crabd Daemon**:

    ```sh
    crabd --config /etc/crabd/config.toml --foreground
    ```

---

## 🤝 **Contributing**

Interested in contributing? Please open pull requests or create issues on the [GitHub repository](https://github.com/fossillogic/crabd).

---

## 💬 **Feedback and Support**

For issues, questions, or feedback, open an issue on the [GitHub repository](https://github.com/fossillogic/crabd/issues).

---

## 📄 **License**

This project is licensed under the [Mozilla Public License](LICENSE).
