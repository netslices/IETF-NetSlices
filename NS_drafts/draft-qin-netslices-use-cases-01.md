% Title = "Network Slicing Use Cases: Network  Customization for different services"
% abbrev = "Use cases for Network Slicing"
% category = "info"
% docName = "draft-qin-netslices-usecase-customization-01"
% ipr= "trust200902"
% area = "Internet"
% workgroup = "none"
% keyword = ["Network Slicing"]
%
% date = 2017-03-24T00:00:00Z
% [pi]
% toc = "yes"
%
% #Independent Submission
% [[author]]
% initials="J."
% surname = "Qin"
% fullname = "Jun Qin"
% organization ="Huawei Technologies"
%    [author.address]
%      email = "qinjun4@huawei.com"
%    [author.address.postal]
%      street = "Huawei Campus, No. 156 Beiqing Rd."
%      city = "Beijing "
%      code = "100095"
%
% [[author]]
% initials="K."
% surname = "Makhijani"
% fullname = "Kiran Makhijani"
% organization ="Huawei Technologies"
%    [author.address]
%      email = "kiran.makhijani@huawei.com"
%    [author.address.postal]
%      street = "2890 Central Expressway"
%      city = "Santa Clara"
%      code = "CA 95050"
% [[author]]
% initials="J."
% surname = "Dong"
% fullname = "Jie Dong"
% organization ="Huawei Technologies"
%    [author.address]
%      email = "jie.dong@huawei.com"
%    [author.address.postal]
%      street = "Huawei Campus, No. 156 Beiqing Rd."
%      city = "Beijing "
%      code = "100095"
% [[author]]
% initials="L."
% surname = "Qiang"
% fullname = "Li Qiang"
% organization ="Huawei Technologies"
%    [author.address]
%      email = "qiangli3@huawei.com"
%    [author.address.postal]
%      street = "Huawei Campus, No. 156 Beiqing Rd."
%      city = "Beijing "
%      code = "100095"
% [[author]]
% initials="S."
% surname = "Peng"
% fullname = "Shuping Peng"
% organization ="Huawei Technologies"
%    [author.address]
%      email = "pengshuping@huawei.com"
%    [author.address.postal]
%      street = "Huawei Campus, No. 156 Beiqing Rd."
%      city = "Beijing "
%      code = "100095"

.# Abstract

Network Slicing paradigm enables creation of partitioned network infrastructure to provide isolated network platforms for various service verticals. The motivation behind Network Slicing (NS) is to allow deployment of new services
without causing or experiencing any disruption due to other already running or
deployed services in the network. The purpose of this document is to focus on use cases that benefit from the usefulness of network slicing.

{mainmatter}

# Introduction

Network Slicing (NS) is a widely discussed paradigm and is a mandatory
requirement in 5G to meet the diverse service requirements in different 5G service scenarios.  NS refers to the
   managed partitions of physical and/or virtual network resources,
   network physical/virtual and service functions [@!RFC7665] that can act
   as an independent instance of a connectivity network and/or as a
   network cloud [@!I-D.gdmb-netslices-intro-and-ps]. In
   3rd Generation Partnership Project (3GPP) [@?TR23.799] defines  "Network
   slicing enables the operator to create networks customized to provide
   optimized solutions for different market scenarios which demands
   diverse requirements, e.g. in the areas of functionality, performance
   and isolation".  Draft [@!I-D.gdmb-netslices-intro-and-ps] defines
   network slicing in a broad context and suggests related problems and
   work areas.  Other organizations like Next Generation
   Mobile Networks (NGMN) [@?Network-Slicing-Concept] and ITU-T FG
   IMT-2020 [@?FG-IMT2020-Gaps] also present their separate definitions of
   NS.

   To maximize resource utilization and minimize infrastructure cost,
   services will need to be deployed simultaneously, next to each other
   over a shared network as against the traditional monolithic model.
   Service operators can utilize or benefit from Network Slicing through
   multi-tenancy, enabling different customized infrastructures for
   different group of services across different network segments and
   operating them independently.  Moreover, NS is also able to guarantee
   the isolation between different network slices.  The operation of the
   data packets traversing one network slice must not adversely affect the
   service operation in other network slices sharing the same underlying
   packet network.

  This document describes use cases, where service operators can utilize or benefit from Network Slicing through multi-tenancy, enabling different customized infrastructures for different group of services across different network segments and operating them independently. Although 5G will drive NS based deployments, the scope of the document is not limited to 5G; it covers example scenarios specified from 5G vision as well as generalized scenarios that can be applied to existing infrastructures.

## Requirements Language

The key words "**MUST**", "**MUST NOT**", "**REQUIRED**", "**SHALL**", "**SHALL
NOT**", "**SHOULD**", "**SHOULD NOT**", "**RECOMMENDED**", "**MAY**", and
"**OPTIONAL**" in this document are to be interpreted as described in RFC 2119.

Additionally, the key words "**MIGHT**", "**COULD**", "**MAY WISH TO**",
"**WOULD PROBABLY**", "**SHOULD CONSIDER**", and "**MUST (BUT WE KNOW YOU
WON'T)**" in this document are to interpreted as described in RFC 6919.
 
## Terminology

- V2X (Vehicle-to-everything):
Is a communication of information from a vehicle to any other entity that may be a user end-device, network element or application end point.
- ITS (Intelligent Transportation Systems):
Considered an aspect of Internet of Things creates a transport network. The network provides  services relating to transport and traffic management systems through flow of information between sensors, smart devices and humans.
- Over-the-top (OTT):
A service, e.g., content delivery using a CDN, operated by a different operator than the NSP to which the users of that service are attached.
- Industry vertical:
A collection of services or tools specific to an
  industry, trade or market sector. Also referred to as Service Verticals in this document.


# Network Customization for diverse services

## Overview
[Note: To discuss diverse set of service attributes]

Often services specify a broader resource requirements to perform normally whereas  the underlying infrastructure is generally best-effort. Traditionally, basic service guarantees are associated with resource attributes such as:

* Latency
* Bandwidth/Burst or other bit rates.
* Security

In addition, other attributes as mentioned below are embedded into the infrastructure to improve over all quality of experience

* Redundancy
* Reliability
* Authentication

More recently, other service attributes have become significant such as

* Continuity during mobility
* Purpose-built network functions.
* Service placement

It should be possible for the providers of any service to
continuously evolve, adapt,  and differentiate  themselves through
purpose-built infrastructures  with minimal impact on network deployment and
operations. The motivation behind 5G Network slicing paradigm  is exactly that.
By creating logically partitioned network infrastructures, isolated platforms
for various industry verticals can be provided.  NS is  envisioned to enable new
service deployments  without having to build new network infrastructures or
causing  disruptions  to other already deployed services in the network. In
regards to NS, there are two primary characteristics, a) Strict demand for network resource, b) Network Customization.

## Strict Resource Demand Concept {#resource-demand}

Several services are sensitive to response times and/or amount of bandwidth, e.g. realtime interactive multimedia, high bandwidth video feed or remote access to an enterprise network. Failure to meet these criteria leads to service degradation.

Moreover, newer scenarios from different industries are evolving  due to these factors - a) everything connected, b) technological advancements in sensors, IoT, robotics and multi-media, c) innovations in social network interactions (including both human-human or human-machine). These may impose even stricter and more specific set of resource and connectivity requirements on per service basis.
The challenge lies in utilizing common network infrastructure and judiciously allocating available infrastructure resources.


## Network Customization Concept{#customization}
Network slicing is enabled through customization. Customization gives control to the operator (of a slice) to create, provision, change and consume network resources to suit their service demands. It requires ability to decompose resources from an underlying network infrastructure and logically aggregate them to tailored a part of network into a slice.  These customizations are not only in the context of the network characteristics but also include network functions.

## Scope of use cases

Network slicing by itself is not a new concept nor its benefits are limited to 5G. While writing use cases following were considered -

* A Network Slicing aware infrastructure allows operators to use part of the network resources to meet stringent resource requirement as in (#resource-demand) or exploit dynamic customizations as described in (#customization). Finally, there will be scenarios that require both customization and strict resource requirements.

* The document doesn't specify whether a network slice consists of a single or multiple service(s). at the simplest level one service may correspond to a slice, however, it is possible that many services may become part of the same slice for the purpose of isolated data or context sharing.

* Use cases below are discussed from 2 perspectives -

  a.  Newer scenarios: that should absolutely meet strict resource requirements, as if they use a dedicated infrastructure. The example use cases are categorized further in (#Demanding-NS).
  b.  Existing Scenarios: Several already deployed or existing examples that would further benefit when deployed through Network Slice paradigm are discussed in (#Using-NS).

# NS Use Cases of Strict Resource Demands {#Demanding-NS}

The International Telecommunication Union (ITU) has classified 5G mobile network services into three categories: Enhanced Mobile Broadband (eMBB), Ultra-reliable and Low-latency Communications (uRLLC), and Massive Machine Type Communications (mMTC).  Following representative use cases are divided based on these criteria.

## eMBB Type of NS Use Cases
The scenarios in this section are discussed in regards to growth in data rate capacity, connection density and interactive media.

###  HD Video

Person-to-person or person-to-group video communication with high resolution (4K/8K) and more advanced capabilities will have a much wider usage in 5G era.  In a large stadium or live event (spots/concert) setting, following kind of services can be offered:

  * Watch HD playback video or instant replay.
  * Stream/share live HD videos with remote friends, or photos to social networks.  

The connection density and date rate requirements will be high. The aim is to provide video streaming and sharing services to everyone, regardless of the physical location, the device being used, and the network connection [@?NGMN-White-Paper].

###  Virtual Reality (VR)/Augmented Reality (AR){#ar-vr}

Virtual Reality(VR)/Augmented Reality(AR) is another demanding use case of eMBB services.  VR/AR video streaming will have far more stringent network resource requirements than on-demand video content.  It may require it's own dedicated infrastructure with enhanced network protocols.  The adoption of bandwidth-intensive VR/AR immersive services will have a direct impact on network capacity.  At present 360 degree videos are mostly low resolution, requiring ~25 Mbps network bandwidth for streaming.  360 degree video is basis of AR/VR and as the display quality improves (retina resolution, 5K per eye), the bandwidth required will ramp up to several Gbps for a fully immersive experience.
The infrastructure required to deliver immersive services will be different from traditional network. It may require several purpose-built hardware-assisted for video processing inline, dedicated immersive service capacity per user and perhaps an alternate transport designed specially for video services.

### Realizing eMBB type Slices
A purpose-built Network Slice for video streaming shall ensure  first and foremost, that there is always sufficient network capacity available for users that are not attending of the live-event (eMBB slice). That is, users not subscribed to eMBB slice dedicated for the event, will not experience service degradation because available bandwidth got used up by stadium attendees.

Since quality of experience is important but not critical; this slice may scale out by borrowing resources on-demand from the common infrastructure resource-pool and may even return dynamically to save costs if the bandwidth demand is low. As such slices of these kind may be temporary and destroyed at the end of the event.

## uRLLC Type of NS Use Cases

###  Industrial Operation and Inspection

   In industry area, usually remote operations need the support of the mobile transport networks.  Operating machinery from a control center at a remote site could avoid on-site hazards relating to sites like waterworks, large process plants, mines, harbors, and chemical factory.  Tele-operating heavy machinery and other equipments with high accuracy in dangerous or hard to access sites requires a high-quality communication link between the control-center and the machines.

###  Remote Surgery
   Remote surgery which enables surgeons to perform critical specialized medical procedures remotely, allowing their vital expertise to be applied globally.  Providing the correct control and feedback for the surgeon entails very strict requirements in terms of latency, reliability and security.

### Realizing uRLLC type Slices

A Network slice dedicated for remote operations requires communication characteristics of low latency and low jitter.  To manipulate equipment efficiently the response time  of a control instruction must be as short as possible.  A typical haptic control loop in a remote operation application requires latency to be below 10ms [@?Technology-Watch-Report].



### Vehicle-to-everything (V2X)

Vehicle-to-everything (V2X) refers to an intelligent transport system where all vehicles and infrastructure systems are interconnected with each other [@?White-paper-5GAA].  The V2X features fall into several categories relating to safety, navigation, infotainment, diagnostics and efficiency [@?ITS-I]. This makes for an interesting use case for network slices as each category is served through a different slice; a vehicle becomes part of 3 or 4 different logical network infrastructures at the same time. For Example:

1. A vehicle may become part of a customized slice that serves low latency and zero-packet loss slice and supports a Vehicular Ad Hoc Network (VANET) type protocols for vehicle to vehicle communication and autonomous driving. It may further have different access selection (short-range DSRC or commercial C-V2X) see [@?White-paper-5GAA] for details.This slice have characteristics of constant, low bandwidth, ultra-low latency.
2. A Vehicle may join an isolated slice that represents its car manufacturer's network for remote diagnostics, software/firmware upgrades to vehicle maybe performed. The key characteristics for this slice is to ensure security of sensors and other devices through VPN style closed network.
3. An infotainment slice of vehicle provides broadband for in vehicle entertainment, Internet access and enhanced navigation.

## mMTC Type NS Use Cases

###  Smart Cities

Smart city is an integration of public infrastructures together through Machine-to-Machine (M2M) communications and other Internet of Things (IoT) solutions. The common smart city services include:

- automatic metering for gas, energy, water, etc.
- environment monitoring for pollution, temperature, humidity, etc.
- light management inside buildings or even the whole city,
- traffic signal control,
public safety alerting for natural disasters and emergencies.

Building a smart city requires a variety of IOT networks to inter-operate together, These IOT networks are run by different departments with different access privileges for administration and access control. For emergency services in smart city, the communication network must ensure the reliable communication.


###  Health Monitoring

  E-health refers to the application that remote monitor the physical conditions (e.g., heart rate, pulse, blood pressure etc.), and accordingly take necessary medical measures remotely. Often E-health service could be life-critical relate its communication network must be able to provide the reliable and fast but small-size of data exchange. In addition, the privacy and security of user’s data must be guaranteed.


### Realizing mMTC Type Slices

mMTC involves potentially a large number of small and power-constrained devices, therefore, resource allocation at scale is of particular importance in mMTC type slices. Furthermore, different kind of IoT devices may exhibit quite different traffic patterns e.g., uninterrupted (heart rate monitors) & periodic delay tolerant (temperature sensors), delay sensitive (e.g., weather forecast & disaster alerting), mobility mode, security awareness etc. The mMTC type slices should be conscious of various requirements of scale, data pattern, reliability, security and energy efficient communications.

# NS Use Cases of Other (Over-The-Top services) type{#Using-NS}

  Besides specific scenarios with special requirements, discussed in previous section, examples in this section benefit from sliced-network infrastructure.

Over-The-Top(OTT) services are typical scenario of this kind. OTT services are those associated with content, like video (with normal definition), audio, IM messages, web-digital content, and other media transmitted via the Internet, this kind of communications are expected to be pervasive and part of everyday life. A high degree of applications such as VOIP, CDNs are deployed as OTT services with low expectations from the underlying network as communication medium and subsequently by building their own application infrastructure.  The trend toward IP (or HTTP) based content delivery may be perceived as an indicative of network as dumb pipe. However, QoE is important to content delivery and requires coordination with the ISPs.  With new advances in multimedia formats and social network channels service offerers must adapt to varying parameters of QoE.

## Realizing OTT Service Slices
A network slice represented by partitioned network infrastructure allocated for content delivery can help create new opportunities for both network operators and content providers. [@!RFC6770] provides many use cases relating to ISP Handling of third-party content.
Following examples may be considered:
   - Content Service Providers (CSPs) could lease a CDN slice and operate it as a well coordinated CDN infrastructure of content awareness, optimally placed servers & proprietary optimization logic functions (different for live video (real-time) and on-demand (caching)).
   - VOIP is a peer to peer service and requires CBR across multiple domains. If a VOIP-slice specification is from a well-known template that is universally understood then a low cost, reliable end-to-end VOIP service can be offered without intense provisioning of the transport.  

# NS Use cases with Mixed Requirements
Along another dimension, many services will have combination of hard resource constraints that were discussed in (#Demanding-NS) such as both eMBB and uRLL.
Some examples are as follows
  - As described in (#ar-vr), AV/VR  has high bandwidth requirement but   'interactive' VR/AR applications are extremely sensitive to delay and require very low  end-to-end latency (~20ms).
  - While operating machinery remotely, the primary communication characteristics are low latency and low jitter but in case of video assisted maintenance, the bandwidth also becomes important. In fact, most of the applications have mixed requirements from the network infrastructure.

# Generic Network Slicing Use Case Analysis

  - Network Operator View: It is a daunting task to manage ever increasing number of services with their customized resource requirements. A logical division of networks shall allow simpler orchestration, management and operation both for service operator and network operators.
  - Opportunities in Industry verticals: With an independent control of services and associated network resources, Industry verticals can test and deploy services quicker.
  - 5G context: While the scope of document does not limit to 5G, it is important to take into consideration that 5G blurs the boundary between fixed and mobile networks. some related factors are (1) end-device access will be mainly radio or wireless but very well be fixed (2) end-device is simultaneously associated with those many access networks (3) transport could be IP or non-IP based. 5G will also be early adopter of Network Slicing in its architecture, therefore, many scenarios from 5G will be prioritized.
  - Heterogeneous resources: Different kind of resources maybe required in difference slices. Each network slice appears to its users as an independent, dedicated private network which is impervious to anything including the heterogeneous resources that is happening on any of the other network slices, a high degree of isolation on data plane is needed.
  - Transport Context: the transport network should give a customized topology built for a different network slices, and provide the network resources and performance characteristics like bandwidth, latency, jitter, security, availability, and etc that required by the corresponding slices.

# Conclusion

Many emerging services, together with the existing and evolving services will be carried out in the context of 5G network slicing. The goal of 5G is to support various service scenarios which have very diverse and strict demands from the network infrastructure.

These scenarios require networks to be more flexible and scalable to support customized service requirements and diverse performance requirements with a single network infrastructure.  Specifically, the current transport network architecture is not as flexible or scalable to provide the required network customizations and the resource assurances for different type of use cases at simultaneously.

Network slicing is a way to to support service or industry verticals over the same physical network such that each network slice appears to its tenant as an independent, dedicated private network and is impervious to anything that is happening on any of the other network slices. For services which do not have special requirements from the network; slicing provides an effective way for those to coexist along with the services having strict requirements.


# Security Considerations

The security considerations  apply to each slice. In addition general security
considerations of underlying infrastructure whether isolated communication with
in a slice apply for links using wireless technologies.

# IANA Considerations

There are no IANA actions requested at this time.

# Acknowledgements
 Thanks to Stewart Bryant for providing details for several use cases.

<reference anchor='ITS-I' target='https://www.ietfjournal.org/intelligent-transportation-systems-and-the-ietf'>
  <front>
    <title>Intelligent Transportation Systems and the IETF</title>
    <author></author>
    <date></date>
  </front>
</reference>

<reference anchor='BT-Ultra-HD-review' target='http://www.techradar.com/reviews/audiovisual/digital-tv-receivers/bt-ultra-hd-youview-box-1301334/review'>
 <front>
 <title>BT Ultra HD YouView box review</title>
  <author></author>
  <date></date>
</front>
</reference>

<reference anchor='FG-IMT2020-Gaps' target='http://www.itu.int/en/ITU-T/focusgroups/imt-2020'>
 <front>
    <title>FG IMT-2020: Report on Standards Gap Analysis</title>
  <author></author>
  <date></date>
   </front>
</reference>

<reference anchor='Network-Slicing-Concept' target='https://www.ngmn.org/uploads/media/160113_Network_Slicing_v1_0.pdf'>
 <front>
   <title>Description of Network Slicing Concept</title>
   <author>
   <organization>Next Generation Mobile Network Alliance</organization>
   </author>
   <date month="January" year="2016"/>
</front>
</reference>

<reference anchor='NGMN-White-Paper'
target='https://www.ngmn.org/uploads/media/NGMN_5G_White_Paper_V1_0.pdf'>
 <front>
 <title>5G White Paper</title>
 <author>
 <organization>Next Generation Mobile Network Alliance</organization>
 </author>
 <date month="March" year="2015"/>
</front>
</reference>

<reference anchor='Technology-Watch-Report'
target='http://ow.ly/Ubmow'>
 <front>
 <title>Technology Watch Report, The Tactile Internet</title>
 <author>
    <organization>ITU-T</organization>
 </author>
 <date month="August" year="2014"/>
</front>
</reference>

<reference anchor='TR23.799' target='http://www.3gpp.org/ftp/Specs/archive/23_series/23.799/'>
<front>
<title>Study on Architecture for Next Generation System</title>
<author>
<organization>International Telecommunications Union</organization>
</author>
<date month="December" year="2017"/>
</front>
<seriesInfo name="SA2 Study" value="3GPP-TR23.799"/>
</reference>

<reference anchor='White-paper-5GAA' target='http://www.5gaa.org/pdfs/5GAA-whitepaper-23-Nov-2016.pdf'>
 <front>
 <title>The Case for Cellular V2X for Safety and Cooperative Driving</title>
  <author>
      <organization>5G Automotive Association</organization>
  </author>
   <date month="November" year="2016"/>
  </front>
</reference>

{backmatter}
