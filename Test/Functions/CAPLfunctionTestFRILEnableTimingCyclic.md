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
