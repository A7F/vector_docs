[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

[CAPL Functions](../../CAPLfunctions.md) » [J1939](../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](CAPLfunctionsGNSSNLOverview.md) » GNSS Node Layer Error Codes: GNSSGetLastError

# GNSS Node Layer Error Codes: GNSSGetLastError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Error Codes

- **0**: No error; the function was performed successfully
- **1**: General internal error
- **2**: Internal error: The node was not found.
- **3**: Internal error: The internal network table was not found.
- **4**: Internal error: Unable to generate a timer.
- **5**: Internal error: Unable to delete a timer.
- **6**: The node layer was not correctly assigned to the node.
- **24**: The specified PG is not activated (see [GNSSSetPGSettings](Functions/CAPLfunctionGNSSsetpgsettings.md))
- **30**: No node with the specified address was found.
- **31**: A request was not sent.
- **32**: The node layer kernel was not correctly initialized.
- **33**: Error while loading a position file.
- **34**: A specified function parameter is outside the valid range of values.
- **35**: An invalid parameter group number was used.
- **36**: The return value of the function is invalid.
- **37**: Size of reserved buffer is too small for the result string.
- **100**: The simulation has already started.
- **101**: The simulation has already stopped.
- **102**: The speed has already been reset (set to zero).
- **103**: The speed cannot be set to its initial value since it has not been reset.
- **104**: The simulation cannot be started since no parameter group to be sent is defined.
- **105**: The simulation cannot be started since no waypoint has been set.
- **106**: The function failed because the simulation has not been started.
- **107**: The function failed because the simulation has started.
