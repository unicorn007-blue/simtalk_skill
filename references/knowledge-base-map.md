# Knowledge Base Map

Index of Plant Simulation documentation files. Use `read_file` to access any file when deeper API details are needed.

**Base path:** `./knowledge_base/pts_help_2504/` (relative to this skill's root directory)

---

## Quick Lookup by Topic

> **When to open KB file:** the API Index entry lacks the specific attribute/method, sensor callback details, or dialog property you need. Otherwise rely on the API Index.

| Object | Use when... | File |
|--------|-------------|------|
| **EventController** | sim clock, start/stop/reset, ExperimentManager link | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/04_EventController.md` |
| **Station** | single-MU processing, setup, failures | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/09_Station.md` |
| **ParallelStation** | multi-place (XDim×YDim) processing | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/10_ParallelStation.md` |
| **AssemblyStation** | attach mounting parts to a main part | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/11_AssemblyStation.md` |
| **DismantleStation** | split one MU into multiple | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/12_DismantleStation.md` |
| **PickAndPlace_Robot** | robot pick/place between predecessors/successors | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/13_PickAndPlace_Robot.md` |
| **Buffer** | FIFO/LIFO MU storage, dwell time | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/16_Buffer.md` |
| **PlaceBuffer** | indexed-place buffer with addressing | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/15_PlaceBuffer.md` |
| **Conveyor** | continuous transport, accumulating logic | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/18_Conveyor.md` |
| **Source** | MU creation, intervals, distributions | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/07_Source.md` |
| **Drain** | MU removal, throughput stats, type stats | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/08_Drain.md` |
| **Store** | 3D grid storage (X,Y,Z), findFreePlace, supermarket | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/14_Store.md` |
| **Connector** | material flow connections, dynamic .connect | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/03_Connector.md` |
| **Frame** | sub-models, hierarchy, interfaces | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/05_Frame.md` |
| **FlowControl** | routing rule object (priority, ratio, blocking) | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/25_FlowControl.md` |
| **Sorter** | sequence-based sorting & merging | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/17_Sorter.md` |
| **Turntable / Turnplate** | rotating transfer between tracks/conveyors | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/21_Turntable.md` |
| **Track / TwoLaneTrack** | length-oriented paths for AGVs/transporters | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/23_Track.md` |
| **AGVPool** | AGV fleet manager, getIdleAGV | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/07_AGVPool.md` |
| **Marker** | AGV waypoint network, free-movement routing | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/08_Marker.md` |
| **Worker** | labor resource, services, travel modes | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/04_Worker.md` |
| **WorkerPool** | worker creation, shifts, parts buffer | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/03_WorkerPool.md` |
| **Broker** | service request mediation (import/export ctrl) | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/06_Broker.md` |
| **Workplace** | location where a worker performs a service | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/01_Workplace.md` |
| **ShiftCalendar** | shift schedules, breaks, calendar exceptions | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/04_Resource_Objects/09_ShiftCalendar.md` |
| **DataTable** | typed tables, column access, sort/insert | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/05_Information_Flow_Objects/04_DataTable.md` |
| **Method** | SimTalk method object, params, return | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/05_Information_Flow_Objects/01_Method.md` |
| **Trigger** | time-based attribute/method driver | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/05_Information_Flow_Objects/09_Trigger.md` |
| **Generator** | periodic interval method activation | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/05_Information_Flow_Objects/10_Generator.md` |
| **AttributeExplorer** | tabular bulk attribute editing | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/05_Information_Flow_Objects/11_AttributeExplorer.md` |
| **GanttChart** | Gantt visualization from log tables | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/06_User_Interface_Objects/05_GanttChart.md` |
| **ExperimentManager** | parametric studies, multi-run, optimization | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/08_Tools/04_ExperimentManager.md` |
| **BottleneckAnalyzer** | identify constraints across stations | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/08_Tools/02_BottleneckAnalyzer.md` |
| **MU / Mobile Units** | base concepts: move, cont, attributes | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/07_Mobile_Objects/01_Mobile_Units_MUs.md` |
| **Transporter** | self-moving MU subtype (folder) | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/07_Mobile_Objects/04_Transporter/` |
| **Container** | MU that carries other MUs | `./knowledge_base/pts_help_2504/11_Objects_Reference_Help/07_Mobile_Objects/03_Container.md` |

---

## SimTalk Language Reference

| Topic | Use when... | File |
|-------|-------------|------|
| SimTalk overview | high-level orientation | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/01_SimTalk_Reference.md` |
| SimTalk 2.0 vs 1.0 | converting legacy 1.0 syntax | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/02_SimTalk_20_and_SimTalk_10_Compared.md` |
| Quick tour SimTalk 2.0 | learn the syntax fast | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/03_A_Quick_Tour_Through_SimTalk_20.md` |
| Variables | `var` declaration, scope | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/06_Variables.md` |
| Parameters | `param` keyword, in/out/inout | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/07_Parameters_in_SimTalk.md` |
| Data Types | all built-in types (time, length, etc.) | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/08_Data_Types.md` |
| Operators & Expressions | precedence, assignment, comparison | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/09_Operators_and_Expressions.md` |
| Control Flow | if/switch/for/while/exitloop/return | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/10_Control_Flow_Statements.md` |
| Math functions | sqrt, sin, abs, mod, etc. | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/11_Predefined_Functions/02_Mathematical_Functions.md` |
| Date/Time functions | str_to_time, str_to_date, time formatting | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/11_Predefined_Functions/04_Functions_for_Managing_Date_and_Time.md` |
| String/Type conversion | to_str, to_num, to_int casts | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/11_Predefined_Functions/10_Functions_for_Converting_Data_Types.md` |
| Output functions | print, debug, messageBox | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/11_Predefined_Functions/09_Output_Functions.md` |
| Debugging functions | breakpoints, profiler, trace | `./knowledge_base/pts_help_2504/12_SimTalk_Reference/04_General_Access_to_SimTalk/11_Predefined_Functions/11_Functions_for_Debugging_the_Model.md` |

---

## Shared Properties (Material Flow Objects)

All material flow objects share common properties documented here:

`./knowledge_base/pts_help_2504/11_Objects_Reference_Help/02_Material_Flow_Objects/02_Shared_Properties/`

Topics include: processing times, failures, exit strategies, statistics, sensors, blocking behavior.

---

## Other Sections

| Section | Path |
|---------|------|
| 3D Reference | `./knowledge_base/pts_help_2504/13_3D_Reference_Help/` |
| Database Interfaces | `./knowledge_base/pts_help_2504/15_Add-Ins_Reference_Help/02_Database_Interfaces.md` |
| Step-by-Step Tutorial | `./knowledge_base/pts_help_2504/10_Step-by-Step_Help/` |
| Program Window | `./knowledge_base/pts_help_2504/09_Plant_Simulation_Program_Window/` |
| What's New | `./knowledge_base/pts_help_2504/02_Whats_New.md` |
| Quick Reference | `./knowledge_base/pts_help_2504/14_Quick_Reference.md` |
