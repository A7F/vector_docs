[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPLoad.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPLoad

# Iso11783OPLoad

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

In case the corresponding node is running in the distributed environment, the object pool file has to be registered under **Configuration | Options… | Configuration Settings | User files** in CANoe.

## Function Syntax

```plaintext
long Iso11783OPLoad( dword ecuHandle, char filename[] );
long Iso11783OPLoad( dword ecuHandle, char filename[], char version[] );
```

## Description

The function loads an object pool file (*.iop). All other object pool access functions can only be used if an object pool is loaded.

If the activation of the object pool was already done, the object pool is transmitted to the Virtual Terminal immediately. If not, this happens when the activation is done with [Iso11783OPActivate](CAPLfunctionIso11783OPActivate.md).

Optional a version designator for the object pool can be specified. The node layer tries to load the version with the **Load Version** command. If this is successful the object pool must not be transmitted to the Virtual Terminal.

## Parameters

- **ecuHandle**  
  Handle of the ECU.  
  The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

- **filename**  
  Filename of an object pool file (*.IOP)

- **version**  
  Optional designator of the object pool version

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword handle = 0;
handle = Iso11783CreateECU( gECUName );

Iso11783OPLoad( handle, "ObjectPool.iop", "pool001" );
ISo11783OPActivate( handle);
Iso11783ECUGoOnline(handle, gECUAddress );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
