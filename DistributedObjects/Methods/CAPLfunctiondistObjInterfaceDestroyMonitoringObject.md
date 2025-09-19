[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjInterfaceDestroyMonitoringObject.md)

## CAPL Functions » Distributed Objects » distObjInterface::DestroyMonitoringObject

### Method Syntax

- `long distObjInterface <Interface>::DestroyMonitoringObject(monitoringDistObjRef <Interface> object);`
- `long distObjInterface <Interface>::DestroyMonitoringObject(monitoringDistObjRef reverse<<Interface>> object);`

### Description

Destroys a dynamic monitoring object from the blueprint.

**Note**: If an error occurs in a test module, the error message will be reported as an error in the test system. Otherwise, a message will be written to the CANoe DE Family Write Window.

### Parameters

- **object**: Dynamic monitoring object to be destroyed.

### Return Values

- **0**: OK
- **1**: An error occurred.

### Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
