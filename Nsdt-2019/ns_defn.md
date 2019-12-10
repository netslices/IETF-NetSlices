%%%
Title = "IETF Definition of Transport Slice"
abbrev = "IETF Definition of Transport Slice"
ipr= "trust200902"
area = "Internet"
workgroup = "TEAS WG"
submissiontype = "IETF"
keyword = [""]
date = 2019-12-09T00:00:00Z

[seriesInfo]
name = "Internet-Draft"
value = "draft-nsdt-teas-transport-slice-00"
stream = "IETF"
status = "informational"

[[author]]
initials="R."
surname="Rokui"
fullname="Reza Rokui"
organization = "Nokia"
  [author.address]
  email = "reza.rokui@nokia.com"
  [author.address.postal]
  code = "Canada"

[[author]]
initials="S."
surname="Homma"
fullname="Shunsuke Homma"
organization = "NTT"
  [author.address]
  email = "shunsuke.homma.fp@hco.ntt.co.jp"
  [author.address.postal]
  code = "Japan"
 
 [[author]]
initials="K."
surname="Makhijani"
fullname="Kiran Makhijani"
organization = "Futurewei"
  [author.address]
  email = "kiranm@futurewei.com"
  [author.address.postal]
  code = "USA"
%%%

.# Abstract

   This document describes the definition of transport slice in IETF,
   and describes considerations for realization of transport slice.
   This work is part of work on TEAS WG network slicing Design Team.

{mainmatter}

# Introduction

   Network slicing is a methodology to generically describe the logical
   partitioning of network resources associated with a service or an
   application.  Network Slicing is considered very useful because there
   is a need to generically describe diverse set of services and related
   resource requirements that can then be applied to any number or type
   of proposed, implemented and/or deployed technologies and associated
   devices.  Some key applications which might benefit from the use of
   network slicing include:

   -  5G services (e.g. eMBB, URLLC, mMTC)(See [TS.23.501-3GPP])
   -  Wholesale business VPN
   -  Network infrastructure sharing among the operators
   -  NFV connectivity (Data Center Interconnect)

   A network slice is composed of different endpoints and application
   specific connectivity between them.  Transport network slices are a
   type of network slices that are created and managed with in the scope
   of transport networks (IP, MPLS, GMPLS).  There is no concrete
   definition for network transport slices established or method to
   realize them.

   This document provides a definition of 'transport slice' in IETF, and
   describes considerations for realization of transport slices.  In
   this document the term transport slice is used as short form for
   transport network slice.


#  Terms and Abbreviations

   Service Level Objective (SLO):

   NS ID

   mMTC

   URLLC

# High level architecture of end-to-end network slicing

   An end-2-end (E2E) network slice is a complete network slice that
   provides a service in its entireity with a specific assurance to the
   customer.  A transport slice concerns those assurance aspects only
   with in the transport networks.  To illustrate the IETF definitions
   of both E2E network slice and transport slice, consider the network
   shown in [@FigE2ENS], where a network operator has an E2E network slice
   that traverses multiple technology-specific networks.  Each of these
   networks might use any of a number of technologies, including IP,
   MPLS, Fiber-Optics (e.g.  WDM, DWDM), Passive Optical Networking
   (PON), Microwave, etc.

   Each of these networks includes multiple (physical or virtual) nodes
   and may also provide network functions beyond simply carrying of
   technology-specific protocol data units.  The types of nodes used in
   any of these networks may include:

   -  Packet Switches (e.g.  Routers, Bridges)
   -  Application servers
   -  Firewalls
   -  Radio Access Network (RAN) components
   -  Mobile Core componets
   -  Microwave transceivers
   -  Optical repeaters
   -  etc.

   Each network may support different technology and an E2E netowrk
   slice is a combination of these networks.  As an example:

   -  Network 1 might contain multiple 5G RAN nodes connected to a few
      Cell Site Gateways (CSG) routers.
   -  Network 2 might have one or more layer-3 routers and layer-2
   -  Network 3 might have a few 5G RAN nodes connecting to Passive
      Optical Network (PON) switches.

{#FigE2ENS}
~~~ ascii-art
           <======================= E2E NS ===================>

           <!--KM: should this be not only TS1?-->
           <-OS1-> <-TS1-> <-TS2-> <-OS2->  ... <-TSn-> <-OSm->

          |------------------------------------------------------|
          |    .--.             .--.                .--.         |
          |   (    )--.        (    )--.           (    )--.     |
          |   .'         '     .'         '        .'        '   |
   [EU-x] |  (  Network-1  )  (  Network-2  ) ... (  Network-p ) |[EU-y]
          |  `-----------'    `-----------'       `----------'   |
          |                                                      |
          |                      Operator-z                      |
          |------------------------------------------------------|
   Legend:
     E2E NS: End-to-end network slice
     TSn: Transport Slice n
     OSm: Other Slice m
     EU-x: End User-x
     EU-y: End User-y

~~~ 
Figure: E2E network slice

   To further clarify the concept of the E2E network slice, consider the
   network operator-z has various customers.  One of the customers,
   needs a separate and an independent E2E logical network for a service
   (e.g.  CCTV, autonomous driving, HD map etc.) and has a specific
   network SLA requirement (e.g. a secure connection with an E2E latency
   less than 5ms) from End User-x (EU-x) to End User-y (EU-y) to the
   other side.  This E2E logical network is called an "E2E network
   slice".  A typical example of EU-x in 5G is the User equipment such
   as infotainment unit in the car, CCTV, Car for autonomous driving
   etc. and a typical example of EU-y in 5G is 5G application server,
   IMS etc.

   In Figure {@FigE2ENS} we use the term "E2E network slice" to show the logical
   network with requested SLA from EU-x to EU-y.  It is important to
   consider that an "E2E network slice" is associated with a customer
   and a service type (e.g.  CCTV service, autonomous driving etc.).

   For example, a customer "City of NY" would like to connect all its
   CCTV cameras for the entire city to one or more locations for viewing
   or collection.  To this end, it requests local carrier - 'operator-z'
   in NY to create a new E2E network slice with a bandwidth no-less-than
   10Mbps from each CCTV coverage area.  In this case, a single E2E
   network slice will be created by the operator-z for customer "City of
   NY", service type of CCTV and requested bandwidth connecting all the
   CCTV camera zones to one or more control-centers for the collection
   of video data.

   It may also be possible that more than one customer and/or service
   types are associated with an E2E network slice.  For instance, an E2E
   network slice is associated with not only to service type CCTV but
   another service "Public Safety", i.e. NS ID 10 is used for two
   services for City of NY.

# IETF Definition and Scope of Transport slice

## Defintion

   The IETF definition of a transport slice is as follows:

   A transport network slice is an abstract network topology connecting
   a number of endpoints, with an expected network service specified
   through a set of service level objectives.

   Note that multiple transport slices can be combined together into one
   transport slice, in that case each segment will be called transport
   subslice or transport subnet slice.  The document will consistently
   use the term transport subslice.  Use of service level objectives
   help to clearly describe different network resources and
   corresponding parameters neccessary to describe a service.

   Informally, a transport slice has a set of connections and various
   endpoints to form a logical network.  The goal is to achieve specific
   SLO for a customer as shown in Figure [@FigTS].  The endpoints maybe any
   physical or virtual network functions (PNF/VNF) or any network
   service for that matter.  Simillarly connections maybe virtual or
   physicals links of any type of technology.

{#FigTS}
~~~ ascii-art

                    <-------  Transport slice -------->

                        .--.               .--.
              [EP11]   (    )- .          (    )- .    [EP21]
                      .'         '       .'         '
              [EP12] (  Network-1 ) ... (  Network-p ) [EP22]
               :     `-----------'      `-----------'    :
              [EP1m]                                   [EP2n]

              Legend
                EP: Endpoint
~~~ 
Figure: Transport network slice

   Referring to Figure [@FigE2ENS], when operator-z creates a specific E2E network
   slice, it should create one or more of the following two types of
   artefacts:

   -  Transport slice (or transport sub-slices)
   -  Other slice (application logic or other non-IETF slice components)

   As shown in Figure [@FigE2ENS], an E2E network slice might have one or more of
   "Transport Slices" and one or more of other slices of any
   combinations.  One of the critical parts of an E2E network slice is
   "Transport Slices" which provides various connections with certain
   SLA between various endpoints.

   Defining the other slices is out-of-scope of current work.

   Figure [@FigTS] illustrates the definition of a Transport Slice where a
   single transport slice provides connectivity between "m" endpoints on
   left-hand side to "n" endpoints on right-hand side with specific
   characteristic for Service Level Agreement (SLA).

   Each transport slice has the following main characteristics:

   -  Transport slice definition: It addresses a set of technology-
      agnostic connections between various endpoints with certain SLA
   -  Transport slice realization: In addition to its definition, a
      Transport Slice has a realization in the operator's network.
      Unlike transport slice definition, which is technology agnostics,
      its realization is technology specific.

## Transport Slice Characteristics

   TODO

### Service Level Objectives

   TODO

### Endpoints

   TODO

### Slice Isolation
   TODO

# Transport Slice Examples

## Scenario-1

   Figure [@Fig5G] depicts an example of transport slice connecting two 5G RAN
   nodes (gNB) to three 5G Core user plan function nodes (UPF).  In this
   case a transport slice 20 is created with SLA including 10 [msec], or
   better, latency between 5G endpoints gNBs and UPFs.

{#Fig5G}
~~~ ascii-art

                     <--- Transport slice(TS ID:20) --->
                          with SLA of latency, less
                          than 10[msec]

                                .----.                [UPF1]
                [gNB1]         (      )----.
                          .---'             '----.    [UPF2]
                [gNB2]   (          Network       )
                         `-----------------------'    [UPF3]


~~~ 
Figure: Example of Transport Slice 20 connecting gNBs to 5G Core UPF

##  Scenario-2

   Figure {#FigSF} depicts another example where transport slice 30 is created
   to connect router ER1 to two firewall endpoints with SLA including 10
   [Mbps], or higher, bandwidth.

{#FigSF}
~~~ ascii-art
                   <--- Transport slice(TS ID:30) --->
                          with SLA B/W 5Mbps

                                .----.
                               (      )----.
                          .---'             '----.    [FW1]
               [ER1]     (          Network       )
                         `-----------------------'    [FW2]

               Legends
                 ER: Edge Router
                 FW: Firewall
~~~ 
Figure: Example of Transport Slice connecting Router to two firewalls

##  Scenario-3

   Another example of transport slice is SFC case as shown in Figure 5
   and Figure 6 which depict an example with SF1 and SF2 (e.g.  DPI,
   Firewall, WAF, video optimizer, content cache server, NAT/CGN, Load
   balancer) and the transport slice between ER1 and ER2 traverses these
   SFs.  There are two approaches:

   -  Approach-1 shown in Figure [@FigSF1] where Transport slice 40 chains
      router ER1, SF1, SF2, and router ER2.  Transport slice 40 needs
      lower than 30 ms delay.  However, endpoints SF1 and SF2 are
      implicitly identified during the transport slice realization.  In
      this case, a single transport slice is created between ER1 and
      ER2.
   -  Approach-2 shown in Figure [@FigSF2] where the transport slice 40 can be
      broken into transport slices 41, 42, 43.  In this case SF1 and SF2
      are explicityly identified and as a results three transport slices
      between following endpoints will be realized:

      --  Between endpoints ER1 and SF1
      --  Between endpoints SF1 and SF2
      --  Between endpoints SF2 and ER2

{#FigSF1}
~~~ ascii-art
                    <--- Transport slice(TS ID:40) --->
                          with SLA of latency 30ms

                         +-----+
                         | SF1 |
                         + *** +     .----.
                           * *      (      )--.
                           * *     (           )
                           * *  --' Network    '--.
               [ER1]******** *********** *************[ER2]
                         `-------------*-*--------'
                                       * *
                                     + *** +
                                     | SF2 |
                                     +-----+
~~~ 
Figure: Approach-1: Example of Transport Slice connecting Edge Routers ER1 and ER2 with SFC

{#FigSF2}
~~~ ascii-art

                   <-- Transport slice (TS ID:40) -->
                         with SLA latency 30ms
                   <- TS41 -> <- TS42 ->  <- TS43 -->
                      SLA        SLA         SLA
                      5[ms]      20[ms]      5[ms]

                         +-----+
                         | SF1 |
                         + *** +     .----.
                           * *      (      )--.
                           * *     (           )
                           * *  --' Network    '--.
               [ER1]******** *********** *************[ER2]
                         `-------------*-*--------'
                                       * *
                                     + *** +
                                     | SF2 |
                                     +-----+
~~~ 
Figure: Approach-2: Example of Transport Slice connecting Edge Routers ER1 and ER2 with SFC

#  Realization of Transport slice

   In addition to its definition, a Transport Slice has another
   characteristic which is its realization in the operator's network as
   shown in Figure [@FigReal].  The creaton of a new Transport Slice will be
   initiated from a northbound interface whereby a higher level system
   can request connections with specific characteristics (Step 1).  This
   request will be processed by a Transport Slice Controller (Step 2)
   which specifies a mapping between northbound request to any IETF
   Services, Tunnels and paths.  A series of requests for creaton of
   services, tunnels and paths will be sent to the network to realize
   the trasport slice.


{#FigReal}
~~~ ascii-art
          |------------------------------------------|
          |         A highter level system           |
          |   (e.g e2e network slice orchestrator)   |
          |------------------------------------------|
                                | (Step 1)
                                |
                                V
          |------------------------------------------|
          |         Transport Slice Controller       |(Step 2)
          |------------------------------------------|
                                | (Step 3)
                                |
                                V

      Step 1:
       The higher level system (e.g. e2e network slice orchestrator)
       can request a transport slice with specific characteristics

      Step 2:
       The transport slice controller maps the northboud request to
       any IETF Services/Tunnels/Paths models

      Step 3:
       Realize the transport slice by creating Services/Tunnels/Paths


~~~ 
Figure: Transport Slice Realization

##  Realization of Scenario-1

   Figure [@FigE2ENS] depicts the realization of the transport slice 20 of
   [@Fig5G].  Operator's transport slice controller invoke an abstract
   API to create a transport slice between 5G endpoints gNB1 and gNB2 to
   5G Core endpoints UPF1, UPF2 and UPF3 with SLA inlcuding 10 [ms]
   latency.

   Since in most cases the passed in endpoints (i.e. 5G RAN and 5G Core
   endpoints) cannot support any IP/MPLS/Optics services, the endpoints
   to realize the transport slice 20 will not be the endpoints passed
   in.  This is one of the most important aspects to consider when
   realizing the transport slices.

   As shown in [@FigE2ENS], the realization of transport slice 20 required
   the transport slice controller to find out the "best" endpoints which
   support the realization of transport slice 20 in the network, i.e.
   endpoints ER1, ER2 and ER3.  After that, the realization of the
   transport slice 20 will be initiated by creation of various
   services/tunnels/paths between edge routers ER1, ER2 and ER3.  The
   type of Services/Tunnels/Paths depends on the supported technologies
   of endpoints ER1, ER2 and ER3.

   In this scenario, the end points of transport slice realization are
   not those endpoints passed in, i.e.

   -  Definition of transport slice is between gNB1 and gNB2 to UPF1,
      UPF2, and UPF3
   -  Realization of transport slice is between edge routers ER1, ER2
      and ER3

{#FigNS20} 
~~~ ascii-art

                        | Create Transport slice 20 between gNB1 & gNB2
                        | to UPF1 & UPF2 & UPF3  with SLA  latency
                        | 10 ms or better
                        v
       +----------------------------------+
       |    Transport Slice Controller    |
       +----------------------------------+
                        | Realize transport slice 20 between
                        | ER1, ER2 and ER3 with SLA latency of
                        | 10 ms or better
                        v                          +----+
                      .----.                       +UPF1|
    [gNB1] +----+    (      )---.                 /+--=-+
         \ |    |===========================[ER2]+
          \| ER1|  (      Network       )          +----+
          /|    |===========================[ER3]+-|UPF2|
         / +----+    `----------------'         +  +----+
    [gNB2]                                       \
                                                  \+----+
                                                   +UPF3|
                                                   +----+
    Legends
      === : Tunnels & Services
      ER: Edge Router

~~~ 
Figure: Realization of Transport slice 20 of [@Fig5G]

##  Realization of Scenario-2

   [@FigNS30} depicts the realization of transport slice 30 of [@FigSF].
   Operator's Transport Slice Controller receives a request to create a
   transport slice between network functions R1 and firewalls FW1 and
   FW2 with SLA including 5 [Mbps].  Depends on the underlying network
   topology, Operator's transport slice controller will realize the
   transport slice.  For example, if both network functions (i.e.  R1,
   FW1, FW2) and network supports segment routing, two Tunnels/Services
   of type SR can be created (or used) in the network between R1, FW1
   and FW2 to realise the transport slice 30.  However, if the network
   just supports RSVP, two tunnels/services of type RSVP can be used to
   realize this transport slice.

   Note that since the network functions ER1, FW1 and FW2 support
   segment routing, the endpoints of the tunnels in this example are
   those endpointss passed in, i.e. the endpoints of the both transport
   slice definiton and its realization are R1, FW1 and FW2:

   -  Definition of transport slice is between network functions R1 to
      FW1 and FW2
   -  Realization of transport slice is between network functions R1 to
      FW1 and FW2

   We will see in next example that in some scenarios this is not the
   case and the endpoints of Transport Slice definition might be
   different from endpoints of its realization of transport slices.

   It is very clear that regardless of how transport slice is realized
   in the network (i.e. using tunnels of type RSVP or SR), the
   definition of transport slice 30 does not change at all but rather
   its realization.

{#FigNS30}
~~~ ascii-art
                             | Create Transport slice 30 between
                             | ER1 and FW1 and FW2 with SLA 5 Mbps
                             v
            +----------------------------------+
            |    Transport Slice Controller    |
            +----------------------------------+
                             | Realize transport slice 30
                             | between R1 and FW1 & FW2
                             | with SLA 5 Mbps
                             v
                           .----.
         +----+      .----(      )----.
         |    |=============================[FW1]
         | ER |    (      Network       )
         |    |=============================[FW2]
         +----+      `----------------'

         Legends
           === : Tunnels & Services of type SR
                 or RSVP with SLA 5 Mbps

~~~ 
Figure: Realization of Transport slice 30 of [@FigSF]

##  Realization of Scenario-3

   Figure 9 depicts the realization of the transport slice 40 of
   Figure 4 where a transport slice needed between network functions R1
   and R2 across SF1 and SF2.  However, the location of SF1 and SF2 are
   decided internally with a logic in Transport Slice Controller.  For
   example, when SLA requires the high secure transport slice between
   ER1 and ER2 which in turn results on adding SF1 and SF2 to the
   realization of transport slice 40 implicitly by transport slice
   controller.

   Figure 10 shows the realization of the transport slice 40 of
   Figure 5.  In this case the location of SF1 and SF2 has been
   explicitly decided by higher level logic.  In this case three
   transport slices 41, 42 and 43 will be created separately and
   eventually bind together to form a single transport slice 40 to meet
   the SLA that delay is lower than 30 ms.

{#FigNSSF1}
~~~ ascii-art
                               | Create transport slice between ER1
                               | and ER2 with latency 30 [msec]
                               v
                      +------------------+              +-----------+
                      | Transport slice  |<------------>|    SF     |
                      |   controller     |              |  Manager  |
                      +------------------+              +-----------+
                               | Realize transport slice 40 between
                               | ER1 & ER2 traversing SF1 and SF2
                               | with SLA of latency 30 [msec]
                               V
          <----------------- TS 40 ------------------->
                  +-----+
                  | SF1 |
                  + === +   .----.
                    # #    (      )--.
                    # #  (           )
                    # #  --' Network    '--.
      [ER1]=========   =========  ===================[ER2]
                `-------------- # # --------'
                                # #
                              + == +
                              | SF2 |
                              +-----+

      Legends
        ===== : Tunnels & Services


~~~ 
Figure: Realization of Transport slice 40 of Figure 5

{#FigNSSF2}
~~~ ascii-art

                         | Requirements on communication
                         | between ER1 and ER2
                         v
             +---------------------+            +-----------+
             |  High level system  | <--------> | SF Manager|
             +---------------------+            +-----------+
                         | Create transport slice between ER1 and SF1,
                         |        with latency 5 [msec]
                         | Create transport slice between SF1 and SF2,
                         |        with latency 20 [msec]
                         | Create transport slice between SF2 and ER2,
                         |        with latency 5 [msec]
                         v
               +-------------------+
               |  Transport slice  |
               |     controller    |
               +-------------------+
                  |      |     |         Realize TS 41 between ER, SF1
                  |      |     |                 with latency 5 msec
           +------+      |     +-------+ Realize TS 42 between SF1, SF2
           |             |             |         with latency  20 msec
           |             |             | Realize TS 43 between SF2, ER2
           |             |             |         with latency 5 msec
           v             v             v
      <--TS 41-->   <--TS 42-->   <--TS 43 -->
     <---------------- TS 40 ---------------->
               +-----+
             #=| SF1 |
             # +-----+ .----.
             #     #  (      )--.
             # .---#' Network    '--.
   [ER1]=====#(    #==========#       )#=====[ER2]
               `--------------#------' #
                              #        #
                            +-----+    #
                            | SF2 |====#
                            +-----+

   Legend
   === : Tunnels & Services


~~
Figure: Realization of Transport slice 40 of Figure 6

{backmatter}

<reference anchor='TS.23.501-3GPP' target='http://www.3gpp.org/ftp//Specs/archive/23_series/23.501/23501-g20.zip'>
  <front>
  <organization>3rd Generation Partnership Project (3GPP)</organization>
   <title>3GPP TS 23.501 (V16.2.0): System Architecture for the 5G System (5GS) Stage 2 (Release 16)</title>
   <author></author>
   <date>month='September', year='2019'</date>
  </front>
</reference>
