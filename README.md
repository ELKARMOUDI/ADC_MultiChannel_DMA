# STM32F411 Discovery Dual-Potentiometer ADC with DMA

![STM32F411](https://img.shields.io/badge/STM32F411-Discovery-blue) 
![ADC](https://img.shields.io/badge/ADC1-MultiChannel_DMA-green)


<img src="https://github.com/user-attachments/assets/a9c634d4-bbe5-4a28-812a-dc3c055f5ad3" width="600" alt="29643BCF-3B0C-4603-89FA-7B0E55DE1A09">


Simultaneous reading of two potentiometers using ADC1 with DMA.

## Features
- **Dual-Channel** ADC (PA1 & PA2)
- **DMA-Enabled** continuous conversions
- **96MHz System Clock** (HSI-based PLL)
- **480-cycle Sampling** for high accuracy
- **Zero CPU Overhead** data collection

## Hardware Setup
| Component | Connection | Discovery Pin |
|-----------|------------|---------------|
| Potentiometer 1 | VCC → 3.3V | - |
| | GND → GND | - |
| | WIPER → PA1 | CN5 pin 34 (A1) |
| Potentiometer 2 | VCC → 3.3V | - |
| | GND → GND | - |
| | WIPER → PA2 | CN5 pin 38 (A2) |

## Technical Details
### ADC/DMA Configuration 
```c
ADC Clock: 12MHz (24MHz PCLK2 / 2)
Channels: 
  - ADC1_IN1 (PA1) - Rank 1
  - ADC1_IN2 (PA2) - Rank 2
Sampling: 480 cycles per channel
DMA: Circular mode, 32-bit transfers
