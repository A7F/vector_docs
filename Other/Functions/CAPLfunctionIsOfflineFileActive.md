[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionIsOfflineFileActive.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » isOfflineFileActive

# isOfflineFileActive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long isOfflineFileActive(long index);
```

## Description

Returns whether events of an offline source file are currently replayed, i.e., the start of the source file has been reached but the end of the source file has not yet been reached.

## Parameters

- **index**: Index of the offline source file.

## Return Values

- **-1**: If error (e.g., not in offline mode)
- **0**: Start of offline source file not yet reached, or end of offline source file already reached.
- **1**: Start of offline source file reached, but end of offline source file not yet reached.

## Example

```c
long isActive;
char buffer[256];
long numFiles;
long i;

numFiles = getNumOfflineFiles();
for (i = 0; i < numFiles; ++i)
{
  getOfflineFileName(i, buffer, 256);
  isActive = isOfflineFileActive(i);
  if (isActive)
  {
    write("Offline file %s is active", buffer);
  }
  else
  {
    write("Offline file %s is inactive", buffer);
  }
}
```
