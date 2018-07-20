# bvs_ns3sim

NS-3 simulation of multi-chain system used in BVS.

## Nodes
In this simulation every ns-3 node(`Node` class) corresponds to a mining node in the target blockchain P2P network. Every node in the network can participate in the block production according to the blockchain protocol and the consensus model. 

## Connections
A node has a capability to connect with any node in the network, but it does not imply that every two nodes in the network has a connection.

Every connection has its own latency and throughput characteristic.

## Concerning consensus model
In a PoW consensus model, a node can have a CPU power or a pre-mined hash pool to produce a candidate block to propose and propagate through the P2P network. It is a non-trivial job to simulate a propagation of every candidate block and crowd selection of the most appropriate block to be declared as the NEXT BLOCK. So, we'll use a more simplified model as described as follows:<br/>
"Every node in the network has a chance to be the "fastest" block proposer with a fixed probability. The simulation will toss a die to select a node that happen to be the lucky node to be picked as the fastest block proposer."

In a real world, every blockchain node has a different CPU power, and in some case it can buy a table of pre-computed hash table. For this, every blockchain node has a different probability to be the fastest block producer. However, this simulation is not for the detailed process of PoW block producing. So we will use the universal fixed probability for every blockchain node.

In a PoS or DPoS consensus model, a node can have a blockchain stake, or a ballot to produce a block to be included in the blockchain. In a pure PoS-like model, one of the nodes is randomly elected as a block producer. There is no on-the-fly competition like PoW race. So, we can summarize the PoS consensus rule to be like the following:<br/>
"Every node in the network has a chance to be the "chosen" block producer with a fixed probability. The simulation will toss a die to select a node that happen to be the lucky node to be elected as the block producer."

As we can see here, there is no difference between PoW and PoS in this simulation.
