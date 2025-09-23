# TestValidateSystemCallWithExitCode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

This test function is intended to invoke application calls in the test sequence. The provided command will be looked-up and executed on that platform, the user can access:

- Generally: Command is looked-up and executed on the local computer.
- RT server: Command is looked-up and executed on the remote (RT) computer.
- VN8900/VT6000: Command is looked-up and executed on the local computer.
- Standalone mode: Command is looked-up and executed on the standalone device.

**Note on Exitcode**

Windows supplies exitcodes for applications in the range from 0 to 255. 255 is always supplied for applications which generate internal values outside this range (e.g., negative values). You might need to take this into account when setting the **aExitcode** parameter.

**Note on Application Directory**

If no application directory has been set, the working directory of the external application is set by default as follows:

- Execution on a local computer, test module in the test setup: directory that contains the **.TSE** file of the test environment.
- Execution on a local computer, test module in the Simulation Setup or test unit: directory that contains the **.CFG** file of the configuration.
- Execution on a remote computer (distributed mode): `Exec32` directory of the CANoe installation on the remote computer.

**Note for Using [User Files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) (for Distributed Mode or Standalone Mode only)**

To avoid absolute paths in CAPL code and to be independent of the execution platform, proceed as follows:

- Add the application to be started to the User Files in [Options](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) dialog.
- At application call the absolute path can be resolved with the CAPL function [GetUserFilePath](../../Other/Functions/CAPLfunctionGetUserFilePath.md).

**Example:**

```plaintext
char absPath[256];
GetUserFilePath("MyApplication.exe", absPath, 256);
TestValidateSystemCallWithExitCode("D:\\temp\\", absPath, 100, 1);
```

## Function Syntax

```plaintext
long TestValidateSystemCallWithExitCode (char workingDir[], char commandLine[], dword timeout, long expectedExitCode);
```

## Description

This function can be used to start an external application and check its exit code. Once the application has been started successfully the system waits for it to exit at the end of the specified wait time. The result depends on whether the application's exit code matches the specified expected value.

You should either use the absolute path to the external application or use the call with the declaration of the working directory. To keep the configuration independent of installation paths on a concrete computer you can use `<workingdir>` alternatively to reference an environment variable of the target system, e.g. `%MYAPP_DIR%`.

Test result of the command is reported.

## Parameters

- **workingDir**: The working directory for the external application. The directory name may include spaces.
- **commandLine**: The command line for the application including any parameters which might be required. Path names or parameters containing blank spaces must be enclosed in quotation marks (as an escape sequence `\"`).
- **timeout**: The maximum wait time at the end of which the application is expected to exit. Transmission of 0: no timeout controlling.
- **expectedExitCode**: The expected exit code for the application. If the application is exited within the wait time, the result of the call will also depend on whether it was exited with this exit code.

## Return Values

- **1**: The application exited with the expected exit code.
- **0**: The application did not exit within the wait time.
- **-1**: The application could not be started, e.g., due to an error in the command line.
- **-2**: The application exited with an exit code other than the one expected.
- **-999**: Waiting aborted due to end of measurement (this does not cause the application to be aborted).

## Example

—
