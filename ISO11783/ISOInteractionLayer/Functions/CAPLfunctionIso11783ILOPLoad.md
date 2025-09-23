[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPLoad.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPLoad

# Iso11783IL_OPLoad

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
In case the corresponding node is running in the distributed environment, the object pool file has to be registered in **Options** dialog (**Configuration Settings|User files**) in CANoe DE product.

## Function Syntax

- `long Iso11783IL_OPLoad( char filename[] ); // form 1`
- `long Iso11783IL_OPLoad( char filename[], char version[] ); // form 2`
- `long Iso11783IL_OPLoad( dbNode implement, char filename[], char version[] ); // form 3`
- `long Iso11783IL_OPLoad( char filename[], char version[], long options ); // form 4`
- `long Iso11783IL_OPLoad( dbNode implement, char filename[], char version[], long options ); // form 5`

## Description

The function loads an object pool file (*.iop or *.iopx). All other object pool access functions can only be used if an object pool is loaded.

If the activation of the object pool was already done, the object pool is transmitted to the Virtual Terminal immediately. If not, this happens when the activation is done with [Iso11873IL_OPActivate](CAPLfunctionIso11783ILOPActivate.md).

Optional a version designator for the object pool can be specified. The node layer tries to load the version with the **Load Version** command. If this is successful the object pool must not be transmitted to the Virtual Terminal.

It is possible to send an object pool in separate files. Therefore, the function syntax **form 4** and **form 5** are used. By setting a flag in the options parameter the **End of Object Pool** message is omitted.

By default, the interaction layer tries to parse the given object pool. If an error occurs the interaction layer stops the upload. In some test cases, it may be helpful to send an object pool as it is without any checks to upload an erroneous object pool. For that case **form 4** and **form 5** provide another flag in the options parameter to avoid the checks.

**Note**  
This function is not necessary if a node was configured completely in the database (DBC):  
**ISO11783IOPFilename** and **ISO11783IOPVersion** are defined and **VT21** message is assigned to the node.

## Parameters

- **filename**: Filename of an object pool file (*.iop or *.iopx)
- **version**: Designator of the object pool version. Pass an empty string if no version should be loaded and the defined object pool should be sent directly to the virtual terminal.
- **implement**: Simulation node to apply the function.
- **options**: bitmask:
  - Bit 0: Suppress **End of Object Pool** message
  - Bit 1: Suppress parsing before sending, send raw data.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example 1**  
`Iso11783IL_OPLoad( "ObjectPool.iop", "pool001" );`  
`Iso11783IL_OPActivate();`

**Example 2**  

```
//Upload Object Pool separated in multiple files.
Iso11783IL_OPLoad( "ObjectPool_Part1.iop", "pool001", 0x01 );
Iso11783IL_OPLoad( "ObjectPool_Part2.iop", "pool001", 0 );
Iso11783IL_OPActivate();
```

**Example 3**  

```
//Upload Object Pool and suppress parsing to be able to upload an erroneous Object Pool
Iso11783IL_OPLoad( "ObjectPool.iop", "pool001", 0x02 );
Iso11783IL_OPActivate();
```
