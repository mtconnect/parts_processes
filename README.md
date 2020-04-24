# MTConnect Parts and Processes
The Parts & Processes working group is developing extensions to the MTConnect standard for collecting and associating information about what a device is doign (*Which Process?*) and what it is currently operating on (*Which Part?*)

This repository is intended to be a prototype of the information models that would be proposed to the standard. A more extensive read-me will be coming soon, but I wanted to provide some initial documentation:
- The draft architecture document can be found here: https://www.overleaf.com/read/svdmvvscnzrk
- Issues can be logged: http://projects.mtconnect.org/projects/parts

This repository is set up to replicate the functionality of the `./agent/cppagent/simulator` directory that comes when you install the agent/adapter simulator per http://mtcup.org/wiki/Installing_C%2B%2B_Agent_on_Ubuntu
- The following files have been modified:
  - `VMC-3Axis.xml`
  - `VMC-3Axis-Log.txt`
  - `agent.cfg`
- Rather than rewrite the systemctl script (which you can if you'd like), you start the agent from this directory:
  - `/usr/local/bin/agent run ./agent.cfg`
- Same for the adapter:
  - `/usr/bin/ruby /etc/mtconnect/adapter/run_scenario.rb -l ./VMC-3Axis-Log.txt
  - OR `/usr/bin/ruby ./run_scenario.rb -l ./VMC-3Axis-Log.txt`

# Current progress
- `VMC-3Axis.xml` includes dataItems for **PartRecord** and **ProcessExecutionRecord**
- `VMC-3Axis-Log.txt` has some instance values for those dataItems included as part of device's stream
  - **TO DO:** the example in the log needs to probably include two parts/processes from start to finish, need to add more detail to the log file.
- `./AssetDefinitions` includes examples of **PartDefinition** and **ProcessDefinition*
  - `partsProcess_scenario.txt` includes curl commands to post these definitions to the agent. The curl commands are the order that you'd expect them to be resolved. Future work is to integrate these into the log file.
