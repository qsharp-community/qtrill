Design for the open-system-simulation QTRIL

Why would I need this:
When working with new existing experimental technologies in a business context, it’s important to make sure that an investment will not go to waste when the technology matures later on. 
Within the fast-moving field of quantum Computing there are a number of languages that are tailored to specific hardware and integrations. 
Programs written in those languages, might become deprecated when hardware will evolve. 
This creates a risk for business, because their investments might evaporate that way. 
Because the Microsoft Q# language for quantum computers doesn’t depend on specific hardware or structure, programs written in Microsoft Q# can move to newer hardware and investments are thus preserved. 
But because a lot of researchers only care for their algorithms or tooling until a next paper, you might run into the situation where you need to interface with code and tools of those other languages. 
Our new project qTril, helps solve this problem to be able to use Microsoft Q# programs on also other types of simulators. 
This will help you keep your investments safe since you don’t need to leave Q# to test on other more specific simulators. 

How does it work:
Withing the context of quantum simulators there are three common types;

1. Stop-the-world: These are simulators which simulate executing on a quantum accellerator device as one atomic job. The simulator does not allow to add additional gates or condition queries during execution. Since the simulator can be handed as a request-resurn they can be considered stateless from a usuage perspective. 
2. Incremental simulators: These are simulators which obtain on gate at a time and execute them in process. They allow a flow of gates to be added to the execution and usually hold their own state.
3. Concurrent simulators: Just like an incremental simulator these simulators which get sent one gate at the time, but don't execute them directly in the same process and time (the execution might be parallel to the host program).

The current QDK full state simulator is an incremental simulator and thus the simulator api's currently used in Q# asume the simulator is statefull.
Some other simulators in the industry however are the other types. 

//Todo: Give better names
