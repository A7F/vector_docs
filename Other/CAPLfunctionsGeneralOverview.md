# General CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsGeneralOverview.md)

**CAPL Functions** » **General** » General CAPL Functions

Valid for: CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

**ON THIS PAGE:**

- [Access to Hardware](#AccessHardware)
- [Access to Panels](#AccessEnvironmentVariablePanels)
- [AUTOSAR PDU](#AUTOSARPDU)
- [Byte Swapping (Intel/Motorola)](#ByteSwapping)
- [Database Access](#DatabaseAccess)
- [E2E Protection](#E2Eprotection)
- [FDX Function](#FDXFunctions)
- [File Functions](#FileFunctions)
- [Flow Control](#FlowControl)
- [General Functions](#GeneralFunctions)
- [Graphics Window](#Graphics)
- [Language Support and Debugging](#LanguageSupportDebugging)
- [Logging Functions](#LoggingFunctions)
- [Offline Functions](#OfflineFunctions)
- [Performance Measurement](#PerformanceMeasurement)
- [Replay Functions](#ReplayFunctions)
- [Standalone Mode](#StandaloneMode)
- [String Functions](#StringFunctions)
- [Time Management](#TimeManagement)
- [Trigonometric and Mathematical Functions](#TrigonometricMathematicalFunctions)
- [User Interactions](#UserInteractions)

## Access to Hardware

- **InterfaceStatus**: The callback occurs when the status of the connection to the interface hardware is changed.
- **xlAcquireLED**: Acquires the specified LEDs of a hardware device.
- **xlReleaseLED**: Releases specified LEDs.
- **xlSetLED**: Sets specified LEDs.

## Access to Panels

- **ClockControlReset**: Resets the Clock Control designed as stop watch in the Panel Designer.
- **ClockControlStart**: Starts the Clock Control designed as stop watch in the Panel Designer.
- **ClockControlStop**: Stops the Clock Control designed as stop watch in the Panel Designer.
- **closePanel**: Closes a panel.
- **DeleteControlContent**: Deletes the content of the Panel Designer CAPL Output View.
- **enableControl**: Selective activation and deactivation of special controls.
- **MakeRGB**: Calculates the color value from the three primary color components.
- **MakeARGB**: Calculates the color value from the alpha value and the three primary color components.
- **openPanel**: Opens a panel.
- **putValueToControl**: Assigns the value to the multi display.
- **SetClockControlTime**: Sets the time of the Panel Designer Clock Control.
- **SetControlBackColor**: Sets the background color of panel controls.
- **SetControlColors**: Sets the background and text color of panel controls.
- **SetControlForeColor**: Sets the text (foreground) color of panel controls.
- **SetControlProperty**: Sets a property of a Panel Designer control.
- **SetControlVisibility**: Sets the visibility of a panel control.
- **SetDefaultControlColors**: Sets the background and text color of panel controls to the default colors defined in the Panel Designer.
- **SetMediaFile**: Replaces the media file of the Panel Designer Media Player.
- **SetMediaStream**: Replaces the media stream at the specified index of the Panel Designer Media Stream Control during runtime.
- **SetMinMax**: Sets the minimum and maximum value of panel controls.
- **SetPictureBoxImage**: Replaces the image of the Panel Designer Picture Box.

## AUTOSAR PDU

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **GetA664Message**: Retrieves the A664Message object to which the PDU corresponds.
- **GetCANMessage**: Returns the CAN (or CAN-FD) message, the PDU was contained.
- **GetEthernetPacket**: Returns in its second parameter the Ethernet packet, the PDU was contained.
- **GetFrFrame**: Returns in its second parameter the FlexRay frame, the PDU was contained.
- **PDU** (object): Create a PDU object.
- **triggerPDU**: Triggers a PDU to be sent.
- **TriggerPDU2**: Function for forwarding any PDU to another bus.
- **GetPDUsTPIPv4DstAddr**: Requests the IPv4 destination address.
- **GetPDUsTPIPv4SrcAddr**: Requests the IPv4 source address.
- **GetPDUsTPIPv6DstAddr**: Requests the IPv6 destination address.
- **GetPDUsTPIPv6SrcAddr**: Requests the IPv6 source address.
- **GetPDUsTPTCPDstPort**: Requests the TCP destination port.
- **GetPDUsTPTCPSrcPort**: Requests the TCP source address.
- **GetPDUsTPUDPDstPort**: Requests the UDP destination port.
- **GetPDUsTPUDPSrcPort**: Requests the UDP source port.

## Byte Swapping (Intel/Motorola)

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **swapDWord**: Swaps bytes of parameters.
- **swapInt**: Swaps bytes of parameters.
- **swapInt64**: Swaps bytes of parameters.
- **swapLong**: Swaps bytes of parameters.
- **swapQWord**: Swaps bytes of parameters.
- **swapWord**: Swaps bytes of parameters.

## Database Access

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **lookupFrFrame**: Searches for a FlexRay frame definition in the database(s).
- **lookupFrPDU**: Searches for a FlexRay PDU definition in the database(s).
- **lookupMessage**: Searches for a message definition in the database(s).
- **lookupNode**: Searches for a node definition in the database(s).
- **lookupPdu**: Searches for a PDU definition in the database(s).
- **lookupSignal**: Searches for a signal in the database(s).
- **lookupServiceSignal**: Searches for a SOME/IP Service Signal in the database(s).
- **lookupServiceSignalData**: Searches for a SOME/IP Service Signal in the database(s).
- **lookupServiceSignalNumber**: Searches for a SOME/IP Service Signal in the database(s).
- **lookupServiceSignalString**: Searches for a SOME/IP Service Signal in the database(s).
- **lookupSysvar**: Searches for a system variable definition.
- **lookupSysvarData**: Searches for a system variable definition.
- **lookupSysvarFloat**: Searches for a system variable definition.
- **lookupSysvarFloatArray**: Searches for a system variable definition.
- **lookupSysvarInt**: Searches for a system variable definition.
- **lookupSysvarIntArray**: Searches for a system variable definition.
- **lookupSysvarLongLong**: Searches for a system variable definition.
- **lookupSysvarString**: Searches for a system variable definition.

## E2E Protection

- **ARE2ECalculateCRC**: Calculates the corresponding checksum and the CRC size (in bits) from a PDU.
- **ARE2EGetDataIDs**: Returns the data IDs of a PDU with E2E protection.
- **ARE2EGetProfileInfos**: Returns profile information of a PDU with E2E protection. It is necessary that the PDU has a valid E2E.
- **Crc_CalculateCRC8**: Calculates the corresponding checksum for CRC8 based on the data.
- **Crc_CalculateCRC8H2F**: Calculates the corresponding checksum for CRC8H2F based on the data.
- **Crc_CalculateCRC16**: Calculates the corresponding checksum for CRC16 based on the data.
- **Crc_CalculateCRC32**: Calculates the corresponding checksum for CRC32 based on the data.
- **Crc_CalculateCRC32P4**: Calculates the corresponding checksum for CRC32P4 based on the data.
- **Crc_CalculateCRC64**: Calculates the corresponding checksum for CRC64 based on the data.

## FDX Functions

- **FDXClientHandleTcp**: Creates an FDX client handle for the FDX client with the specified address.
- **FDXClientHandleUdp**: Creates an FDX client handle for the FDX client with the specified address.
- **FDXConfigureSequenceCounting**: Sets the behavior with which CANoe DE product should fill out the field sequenceNumber in the FDX datagram header.
- **FDXDisableFreeRunningMode**: Disables the Free Running mode for the specified FDX client.
- **FDXEnableFreeRunningMode**: Activates the Free Running mode for the specified FDX client.
- **FDXSetByteOrder**: Configures the byte order of the FDX protocol that should be used for the communication with the specified client.
- **FDXSetProtocolVersion**: Configures the version of the FDX protocol that should be used for the communication with the specified client.
- **FDXTriggerDataGroup**: Triggers the transmission of a data group via CANoe DE product FDX protocol.

## File Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **fileClose**: Closes the specified file.
- **fileGetBinaryBlock**: Reads characters from the specified file in binary format.
- **fileGetString**: Reads a string from the specified file.
- **fileGetStringSZ**: Reads a string from the specified file.
- **filePutString**: Writes a string in the specified file.
- **fileRewind**: Resets the position pointer to the beginning of the file.
- **fileWriteBinaryBlock**: Writes bytes in the specified file.
- **getOfflineFileName**: Returns the complete path of the currently used offline source file.
- **getNumOfflineFiles**: Returns the number of configured offline source files.
- **getAbsFilePath**: Gets the full path name for a path defined relative to the current configuration.
- **getProfileArray**: Reads the value of the given variable from the specified section in the specified file.
- **getProfileFloat**: Reads the value of the given variable from the specified section in the specified file.
- **getProfileInt**: Reads the value of the given variable from the specified section in the specified file.
- **getProfileString**: Reads the value of the given variable from the specified section in the specified file.
- **getUserFilePath**: Gets the absolute path of a user file.
- **Open**: This function opens the filename file.
- **openFileRead**: Opens the file for the read access.
- **openFileWrite**: Opens the file for the write access.
- **RegisterUserFile**: Registers user files dynamically.
- **setFilePath**: Sets the read and write path to the directory.
- **setWritePath**: Sets the write path for the function openFileWrite.
- **writeProfileFloat**: Opens the file, searches the section and writes the variable.
- **writeProfileInt**: Opens the file, searches the section and writes the variable.
- **writeProfileString**: Opens the file, searches the section and writes the variable.

## Flow Control

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **canOffline**: Cuts the connection between the node and the bus.
- **canOnline**: Restores the connection of the node to the bus.
- **getStartdelay**: Determines the value of the start delay configured for this network node in the Simulation Setup.
- **isOfflineFileActive**: Returns whether events of an offline source file are currently replayed.
- **isOfflineMode**: Gets the information if CANoe DE product is in offline mode.
- **isSimulated**: Gets the information if CANoe DE product i is in simulated mode.
- **IsRunningOnRemoteKernel**: Gets the information whether the CAPL code is executed on an RT kernel, running on a remote realtime device.
- **setStartdelay**: Sets the value of the Start Delay for this network node.
- **stop**: Programmed interrupt of the ongoing measurement.

## General Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **CompleteStop**: Indicates completion of pre-stop activities after a measurement stop has been deferred.
- **DeferStop**: Defers a measurement stop so that activities can be completed before the stop takes effect.
- **GetBusContext**: Returns the current bus context of the CAPL block.
- **GetBusNameContext**: Returns the context of the specified bus.
- **GetNetworkName**: Retrieves the name assigned in the Simulation Setup for a specific channel.
- **getConfigurationName**: Returns the filename of the currently loaded configuration without extension.
- **GetComputerName**: Retrieves the fully qualified name of the computer.
- **GetOSEnvironmentVariableValue**: Retrieves the value of the OS environment variable with the specified name.
- **GetEventSortingStatus**: Determines the Event Sorting state.
- **GetIPAddress**: Retrieves the default (first) IP address of the computer as a string.
- **GetMeasurementIndex**: Returns the current measurement index.
- **gmLanGetPID**: Gets the parameter ID of the message.
- **gmLanGetPrio**: Gets the priority of the message.
- **gmLanGetSourceId**: Gets the source address of the message.
- **gmLanId**: Creates a message ID for a GMLAN message.
- **gmLanSetPID**: Sets the parameter ID of the message.
- **gmLanSetPrio**: Sets the priority of the message.
- **gmLanSetSourceId**: Sets the source address of the message.
- **interpretAsDouble**: Interpret the actual bytes of a value as if the value was of another data type.
- **interpretAsDword**: Interpret the actual bytes of a value as if the value was of another data type.
- **interpretAsFloat**: Interpret the actual bytes of a value as if the value was of another data type.
- **interpretAsQword**: Interpret the actual bytes of a value as if the value was of another data type.
- **RegisterQueueOverflowHandler**: Registers a user-defined functions which gets called whenever any events are lost on any hardware queue or on the MainQueue, or if a specific fill level of the MainQueue is reached.
- **SetBusContext**: Sets the bus context of the CAPL block.
- **SetVideoOfflineLoggerCam**: Sets the offline mode logger cam (type and prefix) for a Video Window.
- **SetVideoOfflineSource**: Sets the offline source (type and path) for a Video Window.
- **SetVideoRecordFile**: Sets the record file for a Video Window.
- **SetVideoTriggerTimes**: Sets the trigger times for a Video Window.
- **dataWindowStartLogging**: Starts logging in a specified Data Window.
- **dataWindowStopLogging**: Stops logging in a specified Data Window.
- **startValuesUpdateList**: Sets the start values of symbols to the currently measured values in the CANoe DE product Start Value Window.
- **startValuesUpdateSymbols**: Sets the symbols contained in a specific group to their individual start values in the CANoe DE product Start Value Window.
- **StartVideoRecording**: Starts/resumes the recording for a Video Window.
- **StopVideoRecording**: Stops/suspends the recording for a Video Window.
- **SymbolMappingSetDynamicMappingSet**: Changes the dynamic mapping set that will be used for mapping in the CANoe DE product Symbol Mapping dialog.
- **traceSetEventColors**: Sets the font, and background color for the message display in the Trace Window.
- **traceWindowClear**: Clears the contents of the Trace Window.

## Graphics Window

- **graphicsWindowClear**: Temporarily deletes the contents of the CANoe DE product Graphics Window.
- **graphicsWindowFit**: Scales symbols in a CANoe DE product Graphics Window.
- **graphicsWindowModifyGroup**: Modifies group enabled and expanded states.
- **graphicsWindowPause**: Pauses and resumes a CANoe DE product Graphics Window.
- **graphicsWindowTimeInterval**: Sets the time interval that will be displayed in a CANoe DE product Graphics Window.

## Language Support and Debugging

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **elCount**: Determines the number of elements of an array.
- **fileName**: Output of the CAPL program in the Write Window.
- **halt**: Stops the execution of the simulation.
- **runError**: Triggers a run error.
- **setWriteDbgLevel**: Sets the priority level for the writeDbgLevel CAPL function.
- **writeDbgLevel**: Outputs a message to the Write Window with the specified priority.

## Logging Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **closeLogFile**: Explicitely closes the logging file of a given Logging Block.
- **setLogFileName**: Sets the name of the logging file.
- **setPostTrigger**: Sets the posttrigger of the logging.
- **setPreTrigger**: Sets the pretrigger of the logging.
- **startLogging**: Starts all Logging Blocks immediately bypassing all logging trigger settings.
- **stopLogging**: Stops all Logging Blocks immediately bypassing all logging trigger settings.
- **trigger**: Activates/Deactivates logging triggering of all Logging and Trigger Blocks.
- **triggerEx**: Activates/Deactivates logging triggering of a special Logging or Trigger Block.
- **writeToLog**: Writes an output string to an ASCII logging file.
- **writeToLogEx**: Writes an output string to an ASCII logging file.

## Offline Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **getOfflineFileName**: Returns the complete path of the currently used offline source file.
- **getNumOfflineFiles**: Returns the number of configured offline source files.
- **isOfflineFileActive**: Returns whether events of an offline source file are currently replayed.
- **isOfflineMode**: Gets the information if CANoe DE product is in offline mode.

## Performance Measurement

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **GetAverageCallTimeNS**: Gets the average call time of the profiler.
- **GetCallCount**: Gets the number of measured calls of the profiler.
- **GetLastCallTimeNS**: Gets the last call time of the profiler.
- **GetLastTimerAccuracyNS**: Returns the last measured accuracy of a timer.
- **GetMaximumCallTimeNS**: Gets the maximum call time of the profiler.
- **GetSteadyClockCurrentTimeNS**: Returns the current time of a steady clock.
- **GetSteadyClockStartDurationNS**: Returns the duration of the measurement start.
- **GetSteadyClockStartTimeNS**: Returns the measurement start time of a steady clock.
- **Reset**: Resets the profiler time measurements.
- **SetTimerAccuracyMonitoringActive**: Configures the accuracy monitoring of a timer.
- **Start**: Starts the profiler time measurement.
- **Stop**: Stops the profiler time measurement.

## Replay Functions

- **ReplayResume**: Starts the Replay Block after it is suspended.
- **ReplayStart**: Starts the Replay Block.
- **ReplayState**: Returns the state of the Replay Block.
- **ReplayStop**: Stops the Replay Block.
- **ReplaySuspend**: Suspends the Replay Block.
- **SetReplayFileName**: Replaces the source file of an existing Replay Block.
- **SetReplayFileNameAndTimeInterval**: Switches Replay Block to a different input file and sets the time interval to replay.
- **StartDOReplayFile**: Starts the replay file containing distributed objects.
- **StartMacroFile**: Starts playing the macro.
- **StartReplayFile**: Starts playing the replay file.
- **StopMacroFile**: Stops the macro from playing.
- **StopReplayFile**: Stops the replay file from playing.

## Standalone Mode

- **IsRunningInStandaloneMode**: Gets the information whether the CAPL code is executed in standalone mode.
- **StandaloneConfigOpen**: Opens the RTCFG file with the given name as standalone configuration.
- **StandaloneConfigSetDefault**: Changes the default configuration file.
- **StandaloneGetCurrentConfig**: Gets the name of the currently loaded configuration in standalone mode.
- **StandaloneGetDefaultConfig**: Gets the name of the default configuration in standalone mode.

## String Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

Note string literals when using the following string functions.

- **_atoi64**: Converts a string to a 64bit integer.
- **_gcvt**: Converts a number to a string.
- **atodbl**: Converts a string into a double number.
- **atol**: Converts a string to a LONG number.
- **BytesToString**: Convert byte array to formatted string.
- **ConvertString**: Converts a string from one encoding to another encoding.
- **DecodeString**: Decodes the byte array input from the encoding codepage.
- **EncodeString**: Encodes the string input with the encoding codepage.
- **ltoa**: Converts a number to a string.
- **mbstrlen**: Returns the length of a string in characters.
- **mbstrncmp**: Compares two strings (positions in characters).
- **mbstrncmp_off**: Compares two strings (positions in characters).
- **mbstrncpy**: Copies a string to another string (positions in characters).
- **mbstrncpy_off**: Copies a string to another string (positions in characters).
- **mbstrstr**: Searches a string in another string (positions in characters).
- **mbstrstr_off**: Searches a string in another string (positions in characters).
- **mbsubstr_cpy**: Copies a substring to another string (positions in characters).
- **mbsubstr_cpy_off**: Copies a substring to another string (positions in characters).
- **snprintf**: Prints a formatted string to character array.
- **strlen**: Gets the length of a string in bytes.
- **strncat**: Appends a string to another string.
- **strncmp**: Compares two strings (positions in bytes).
- **strncmp_off**: Compares two strings (positions in bytes).
- **strncpy**: Copies a string to another string (positions in bytes).
- **strncpy_off**: Copies a string to another string (positions in bytes).
- **strstr**: Searches a string in another string (positions in bytes).
- **strstr_off**: Searches a string in another string (positions in bytes).
- **strtod**: Converts a string to a floating point number.
- **strtol**: Converts a string to a 32bit integer.
- **strtoll**: Converts a string to a 64bit integer.
- **strtoul**: Converts a string to an unsigned 32bit integer.
- **strtoull**: Converts a string to an unsigned 64bit integer.
- **substr_cpy**: Copies a substring to another string (positions in bytes).
- **substr_cpy_off**: Copies a substring to another string (positions in bytes).
- **StringToBytes**: Parses byte array from formatted string.
- **str_match_regex**: Checks whether a string completely matches a regular expression pattern.
- **str_replace**: Replaces all occurrences of a text in a string with another string. Replaces a part of a string with another string.
- **str_replace_regex**: Replaces all occurrences of pattern in a string with another string.
- **strstr_regex**: Searches for a regular expression pattern in a string.
- **strstr_regex_off**: Searches for a regular expression pattern in a string.
- **toLower**: Transforms a character or string to lower case.
- **toUpper**: Transforms a character or string to upper case.

## Time Management

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **addTimeToMeasurementStartTime**: Calculates the absolute date/time of the measurement start plus an offset.
- **cancelTimer**: Stops an active timer.
- **convertGPSTimestamp**: Converts a GPS time stamp into UTC based date and time information.
- **convertTimestamp**: Converts a time stamp to separate parts.
- **convertTimestampNS**: Converts a time stamp to separate parts.
- **convertTimestampToNS**: Converts a time stamp given in days, hours, minutes and seconds into a nanosecond time stamp.
- **convertUTCDateToUnixTimestamp**: Converts the given UTC time and date into a UNIX timestamp (seconds since 1970-01-01).
- **EnvVarTimeNS**: Returns the time stamp of the environment variable envVariable in nanoseconds.
- **getApplicationClockCurrentTimeNs**: Gets the absolute domain time from the synchronized Application-Clock.
- **getApplicationClockRelativeTimeNs**: Gets the relative domain time since measurement start from the synchronized Application-Clock.
- **getDrift**: Determines the constant deviation when Drift is set.
- **getGPSTimeString**: Copies a printed representation of the GPS time stamp represented as UTC date and time into the supplied character buffer.
- **getJitterMax**: Determines the upper limit for the allowable deviation when Jitter is set.
- **getJitterMin**: Determines the lower limit for the allowable deviation when Jitter is set.
- **getLocalTime**: Returns details to the current date and time.
- **getLocalTimeString**: Copies a printed representation of the current date and time.
- **getMeasurementStartTime**: Returns details about the absolute time the measurement was started.
- **isTimerActive**: Return value indicates whether a specific timer is active.
- **MessageTimeNS**: Returns the time stamp in nanoseconds.
- **setDrift**: Sets a constant deviation for the timers of a network node.
- **setJitter**: Sets the Jitter interval for the timers of a network node.
- **setTimer**: Sets a timer.
- **setTimerCyclic**: Sets a cyclical timer.
- **timeDiff**: Time difference between messages or between a message and the current time in ms.
- **timeNow**: Supplies the current simulation time [10 microseconds].
- **timeNowFloat**: Supplies the current simulation time [10 microseconds].
- **timeNowInt64**: Supplies the current simulation time [nanoseconds].
- **timeNowNS**: Supplies the current simulation time [nanoseconds].
- **timeToElapse**: Returns a value indicating how much more time will elapse before an on timer event procedure is called.
- **TimeToString**: Converts a timestamp or duration into a string format.

## Trigonometric and Mathematical Functions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **arccos**: Calculates arccosine of a value.
- **arcsin**: Calculates arcsine of a value.
- **arctan**: Calculates arctangent of a value.
- **_ceil**: Calculates the ceiling of a value.
- **_floor**: Calculates the floor of a value.
- **_Log**: Calculates the natural logarithm.
- **_Log10**: Calculates the logarithm to base 10.
- **_max**: Returns the maximum of the parameters.
- **_min**: Returns the minimum of the parameters.
- **_pow**: Returns x to the power of y.
- **_round**: Rounds a number.
- **abs**: Returns the absolute value.
- **cos**: Calculates the cosine.
- **exp**: Calculates the exponential function.
- **random**: Calculates a random number.
- **sin**: Calculates the sine.
- **sqrt**: Calculates the square root.

## User Interactions

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

- **CreateGlobalMarker**: Sets a marker.
- **keypressed**: Returns the key code of a currently pressed key.
- **msgBeep**: Plays back a sound predefined by the Windows system.
- **sysExec, sysExecCmd**: Executes an external command.
- **sysExit**: Exits the application from within a CAPL program.
- **sysMinimize**: Minimizes or restores the application window.
- **write**: Outputs a text message to the Write Window.
- **writeClear**: Clears the contents of the specified page in the Write Window.
- **writeConfigure**: Configures the specified page in the Write Window.
- **writeCreate**: Generates a new page in the Write Window with the specified name.
- **writeDestroy**: Removes the specified page from the Write Window.
- **writeEx**: Writes the text into the last line of the specified window or into a page of the Write Window without previously creating a new line.
- **writeLineEX**: Writes the text into a new line of the specified window or into a page of the Write Window.
- **writeTextBkgColor**: Sets the color for text background of the specified page in the Write Window.
- **writeTextColor**: Sets the color for text of the specified page in the Write Window.
