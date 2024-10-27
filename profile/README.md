# Dynamo

## Server(Process)
Attributes:
* info: ServerInfo
* ring: Ring
* storage: Storage
* cmdQueue: CmdQueue

Methods:
* processRequests()  // Thread to process reqests in cmdQueue
* recv()  // Thread to receive messages and add to cmdQueue
* _read()
* _write()

## Ring
Attributes:
* servers: set[ServerInfo]
* state: SortedList[VirtualNode]

Methods:
* addNode()
* mapKeyToServer(key: int)
* gossip()  // Thread
* sendHintedHandoffs()  // Thread
* _send()

## Virtual Node
Attribtes:
* info: ServerInfo
* pos: int

## ServerInfo
Attributes:
* ip: string
* port: int
* name: string

## Client
Methods:
* read(key: int)
* write()

## Storage
TODO
