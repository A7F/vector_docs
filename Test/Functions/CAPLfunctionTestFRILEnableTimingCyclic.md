[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestFRILEnableTimingCyclic.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestFRILEnableTimingCyclic

# TestFRILEnableTimingCyclic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

```plaintext
long TestFRILEnableTimingCyclic(char pduName[], int enable);
```

## Description

Controls the cyclic timing of PDUs. The cyclic timing can be enabled/disabled. This function influences a simulation node with an assigned CANoe Interaction Layer.

**Note**  
Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDUName**: Name of the PDU that should be modified.
- **enable**:
  - 0 = disable
  - 1 = enable

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```plaintext
int enable;
.....
If( stopCyclicSending == 1 )
{
   enable = 0;
}
else
{
   enable = 1;
}
TestFRILEnableTimingCyclic(pduXY, enable);
.....
```

[OEM Addn Based Fault Injection Functions](../CAPLfunctionsTFSOverview.md#OEMPackageFaultInjection)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
