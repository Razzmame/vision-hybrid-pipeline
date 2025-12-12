# Vision Hybrid Pipeline (C++ + Python)

Proyecto demostrativo de visión artificial en tiempo real con arquitectura híbrida:

- **C++ (OpenCV)**: captura de webcam, detección de objetos y recorte de ROIs.
- **Python (PyTorch)**: inferencia de un modelo ligero sobre cada ROI detectada.
- Comunicación local **C++ ↔ Python** mediante **ZeroMQ**.

## Objetivo
Construir un pipeline modular donde el rendimiento y la captura se gestionan en C++,
mientras que la parte de IA se desacopla en un servicio Python.

## Estructura del repositorio
- `cpp/`: aplicación C++ (webcam + detección + cliente ZMQ)
- `py/`: servidor Python (PyTorch) + entrenamiento
- `data/`: dataset local (no se versiona)
- `docs/`: documentación

## Requisitos
- Python 3.10+ (recomendado)
- CMake + compilador C++ 
- Webcam

## Instalación (Python)
1. Crear y activar entorno virtual:
   - Windows (PowerShell):
     ```powershell
     python -m venv .venv
     .\.venv\Scripts\Activate.ps1
     ```
   - Linux/macOS:
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```

2. Instalar dependencias:
   ```bash
   python -m pip install --upgrade pip
   pip install -r py/requirements.txt
