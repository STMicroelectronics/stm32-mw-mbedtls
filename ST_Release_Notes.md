


# Release Notes for MbedTLS SW Pack


# Purpose

STM32Cube enables developers to achieve design success. With a comprehensive suite of professional development tools and embedded software components, STM32Cube allows developers to differentiate products, streamline design cycles, and reduce costs. STM32Cube ecosystem supports all design steps, including selection, configuration, development, debugging, programming, and monitoring.

The STM32Cube embedded software offer provides ready-to-use software components that can be added to a project. It includes STM32 peripheral driver APIs with two levels of abstraction, middleware, board drivers, and examples. There are several distribution channels, including the STM32CubeMX2 tool, the ST website, and GitHub. All embedded software comes with enhanced online documentation, with flowcharts and user sequences.

MbedTLS Pack is a STMicroelectronics initiative to split the [Mbed TLS library](https://www.trustedfirmware.org/projects/mbed-tls/) into software components.

This MW contains only software components that deal with cryptography, the TLS implementation, and sockets references.

More  documentation is available at [MbedTLS SW Pack online documentation](https://stm32cubedocs-dev.st.com/stm32cube-docs/mw-mbedtls/latest/en/index.html).


# Update History

<label for="collapse-section1" aria-hidden="true">__2.0.0 / 13-March-2026__</label>
<div>

## Main Changes

- First official release of MbedTLS SW Pack based on Mbed TLS 3.6.5.

## Contents

- Mbed TLS middleware modified by STMicroelectronics.

## Known Limitations

- The MbedTLS is not useful inside STM32CubeMX2 directly, but configurable through the STFCF middleware.

## Development Toolchains and Compilers

- IAR Embedded Workbench for ARM (EWARM) toolchain V9.60.3 + ST-LINK
- MDK-ARM Keil uVision V5.42
- STM32CubeIDE for Visual Studio Code (GCC13 compiler)

## Supported devices and boards

- STM32C5 series.

## Backward compatibility

- None.

## Dependencies

- STM32C5xx HAL Drivers V2.0.0

</div>



For complete documentation on STM32 Microcontrollers </mark> ,
visit: http://www.st.com/stm32
<abbr title="Based on template cx566953 version 2.1">Info</abbr>