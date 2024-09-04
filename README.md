# 🟢 Beamforming en el Dominio de la Frecuencia 🎧

Este repositorio contiene un sistema de procesamiento de señales de audio, diseñado para implementar **beamforming** en el dominio de la frecuencia. Este método mejora la señal de audio mezclada con ruido. Utilizamos múltiples señales de entrada de audio (captadas por micrófonos) para reforzar la señal deseada y reducir el impacto del ruido mediante técnicas de transformación de Fourier.

## 📂 Archivos en el Proyecto

- `audio1.wav` - Primer archivo de audio de entrada.
- `audio2.wav` - Segundo archivo de audio de entrada.
- `ruido.wav` - Archivo de ruido que será sumado a los audios de entrada.
- `audio_mezclado.wav` - Resultado de mezclar las señales de audio con el ruido.
- `audio_beamformed.wav` - Archivo resultante tras aplicar beamforming.

## 📊 Funcionalidades del Código
- **Mezcla de Audio**: Las señales de audio (audio1 y audio2) se mezclan con ruido para simular una señal contaminada.
- **Beamforming FFT**: Se aplica beamforming en el dominio de la frecuencia utilizando la Transformada Rápida de Fourier (FFT) para aislar la señal deseada.
- **Cálculo de Potencia y SNR**: Se calculan las potencias y la relación señal/ruido (SNR) de cada señal antes y después de aplicar beamforming.
- **Visualización**: Gráficas en escala semilogarítmica del espectro de frecuencia de las señales procesadas.

## 🚀 Ejecución del Proyecto

1. Coloca los archivos de audio en la carpeta `audios/` dentro del directorio raíz del proyecto.
2. Asegúrate de tener instaladas las siguientes dependencias:
   ```bash
   pip install numpy matplotlib soundfile

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

📊 Resultados
🖼 Gráficas Generadas
## Dominio del Tiempo:
Se generan gráficos para las señales originales, la señal mezclada con ruido y la señal procesada con beamforming.
## Espectro de Frecuencia (FFT):
## Gráficos en escala semilogarítmica de las señales y del ruido

Los gráficos de las señales y el ruido se representan en escala semilogarítmica para resaltar la amplitud de las distintas frecuencias. Esto permite observar con mayor claridad las diferencias en los espectros de cada señal procesada.

### 💡 Mejora del SNR
Tras aplicar el beamforming, se mide la mejora de la relación señal-ruido (SNR) para cada una de las señales procesadas.

### Ejemplo de salida del código:
```plaintext
Potencia de audio1: 0.0012
Potencia de audio2: 0.0010
Potencia de ruido: 0.0003
Potencia de audio mezclado: 0.0035
Potencia de la señal aislada: 0.0021

SNR de audio1: 12.33 dB
SNR de audio2: 11.67 dB
SNR de audio mezclado: 9.32 dB
SNR de la señal aislada: 15.21 dB

```

🎧 Salida de Audio
El archivo audio_beamformed.wav es el resultado del proceso de beamforming, y presenta una mejora en la claridad de la señal en comparación con el audio mezclado.

📈 Detalles Técnicos del Script
1. Cálculo de Potencia
El cálculo de la potencia de cada señal (audio1, audio2, ruido) se realiza mediante la función calcular_potencia().

2. Transformada de Fourier (FFT)
Se aplica la FFT para convertir las señales del dominio temporal al dominio frecuencial, lo cual es clave para el beamforming basado en frecuencias.

3. Beamforming FFT
La función beamforming_fft() aplica el beamforming en el dominio de la frecuencia, calculando retardos y combinando señales de diferentes micrófonos para mejorar la señal deseada.
