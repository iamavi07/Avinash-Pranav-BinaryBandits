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
Refer to the [VSDSquadron Mini Datasheet](https://www.vlsisystemdesign.com/docs/vsdsquadronminidatasheet/getting-started/) for detailed specifications and pin configurations.

<img width="550" alt="PowerPoint Slide Show  -  Presentation1 pptx 5_3_2024 12_29_08 PM" src="https://github.com/iamavi07/Avinash-Pranav-BinaryBandits/assets/170928924/22f2b3ee-58fa-40c5-9ac7-7c786cd3f145">

## Table for Pin Connection

| Function       | EMG Module Pin | VSDSquadron Mini Pin |
|----------------|-----------------|----------------------|
| Signal Output  | OUT             | Analog Pin (PA1)     |
| Power Supply   | VCC             | 3.3V                 |
| Ground         | GND             | GND                  |
| LED Control    | -               | Digital Pin (PD6)    |
| USART RX       | -               | PD6                  |
| USART TX       | -               | PD5                  |
| I2C SDA        | -               | PC1                  |
| I2C SCL        | -               | PC2                  |
| SPI SCK        | -               | PC5                  |
| SPI NSS        | -               | PC1                  |
| SPI MOSI       | -               | PC6                  |
| SPI MISO       | -               | PC7                  |


## Discussion
The discussion section interprets the results within the context of the research objectives and literature reviewed. Key findings, including muscle activation patterns, fatigue mechanisms, and neuromuscular coordination, are analyzed and discussed concerning existing theories and hypotheses. The implications of the findings for clinical diagnosis, rehabilitation strategies, and biomechanical modeling are explored, highlighting the potential applications of electromyography in various medical and engineering fields. Limitations of the study, including sample size constraints, electrode placement variability, and signal processing assumptions, are acknowledged, and future research directions are proposed to address these challenges and expand our understanding of electromyographic principles and practices.

## Results
The results of the electromyographic data analysis reveal significant insights into muscle activity patterns, signal characteristics, and neuromuscular function. Statistical analysis techniques, including mean amplitude analysis, root mean square analysis, and spectral analysis, provide quantitative measures of muscle activation, fatigue, and coordination. Additionally, visual representations, such as electromyogram waveforms and power spectral density plots, illustrate the temporal and spectral characteristics of the electromyographic signals. Comparative analysis with previous studies and normative data sets further elucidates the findings and their implications for clinical practice and research.


## Conclusion
In conclusion, the Electromyography (EMG) Research Project has provided valuable insights into the diagnostic capabilities and practical applications of electromyography in assessing muscle and nerve health. By employing a multidisciplinary approach that integrates theoretical knowledge, experimental techniques, and data analysis methods, this project has advanced our understanding of electromyographic principles and practices. The findings contribute to the growing body of literature on EMG technology and its potential for clinical diagnosis, rehabilitation, and biomedical engineering applications. Moving forward, continued research and innovation in electromyography are essential to unlock its full potential and improve healthcare outcomes for patients worldwide.



## References
[Provide a list of all sources cited in the research project, following a standardized citation format (e.g., APA, MLA). Ensure that all references are properly formatted and linked to their respective sources.]
