# NifiTemplatizer
The purpose of this project is to create exports of NiFi workspaces that are easier for developers to read and modify. With that purpose in mind, a simplified YAML format was generated to concisely express the content in the NiFi workspace. As an added bonus, the simplified YAML format also makes it easier to perform standard actions (diffs/merges/etc) in version control systems to track changes over time to the NiFi workspace.

# Commands:
* Import (60% complete)
  - [x] Generic
    - [x] Position
  - [ ] Controllers
    - [x] Name
    - [ ] Annotation Data
    - [x] Comments
    - [ ] Properties
  - [ ] Processors
    - [x] Name
    - [ ] Styles (Colors/Fonts)
    - [x] Properties
    - [ ] Annotation Data (advanced rules)
    - [ ] Scheduling 
      - (schedulingStrategy, schedulingPeriod, maxTasks, penaltyDuration, yieldDuration, runDuration, executionNode)
    - [ ] Bulletin Level
    - [ ] Terminated relationships
    - [x] Comments
  - [ ] Ports (Input/Output)
    - [x] Name
    - [ ] Comments
  - [x] Funnels
  - [x] Process Groups
    - [x] Name
    - [x] Comments (works on update call only)
  - [ ] Remote Process Groups
    - [x] TargetUris
    - [x] Name
    - [ ] Comments
    - [ ] Yield Duration
    - [ ] Connection Properties:
      - Proxy Host, Proxy Port, Proxy User, Proxy Password
      - Communications timeout, Transport Protocol, Local Network Interface
  - [x] Labels
    - [x] Comment
    - [x] Styles (Colors/Fonts)
    - [x] Width/Height
  - [ ] Connectivity (Inputs/Outputs/Relationships) (90%)
    - [x] Name
    - [ ] Queueing properties
      - FlowFileExpiration, BackPressureObjectThreshold, BackPressureDataSizeThreshold, Prioritizers
      - Load balance strategy, load balance compression
    - [ ] Link bends (aesthetic)
    - [ ] Label Index?
    - [ ] Z index
    - [ ] Links to/from RemoteProcessGroups
* Export (95% complete)
  - [x] Generic
    - [x] Position
  - [x] Dependency Tree
    - [x] Extract all dependencies of workspace
    - [x] Canonical name generation for dependencies
  - [ ] Controllers
    - [x] Name
    - [ ] Annotation Data
    - [x] Comments
    - [x] Properties
  - [ ] Processors
    - [x] Name
    - [x] Styles (Colors/Fonts)
    - [x] Properties
    - [x] Annotation Data (advanced rules)
    - [ ] Scheduling 
      - (schedulingStrategy, schedulingPeriod, maxTasks, penaltyDuration, yieldDuration, runDuration, executionNode)
    - [ ] Bulletin Level
    - [ ] Terminated relationships (may just be implied)
    - [x] Comments
  - [x] Ports (Input/Output)
    - [x] Name
    - [x] Comments
  - [x] Funnels
  - [ ] Process Groups
    - [x] Name
    - [x] Comments
    - [ ] TODO: De-duplicate structurally similar templates (extract variables for varying properties)
  - [ ] Remote Process Groups
    - [x] TargetUris
    - [x] Name
    - [x] Comments
    - [ ] Yield Duration
    - [ ] Connection Properties:
      - Proxy Host, Proxy Port, Proxy User, Proxy Password
      - Communications timeout, Transport Protocol, Local Network Interface
  - [x] Labels
    - [x] Comment
    - [x] Styles (Colors/Fonts)
    - [x] Width/Height
  - [ ] Connectivity (Inputs/Outputs/Relationships) (90%)
    - [x] Name
    - [ ] Queueing properties
      - FlowFileExpiration, BackPressureObjectThreshold, BackPressureDataSizeThreshold, Prioritizers
      - Load balance strategy, load balance compression
    - [x] Link bends (aesthetic)
    - [ ] Label Index?
    - [ ] Z index
* Clean (100% complete)
  - Remove all content from workspace (clean slate)
* Set State (100% complete)
  - Enable or disable all processors in a workspace
* Permissions (0% complete)
  - TODO: Give all permissions to specified user

# Example
Test workspace to cover lots of commonly used features in NiFi. The exported YAML is roughly 1/10th the size of the XML template export.

Total Size: 
- YAML Export = 5297 bytes (8% size of XML)
- XML  Export = 66842 bytes

[Export of the NiFi template XML](https://github.com/profour/NifiTemplatizer/blob/master/examples/simple/Simple_Example.xml)

[Export of the Root workspace](https://github.com/profour/NifiTemplatizer/blob/master/examples/simple/root.yaml)

[Export of the Test Subgroup](https://github.com/profour/NifiTemplatizer/blob/master/examples/simple/bbfb5e15-016c-1000-24e9-c7827e34b838.yaml)


Input Root workspace:
![](examples/simple/root.png)

Test Process Group workspace:
![](examples/simple/subprocessgroup.png)
