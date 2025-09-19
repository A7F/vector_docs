[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetElementNumbers.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetElementNumbers**

# TCIL_GetElementNumbers

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long TCIL_GetElementNumbers(dbNode client, long ddi, word[] elementNumbers, long length); // form 1`
- `long TCIL_GetElementNumbers(long clientAddress, long ddi, word[] elementNumbers, long length); // form 2`
- `long TCIL_GetElementNumbers(dbNode tc, dbNode client, long ddi, word[] elementNumbers, long length); // form 3`
- `long TCIL_GetElementNumbers(dbNode tc, long clientAddress, long ddi, word[] elementNumbers, long length); // form 4`

## Description

Seeks the device description of a client for the given DDI.

## Parameters

- **client**: Node of the client.
- **ddi**: DDI to seek.
- **elementNumbers**: Out parameter with found element numbers corresponding to the given DDI.
- **length**: Length of the given array.
- **clientAddress**: Address of the client.
- **tc**: Simulation Node to apply the function.

## Return Values

- **≥ 0**: Number of found element numbers.
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
void GetElementNumbers(long ddi, long address)
{
  word elNumBuffer[255];
  long elemenCount, idx;

  elemenCount = TCIL_GetElementNumbers(address, ddi, elNumBuffer, elcount(elNumBuffer));
  if(elemenCount < 0)
  {
    write("TCIL_GetElementNumbers returned an error: %d", elemenCount);
    return;
  }
  for(idx = 0; idx < elemenCount; idx++)
  {
    write("DDI is contained in ElNum: %d", elNumBuffer[idx]);
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
