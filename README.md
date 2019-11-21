# node-topology
This is a `kubectl` plugin to view the topology of CPU and device resources on the current node. `kubectl topology` uses the local CPU Manager and Device Manager checkpoint files to access resource information. Therefore this is a node level application and the plugin is limited to the node on which you are logged in.
## Install
- `cd $GOPATH/src/github.com`
- `mkdir nolancon && cd nolancon`
- `git clone https://github.com/nolancon/node-topology && cd node-topology`
- `go get ./...`
- `go build -ldflags "-X github.com/nolancon/node-topology/cmd.GOPATH=$GOPATH" -o /usr/bin/kubectl-topology`

## Usage
- Display topology of CPU and device resources for the current node:
`kubectl topology node`
- Display topology of assigned CPUs and devices for all pods on current node consuming CPU and/or devices:
`kubectl topology pod`
- Display topology of assigned CPUs and devices for a specified pod:
`kubectl topology pod <pod-name>`
- Help
`kubectl topology --help`
`kubectl topology node --help`
`kubectl topology pod --help`
  #### Note: Only pods on the current node, consuming CPU and/or device resources will be considered by the plugin.
  

  
## Configuration
