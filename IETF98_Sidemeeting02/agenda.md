# Draft Agenda of Network Slicing side meeting at IETF98

- Location: Room Vevey 1/2, 
- Date/Time: 2017.03.27, 18:15-21:15

### Scope of the NS meeting: 
Present and discuss use cases, architecture and identify technical problems to be address by future work at IETF. The place of such work either as part of re-scoping some exiting WG or a new dedicated WG is not part of this meeting.

### Presentation 01: Agenda bash
    Meeting Organisers: Alex Galis – UCL, J. Dong – Huawei, K. Makhijani-Huawei, Stewart Bryant – Huawei
    Chairs of the meeting: Stewart Bryant – Huawei, Alex Galis - UCL
    Duration: 1-3 mins

### Presentation 02: Introductory Document and Revised Problem Statement walk through
     Presenter: Alex Galis - UCL/Stewart - Huawei
     Duration:  10 mins + 5 mins Q&A
     Abstract: This presentation represents an introduction to the motivation and SoA review for NS work ares including a revision of NS problem statement derived from the analysis of the technical gaps in IETF protocols ecosystem related to NS capabilities, functions, APIs and operations.
     https://tools.ietf.org/html/draft-gdmb-netslices-intro-and-ps-02

**I. Towards NS Use Cases**
### Presentation 03: 5G Network Slicing - 3GPP Use Case background
     Presenter: Xavier DeFoy -InterDigital
     Duration:  10 mins + 5 mins Q&A
     Abstract: This presentation describes work conducted at the 3GPP standard organization on 5G Network Slicing, and attempts to derive high level requirements and context information for future Network Slicing work in IETF.
     https://datatracker.ietf.org/doc/html/draft-defoy-netslices-3gpp-network-slicing

### Presentation 04: Generalized Market/Service Verticals with Network Slicing Use cases
    Presenter: K. Makhijani- Huawei/J. Dongjie - Huawei
    Duration:  10 mins + 5 mins Q&A
    Agenda: Present a generalized structure of use case categories and corresponding requirements. Both new and traditional services and use cases are described.
    https://tools.ietf.org/html/draft-qin-netslices-use-cases-00


### Presentation 05: An ICN service delivery prototype using slices.
    Presenter: Ravi Ravindran - Huawei
    Duration: 10 mins + 5 mins Q&A
    Abstract: A network slicing framework allows one to deliver services over IP or new network architectures like ICN. ICN provides desirable features to support applications such as name-based networking, in-network mobility, multicasting and caching while operating over heterogeneous transports . Moreover, depending on the granularity of slicing, these features can be delivered as service-centric ICN slices or as a narrow waist serving multiple services. Through this presentation we present ICN as a use case for the network slicing group, with some details on a working prototype and requirements to orchestrate ICN slices.

**II. Towards Operators Ecosystem Viewpoints**

### Presentation 06: Network Slicing architecture
    Presenter: Liang Geng – China Mobile
    Duration: 10 mins + 5 mins Q&A
    
    Abstract: This document defines the overall architecture of network slicing. Base on the general architecture, basic concepts of network slicing and examples of network slicing instances are introduced for clarification purposes.  Some architectural considerations about the data plane, control plane, management and orchestration of network slicing are described to give a general view of network slicing implementation principles.  This also helps to identify the gaps in existing IETF works relating to network slicing.
    https://datatracker.ietf.org/doc/draft-geng-netslices-architecture/ 

### Presentation 07: Network Slicing: Technical Viewpoints and Functional Roles
    Presenter: Pedro Martinez-Julia - NICT (Japan)
    Duration: 10 mins + 5 mins Q&A
    Abstract: The limitations on internal and external flexibility of network resources and the benefits of network service composability are key aspects to promote network slicing and its related technologies. This presentation discusses a set of basic requirements that should be added to the reference architecture for network slicing, supported by two technical points of view of NS and the minimum functional roles involves in NS and their interactions. It also illustrates a potential use case, an envisioned advanced scenario, and required interfaces.


**III. Towards Manufactures Viewpoints**
### Presentation 08: How to slice Network Slicing for the IETF
    Presenter: H. Flinck - Nokia
    Duration:  10 mins + 5 mins Q&A
    Abstract: Network slicing is motivated by sharing network infrastructure among multiple tenants. It is based in X as a Service model and motivated total cost of ownership and extending the communication services towards vertical markets. It is concept for customizing shared network resources for particular use for a tenant. A slice is composed by network functions and connectivity between these functions to meet a special SLA. Slice management and control can be divided into customer face management capabilities and to network resources facing capabilities. 3GPP, ETSI, NGMN and TM forum   are already working on the slice management aspects.  The issue addressed by this talk is how would the IETF complement this ongoing work. We suggest developing transport slices would be most natural work area.  This would include interfaces and APIs of offered to the slice management to compose slices and to provide needed control for transport services.

### Presentation 09: ACTN Virtual Network operation (with Network Slicing Insights)
    Presenter: G. Grammel - Juniper/L. Young - Huawei
    Duration: 10 mins + 5 mins Q&A
    Abstract: This draft describes how ACTN can provide transport network resources based on the VN service and instantiation request from orchestrator that is in charge of orchestrating 5G network slicing. This is work in progress in the TEAS WG and it might be beneficial to your side meeting. Although it is YANG model, it is presented in the context of architecture’s point of view and what ACTN can contribute.
    https://datatracker.ietf.org/doc/draft-lee-teas-actn-vn-yang/?include_text=1


### Presentation 10: Automatic Network Slicing Management for Transport Network
    Presenter: Qiang Li - Huawei
    Duration: 10 mins + 5 mins Q&A
    Abstract: Coming soon
    
### Presentation 11:  Managing Slices – Dynamic Control Plane Datastores  
    Presenter: Susan Hares - Huawei
    Duration: 10 mins + 5 mins Q&A
    Abstract: One the important parts of network slides is network management of the slides.  The dynamic nature of the network slices may not align with traditional network management.  Traditional network management considers there is a box with a configuration file which aids the box to boot up and run.  Fitting the dynamic nature of network slides into this tradition box may seem like putting a round peg into a square hole.  Recently, the NETMOD, RESTCONF and the I2RS working groups have been working on a transformation of the traditional management system.   A “revised-datastore” model suggest that beside a “configuration” for the box with traditional rules, there can be dynamic datastores with configuration.  The rules on interaction between “datastores” are being developed.   Other routing groups (TEAS, I2RS, RTGWG) have made use of this new concept in their yang data models for topology discover.  My hope is this presentation will apprise those interested in NETSLICES on current IETF work that can be leveraged to accomplish your aids, and aid “gap analysis” needed for any charter development for a IETF BOF proposal.   
 

### Final Q&A & Conclusions: 30 mins

**Call for collaboration, contribution on**
- Problem statement
- Scope of the work
- Work Priorities
- Gap Analysis
- Use cases & Requirements (multiple drafts)
- Architectures / Reference Models (multiple drafts)
- NS Capability Exposure (multiple drafts)
- NS functions and operations (multiple drafts)
- Terminology

*Close Meeting*
