[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetValuePresentationData.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_GetValuePresentationData

# TCIL_GetValuePresentationData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_GetValuePresentationData(dbNode client, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale, dword numberOfDecimals, 
dword designatorBufferSize, char designatorBuffer[]); // form 1: deprecated with 13

long TCIL_GetValuePresentationData(dbNode client, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale,
dword numberOfDecimals, char designatorBuffer[]); // form 2

long TCIL_GetValuePresentationData(dword addressClient, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale,
dword numberOfDecimals, char designatorBuffer[]); // form 3

long TCIL_GetValuePresentationData(dbNode tc, dbNode client, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale, dword numberOfDecimals,
dword designatorBufferSize, char designatorBuffer[]); // form 4: deprecated with 13

long TCIL_GetValuePresentationData(dbNode tc, dbNode client, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale,
dword numberOfDecimals, char designatorBuffer[]); // form 5

long TCIL_GetValuePresentationData(dbNode tc, dword addressClient, dword ddi, dword elementNumber,
dword idOfDVP, long offset, float scale,
dword numberOfDecimals, char designatorBuffer[]); // form 6
```

## Description

Returns all properties (id, offset, scale, numberDecimals, designator) of the ValuePresentation object referenced by the DeviceProcessData (DPD) or DeviceProperty (DPT) object defined by DDI/elementNumber.

Form 5 and 6 applicable in test module / test unit only.

## Parameters

- **tc**: TC simulation node to apply the function.
- **client**: TC client node the data entity belongs to.
- **addressClient**: Address of the TC client node the data entity belongs to.
- **ddi**: Data dictionary identifier of DPD/DPT object, 0x0000..0xFFFF.
- **elementNumber**: Element number of DPD/DPT object, 0x000..0xFFF.
- **idOfDVP**: ID of the referenced DVP object. 0xFF means **no DVP object is referenced**.
- **offset**: Property **offset** of the referenced DVP object.
- **scale**: Property **scale** of the referenced DVP object.
- **numberOfDecimals**: Property **numberOfDecimals** of the referenced DVP object.
- **designatorBufferSize**: Size of the return buffer.
- **designatorBuffer**: Return buffer. Contains the designator of the DVP objects as a string.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 5

```plaintext
long result;
char designator[256];
dword idOfDVP, numOfDecimals;
long offset;
float scale;
// Retrieve all properties of the DVP object used by the DPD with DDI=17 and elementNumber=3
// from DDOP uploaded by Sprayer to TC
result = TCIL_GetValuePresentationData(TC, Sprayer, 17, 3, idOfDVP, offset, scale, numOfDecimals, 256, designator);
```
