[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/CAPLfunctionsGNSSNLOverview.md)

**CAPL Functions** » **1939** » **GNSS Node Layer**

# GNSS Node Layer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## J1939

- Only available with J1939.
- To use the CAPL functions, the node layer via the [module description file](../../../Shared/Interfaces/VModule/VModule.md) [GNSS_NL.vmodule](../../../CANoeCANalyzer/J1939/gnssNL/gnssNLOverview.md) must be included.
- You can include the node layer by using the configuration dialog of the node on page **Components** or via the node attribute **NodeLayerModules** in the database.

---

**ON THIS PAGE:**

- [Events](#Events)
- [Node Control](#Node)
- [Other Function](#Other)
- [Settings](#Settings)
- [Simulation](#Simulati)
- [Waypoints](#Waypoints)

## Events [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSAppAddrClaimed](Functions/CAPLfunctionGNSSappaddrclaimed.md) | Identifies an Address Claiming procedure that was performed successfully. |
| [GNSSAppCmdAddrIndication](Functions/CAPLfunctionGNSSappcmdaddrindication.md) | Indicates that a new address has been assigned to the node. |
| [GNSSAppErrorIndication](Functions/CAPLfunctionGNSSapperrorindication.md) | Identifies errors. |
| [GNSSOnLastWpReached](Functions/CAPLfunctionGNSSonlastwpreached.md) | Is called when the last waypoint of the waypoint list has been reached. |
| [GNSSOnSetSpeed](Functions/CAPLfunctionGNSSonsetspeed.md) | Is called if the speed of the simulation has been changed. |
| [GNSSOnWpBeforeLastReached](Functions/CAPLfunctionGNSSonwpbeforelastreached.md) | Is called when the next-to-last waypoint of the waypoint list has been reached. |

## Node Control [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSGetAddress](Functions/CAPLfunctionGNSSgetaddress.md) | Returns a network address. |
| [GNSSGetName](Functions/CAPLfunctionGNSSgetname.md) | Returns the J1939 device name of a control device. |
| [GNSSMakeName](Functions/CAPLfunctionGNSSmakename.md) | Generates a J1939 device name. |
| [GNSSShutDown](Functions/CAPLfunctionGNSSshutdown.md) | Removes the node from the network. |
| [GNSSStartUp](Functions/CAPLfunctionGNSSstartup.md) | Sets up a logical node within a CANoe network node. |
| [GNSSUpdateTable](Functions/CAPLfunctionGNSSupdatetable.md) | Updates the network table. |

## Other Functions [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSGetAbsFilePath](Functions/CAPLfunctionGNSSGetAbsFilePath.md) | Gets the absolute path of a file. |
| [GNSSGetLastError](Functions/CAPLfunctionGNSSgetlasterror.md) | Returns the error status of the last executed function. |

## Settings [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSSetCOGSOGVal](Functions/CAPLfunctionGNSSSetCOGSOGVal.md) | Changes the value of the parameter group **COG&SOG, Rapid Update**. |
| [GNSSSetJitterAlt](Functions/CAPLfunctionGNSSsetjitteralt.md) | Sets the jitter by which the altitude deviates from its nominal value. |
| [GNSSSetJitterLatLon](Functions/CAPLfunctionGNSSsetjitterlatlon.md) | Sets the jitter by which the longitudinal and latitudinal degree deviates from the respective nominal value. |
| [GNSSSetPGSettings](Functions/CAPLfunctionGNSSsetpgsettings.md) | Changes the values of individual parameter groups. |
| [GNSSSetPosDataVal](Functions/CAPLfunctionGNSSsetposdataval.md) | Changes the value of the parameter group **GNSS Position Data**. |
| [GNSSSetUnits](Functions/CAPLfunctionGNSSsetunits.md) | Determines the system of measurement units. |

## Simulation [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSContinueSpeed](Functions/CAPLfunctionGNSScontinuespeed.md) | Restores an old speed. |
| [GNSSGetCurCourse](Functions/CAPLfunctionGNSSgetcurcourse.md) | Returns the current course of the GNSS receiver. |
| [GNSSGetCurGradient](Functions/CAPLfunctionGNSSgetcurgradient.md) | Returns the current gradient of the GNSS receiver. |
| [GNSSGetCurSpeed](Functions/CAPLfunctionGNSSgetcurspeed.md) | Returns the current speed at which the GNSS receiver is moving. |
| [GNSSPauseSpeed](Functions/CAPLfunctionGNSSpausespeed.md) | Sets the speed to zero, temporarily. |
| [GNSSSetCourse](Functions/CAPLfunctionGNSSsetcourse.md) | Determines a new course and a new gradient for the GNSS receiver. |
| [GNSSSetSpeed](Functions/CAPLfunctionGNSSsetspeed.md) | Sets the speed at which the GNSS receiver moves. |
| [GNSSStartSimulation](Functions/CAPLfunctionGNSSstartsimulation.md) | Starts the simulation. |
| [GNSSStopSimulation](Functions/CAPLfunctionGNSSstopsimulation.md) | Stops the simulation. |

## Waypoints [▲ back](#Shortcuts)

| Function | Short Description |
|----------|-------------------|
| [GNSSAddWp](Functions/CAPLfunctionGNSSaddwp.md) | Inserts a new waypoint at the end of the waypoint list. |
| [GNSSAddWpFile](Functions/CAPLfunctionGNSSaddwpfile.md) | Inserts the GNSS positions of a file into the waypoint list. |
| [GNSSAddWpLine](Functions/CAPLfunctionGNSSaddwpline.md) | Describes a line. |
| [GNSSAddWpMeander](Functions/CAPLfunctionGNSSaddwpmeander.md) | Describes a meander with rounded off corners. |
| [GNSSAddWpRect](Functions/CAPLfunctionGNSSaddwprect.md) | Describes a rectangle with rounded off corners. |
| [GNSSAddWpRef](Functions/CAPLfunctionGNSSaddwpref.md) | Inserts a new waypoint at the end of the waypoint list. |
| [GNSSAddWpRefS](Functions/CAPLfunctionGNSSaddwprefs.md) | Inserts a new waypoint at a given speed at the end of the waypoint list. |
| [GNSSAddWpRel](Functions/CAPLfunctionGNSSaddwprel.md) | Inserts a new waypoint at the end of the waypoint list. |
| [GNSSAddWpRelS](Functions/CAPLfunctionGNSSaddwprels.md) | Inserts a new waypoint at a given speed at the end of the waypoint list. |
| [GNSSAddWpS](Functions/CAPLfunctionGNSSaddwps.md) | Inserts a new waypoint at a given speed at the end of the waypoint list. |
| [GNSSGetCurAlt](Functions/CAPLfunctionGNSSgetcuralt.md) | Returns the current altitude at which the receiver is located. |
| [GNSSGetCurLat](Functions/CAPLfunctionGNSSgetcurlat.md) | Returns the current latitude at which the receiver is located. |
| [GNSSGetCurLon](Functions/CAPLfunctionGNSSgetcurlon.md) | Returns the current longitude at which the receiver is located. |
| [GNSSRemoveWp](Functions/CAPLfunctionGNSSremovewp.md) | Deletes all waypoints of the waypoint list. |
| [GNSSSetRefPoint](Functions/CAPLfunctionGNSSsetrefpoint.md) | Defines reference points. |

[Error Codes GNSSAppErrorIndication](CAPLfunctionsGNSSNLErrorCodesAppErrorIndication.md) • [Error Codes GNSSGetLastError](CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)