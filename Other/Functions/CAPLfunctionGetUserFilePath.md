[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetUserFilePath.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getUserFilePath

# getUserFilePath

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The main application case for this function is to forward the path of a registered user file to a CAPL DLL in case of a [distributed environment](../CAPLfunctionsEventProceduresOverview.md). The function is, however, also available in a single Computer setup.

## Function Syntax

`long getUserFilePath(char fileName[], char absPath[], long absPathLen);`

## Description

Gets the absolute path of a [user file](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md).

In case of execution in a distributed environment, the absolute user file path (including filename) on the remote device (e.g., VN8900) is returned if the user file was predefined. If the file was not predefined, an error code is returned.

In case of a single Computer environment, the registered absolute file path (including filename) of the user file is returned if the user file was predefined. If the file was not predefined, the function returns the same result as [getAbsFilePath](CAPLfunctionGetAbsFilePath.md) (converting a path relative to the configuration directory to an absolute path).

## Parameters

- **fileName**: A filename potentially containing a path. If the filename is predefined, the path is ignored. Otherwise, the path is interpreted as relative to the current configuration path in a single Computer environment.
- **absPath**: Buffer to which the full path name should be copied.
- **absPathLen**: Size of the buffer [in bytes] for the full path name.

## Return Values

On success, this function returns the length of the full path name. Otherwise, the function returns -1 if parameters do not fit or buffer size is too small, or -2 if no user file with the given name was registered in case of a distributed environment.

## Example

```plaintext
on preStart
{
    char absPath[256];
    getUserFilePath("MyCAPLDll.INI", absPath, 256);
    MyCAPLDllFunction(absPath);
}
```

[RegisterUserFile](CAPLfunctionRegisterUserFile.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
