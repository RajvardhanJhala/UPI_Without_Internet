# UPI Mesh Status Dashboard

A Spring Boot dashboard that tracks offline UPI payments routed through a Bluetooth mesh network. Displays real-time settlement stats — settled, duplicate, and tampered transactions — from packets that hop between phones until one reaches the internet and syncs to the backend.

---

## Prerequisites

- JDK 17 or newer
- Git

No need to install Maven — the project ships its own wrapper.

---

## Install JDK 17 (Windows)

```powershell
winget install EclipseAdoptium.Temurin.17.JDK
```

After installing, close and reopen your terminal. Verify with:

```powershell
java -version
```

---

## Set JAVA_HOME (Windows — required)

Run PowerShell as Administrator:

```powershell
[System.Environment]::SetEnvironmentVariable("JAVA_HOME", "C:\Program Files\Eclipse Adoptium\jdk-17.x.x.x-hotspot", "Machine")
[System.Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\Program Files\Eclipse Adoptium\jdk-17.x.x.x-hotspot\bin", "Machine")
```

Replace the path with your actual JDK folder. Find it with:

```powershell
dir "C:\Program Files\Eclipse Adoptium\"
```

Close all terminals and open a fresh one after setting these.

---

## Clone the Repository

```powershell
git clone https://github.com/RajvardhanJhala/UPI_Without_Internet.git
cd UPI_Without_Internet
```

---

## Run the Project

**Windows (PowerShell):**
```powershell
.\mvnw.cmd spring-boot:run
```

**Mac/Linux:**
```bash
./mvnw spring-boot:run
```

First run downloads Maven and dependencies (~90 MB). Give it 2-3 minutes.
Once you see: Started MeshStatusApplication in X.XXX seconds
Open your browser and go to: http://localhost:8080

---

## Troubleshooting

**`.\mvnw.cmd` not recognized** — Make sure you are inside the project folder:
```powershell
cd C:\Users\YourName\Desktop\UPI_Without_Internet
```

**`C:\Program` is not recognized** — Your JAVA_HOME path has spaces. Use the short path format:
```powershell
cmd /c "for %I in ("C:\Program Files\Eclipse Adoptium\jdk-17.x.x.x-hotspot") do echo %~sI"
```
Use the output of that command as your JAVA_HOME value.

**Port 8080 already in use** — Add this to `src/main/resources/application.properties`: server.port=9090
**`java: command not found`** — JDK is not on PATH. Redo the JAVA_HOME steps above and open a fresh terminal.

---

## Live Demo

[https://mesh-status-xxxx.onrender.com](https://mesh-status-xxxx.onrender.com)

---

## Tech Stack

- Java 17
- Spring Boot 3.x
- Spring Data JPA
- Thymeleaf
- H2 In-Memory Database
- Maven
