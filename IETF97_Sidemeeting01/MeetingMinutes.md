# Network Slicing Side Meeting

- Nov 14, 2016, 19:00-21:00, Studio 3
- 67 People signed the attendance sheet.

#   General Admin

_Jie Dong_ introduced the purpose of the meeting.

Services have unique requirements, end-2-end slicing is required for 5G. Among definitions we need to establish common definition.
Purpose is to have a common view of what network slicing is in IETF.

List request has been sent to Deborah (Routing Area AD).
# Topics Covered
## Network slicing problem statement [Stewart Bryant]

https://tools.ietf.org/html/draft-dong-network-slicing-problem-statement-00

## Presentation:

What is to be done in IETF, what existing and new work?

Existing definition
- 3GPP
- ITU-T (FG IMT-2020)
- IETF?

**Requirements of Network Slicing**
-  Isolation/separation
-  Customization of topology
-  Flexibility of topology
-  Guaranteed QoS
-  Management consideration


1. What should be definition of network slicing in IETF?
2. What is needed beyond connectivity?
3. What is the scope of network slicing in IETF?
4. How much can existing/on-going tech meet the reqt?

## Discussion/Questions:

Comment 1. IETF is protocol-oriented, how would slicing change the semantics of
existing protocols?

Stewart: We typically have a set of tools designed for best-effort fabrics and
adding BW, these are not scalable and we need some additional scheduling.

Comment 2. We typically build separate networks for banking and other low
latency apps, this is not economical. Isolation and security are weak points.

Comment 3. What are the performance and isolation requirements? Does this mean
statistical sharing is out of scope? Fixed fraction of b/w seems to be a must.

Stewart: There will be a spectrum of requirements, different QoS for different
application, we may need some packet scheduling.Do we need isolation using
mechanisms like IEEE (time sensitive networking ? TSN) or detnet. If its
bit-level, we will go back to TDM.

Andrew: isolation and security is the biggest challenge, figure out how to
provide banking applications in economic manner, such as a slice. Packet
scheduling at buffer and line speed level is not enough we need to adapt to
packet changes at micro-level
(it was quietly mentioned, we are not thinking at bit-level but focus at packet
level).

Comment 4. Look at 5G applications for machine critical, interface b/w down to
radio is key, we may adapt BW based on radio capacity, Internet does not do
this today, we need to figure this out.

Stewart: It may be a packet level.  factoring into a lower layer is an issue

Comment 5. Can we define slicing??

Stewart: We can also agree on an existing definition, which would be useful.

Comment 6. Generalised packet networks are not suitable for hard packet
tunnels.

Comment 7. Dave Allen (Ericsson):  slicing definition leave it open disjoint
resource like wavelength is considered in other forum as the only way to
achieve isolation. e.g. WDM-PON, wavelengths allocated per slice. (Young Lee
added that WSON controller is already doing this). What does packet have to do
if isolation cannot be guaranteed?

# Autonomic slice networking    [Alex Galis]

## Presentation:
https://tools.ietf.org/html/draft-galis-anima-autonomic-slice-networking-00

- Generation 1 - Resource partition of network resource is one definition.
- Generation 2 - Network function and services are another definition of network
slicing.
- Generation 3 - Grouping of partitioning of 5G slicing
- Generation 4 - Management and control and advertisement has to be added to the Network slicing definition

*ANIMA* - unified network slicing definition in the context of autonomic
networking

- The service instance component
- A network slice instance component
- Resource component
- Slice capability exposure component

*Suggested 15 work items and issues*

## Discussion/Questions:

Comment 1. Dino: asked difference between horizontal and vertical slicing.
Vertical slicing, can an application be a member of multiple slices? Will
Extranet be required? For horizontal slicing, would it be stitching or
something else? These would be for customers ill shared services and isolation
for specific VPN connectivity

Alex: Yes, level of abstraction and level of isolation need to be considered,
and separate control may also be needed.

Stewart: We may see both models

Comment 2. This complicates the solution space.

Alex: This is not an intent to recreate a VPN technology.

Comment 3. Feels like IETF is lagging in industry work, upper service layer
which drives network resources. OpenSource is already ahead/doing some of this,
slicing is mainly multi-tenant, this is not rocket science or new. They are
trying to map existing technology like VXLAN and mapping it into YANG. Is there
a new architecture and protocol required? what is the role of IETF? API
? application level TOSCA; policy; YANG; already in place in industry. Question
is where is the gap? Map to protocol of new or existing protocols.

Stewart: Those are the questions we are asking at the start of the session.

Comment 4.  Slicing is a service definition, where is the gap?
Categorise them and see if we need new protocols, or adapt existing.

Alex: Yes, at least 15 problems, these are not supported by existing protocols.

Comment 5. We have a slicing architecture (as part of a H2020 project), and
service orchestrator, we then define flows which are application specific: IoT,
video, etc.

Comment 6. Ravi: IMT-2020 challenge was that service context could be only
identified by flow tuple in cp, dp and mgmt. Also slicing is interesting for
ICN as it allows new architectures and new properites per slice basis.

# Architecture for delivering multicast mobility services using network slicing [Truong-Xuan Do]

https://tools.ietf.org/html/draft-xuan-dmm-multicast-mobility-slicing-00

## Presentation:

Multicast functionality is different for say broadcast, mobility etc cases, so
there is a need to function decomposition and function chaining.

## Discussion/Questions:

Comment 1. You are aware of DMM working group, DMM FTC draft defines a model
that covers this. I think the group does not have a good definition of "slice",
domain is similar with 5G slice. I think it’s not clear what a slice is.

Stewart: This is why we are here; do we need to define "slice"?

# ACTN and network slicing  [Daniele Ceccarelli]

https://tools.ietf.org/html/draft-ietf-teas-actn-framework-01

## Presentation:

Describe end to end L2VPN/L3VPN is not enough, so there are 3 different level of controls (CNC, PNC and MDSC for customer, physical, multi-domain network controls). Access points, per domain tunnels and inter-domain links. Customer is able to provide constraints during network provisioning.

## Discussion/Questions:

Comment 1. Parviz: ACTN is a great piece of work, we have integrated based on
this framework. We shipped and integrate into ONOS. ACTN is used for integrated
packet optical SDN based solution. It is generalized for L0-L3 layers and need
to be perhaps extended for L1,L2 and NS. ACTN seems to have a good starting
point for network resource slicing and Detnet may be implementing a protocol
solution for time-sensitive networking.

Comment 2. Do you slice at the lower/physical lower and provide a slice to the
customer? So they can modify network resource, based on their specific slice?
Customer may just want the resource, not a solution, they want to manage it by
themselves.

Daniele:  Yes, they can manage their own resource.

Young Lee: VNF connectivity is included in the solution.

Alex: Maybe methods for slicing exist, the management methods for specific
applications and network functions are missing.

Comment 3. ACTN has multiple topology descriptions (physical, virtual and
customer), can it support end to end slicing with applications?

YoungLee:  ACTN also support NFV-constraints as part of abstraction and
connectivity.

Comment 4. Looking at ACTN it seems it can abstract multiple physical domains
and give us a logical view of TE/transport.

Daniele: ACTN introduces virtual networking, between MDSC and CNC, beneath PNC,
its technology/vendor specific.

Comment 5: Why ACTN for network slicing? Does it support hierarchy?

YoungLee: Yes. It does via MDSC-MDSC recursion.

Comment 6. ACTN is for multi-domain. How about for a single domain?

YoungLee: Yes, multi-domain solution includes single-domain, which is easier.

Comment 7. For 5G transport, IETF has a role to play. Front-haul, back-haul and
cross haul need transport network abstraction which is needed for 5G network.
Orchestration federation takes each component  to give end-to-end solution.


Georgios: Asked how does it do QoS besides partitioning of n/w resources.

Ans: Whatever TC can do is supported

Pedro: There are 2 aspects of slices - an act of creating it, and second
customizing and managing it in isolation is second part of the problem.

Comment: Service abstraction layer is missing and Information models.

Seil: is there a gap to be discussed.

Natasha from GSMA: not duplicate the work of other SDOs, if work needs to
evolve they will let IETF specific group know.

Wim from Nokia: slicing includes all - management, applications, radio etc
beyond transport.

Chris Seal: we need a stable platform first that doesnt exist.

Loa: non WG BOF can be done, it is way too early to exclude from IETF

Dave Allend: so many people are working on it. Problem space need to be
deconstructed, work needs to be done in totality of it.

Jonas: can we invite 3GPP for next meeting?

## Open Discussion 60 mins

Stewart posed several questions
##### 1. Does the IETF need to work on slicing?   
   Yes
##### 2. Does existing technologies solve the full set of slicing requirements?  
No

###### Comments:

Already there are several slice definitions, educating and agreeing definitions is useful

- Suggest we allow implementations first using existing solutions, using the
  tools which are already available.

- Network slicing is important; it needs to be end-to-end and the IETF has be
  involved. We also need to engage with other SDOs (3GPP, et al.),including
inviting the (SDOs) to participate in a BoF.

- ACTN seems like a good starting point, maybe this needs to be extended for
  additional technologies like Radio

- A lot of this discussion needs to be relevant to the IETF, what's on and in
  the wire

- Process from here for the discussion, is non-WG BoF and then WG-forming BoF.
  We should not exclude a potential WG on this topic, we should prepare and
investigate, then if we decide not to form that’s better than not being able to
form due to a lack of investigation work.

- One reason for lots of slicing definitions is the fact so many people are
  working on this topic. Across different areas and functions (controllers,
orchestrations), and scheduling and APIs. We would need to deconstruct the
problem space to understand what is needed, and how the IETF can help.

- Of the questions asked through show of hands, people favored forming
  a non-working group and agreed this is an area IETF can work into.

- Identifying gaps from IETF perspective is the most important aspect.

##### 3. Does the IETF need to focus discussion and develop tools for slicing?
(no discussion captured)

##### 4. Interests to work on slicing?  
A lot

##### 5. Willing to contribute to drafts and discussions?
Some

<end>
