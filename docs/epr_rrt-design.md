# Rapid Responde Team rostering { #epr-rrt-design }

## Introduction

The DHIS2 Rapid Response Team (RRT) Roster is a flexible, digitised system that helps manage public health RRTs during non-emergencies and emergencies. Built on the DHIS2 platform, which is used in over 40 countries for health surveillance, the RRT Roster links emergency detection alerts deployable RRT response data. Developed to accelerate the deployment of the right personnel when public health threats arise, the RRT Roster aims to ensure faster, more informed, and coordinated responses. It is the first module of its kind to integrate responder data with surveillance systems, significantly reducing the time from detection to response.

Developed in collaboration with the US CDC’s Emergency Response Capacity Team (ERCT), the RRT Roster module uses DHIS2’s advanced data and analytics tools to streamline RRT workforce management. The DHIS2 system guides users through the RRT workforce cycle, from finding and selecting staff, notifying, and deploying staff for an emergency. This makes it faster and more efficient to mobilise skilled teams as well as support with workforce forecasting and deployment analysis.

The system follows a customizable six-step process: registration, vetting, responder selection, readiness tracking, deployment notifications, and post-deployment evaluation ensuring a systematic approach to managing emergency RRT responders. Data management capabilities such as ease of data entry, deployer selection, data validation, data shareability and analysis is also incorporated into the process. Other hallmark features include automated notifications and customizable visual dashboards and reporting tools further support managers and leadership make better decisions during an emergency.

This system design document offers a comprehensive overview of the ERR configuration within DHIS2, including detailed descriptions of the Tracker and dashboard functionalities, data management strategies, and implementation considerations. This document also does not consider the resources and infrastructure needed to implement such a system, such as servers, power, internet connections, backups, training and user support, which can be found in the DHIS2 Tracker Implementation Guide. The tracker was designed based on CDC RRT Roster and Management Guidelines.
Reference metadata for this toolkit is available at: [dhis2.org/metadata-downloads.](https://dhis2.org/metadata-downloads/)

### Acknowledgements

The rapid response team rostering tool was developed in partnership with CDC’s Emergency Response Capacity Team and HISP Uganda, with funding support through a cooperative agreement between HISP Centre and US CDC. We would like to extend our gratitude to the Ministries of Health in Uganda, DRC and Sierra Leone, CDC staff and the community who contributed their inputs, field experiences and expertise to the development of the tool.

## System design overview

### Use case

Rapid Response Teams (RRTs) are multidisciplinary teams that are trained and equipped to rapidly respond to public health emergencies.

A roster is a searchable system that stores and manages up-to-date information about Rapid Response Team (RRT) responders and members. It functions as a registry of specialists, tracking essential data such as skills, location, availability, and readiness requirements. This system allows for quick identification of staff with the necessary skills for deployment in public health emergencies. A roster may also be referred to as a personnel management or workforce system, designed to support efficient emergency response operations.

A well-maintained roster is crucial for efficient emergency preparedness and response. It ensures that health authorities can quickly mobilise qualified staff by having a comprehensive view of each RRT member's skills, training, and readiness status. Key benefits of having a roster include:

- Rapid identification of RRT members with the necessary skills and characteristics to meet the needs of an emergency response.
- Efficient mobilisation of surge staff with up-to-date contact information, ensuring immediate response.
- Monitoring and optimising the composition of the roster to ensure preparedness.
- Tracking readiness requirements such as completed training and certifications, ensuring staff are prepared for deployment

The RRT roster system supports the entire staffing and deployment process, from identifying and selecting candidates to tracking their readiness and managing their post-deployment evaluations. The system operates through a six-step workflow: RRT staffing recruitment and registration, vetting of candidates, selection of candidates, deployment readiness, deployment notification through pushed- and automated communications, and post-deployment evaluation including in-depth analysis dashboards and reporting.

This system is not only valuable during emergencies but also plays an essential role in preparedness during non-emergency periods. In preparedness mode, it allows users to monitor staff skills, track training completion, assess surge capacity readiness, and verify staff participation in previous responses. In response mode, the system facilitates the rapid selection and deployment of responders, monitors the availability of surge capacity, and checks the status of ongoing deployments.

By integrating robust data management, real-time communication, and in-depth workforce analysis, a roster maximises both response efficiency and effectiveness, ensuring a well-prepared and capable public health emergency response team.

### Intended users

When integrated into a national DHIS2 system, the DHIS2 Rapid Response Team (RRT) Roster can be effectively utilised at any level – national, subnational or district – during both routine (non-emergency) and emergency response phases. Key functions including roster management, candidate selection and workforce recruitment and verification can be adapted based on the size of the roster and needs of the response.

#### National and Subnational RRT Manager or RRT Roster Manager

At the national or subnational level, RRT Managers or RRT Roster Managers are responsible for ensuring the RRT Roster is effectively established and maintained during non-emergency periods and utilised during emergency periods. An RRT Manager or RRT Roster Manager my utilise the system during the non-emergency phase to:

- recruit potential responders
- identify, verify, and accept candidates for current and future roles
- monitor skills and experience of rostered staff for timeliness and accuracy
- track completed and needed trainings
- communicate with rostered staff about readiness

The suite of management tools provides valuable non-emergency insights such as submission metrics, application data, and automatic staff selection notifications. Furthermore, managers can generate reports on responder demographics, workforce skills capabilities, availability forecasting, and training and readiness requirement completion.

During an emergency or outbreak, RRT Managers or RRT Roster Managers can use the verification, search, and notification features to identify and select responders based on technical skills, language proficiency, availability, and location. Managers may also utilise the system to customise dashboards for management support and showcase surge capacity, deployments, and other critical response metrics for a variety of audiences including EOC staff and leadership.

#### District Level Workforce Managers

District Workforce Managers support their district’s roster during the non-emergency and emergency phases. Workforce Managers may use the system to select staff, ensure roster information is accurate and up to date, and ensure their district has sufficient personnel with specialised skills to support core RRT functions and surge capacity. During emergencies, District Managers may be responsible for deploying staff into the field, ensuring effective response at the local level.

#### Potential RRT Responders

Potential RRT Responders are staff who are applying to serve as part of a RRT roster. Potential responder candidates are dependent on country requirements but can include active full-time technical and operational staff, active part-time technical and operational staff, retired public health workers, Fellows, students, and non-technical surge support volunteers. Staff interested in joining the roster will use the system to complete the RRT Roster application. Application data will be dependent on the requirements of the country but may include demographics, education, technical and language skills, relevant training, and availability.

#### Selected RRT Responders

Once approved and selected, RRT Responders may use the system to update their personal information, such as demographics, education, and skills. Responders may also use the system to update training completions as well as readiness requirements including passports, medical clearances, and safety training. During an emergency, responders may receive notifications about potential deployments, and upon return from the field, may be asked to upload important documents such as handover notes and evaluation forms.

#### Supervisors and Managers

A requirement for RRT Responder acceptance, may include supervisory approval from the responder’s home program. Program supervisors and managers will use the system to review and approve staff to be considered to join the roster.

#### Emergency Coordination Unit (ECU) and Emergency Operations Center (EOC) Staff

Responsible ECU and EOC staff at national or subnational levels can use the system’s dashboard feature to assess surge capacity readiness during the watch or non-emergency phase and monitor availability and workforce allocation during a response. Customizable dashboards that are completed by the RRT Manager or RRT Roster Manager may provide ECU and EOC staff a visual overview of the roster’s size, skill availability and need, and potential surge staff, enabling the PHEOC or ECU staff to make informed planning, operational and logistics decisions prior to and in real-time during an emergency. 

#### Leadership

Leadership, including Ministry of Health and National Public Health Institute (NPHI) officials, can utilize the system’s dashboard and analytical tools to gain insights into workforce management. Customizable dashboards, created by RRT Managers or RRT Roster Managers, offer detailed visual reports on deployed and available personnel. Leadership can access this information to provide a comprehensive view of imminent, ongoing, and completed deployments, enabling informed decisions about critical human resource allocation and geographic positioning in the field.

The dashboard also offers key metrics, such as total person-days, roles filled and required, and average deployment length, helping leaders assess the effectiveness of RRT rostering. By tracking RRT roster non-emergency and emergency data, leadership can better understand the system’s impact on response efforts and the overall effectiveness of RRT programs during public health emergencies.

## Tracker

### Tracker program structure

The tracker program structure is as follows:

