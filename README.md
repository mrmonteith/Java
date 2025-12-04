## Getting Started

WSL2 + Java setup and includes a simple ASCII diagram of the workflow so anyone can reproduce your environment.

---

```markdown
# Java Development in WSL2 with VS Code

This repository demonstrates how to set up and run Java projects inside **WSL2 (Ubuntu)** using **Visual Studio Code**.  
It provides reproducible steps for installing Java, configuring environment variables, and integrating with VS Code.

---

## 🚀 Prerequisites
- Windows 10/11 with **WSL2** enabled
- Ubuntu installed via WSL2
- Visual Studio Code with:
  - [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)
  - [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)

---

## ☕ Install Java (OpenJDK 21 LTS)

Update package index:
```bash
sudo apt update
```

Install OpenJDK:
```bash
sudo apt install openjdk-21-jdk -y
```

Verify installation:
```bash
java -version
```

Expected output:
```
openjdk version "21" ...
```

---

## ⚙️ Configure Environment Variables

Add to `~/.bashrc` (or `~/.zshrc`):
```bash
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

Reload:
```bash
source ~/.bashrc
```

---

## 🖥 Configure VS Code

1. Install **Java Extension Pack**.
2. Install **Remote - WSL** extension.
3. Open your project folder inside WSL (`Remote Explorer → Ubuntu`).
4. In Command Palette (`Ctrl+Shift+P`), run `Java: Configure Java Runtime` and ensure it points to `$JAVA_HOME`.

---

## 📂 Project Structure

```
java-wsl2-vscode/
├── src/
│   └── HelloWorld.java
├── bin/
└── README.md
```

---

## ✅ Test Run

Create `src/HelloWorld.java`:
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, WSL2 + Java!");
    }
}
```

Compile and run:
```bash
javac -d bin src/HelloWorld.java
java -cp bin HelloWorld
```

---

## 🔗 Workflow Diagram

```text
+-------------------+        +-------------------+        +-------------------+
|   Windows Host    |        |      WSL2         |        |     VS Code       |
| (VS Code Editor)  | <----> | (Ubuntu + Java)   | <----> | Java Extensions   |
+-------------------+        +-------------------+        +-------------------+
        |                           |                           |
        |   Remote - WSL Bridge     |   OpenJDK Runtime         |
        |-------------------------->|-------------------------->|
```

---

## 📖 Notes
- This setup uses **OpenJDK 21 LTS** for long-term support.
- For advanced builds (JavaFX, GraalVM, Gluon Mobile), you can swap in GraalVM later.
- Keep your repo recruiter-friendly by documenting each step and including diagrams like above.
```

---


