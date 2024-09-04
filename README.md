# Analisis-en-frecuencia-de-voz
# Beamforming en el Dominio de la Frecuencia

Este proyecto implementa un sistema básico de **beamforming** en el dominio de la frecuencia, utilizando señales de audio. El objetivo es mejorar la relación señal-ruido (SNR) de señales de audio mezcladas con ruido.

## Archivos de Audio Utilizados

- `audio1.wav`: Primer audio de entrada.
- `audio2.wav`: Segundo audio de entrada.
- `ruido.wav`: Ruido que será añadido a los audios.
- `audio_mezclado.wav`: Archivo resultante de la mezcla de las señales de audio y el ruido.
- `audio_beamformed.wav`: Archivo con la señal mejorada mediante beamforming.

## Formulación Matemática

### 1. **Cálculo de Potencia**

La potencia de una señal \(x(t)\) se calcula como el promedio de los cuadrados de las muestras de la señal:

\[
P_x = \frac{1}{N} \sum_{n=0}^{N-1} x(n)^2
\]

Donde \(x(n)\) es el valor de la señal en el tiempo \(n\) y \(N\) es la cantidad de muestras.

### 2. **Transformada de Fourier (FFT)**

La **Transformada Rápida de Fourier (FFT)** se usa para convertir una señal del dominio del tiempo al dominio de la frecuencia:

\[
X(k) = \sum_{n=0}^{N-1} x(n) e^{-2\pi i k n / N}
\]

Donde \(X(k)\) representa las componentes de frecuencia de la señal.

### 3. **Beamforming**

El beamforming se basa en calcular los retardos en función de las posiciones relativas de los micrófonos y las frecuencias presentes en la señal:

\[
\text{Delay}(f, d) = e^{-2\pi i f \frac{d}{v}}
\]

Donde \(d\) es la distancia entre los micrófonos y \(v\) la velocidad del sonido (343 m/s).

### 4. **Relación Señal-Ruido (SNR)**

El **SNR** es la proporción entre la potencia de la señal y la del ruido, calculada en decibelios (dB):

\[
\text{SNR} = 10 \log_{10} \left( \frac{P_{\text{señal}}}{P_{\text{ruido}}} \right)
\]

## Instalación

Para ejecutar el código, necesitas tener instaladas las siguientes bibliotecas de Python:

```bash
pip install numpy soundfile matplotlib
