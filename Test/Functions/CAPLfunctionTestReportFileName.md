# TestReportFileName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

This command should only be used if the filename of the test report has to be assigned dynamically by the test module. If the function is called several times in the same test, the last call will set the final report name.

## Function Syntax

```
TestReportFileName (char data name[]);
```

## Description

Sets the name and path of a report file. In the GUI, the name and path of a report file can be set. With this function, these settings can be overwritten.

## Parameters

- **data name**: Name and path of the report file. Without path specification, the directory of the configuration file is used. The extension `.xml`, `.html` or `.vtestreport` is added automatically.

## Return Values

—

## Example

```c
void MainTest()
{
   // report is written in a file with the name ‘DynamicName’ beside the configuration
   TestReportFileName("DynamicName");
}
```
