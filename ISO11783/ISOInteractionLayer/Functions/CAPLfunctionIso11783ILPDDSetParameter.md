[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILPDDSetParameter.md)

## Iso11783IL_PDDSetParameter

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_PDDSetParameter

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

- `long Iso11783IL_PDDSetParameter( char paramName[], float paramValue ); // form 1`
- `long Iso11783IL_PDDSetParameter( dbNode simulNode, char paramName[], float paramValue ); // form 2`

### Description

Changes an internal parameter of the PDD API.

### Parameters

- **paramName**

  - **debug**: activates debug outputs in the Write Window
    - 1: on
    - 0: off

  - **autoUpdateVariable**: process variable is updated if value command is received
    - 1: auto update
    - 0: process variable have to be updated manually by [Iso11783IL_PDDSetValue](CAPLfunctionIso11783ILpddsetvalue.md) e.g. in callback function [Iso11783IL_PDDOnDataChanged](CAPLfunctionIso11783ILPDDOnDataChanged.md)

  - **version**: supported version of the ISO11783 specification: 1,2 (default),3, and 4

    Note: Using `version` the version value obtained from the database (node attribute `ISO11783PDDVersion`) is overwritten.

    If `version` is set to 3 or higher, further parameter values can be used for the Version message that is sent by the implement (see specification ISO11783-10, B.5.3).

    - **BootTimeTC**: maximum number of seconds from a power cycle to transmission of the first Task Controller Status message, default: 255
    - **ImplementSectionControl**
      - 1: supports implement section control
      - default: doesn’t support.
    - **PeerControlAssignment**
      - 1: supports peer control assignment
      - default: doesn’t support
    - **TC_GEO_DefinitionPositionBasedControl**
      - 1: TC-GEO definition, position based control
      - default: doesn’t support.
    - **TimeAndPositionForDataLogging**
      - 1: supports time and position for data logging
      - default: doesn’t support
    - **Documentation**
      - 1: supports documentation
      - default: doesn’t support
    - **NumberOfBooms**: minimum required number of booms that the Working Set requires to operate correctly, default: 0
    - **NumberOfSection**: minimum required number of sections that the Working Set requires to operate correctly, default: 0
    - **NumberOfControlChannels**: minimum required number of individual control channels that the Working Set requires to operate correctly, default: 0

    If `version` is set to 3 or higher, further parameter values can be used for the Request Structure Label message that is sent by the implement (see specification ISO11783-10, B.6.2).

    - **RequestForLatestStructureLabel**
      - 1: bytes 2..8 of the Request Structure Label message are transmitted as FF. It is used to determine the version of the latest device description structure present at the Task Controller or Data Logger.
      - 0: default

- **paramValue**

  - New value for the parameter

- **simulNode**

  - Simulation node to apply the function.

### Return Values

- **0**: process data dictionary has been created successfully
- **< 0**: an error has occurred

### Example

```plaintext
if (Iso11783IL_PDDSetParameter( "debug", 1 ) == 0) {
  write( "Debug mode activated" );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)