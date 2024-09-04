# 🟢 Beamforming en el Dominio de la Frecuencia 🎧

Este repositorio contiene un sistema de procesamiento de señales de audio, diseñado para implementar **beamforming** en el dominio de la frecuencia. Este método mejora la señal de audio mezclada con ruido. Utilizamos múltiples señales de entrada de audio (captadas por micrófonos) para reforzar la señal deseada y reducir el impacto del ruido mediante técnicas de transformación de Fourier.

## 🔧 Funcionamiento

### 💻 Beamforming - Conceptos Clave
El **beamforming** es una técnica que permite combinar señales provenientes de diferentes fuentes (micrófonos) con diferentes retardos. Su objetivo es **amplificar** la señal deseada mientras **reduce** el ruido de fondo o interferencias no deseadas.

Se utiliza especialmente en sistemas de **procesamiento de audio** y **comunicaciones** para focalizar la captura de sonido desde una dirección específica, mejorando la claridad de la señal. El sistema ajusta los tiempos de retardo aplicados a cada señal en función de la distancia entre los micrófonos y la fuente de sonido, logrando una mayor **precisión espacial**.

### 🛠️ Cómo Funciona
1. **Captura de Audio**: Los micrófonos captan múltiples versiones de la misma señal de audio (por ejemplo, una conversación en una sala).
2. **Cálculo de Retardos**: Dependiendo de la distancia entre los micrófonos y la fuente, la señal llega con un ligero desfase a cada uno de los micrófonos. Este desfase se corrige calculando los **retardos**.
3. **Transformada de Fourier (FFT)**: Las señales de audio en el dominio del tiempo se convierten al **dominio de la frecuencia** utilizando la FFT.
4. **Ajuste de Retardos en Frecuencia**: En el dominio de la frecuencia, se aplican retardos precisos a cada micrófono para alinear las señales.
5. **Combinación de Señales**: Se promedian las señales ajustadas para obtener una única señal, la cual tiene un mejor **SNR** y menos ruido.
6. **Transformada Inversa (IFFT)**: Finalmente, se aplica la **IFFT** para obtener la señal combinada en el dominio del tiempo, que es la versión mejorada de la señal original.

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
La relación señal/ruido SNR se calcula en dB como:

<div align="center">
  <img src="https://github.com/user-attachments/assets/457f5a19-12d1-4020-a981-3234372344a8" width="400">
</div>

### ⚙️ Configuración del Sistema

## 🎤 Interfaz de Audio


### Interfaz de Audio: Behringer UMC202HD
<div align="center">
  <img src="https://github.com/user-attachments/assets/5d9ba424-a3c8-440a-93fe-ce6e960f4862" width="500">
</div>

### Micrófono 1: SM-8B Takstar
<div align="center">
  <img src="https://github.com/user-attachments/assets/b8158f7a-d3c0-43a7-949d-895c40707105" width="500">
</div>

### Micrófono 2: Shure
<div align="center">
  <img src="https://github.com/user-attachments/assets/7a0a38b7-1a2f-461d-9e25-141e2b9bfdb6" width="500">
</div>

### 📏 Distancias y Configuración

- **Distancia entre micrófonos**: 2 metros

- **Distancias entre las fuentes de sonido y micrófonos**:
  - **Fuente 1 (Santiago Mora)**:
    - Distancia a Micrófono 1: 3-4 metros
    - Distancia a Micrófono 2: 2 metros

  - **Fuente 2 (Laura Lopez)**:
    - Distancia a Micrófono 1: 2 metros
    - Distancia a Micrófono 2: 0.5 metro

### 📝 Descripción de la Configuración

La configuración del sistema está diseñada con rigurosidad y se detalla de la siguiente manera:

- **Micrófonos**: Se utilizan dos micrófonos, un SM-8B Takstar y un micrófono Shure.
- **Fuentes de Sonido**: Se han ubicado dos fuentes de sonido, cada una a diferentes distancias de los micrófonos para evaluar su impacto.
- **Distancias**: Las distancias entre los micrófonos y las fuentes de sonido se han definido con precisión para permitir una evaluación efectiva del beamforming. Las distancias varían desde 0.5 metros hasta 4 metros, proporcionando un rango completo para el análisis de la señal.

## 📊 Orientación Gráfica de Micrófonos y Fuentes

<div align="center">
  <img src="https://github.com/user-attachments/assets/379a93ff-aa06-4735-a3db-19f142a16a99" width="500">
</div>

### Descripción de la Configuración

La gráfica muestra la disposición de los micrófonos y fuentes de sonido en el entorno de prueba:

- **Micrófono 1 (SM-8B Takstar)** y **Micrófono 2 (Shure)** están ubicados a distancias específicas de las fuentes.
- **Fuente 1 (Santiago Mora)** y **Fuente 2 (Laura Lopez)** están situadas en distintas posiciones con respecto a los micrófonos.

📊 Configuración del Sistema de Adquisición
El sistema de adquisición de datos se describe con los siguientes criterios:

Criterios de Digitalización
## Frecuencia de Muestreo: 44,100 Hz
Esta frecuencia de muestreo es estándar para la mayoría de las grabaciones de audio digital, proporcionando una resolución adecuada para capturar detalles en el rango auditivo.

## Tiempo de Captura: 10 segundos
El tiempo de captura define la duración de la grabación. Se ha establecido un periodo de 10 segundos para asegurar que se capturen suficientes datos para el análisis.

## Número de Canales: Mono (1 canal)
El audio se ha grabado en formato mono, utilizando un único canal de audio.

## Profundidad de Bit: 16 bits
La profundidad de bit de 16 bits proporciona una calidad de audio adecuada para la mayoría de las aplicaciones.

## Grabación en Audacity
Los audios fueron grabados utilizando Audacity, una aplicación de edición de audio de código abierto. Esta herramienta permitió capturar las señales de los micrófonos en formato mono con los parámetros especificados, asegurando una grabación de alta calidad para el análisis posterior.

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


### 💡 Mejora del SNR
Tras aplicar el beamforming, se mide la mejora de la relación señal-ruido (SNR) para cada una de las señales procesadas.

### Ejemplo de salida del código:
```plaintext
Potencia de audio1: 0.003391749316358627
Potencia de audio2: 0.001645232435617203
Potencia de ruido: 4.226501938593041e-06
Potencia de audio mezclado: 0.005340377730770212
Potencia de la señal aislada: 0.0013344059571859226
SNR de audio1: 29.04 dB
SNR de audio2: 25.90 dB
SNR de audio mezclado: 31.02 dB
SNR de la señal aislada: 24.99 dB

```
📈 Detalles Técnicos del Script
1. Cálculo de Potencia
El cálculo de la potencia de cada señal (audio1, audio2, ruido) se realiza mediante la función calcular_potencia().

2. Transformada de Fourier (FFT)
Se aplica la FFT para convertir las señales del dominio temporal al dominio frecuencial, lo cual es clave para el beamforming basado en frecuencias.

3. Beamforming FFT
La función beamforming_fft() aplica el beamforming en el dominio de la frecuencia, calculando retardos y combinando señales de diferentes micrófonos para mejorar la señal deseada.

📊 Resultados
🖼 Gráficas Generadas

## Dominio del Tiempo

Se generan gráficos para visualizar las señales en el dominio del tiempo. Estos incluyen:
- **Audio 1**: La señal original captada por el primer micrófono.
- **Audio 2**: La señal original captada por el segundo micrófono.
- **Audio Mezclado**: La señal resultante de la combinación de audio1, audio2 y ruido.
- **Ruido**: La señal de ruido independiente.
- **Señal Beamformed**: La señal mejorada tras aplicar el beamforming.

Estas gráficas muestran la amplitud de las señales a lo largo del tiempo, permitiendo comparar la señal original, la mezclada con ruido y la procesada.



Estos gráficos permiten observar las diferencias en la amplitud de las frecuencias para cada señal, mostrando con claridad cómo el contenido frecuencial se ve afectado por el ruido y el procesamiento.
Se generan gráficos para las señales originales, el ruido, la señal mezclada con ruido y la señal procesada con beamforming.
![tiempo](https://github.com/user-attachments/assets/45385978-91c3-47aa-9caa-bc8db643435a)

#### Espectro de Frecuencia (FFT)
Se generan gráficos en escala semilogarítmica para representar el espectro de frecuencia de cada señal:
- **Audio 1**: El espectro de frecuencia de la primera señal.
- **Audio 2**: El espectro de frecuencia de la segunda señal.
- **Ruido**: El espectro de frecuencia del ruido.

## Gráficos en escala semilogarítmica de las señales y del ruido

Los gráficos de las señales y el ruido se representan en escala semilogarítmica para resaltar la amplitud de las distintas frecuencias. Esto permite observar con mayor claridad las diferencias en los espectros de cada señal procesada.
A continuacón encontraremos las gráficas del espectro de frecuencias para la señal del audio 1, audio 2 y el ruido.
![espectro](https://github.com/user-attachments/assets/d6604641-6126-4bbc-a0aa-b99788fa12a7)

En la siguiente imagén encontraremos las gráficas del espectro de frecuencias para la señal mezclada y la señal final o aislada.

![espectro mezcla y aislada](https://github.com/user-attachments/assets/7904d6bd-9ef3-4ab5-8abf-32d23e363087)

La señal mezclada y la señal aislada tienen un espectro muy similar pero magnitudes muy diferentes. La razón por la cual la magnitud de la señal aislada es menor (llegando a aproximadamente 800 en el gráfico) que la de la señal mezclada (que llega a 1750) tiene que ver con varios factores. Al aplicar beamforming, parte del ruido y otras señales fuera de la dirección focalizada se atenúan. Esto reduce la potencia total de la señal, lo que explica la disminución en la magnitud del espectro de frecuencia. En el proceso de beamforming, las fases de las señales se ajustan para que las señales provenientes de la dirección objetivo se sumen constructivamente, mientras que las señales que provienen de otras direcciones pueden sumarse destructivamente. Esto contribuye reducción en la magnitud total de la señal.
Cuando las señales de los micrófonos están en fase después de aplicar el retardo adecuado (delays), las componentes de frecuencia se alinean correctamente, y la magnitud de la señal resultante será mayor. Este es el proceso de suma constructiva que refuerza la señal de interés.
Pero cuando las señales de los micrófonos no están en fase correcta después de aplicar los retardos, entonces se cancelarán entre sí en ciertos puntos, reduciendo la magnitud de la señal resultante. Este es el proceso de suma destructiva.

En cuanto al espectro de frecuencia las señales son muy similares pues la señal aislada sigue capturando las frecuencias dominantes de los audios originales (audio 1 y 2), ya que el beamforming está diseñado para resaltar las señales deseadas y reducir el ruido.
Las frecuencias dominantes en los audios originales están presentes en ambas señales (mezclada y beamformed) porque el beamforming no elimina esas frecuencias, sino que las mantiene al intentar focalizarlas.


