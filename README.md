# Analisis-en-frecuencia-de-voz
🟢 Beamforming en el Dominio de la Frecuencia 🎧
Este repositorio contiene un sistema de procesamiento de señales de audio, diseñado para implementar beamforming en el dominio de la frecuencia, que mejora la señal de audio mezclada con ruido. Utilizamos múltiples señales de entrada de audio (captadas por micrófonos) para reforzar la señal deseada y reducir el impacto del ruido mediante técnicas de transformación de Fourier.
📂 Archivos en el Proyecto
audio1.wav - Primer archivo de audio de entrada.
audio2.wav - Segundo archivo de audio de entrada.
ruido.wav - Archivo de ruido que será sumado a los audios de entrada.
audio_mezclado.wav - Resultado de mezclar las señales de audio con el ruido.
audio_beamformed.wav - Archivo resultante tras aplicar beamforming.
🚀 Instalación y Configuración
Requisitos Previos
Asegúrate de tener Python instalado. Instala las dependencias necesarias ejecutando el siguiente comando:
pip install numpy soundfile matplotlib
## Estructura del Proyecto
.
├── audios/
│   ├── audio1.wav
│   ├── audio2.wav
│   ├── ruido.wav
├── beamforming.py
├── README.md
## Ejecución del Código
Coloca los archivos de audio (audio1.wav, audio2.wav, ruido.wav) en la carpeta audios/.
Ejecuta el archivo beamforming.py desde la terminal:
python beamforming.py
El script procesará las señales de audio y generará las gráficas, además de almacenar el archivo audio_beamformed.wav con la señal aislada mediante beamforming.
🔧 Funcionamiento
💻 Beamforming - Conceptos Clave
El beamforming es una técnica que permite combinar señales provenientes de diferentes fuentes (micrófonos) con diferentes retardos, amplificando la señal deseada y reduciendo el ruido de fondo.

## 🧮 Fórmulas Importantes

### Potencia de la Señal:
La potencia de una señal \( x(n) \) se calcula con la fórmula:

<div align="center">
  <img src="https://github.com/user-attachments/assets/469cbc91-d496-480f-96cf-6203e27ecb28" width="400">
</div>

Donde:

- \( P_x \) es la potencia.
- \( x(n) \) es la señal en el instante \( n \).
- \( N \) es el número total de muestras.

---

### Transformada Rápida de Fourier (FFT):
Para pasar una señal del dominio del tiempo al dominio de la frecuencia, se utiliza la FFT:

<div align="center">
  <img src="https://github.com/user-attachments/assets/bed3d240-8288-4c17-b333-34b90f550fc6" width="500">
</div>

### Beamforming (Retardo de la Señal):
El retardo aplicado a las señales captadas por micrófonos se calcula en función de la distancia \( d \) entre ellos y la velocidad del sonido \( v \):

<div align="center">
  <img src="https://github.com/user-attachments/assets/4fb54c1e-8170-474b-a2ab-9179cabf4c27" width="400">
</div>

### Relación Señal/Ruido (SNR):
La relación señal/ruido \( \text{SNR} \) se calcula en dB como:

<div align="center">
  <img src="https://github.com/user-attachments/assets/457f5a19-12d1-4020-a981-3234372344a8" width="400">
</div>


