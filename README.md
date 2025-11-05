# Audiotate: Audio segments validator annotator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Gradio](https://img.shields.io/badge/Framework-Gradio-orange.svg)](https://gradio.app/)

## Overview

**Audiotate: Audio Segments Validator–Annotator** is a lightweight, **Python-based application** built with **Gradio** that enables users to efficiently **annotate and validate short audio segments**.  
It is designed for **researchers, ecologists, sound analysts, and developers** who need a simple, intuitive interface to review, correct, or label short audio clips—either unlabeled samples or predictions from deep learning models (e.g., BirdNET, Perch, or any other classifiers).

Audiotate allows users to:
- Load a structured folder of audio files.
- Listen to each audio segment.
- View its spectrogram.
- Assign or edit labels (either predefined or custom).
- Add optional comments.
- Save all annotations to a **CSV file** for downstream analysis or model training.

Although originally inspired by bird sound validation workflows with BirdNET, **Audiotate** is **domain-agnostic**—it can be applied to any sound classification task, from terrestrial ecology, underwater monitoring to urban soundscape analysis.

### Citation

If you use this application, please cite the software:

```
@misc{BirdNETPredictionsValidator2024,
  author       = {Márquez-Rodríguez, Alba},
  title        = {Audiotate: Audio segments validator annotator},
  year         = {2024},
  howpublished = {\url{https://https://github.com/SEANIMALMOVE/Audiotate_Audio-Segments-Validator-Annotator}},
  note         = {Version 1.6, accessed: YYYY-MM-DD},
}
```

A software manuscript is being prepared with the name *Audiotate: A GUI tool for human annotation and validation of audio segments*.

<!--
> Márquez-Rodríguez, Alba, Mohedano-Munoz, M. Á., Marín-Jiménez, M. J., Santamaría-García, E., Bastianelli, G., Jordano, P., & Mendoza, I.  
> **A Bird Song Detector for improving bird identification through Deep Learning: a case study from Doñana**  
> Ecological Informatics, 2025, 103254. https://doi.org/10.1016/j.ecoinf.2025.103254
-->

<!--📄 [Read the article](https://doi.org/10.1016/j.ecoinf.2025.103254)-->

- [Download Linux Installer](https://github.com/GrunCrow/BirdNET-PredictionsValidator-App/releases/download/v1.7/app_linux)
- [Download Windows Installer](https://github.com/GrunCrow/BirdNET-PredictionsValidator-App/releases/download/v1.7/app_windows.exe)

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
  - [Executable Files](#executable-files)
    - [Installation on Windows](#installation-on-windows)
    - [Installation on Linux](#installation-on-linux)
    - [Running the Application](#running-the-application)
  - [Repository use](#repository-use)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Usage](#usage)
  - [Using the GUI](#using-the-gui)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- **Audio Playback:** Listen to `.wav` or `.mp3` files directly in the browser.
- **Spectrogram Visualization:** Each segment is displayed as a mel-spectrogram using `librosa`.
- **Annotation & Validation:** Assign labels via buttons or free text; ideal for both annotation and verification.
- **Comments:** Add notes or context to each sample.
- **CSV Export:** Save all annotations and comments in a structured `.csv` file.
- **Session Resume:** Continue where you left off—reload previous annotation sessions.
- **Cross-Platform:** Works on Windows, Linux, and macOS (through the web browser).
- **No Installation Required:** Executable versions available for easy use.

## Getting Started

### Executable Files

You can run Audiotate directly without installation by downloading the standalone executable:

- [⬇️ Download for Windows](https://github.com/SEANIMALMOVE/BirdNET-PredictionsValidator-App/releases/download/v1.7/app_windows.exe)
- [⬇️ Download for Linux](https://github.com/SEANIMALMOVE/BirdNET-PredictionsValidator-App/releases/download/v1.7/app_linux)
- [⬇️ Download Underwater Acousitcs App adaptation for Windows](https://github.com/SEANIMALMOVE/Audiotate_Audio-Segments-Validator-Annotator/releases/download/v1.7/Underwater.Acoustics.Validator.exe)

The following video tutorial demonstrates how to use the BirdNET Predictions Validator App executable file on a Windows system. It covers the installation process, how to run the application, and a walkthrough of the graphical user interface (GUI).

[![Youtube Video Tutorial](assets/Docs/Images/video_tutorial.png)](https://youtu.be/BJYW3RqA2uQ)

#### Installation on Windows

1. **Download the Installer**: Download the Windows installer from the [Download Windows Installer](https://github.com/GrunCrow/BirdNET-PredictionsValidator-App/releases/download/v1.3/app_windows.exe) link.
2. **Run the Installer**: Double-click the downloaded `.exe` file and follow the on-screen instructions to install the application.

#### Installation on Linux

1. **Download the Installer**: Download the Linux installer from the [Download Linux Installer](https://github.com/GrunCrow/BirdNET-PredictionsValidator-App/releases/download/v1.3/app_linux) link.
2. **Run the Installer**: Run the following command:

```bash
./app_linux
```

#### Running the Application

1. **Create a `Bird Vocalization Sample` Folder**: In the same directory as the executable file, create a folder named `Bird Vocalization Sample`. Within this folder, create subfolders named after each bird species (using the BirdNET format). Populate these subfolders with `.WAV` files containing sample vocalizations for each species. While this step is not mandatory, it is highly recommended as it allows the application to display sample vocalizations from your dataset alongside the data you are validating.
2. **Select Audios Folder**: Choose the folder containing the audio files you want to validate.

For a detailed walkthrough, please refer to the video tutorial above.

### Repository use

#### Prerequisites

- Python 3.7 or higher
- Gradio
- Pandas
- Librosa (for audio processing)
- See more in the `environment_linux.yml`

#### Installation

1. Clone the repository:

```bash
git clone https://github.com/GrunCrow/BirdNET-PredictionsValidator-App.git
cd BirdNET-PredictionsValidator-App
```

2. Install the required packages:

```bash
pip install -r requirements.txt
```

#### Usage

1. Run the application:

```bash
python app.py
```

2. Open the provided link in your web browser to access the app.

### Using the GUI

1. **Prepare your audio files** in the following format:

```python
root_folder/
├── Specie1/
│ ├── audio1.wav
│ └── audio2.WAV
├── Specie2/
│ ├── audio1.wav
│ └── audio2.WAV
...
```

2. **Select Audios Folder**: Choose the folder containing the audio files.

![Load Audio Files](assets/Docs/Images/load_audio_files.png)

3. **Visualize and Play Audio**: View and listen to the audio segments. The app provides a visual representation of audio segments for easy navigation. You can listen to the audio files directly within the app.

![Visualize and Play Audio](assets/Docs/Images/visualize_segments.png)

4. **Validate Predictions**: Mark the prediction as correct or incorrect.

![Validate Predictions](assets/Docs/Images/validate.png)

5. **Download CSV**: Export the validation results as a CSV file for further analysis.

## Contributing

Contributions are welcome! If you have suggestions for improvements or find bugs, please create an issue or submit a pull request. Your contributions can help make this app better for everyone.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

Author: Alba Márquez-Rodríguez

If you have any questions or need further assistance, please feel free to contact me in the Issues of the repository.

> Audiotate was developed as part of ongoing research into AI-assisted acoustic analysis and validation tools for ecological monitoring and sound classification.
