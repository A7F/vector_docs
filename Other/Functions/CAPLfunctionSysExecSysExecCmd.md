[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSysExecSysExecCmd.md)

# sysExec, sysExecCmd

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » sysExec, sysExecCmd

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Note

In case of a distributed simulation environment using a VN8900 device, a realtime module (VT 6000 family) or a RT server, **sysExec** executes the requested command as follows:

- Function call in Simulation Setup/Test Setup ([realtime area](../../../CANoeCANalyzer/CANoeCANalyzerConcept.md)): Execution on the remote platform
- Function call in Measurement Setup: Execution on local computer

**Note for Using [User Files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md)**

To avoid absolute paths in CAPL code and to be independent of the execution platform, proceed as follows:

- Add the application to be started to the User Files in CANoe DE product [Options](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) dialog.
- At application call the absolute path can be resolved with the CAPL function [GetUserFilePath](CAPLfunctionGetUserFilePath.md).

**Example:**

```plaintext
char absPath[256];
GetUserFilePath("MyApplication.exe", absPath, 256);
SysExec(absPath, "");
```

## Function Syntax

```plaintext
long sysExec(char cmd[], char params[]); // form 1
long sysExec(char cmd[], char params[], char directory[]); // form 2
void sysExec(char cmd[], char params[], char directory[], dword timeoutMs, SysExecCallbackFunction callback); // form 3
```

```plaintext
long sysExecCmd(char cmd[], char params[]); // form 1
long sysExecCmd(char cmd[], char params[], char directory[]); // form 2
```

## Description

Executes an external command. Does not wait until the command has completed its execution.

`sysExec` must be given an executable; `sysExecCmd` calls **cmd.EXE /K** with the first parameter, which opens a command window where the command is executed as if it was entered directly.

Form 3 takes an additional callback that is executed once the process terminates and is given the exit code of the process. The callback is only executed if the process terminates while the measurement is still running.

**Note**

Note that in the Server Editions (e.g. CANoe4SW Server Edition) only the sysExec function is available. This applies to Windows and Linux.

## Parameters

- **cmd**: The command to be executed. Either the full absolute path or a path relative to the current working directory must be given or the command must be in the system path.
- **params**: Parameters to the command. A parameter which contains spaces must be enclosed in " ".
- **directory**: Working directory for the command. Either an absolute path or a path relative to the current working directory must be given.
- **timeoutMs**: The maximum time to wait for the process termination in milliseconds. After the timeout expires, the callback is called without the exit code of the process. A timeout of 0 indicates indefinite waiting.
- **callback**: Callback to be executed when the process terminates. The callback is given the following two parameters:
  - `dword result`
    - 0 if the process terminated normally
    - 1 if the timeout was reached and the process is still running
    - 2 if the process could not be started (in this case the timeout is called immediately)
  - `dword processReturnCode`: if the process terminated normally (i.e. result is 0), this parameter contains the exit code of the process

## Return Values

- **Form 1, 2**: 1 if the command was successfully started, else 0.
- **Form 3**: Nothing is returned, the success indicator is given as the first argument of the callback.

**Note**

Note that this function does not wait for the process to finish. Thus, forms 1 and 2 do not return the return code of the process itself.

## Example

**Example 1**

If the working directory is not the same as the directory of a called program, the path for this program must be given in the function.

```plaintext
sysExec("C:\\Program Files\\Beyond Compare 3\\BCompare.EXE", Commandline, "C:\\Program Files\\Beyond Compare 3");
```

**Example 2**

```plaintext
char configDir[1024];
getAbsFilePath("", configDir, elcount(configDir));
sysExecCmd("dir", "/O:-D", configDir); // show files in configuration directory, newest files first
```

**Example 3**

```plaintext
sysExec("wscript MyCmd.vbs", "testparam", ".", 2000, delegate (long result, long processReturnCode) {
  switch (result) {
    case 0: Write("Script exited with code %d", processReturnCode); break;
    case 1: Write("Script execution timed out"); break;
    default: Write("Failed to start script, error code");
  }
});
```

[getAbsFilePath](CAPLfunctionGetAbsFilePath.md) • [TestWaitForSyscall](../../Test/Functions/CAPLfunctionTestWaitForSyscall.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
