# Non-Invasive Blood Glucometer

## Table of Contents
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Problem Definition](#problem-definition)
- [Objectives](#objectives)
- [Methodology](#methodology)
- [Components Used](#components-used)
- [Working](#working)
- [Results and Discussion](#results-and-discussion)
- [Output](#output)
- [Discussion and Future Scope](#discussion-and-future-scope)
- [Advantages](#advantages)
- [Conclusion](#conclusion)
- [Contributors](#contributors)

## Abstract
Diabetes, a chronic condition characterized by elevated blood sugar levels, particularly type 2 diabetes, has seen a significant rise globally over recent decades, impacting individuals across various populations. Diabetes is associated with various health complications, including cardiovascular diseases, kidney failure, and neuropathy. Lifestyle factors such as diet, exercise, and weight management play a significant role in managing diabetes and preventing complications. Access to affordable treatment, notably insulin, is crucial in managing diabetes and reducing associated risks. Monitoring blood sugar levels is crucial, and while both invasive and non-invasive methods exist, techniques like near-infrared (NIR) spectroscopy offer a more comfortable option.

## Introduction
Global advancements in patient monitoring systems, particularly multi-parameter devices, are being made with blood glucose (diabetics) as a primary focus to improve health maintenance. When combined with strong communication abilities, these technologies can promote healthier lifestyles in a manner similar to actual healthcare professionals. Diabetes, often known as diabetes mellitus, is a chronic illness in which the insulin hormone controls blood sugar levels. Low insulin production results in raised blood sugar levels, known as hyperglycemia, which can lead to problems with the kidneys, eyes, nerves, teeth, and heart. Hypoglycemia is another problem that affects about 387 million people globally. Timely treatment and glucose regulation are essential for assessing the quality of blood glucose monitoring.

## Problem Definition
Diabetes is a chronic health condition characterized by elevated levels of sugar in the blood, leading to severe damage to the heart, blood vessels, eyes, kidneys, and nerves over time. The most common form is type 2 diabetes, often diagnosed in adults, where the body either resists the effects of insulin or does not produce enough of it. Over the past 30 years, the number of people with type 2 diabetes has significantly increased globally, affecting nations with various income levels. Type 1 diabetes, formerly referred to as juvenile or insulin-dependent diabetes, is another form where the pancreas fails to generate enough insulin. Affordable treatment, especially insulin, is important for the well-being of people with diabetes. The global objective is to reduce the growth of diabetes and obesity by 2025.

## Objectives
The primary objectives of this project are:
- To develop a monitoring system that does not require invasive methods, ensuring a pain-free experience for the user.
- To provide a cost-effective and real-time blood glucose monitoring device.
- To design a portable device to monitor blood glucose levels.

## Methodology
The methodology includes the following steps:
- Research Design: Using NIR spectroscopy for non-invasive glucose measurement.
- Data Collection and Analysis: Collecting data and analyzing it to develop a reliable monitoring system.
- Block Diagram and Circuit Diagram: Designing the system using appropriate components.
- Ethical Considerations: Ensuring the ethical use of the device.
- Limitations: Addressing any limitations in the current design.

## Components Used
The following components were used in the project:
1. **Arduino Uno/ESP8266**: Microcontroller boards for prototyping and wireless connectivity.
2. **LM358**: Dual-operational amplifier for analog signal processing.
3. **Resistors**: Various values for controlling voltage and signal levels.
4. **Capacitors**: For filtering, decoupling, and energy storage.
5. **MAX30102**: Integrated pulse oximeter and heart-rate sensor module.
6. **LCD Display**: For output display.

## Working
The device uses NIR spectroscopy to measure blood glucose levels. The NIR LED and photodetector are used to detect glucose concentration through diffused reflectance. The Arduino processes the photodiode output to calculate glucose levels, which are then displayed on an LCD screen for real-time monitoring.

## Results and Discussion
The designed circuit for noise cancellation and signal amplification was simulated using Multisim for various values of the photodiode, resulting in precise voltage values. Regression analysis using MATLAB helped derive a polynomial equation relating analog voltage and glucose levels, leading to accurate glucose concentration measurements.

## Output
The output includes waveforms and glucose values derived from the simulations and real-time measurements.

## Discussion and Future Scope
Future improvements can include enhancing the device's accuracy and reliability, making it more compact, and integrating it with mobile applications for better user interface and data management.

## Advantages
- **Non-invasive**: Ensures a pain-free experience for users.
- **Real-time Monitoring**: Provides immediate glucose level readings.
- **Portable**: Easy to carry and use anywhere.

## Conclusion
This project successfully developed a non-invasive blood glucose monitoring system using NIR spectroscopy. The device provides a cost-effective, real-time, and portable solution for diabetes management.

## Contributors
- **Aaron Dsouza (aarudsouza2002@gmail.com)**


