# Agent-oriented development
In this section, we highlight some of the most fundamental characteristics of the agent-oriented approach to solution development, which might be different from some of the existing paradigms and methodologies you may be used to. We hope that with this, we can guide you towards having the right mindset when you are designing your own agent-based solutions to real world problems. 

## Decentralisation
Multi-Agent Systems (**MAS**) are inherently decentralised. The vision is, an environment in which every agent is able to directly connect with everyone else and interact with them without having to rely on third-parties to facilitate this. This is in direct contrast to centralised systems in which a single entity is the central point of authority, through which all interactions happen. For example systems based on the client-server architecture, in which clients interact with one another, regarding a specific service (e.g. communication, trade), only through the server.

Note, this is not to say that facilitators and middlemen have no place in a multi-agent system; rather it is the 'commanding reliance on middlemen' that MAS disagrees with.

**Division of responsibilities:** In a decentralised system, every agent is equally privileged, and (in principle) should be able to interact with any other agent. The idea is very much aligned with the peer-to-peer paradigm, in which it is the voluntary participation and contribution of peers that creates the infrastructure. As such, in a decentralised system, there is no central 'enforcer'. This means all the work that would typically fall under the responsibilities of a central entity must be performed by individual parties in a decentralised system. Blockchain-based cryptocurrencies are a good example of this. People who are getting into cryptocurrencies are often reminded that, due to the lack of a central trusted entity (e.g. a bank), most security precautions related to the handling of digital assets and the execution of transactions fall on individuals themselves. 

<!--Another example is the verification of protocol adherence in regulated systems. Consider the problem of traffic management. The success of such a system relies on its participants (e.g. pedestrians, cars, motorbikes, bicycles, etc) conforming with the traffic management protocol, which specifies, for instance, who has the right of way in a junction. It is trivial, that the continuous functioning of this system does not rest solely on the existence of a protocol; there should also be a mechanism in place that verifies the protocol is followed by the participants. In a central system, verifying whether parties adhere to the system's protocol is often the responsibility of a central unit that checks (some or all) actions of the parties involved. The police could be considered a central entity that enforces traffic protocols and punishes those violating it. However, in a decentralised environment, this burden falls on the parties involved in the interaction themselves. Therefore, one could imagine a self-governing traffic management system whereby individuals on the road enforce protocol adherence on each other and decide on the appropriate method(s) of enforcement (e.g. through collective punishments, sanctions, rewards, ratings, etc).-->

**Decentralisation vs distribution:** It is important to emphasise that by decentralisation we do not mean distribution; although multi-agent systems typically do tend to also be distributed. A distributed system is one whose components are physically located in different places and connected over a network. A fully centralised system, owned and operated by a single entity, may in fact be highly distributed. Google's infrastructure is an example of this, where all of the components are distributed across the globe, yet designed to work together highly efficiently and function in unison. Decentralisation on the other hand refers to a system whose components may be owned, operated, and managed by different stakeholders, each with their own personal objectives, interests, and preferences, which may not necessarily be aligned with one another or that of the system itself. Therefore, distribution refers to the physical placement of a system's components, whereas decentralisation refers to **a)** the diversity of ownership and control over a system's constituents, and **b)** the absence of a central point of authority between them.

**Example:** To better illustrate the distinction between centralised and decentralised systems, consider another example: search and discoverability in a commerce environment. In a centralised system (say Amazon), there is a single search service -- provided, owned and run by the commerce company itself -- which takes care of all search related functionality for every product within their domain. So to be discoverable in this system, all sellers must register their products with this particular service. However in a decentralised system, there may not necessarily be a single search service provider. There may be multiple such services, run by different, perhaps competing entities. Each seller has the freedom to register with (i.e. make themselves known to) one or a handful of services. On the buyers side, the more services they contact and query, the higher their chances of finding the product they are looking for. 

## Conflicting Environment

As discussed above, the notion of decentralisation extends as far as ownership and control. Therefore, the different components that make up a decentralised system may each be owned by a different entity, designed according to very different principles and standards, with heterogeneous software and hardware, and each with internal objectives that may be fundamentally inconsistent, worst yet contradictory, with those of others. 

As such, a distinctive characteristic of a multi-agent environment, is that it is inhabited by more than one agent (as the name suggests), where each agent may be owned potentially by a different stakeholder (individual, company, government). Since by design, each agent represents and looks after the interests of its owner(s), and because different stakeholders may have unaligned, conflicting, or contradictory interests, it is very common to have multi-agent systems in which the agents' objectives, values and preferences are unaligned, conflicting, or contradictory.

**In practice:** There are practical implications that follow from the above when it comes to designing an agent. For example, it is not rational for an agent to automatically rely on the information it receives from other agents. The information could be:

* Incomplete: what is unrevealed may have been deemed private for strategic reasons. 
* Uncertain: it may be the result of an inaccurate prediction. 
* Incorrect: it could be an outright lie, due to the adversarial nature of the environment.

Therefore one can argue, that there is a degree of uncertainty attached to almost all information an agent receives or infers in a multi-agent system. It wouldn't then be illogical for an agent to take a sceptical approach: treating everything as uncertain, unless proved otherwise.

## Asynchronisation

The conflicting nature of multi-agent systems, consisting of self-interested autonomous agents, points to _asynchronisation_ as the preferred method of designing and managing processes and interactions.

**Synchronisation vs asynchronisation:** In general, asynchronisation refers to the decoupling of events that do interact with one another but do not occur at predetermined intervals, not necessarily relying on each other's existence to function. This is in contrast with _synchronous_ systems in which processes are aware of one another, where one's execution depends in some way on the other.

**Asynchronisation in MAS:** In the context of multi-agent systems, the decentralised and potentially conflicting nature of the environment creates uncertainty over the behaviour of the whole system, in particular of other agents. For example, suppose an agent _i_ sends a message requesting some resources from an agent _j_. Since MAS often tends to be distributed, there is the usual uncertainties with communication over a network: _j_ may never receive _i_'s request, or may receive it after a long delay. Furthermore, _j_ could receive the request in time and respond immediately, but as mentioned in the last section, its answer might be incomplete (gives only some of the requested resources), uncertain (promises to give the resources, but cannot be fully trusted), or incorrect (sends a wrong resource). In addition, since agents are self-interested, _j_ may _decide_ to reply much later, to the point that the resource is no longer useful to agent _i_, or _j_ may simply decide not to respond at all. There might be a myriad of reasons why it may choose to do that; it could be because _j_ assigns a low priority to answering _i_ over its other tasks. But that's beside the point. The take away is that agents' autonomy strongly influences what can be expected of them, and of an environment inhabited by them. As such, developing for a system whose constituents are autonomous, e.g. agents in a multi-agent system, is fundamentally different from one whose constituents aren't, e.g. objects in an object-oriented system.

**Objects vs agents:** In object-oriented systems, objects are entities that encapsulate state and perform actions, i.e. call methods, on this state. In object-oriented languages, like C++ and Java, it is common practice to declare methods as public, so they can be invoked by other objects in the system whenever they wish. This implies that an object does not control its own behaviour. If an object’s method is public, the object has no control over whether or not that method is executed.  

We cannot take for granted that an agent _j_ will execute an action (the equivalent of a method in object-oriented systems) just because another agent _i_ wants it to; this action may not be in the best interests of agent _j_. So we do not think of agents as invoking methods on one another, rather as _requesting_ actions. If _i_ requests _j_ to perform an action, then _j_ may or may not perform the action. It may choose to do it later or do it in exchange for something. The locus of control is therefore different in object-oriented and agent-oriented systems. In the former, the decision lies with the object invoking the method, whereas in the latter, the decision lies with the agent receiving the request. This distinction could be summarised by the following slogan (from <a href="https://www.wiley.com/en-gb/An+Introduction+to+MultiAgent+Systems%2C+2nd+Edition-p-9781119959519" target=_blank>An Introduction to MultiAgent Systems</a> by <a href="https://www.cs.ox.ac.uk/people/michael.wooldridge/" target=_blank>Michael Wooldridge</a>):
>objects do it for free; agents do it because they want to.

All of this makes asynchronisation the preferred method for designing agent processes and interactions. An agent's interactions should be independent of each other, as much as possible, and of the agent's decision making processes and actions. This means the success or failure of, or delay in any single interaction does not block the agent's other tasks. 

## Complex, Incomplete, Inconsistent and Uncertain

The forth characteristic(s) relate to the environment in which agents are expected to operate in, and these have been mentioned a number of times in the previous sections. 

The environment agents are suited for typically tend to be complex, to the point that it is usually impossible for any single agent to perceive the whole of the environment on its own. This means that at any point in time, any agent has a limited knowledge about the state of the environment. In other words, the agents;' information tend to be incomplete due to the complexity and sophistication of the world in which they reside. 

Consider an agent which represents a driverless vehicle. The complexity of the problem of driving on the road makes it impossible for a single vehicle to have an accurate and up-to-date knowledge of the overall state of the world . This means that an agent's model of the world is at best uncertain. For instance, the vehicle, through its sensor may detect green light at a junction, and by being aware of what it means, it may infer that it is safe to cross a junction. However, that simply may not be true as another car in the opposite direction may still cross the junction violating their red light. Therefore, there is uncertainty associated with the knowledge "it is safe to cross the road because the light is green", and the agent must recognise that. 

Furthermore, the often conflicting nature of the environment means information obtained from multiple sources (agents) may be inconsistent. Again, this must be taken into consideration when designing an agent which is expected to operate successfully in a potentially conflicting environment. 

<br />