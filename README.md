<p align="center">
<img src="https://raw.githubusercontent.com/freerouting/freerouting/master/design/social_preview/freerouting_social_preview_1280x960_v2.png" alt="Freerouting" title="Freerouting" align="center">
</p>
<h1 align="center">Freerouting</h1>
<h5 align="center">Freerouting is an advanced autorouter for all PCB programs that support the standard Specctra or Electra DSN interface.</h5>

<p align="center">
    <a href="https://github.com/freerouting/freerouting/releases"><img src="https://img.shields.io/github/v/release/freerouting/freerouting" alt="Release version" /></a>
    <img src="https://img.shields.io/github/downloads/freerouting/freerouting/v1.9.0/total" alt="Downloads"/>
    <img src="https://img.shields.io/github/downloads/freerouting/freerouting/total" alt="Downloads"/>
    <a href="LICENSE"><img src="https://img.shields.io/github/license/freerouting/freerouting" alt="License"/></a>
	<a href="https://github.com/freerouting/freerouting/blob/master/docs/code_of_conduct.md"><img src="https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg" alt="Contributor Covenant" /></a>
</p>

<br/>

[**Download installers for Windows, Linux, and macOS here.**](https://github.com/freerouting/freerouting/releases)

## Introduction

Freerouting is a powerful PCB autorouter compatible with any PCB design software that supports the standard Specctra or Electra DSN interface. It imports `.dsn` files generated by the host system's Specctra interface and exports `.ses` Specctra session files.

## Getting started

You can interact with Freerouting using the Graphical User Interface ([GUI](#graphical-user-interface-gui)), the Command Line Interface ([CLI](#command-line-interface-cli)), or the Freerouting [API](#freerouting-api). All interfaces support command-line arguments to set input/output files or modify settings.

Integrations are available with:

- [KiCad](https://www.kicad.org/)
- [Autodesk EAGLE](http://eagle.autodesk.com/)
- [Target3001!](https://ibfriedrich.com/en/index.html)
- [EasyEDA](https://www.easyeda.com/)
- [tscircuit](https://tscircuit.com/)
- [pcb-rnd](https://www.pcb-rnd.com/)

[Click here for more details](docs/integrations.md).

### Graphical User Interface (GUI)

1) **Launch Freerouting**: Upon launching, you'll see the main interface.
   ![image](https://github.com/user-attachments/assets/4086cd74-313e-4d17-8e25-5e006497e566)

2) **Open Your Design**: Go to `File` > `Open...` and select your `.dsn` input file.
   ![image](https://github.com/user-attachments/assets/25907be1-fde9-44b1-addf-510f30b3ff89)

3) **Start Autorouting**: Click the `Magic Wand` icon to begin the autorouting process.
   ![image](https://github.com/user-attachments/assets/e104cd3a-00b9-49a5-8f28-3b803e79d973)
   
4) **Monitor Progress**: Watch the routing progress visually in the board editor and numerically in the footer.
   ![image](https://github.com/user-attachments/assets/e553f98c-143d-46ea-8cc1-90348c9cc379)

5) **Completion**: Wait for the autorouter to finish all passes. This may take from a few minutes to several hours.

6) **Save Your Routed Board**: Go to `File` > `Save as...` to save your routed board as a `.ses` file.
   ![image](https://github.com/user-attachments/assets/355a1cb2-b2e8-46b5-aec0-4979748bd57a)

### Command Line Interface (CLI)

When using the CLI, you'll work with an input file (e.g., Specctra `.dsn`) exported from your EDA tool. Freerouting will autoroute unconnected nets and save the results for re-import into your EDA (e.g., as a Specctra `.ses` file).

Common command-line arguments:

- `-de [design input file]`: Load a Specctra design file (`.dsn`) at startup.
- `-do [design output file]`: Save a Specctra session file (`.ses`) after routing.
- `-l [language]`: Set the language (e.g., `en` for English, `de` for German).
- `-inc [net class names]`: Ignore specified net classes during routing.
- `-help`: Display help information.

**Example Command:**

```bash
java -jar freerouting-2.0.0.jar -de MyBoard.dsn -do MyBoard.ses -inc GND,VCC
```

This command routes `MyBoard.dsn`, ignores the `GND` and `VCC` net classes, and outputs `MyBoard.ses`.

For more details (including headless mode), see the [CLI documentation](docs/command_line_arguments.md).

### Freerouting API

Freerouting offers public API endpoints for PCB routing. The API root is `https://api.freerouting.app/v1`. Check the service status at [`/system/status`](https://api.freerouting.app/v1/system/status).

To access full functionality, request access on the [Freerouting website](https://www.freerouting.app/).

Please note that the Freerouting API and [its documentation](docs/API_v1.md) are in beta and may change.

## Running Freerouting using Java JRE

Installers are available for Windows x64, Linux x64, and macOS. For other systems, you can run the platform-independent `.jar` file if you have Java JRE installed.

**Steps:**

1. **Download the JAR File**: Get the latest `.jar` from the [Releases page](https://github.com/freerouting/freerouting/releases).

2. **Install Java JRE**: Download and install [Java JRE](https://adoptium.net/temurin/releases/).

   - Choose your operating system and architecture.
   - Select `JRE` as the package type.
   - Choose version `21`.

3. **Run Freerouting**:

   ```bash
   java -jar freerouting-2.0.0.jar
   ```

   **Note for macOS Users**: Launch Freerouting from the Terminal; starting from Finder is not supported.

## Contributing

We ❤️ all our contributors; this project wouldn't be possible without you!

- **Report Issues**: Help us by reporting [issues](https://github.com/freerouting/freerouting/issues).
- **Contribute Code**: Submit fixes and improvements via [pull requests](https://github.com/freerouting/freerouting/pulls).
- **Guidelines**: Check out our [Contribution Guide](docs/CONTRIBUTING.md) and [Developer Documentation](docs/developer.md).

## 🙏 Support the Project

**If you'd like to support the project financially, [please consider sponsoring me](https://github.com/sponsors/andrasfuchs).**

**Every contribution, no matter how small, is greatly appreciated!**

[![Sponsor](https://img.shields.io/badge/Sponsor%20me-✨-darkgreen?style=for-the-badge&logo=github)](https://github.com/sponsors/andrasfuchs)
