[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSaveAsImage.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_SaveAsImage**

# VTIL_SaveAsImage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_SaveAsImage(dbNode workingSetMaster, dword maskOrSoftkey, char imagePath[]); // form 1`
- `long VTIL_SaveAsImage(dword addressWorkingSetMaster, dword maskOrSoftkey, char imagePath[]); // form 2`
- `long VTIL_SaveAsImage(dbNode workingSetMaster, char imagePath[]); // form 3`
- `long VTIL_SaveAsImage(dword addressWorkingSetMaster, char imagePath[]); // form 4`
- `long VTIL_SaveAsImage(char imagePath[]); // form 5`
- `long VTIL_SaveAsImage(dbNode vt, dbNode workingSetMaster, dword maskOrSoftkey, char imagePath[]); // form 6`
- `long VTIL_SaveAsImage(dbNode vt, dword addressWorkingSetMaster, dword maskOrSoftkey, char imagePath[]); // form 7`
- `long VTIL_SaveAsImage(dbNode vt, dbNode workingSetMaster, char imagePath[]); // form 8`
- `long VTIL_SaveAsImage(dbNode vt, dword addressWorkingSetMaster, char imagePath[]); // form 9`
- `long VTIL_SaveAsImage(dbNode vt, char imagePath[]); // form 10`

## Description

- Form 1, 2, 6, 7 saves the current Data/Alarm Mask or one of the current Soft Keys of the specified Working Set as an image.
- Form 3, 4, 8 and 9 saves the current Data/Alarm Mask and all Soft Keys of the specified Working Set as a single image.
- Form 5 and 10 saves the current Data/Alarm Mask and all Soft Keys of the active Working Set as a single image.
- An existing file is overwritten.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master which Data/Alarm Mask or Soft Key is saved as an image (must not be the active Working Set)
- **addressWorkingSetMaster**: Address of the Working Set Master which Data/Alarm Mask or Soft Key is saved as an image (must not be the active Working Set)
- **maskOrSoftkey**:
  - 0: Current active Data or Alarm Mask
  - 1-64: A current active Soft Key
- **imagePath**: Saves the current Data/Alarm Mask or/and soft key(s) in this file (*.bmp, *.png, *.jpg or *.gif). Path has to be absolute or relative relating to the folder of the CANoe configuration.

## Return Values

- **0**: Data/Alarm Mask has been saved successfully.
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

Example form 6:

```c
long result;
result = VTIL_SaveAsImage(VT, Loader, 0, "BMP\\DataMask.bmp");
switch (result)
{
  case 0: TestStepPass(); break;
  case -2113: TestStepFail("Invalid parameter!"); break;
  case -2122: TestStepFail("Failed to save active Data Mask to file!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
