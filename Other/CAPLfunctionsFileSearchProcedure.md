[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsFileSearchProcedure.md)

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » File Search Procedure

# File Search Procedure

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Single Host Environment

A file search procedure is used to determine the absolute file path. There are different procedures for writing and reading files.

### File Search Order on Read Access:

1. If the CAPL file function is used in the CANoe DE Family Simulation or Test Setup, look up the filename in the list of predefined user files (Configuration|Options|Extensions|User Files) and take the path specified there.
2. If the filename is not found in the list of predefined user files and the CAPL function [setFilePath](Functions/CAPLfunctionSetFilePath.md) has been called before, use the directory specified with [setFilePath](Functions/CAPLfunctionSetFilePath.md) as base to determine the absolute path.
3. If [setFilePath](Functions/CAPLfunctionSetFilePath.md) was not called before opening a file for read access, search the file in the directory of the first database.
4. If the file could not be found there, the directories of further databases will be used.
5. If the file still could not be found, the directory of the configuration file will be used.

### File Search Order on Write Access

1. If the CAPL file function is used in the CANoe DE Family Simulation or Test setup, look up the filename in the list of predefined user files (Configuration|Options|Extensions|User Files) and take the path specified there.
2. If the filename is not found in the list of predefined user files and the CAPL functions [setFilePath](Functions/CAPLfunctionSetFilePath.md) or [setWritePath](Functions/CAPLfunctionSetWritePath.md) have been called before, use the directory specified with [setFilePath](Functions/CAPLfunctionSetFilePath.md)/[setWritePath](Functions/CAPLfunctionSetWritePath.md) as base to determine the absolute path.
3. If [setFilePath](Functions/CAPLfunctionSetFilePath.md)/[setWritePath](Functions/CAPLfunctionSetWritePath.md) was not called before opening a file for write access, the configuration directory will be used as base to determine the absolute path instead.

## Distributed Simulation Environment

In distributed mode or standalone mode it is required to pre-define all files to be read in CAPL programs in the CANoe DE product simulation or test setup under Configuration|Options|Extensions|User Files. On measurement start they are copied to a special synchronization directory on the remote device. CAPL file functions called on a remote RT kernel implicitly resolve a given filename to a file path based on this synchronization directory.

Files that are only used for write access may also be predefined as mentioned above. If they have not been predefined they will be implicitly registered as user files for the current measurement. All files created or changed on the remote device are transferred back to the user computer on end of measurement.

The CAPL functions that require a filename also accept a path preceding the filename. If the filename is already registered the path component is just ignored. In case of implicitly registered user files the file path is interpreted as the file path on the user computer to which the file is copied on measurement end.

CAPL functions [setFilePath](Functions/CAPLfunctionSetFilePath.md), [setWritePath](Functions/CAPLfunctionSetWritePath.md) and [getAbsFilePath](Functions/CAPLfunctionGetAbsFilePath.md) are not available in case of a distributed environment.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
