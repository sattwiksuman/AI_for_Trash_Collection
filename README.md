# AI_for_Trash_Collection
Reinforcement Learning to model efficient Trash Collection 

Efficient Trash Collection using AI
A grid environment is created in which the AI agent is expected to operate. The grid element which represent the road constitute the state space. Three of these grid elements are marked as garbage collection points. Refer to the attached figure in the notebook for clarity. The following explanation refer to the image in the notebook.

States of the Environment:
The gray squares above depict the states in which the agent can reside.
So there are 26 states in total numbered 0 to 25.
The movement of the agent from one state to another is defined by defining the rewards of the adjacent states.

Actions
At each state the agent can 5 actions as follows:

Do nothing
Move North
Move East
Move South
Move West
Action_Space: control the motion
For each state, the next state corresponding to the consequence of the 5 actions will be pre-defined as part of the environment definition.

Rewards
The reward of the trash locations 03, 17 and 321 are defined to reflect the amount of trash in the following manner:

if trash >= threshold:
 reward= percentage of trash bin full
else:
 reward = 0

The threshold can be set to 70% .
Reward for road states in form of Living Penalty
A Living Penalty is defined to each of the states on the road because we want the agent to move by taking the shortest time, which would ultimately be the most efficient way to travel.
Living Penalty is not defined to the start location '0' and the trash locations.
The agent is expected to reside at the starting point till it needs to make it's first trip and then reside at the location from which it has collected the trash till it needs to move to the next location to collect from the next location.
Living penalty can be set to -0.2

Carrying capacity of the Agent
For the initial model, the agent is assumed to have infinite capacity.
This effectively means it never has to return to the depot to empty itself.

Timestep of the simulation
The timestep can be assumed to be one hour.
In each timestep:

the vehicle is assumed to have one state transition.
the garbage is updated to new quatities
