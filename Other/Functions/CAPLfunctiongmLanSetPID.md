[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctiongmLanSetPID.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » gmLanSetPID, gmLanSetSourceId, gmLanSetPrio, gmLanGetPID, gmLanGetSourceId, gmLanGetPrio

# gmLanSetPID, gmLanSetSourceId, gmLanSetPrio, gmLanGetPID, gmLanGetSourceId, gmLanGetPrio

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `gmLanSetPID(gmLanMessage msg, long v);`
- `gmLanSetSourceId(gmLanMessage msg, long v);`
- `gmLanSetPrio(gmLanMessage msg, long v);`
- `gmLanGetPID(gmLanMessage msg);`
- `gmLanGetSourceId(gmLanMessage msg);`
- `gmLanGetPrio(gmLanMessage msg);`

## Description

- `gmLanSetPID` sets the parameter ID of the message.
- `gmLanSetSourceId` sets the source address of the message.
- `gmLanSetPrio` sets the priority of the message.
- `gmLanGetPID` gets the parameter ID of the message.
- `gmLanGetSourceId` gets the source address of the message.
- `gmLanGetPrio` gets the priority of the message.

## Parameters

- **msg**: Message
- **v**: Parameter ID, source address or priority

## Return Values

- `gmLanSetPID`, `gmLanSetSourceId`, `gmLanSetPrio`: —
- `gmLanGetPID`, `gmLanGetSourceId`, `gmLanGetPrio`: Parameter ID, source address or priority

## Example

A GMLAN message is modified and sent with **output(msg)**.  
The parameter ID is set with selector **gm_pid**.

```plaintext
gmLanMessage * msg1 ={SA =0x44, PRIO=  0x7,  gm_pid=0x11};
gmLanSetSourceId(msg1,0x55);
gmLanSetPID(msg1,0x11);
gmLanSetPrio(msg1,0x5);

output(msg1);

write("pid: 0x%x, source: 0x%x, prio:  x%x",gmLanGetPID(msg1),gmLanGetSourceId(msg1),gmLanGetPrio(msg1));
```

Priority and source address are copied from **Battery_Voltage** message to the new message **msg**:

```plaintext
on gmlanmessage  Battery_Voltage
{
  gmlanmessage Battery_Voltage msg;
  msg = this;  // SA and PRIO are not copied
  gmLanSetSourceId(msg, gmLanGetSourceId(this));
  // Copy  source address from Battery_Voltage to msg
  gmLanSetPrio(msg,  gmLanGetPrio(this));
  // Copy priority from Battery_Voltage to msg
  ...
}
```

[GMLAN add-on](../../../CANoeCANalyzer/Interfaces/GMLAN.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
