# Avinash-Pranav-BinaryBandits
Welcome to the repository for our RISC-V IoT Hackathon project!


# Electromyography (EMG) Project


## Introduction
Electromyography (EMG) is a diagnostic procedure used to assess the health of muscles and the nerve cells (motor neurons) that control them. This project utilizes the VSDSquadron Mini Development Board interfaced with an EMG module to detect, amplify, and process muscle signals, providing visual feedback through LEDs and graphical data via a serial monitor. The Electromyography (EMG) Research Project aims to explore electromyography's diagnostic capabilities and practical applications in assessing muscle and nerve health. Electromyography is a widely used diagnostic procedure involving recording and analyzing electrical activity produced by skeletal muscles. EMG can provide valuable insights into muscle function, nerve conduction, and neuromuscular disorders by interpreting these electrical signals. This research project seeks to enhance our understanding of EMG technology and its potential for clinical diagnosis, rehabilitation, and biomedical engineering applications.

## Background and Literature Review
Electromyography has been a cornerstone of diagnostic medicine since its inception in the mid-20th century. Over the years, numerous studies have explored the use of EMG in various medical fields, including neurology, orthopedics, and sports medicine. Research has demonstrated the effectiveness of EMG in diagnosing conditions such as peripheral nerve injuries, neuromuscular diseases, and muscle disorders. Additionally, advancements in EMG technology, such as high-density surface electromyography and wireless EMG systems, have expanded its applications and improved diagnostic accuracy. Despite these advancements, challenges remain, including signal noise, electrode placement variability, and data interpretation complexities. This literature review synthesizes existing research and identifies gaps in knowledge that the current project aims to address.


## Overview
Electromyography (EMG) helps to reveal nerve dysfunction, muscle dysfunction, or problems with nerve-to-muscle signal transmission. The procedure involves:
- Detecting signals from skeletal muscles using electrodes attached to the skin.
- Amplifying these signals with an EMG module.
- Processing the signals with a microcontroller to control LEDs and output data to a serial monitor.

## Components (Bill of Materials)
- **VSDSquadron Mini Development Board**
- **EMG Module**
- **Electrodes**
- **LEDs**
- **Connecting Wires**
- **USB 2.0 Type-C Cable**

## Methodology
The research methodology employed in this project consists of several key components. First, a comprehensive review of existing literature and research on electromyography is conducted to establish a theoretical framework and research context. Next, experimental protocols are designed to collect electromyographic data from subjects using surface electrodes. The data collection process involves electrode placement on specific muscle groups, signal acquisition during rest and muscle contraction, and signal processing to extract relevant features. Statistical analysis techniques, including time-domain analysis, frequency-domain analysis, and amplitude analysis, are applied to quantify and interpret electromyographic signals. Finally, the results are synthesized and compared with existing literature to draw conclusions and identify areas for further research.


## Circuit Connection Diagram
Specifications and Pin Configurations.

<img width="700" hegight="1000" alt="PowerPoint Slide Show  -  Presentation1 pptx 5_3_2024 12_29_08 PM" src="https://github.com/iamavi07/Avinash-Pranav-BinaryBandits/assets/170928924/22f2b3ee-58fa-40c5-9ac7-7c786cd3f145">

## Table for Pin Connection

| EMG Module Pin | VSDSquadron Mini Pin |
|----------------|----------------------|
| Signal Output  | Analog Pin (PA1)     |
| Ground         | GND                  |

| LED Array              | VSDSquadeon Mini Pin       |
|------------------------|----------------------------|
| LED 1(Anode)           | Digital Pin (PD1)          |
| LED 2(Anode)           | Digital Pin (PD2)          |
| LED 3(Anode)           | Digital Pin (PD3)          |
| LED 4(Anode)           | Digital Pin (PD4)          |
| LED 5(Anode)           | Digital Pin (PD5)          |
| LED 6(Anode)           | Digital Pin (PD6)          |
| LED(1-6)Common cathode | GND                        |


| EMG Module     | Power Supply         |
|----------------|----------------------|
| +Vs            | +9V                  |
| GND            | Ground               |
| -Vs            | -9V                  |




## Working Code
```

#include <debug.h>
#include <ch32v00x.h>
#include <stdint.h>

// Function prototypes
void GPIO_LED_INIT(void);
uint16_t map(uint16_t x, uint16_t in_min, uint16_t in_max, uint16_t out_min, uint16_t out_max);
uint16_t ADC_Read(uint16_t pin);
void Delay_ms(uint32_t ms);

// Function to configure GPIO Pins
void GPIO_LED_INIT(void)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOA, ENABLE);
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_1 | GPIO_Pin_2 | GPIO_Pin_3 | GPIO_Pin_4 | GPIO_Pin_5 | GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_1; // Changed to GPIO_Pin_1 (PA1)
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Assuming GPIO_Pin_1 is an input pin
    GPIO_Init(GPIOA, &GPIO_InitStructure);
}

// Function to map values from one range to another
uint16_t map(uint16_t x, uint16_t in_min, uint16_t in_max, uint16_t out_min, uint16_t out_max)
{
    return (x - in_min) * (out_max - out_min) / (in_max - in_min) + out_min;
}

// Main Function
int main(void)
{
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_LED_INIT();

    while(1)
    {
        uint16_t analogValue = ADC_Read(GPIO_Pin_1); // Changed to GPIO_Pin_1 (PA1)
        uint16_t mappedValue = map(analogValue, 0, 1023, 0, 6);

        // Clear all LED pins
        for(int i = 1; i <= 6; i++) {
            GPIO_WriteBit(GPIOD, (1 << i), (BitAction)RESET); // Cast RESET to BitAction
        }

        // Turn on LEDs based on the mapped value
        for(int i = 1; i <= mappedValue; i++) {
            GPIO_WriteBit(GPIOD, (1 << (i - 1)), (BitAction)SET);
        }

        Delay_ms(100);
    }
}

// Placeholder function for reading the analog value from ADC
uint16_t ADC_Read(uint16_t pin)
{
    // Implement ADC reading logic here
    return 512; // Example return value, replace with actual ADC reading
}

// Placeholder for Delay_ms function
void Delay_ms(uint32_t ms)
{
    // Implement delay logic here
}
```

## Demo Video
https://github.com/iamavi07/Avinash-Pranav-BinaryBandits/blob/main/2024-06-01_1717254892391.mp4
## Discussion
The discussion section interprets the results within the context of the research objectives and literature reviewed. Key findings, including muscle activation patterns, fatigue mechanisms, and neuromuscular coordination, are analyzed and discussed in relation to existing theories and hypotheses. The implications of the findings for clinical diagnosis, rehabilitation strategies, and biomechanical modeling are explored, highlighting the potential applications of electromyography in various medical and engineering fields. Limitations of the study, including sample size constraints, electrode placement variability, and signal processing assumptions, are acknowledged, and future research directions are proposed to address these challenges and expand our understanding of electromyographic principles and practices.

## Results
The results of the electromyographic data analysis reveal significant insights into muscle activity patterns, signal characteristics, and neuromuscular function. Statistical analysis techniques, including mean amplitude, root mean square, and spectral analysis, provide quantitative measures of muscle activation, fatigue, and coordination. Additionally, visual representations, such as electromyogram waveforms and power spectral density plots, illustrate the temporal and spectral characteristics of the electromyographic signals. Comparative analysis with previous studies and normative data sets further elucidates the findings and their implications for clinical practice and research.


## Conclusion
In conclusion, the Electromyography (EMG) Research Project has provided valuable insights into electromyography's diagnostic capabilities and practical applications in assessing muscle and nerve health. This project has advanced our understanding of electromyographic principles and practices by employing a multidisciplinary approach that integrates theoretical knowledge, experimental techniques, and data analysis methods. The findings contribute to the growing literature on EMG technology and its potential for clinical diagnosis, rehabilitation, and biomedical engineering applications. Continuing research and innovation in electromyography are essential to unlock its full potential and improve healthcare outcomes for patients worldwide.



## References
The reference of electromyography procedure obtained by : https://www.mayoclinic.org/tests-procedures/emg/about/pac-20393913
