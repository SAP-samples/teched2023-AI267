[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-AI267)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-AI267)

# AI267 - Empower AI Embedding into SAP S/4HANA with ISLM 

## Description

This repository contains the material for the SAP TechEd 2023 session called **AI267 - Empower AI Embedding into SAP S/4HANA with ISLM**.<br>

In the rapidly evolving landscape of AI and machine learning, Intelligent Scenario Lifecycle Management (ISLM) has emerged as a critical framework that bridges the gap between data science endeavors and practical application development.<br>

ISLM plays a pivotal role in streamlining and optimizing the adoption of AI solutions, particularly within the SAP S/4HANA environment.
<br>
ISLM standardizes the integration and consumption of intelligent scenarios within SAP S/4HANA for both embedded as well as side-by-side scenarios.

ISLM can be leveraged to perform lifecycle operations, including (scheduled) (re-)training and deployment as well as activation of the model that should be consumed by the business application, directly within SAP S/4HANA. MLOps in ISLM is supported in the context of ML use case (Intelligent Scenario). 

## Overview
![](Overview.png) <br>

*   **Business User**:  The end user who interacts with the business application and uses the predictions from machine learning for the business purpose.<br>
*   **Business Administrator**:   A domain expert or analytics specialist, who can perform model trainings based on business context, evaluate model quality, and can activate a model for production usage.<br>
*   **Technical Administrator**:  A system administrator who can perform the configurations of connectivity between different entities as well as maintains the technical configurations of the system.<br>
*   **ABAP Developer**: A developer who can create ABAP artifacts required for Intelligent Scenario registration.<br>
*   **Intelligent Scenario Owner**: A owner who creates, reviews and publishes Intelligent Scenario.

<br>

This technical workshop will provide a deep dive into ISLM, focusing on its role as a catalyst for efficient AI content development and integration within SAP S/4HANA. The scope of this workshop includes:
1)	**Introduction to ISLM**: Understanding the fundamentals of ISLM and its significance in the AI ecosystem.
2)	**ISLM Integration**: Learning how ISLM standardizes the integration of intelligent scenarios within SAP S/4HANA.
3)	**Embedding AI into applications**: Understanding how application developers leverage ISLM for creating, registering, publishing, and managing scenarios.
4)	**Lifecycle Streamlining**: Discovering how ISLM simplifies and streamlines essential lifecycle operations, including training and deployment, to enhance efficiency.



By the end of this workshop, participants will gain a comprehensive understanding of how ISLM empowers organizations to smoothly transition from data science experimentation to real-world AI application development, all within the SAP S/4HANA environment.

**Note**: Data science and AI Content development is out of the scope of this session. In this workshop, we will explore ML lifecycle management process. 


## Requirements

There are no dedicated requirement for this exercise. But in case you want to gain some further knowledge around Intelligent Scenario Lifecycle Management please visit
[ISLM Community topic page](https://community.sap.com/topics/intelligent-scenario-lifecycle-management-s4hana)

## Exercises

In this workshop, our focus will be on a real-world use case example where a leading airline is looking to enhance its customer experience using AI-driven predictive technology. Data scientists are tasked with developing and testing machine learning models. After the data science phase, the challenge lies in seamlessly transitioning these models into production within the SAP S/4HANA landscape. This is where ISLM comes into play, offering a unified framework to simplify integration, streamline deployment, and manage the lifecycle of these intelligent scenarios.


1)	**Exercise 1 - Predict the airplane seats that are being occupied in the first class of a flight** <br/>
   In this specific use case, our goal is to forecast the occupancy of first-class seats on flights by harnessing the power of SAP HANA's Machine Learning (ML) algorithm.  
   
2)	**Exercise 2 - Predict the plane type of an aircraft** <br/>
   This use case involves predicting the aircraft type using the SAP BTP-based reusable SAP AI Business Service, Data Attribute Recommendation Service (DAR), powered by an ML algorithm.  

Navigate to the links below in specified sequence to get a detailed description and to perform each exercise.

1) [Exercise 1 - Predict the first class seats occupied of an aircraft](exercises/ex0/README.md)
2) [Exercise 2 - Predict the plane type of an aircraft](exercises/ex1/README.md)
3) [Summary](exercises/ex2/README.md)


## Additional Exercises
The following exercise is Advanced exercise where the Model Training can be scheduled automatically.

- [Schedule training](exercises/ex3/README.md)

## Additional Links
- [Attendee Details](exercises/ex5/README.md)
- [Additional Information](exercises/ex4/README.md)

  
## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
