[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/CAPLfunctionsSystemVariablesOverview.md)

[CAPL Functions](../CAPLfunctions.md) » System Variables CAPL Functions

# System Variables CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## System Variables

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

---

**ON THIS PAGE:**

- [Define Variables](#FunctionsDefineVariables)
- [General Functions](#GeneralFunctions)
- [Return Data of a Variable](#FunctionsReturnValueVariable)
- [Set the Value of a Variable](#FunctionsSetValueVariable)
- [Structs of System Variables](#FunctionsValueElements)
- [Variable Filters](#FunctionsVariableFilters)

## Define Variables

- [sysDefineVariableData](Functions/CAPLfunctionSysDefineVariableData.md): Defines a variable of the data type.
- [sysDefineVariableFloat](Functions/CAPLfunctionSysDefineVariableFloat.md): Defines a variable of the float type.
- [sysDefineVariableFloatArray](Functions/CAPLfunctionSysDefineVariableFloatArray.md): Defines a variable of the float[] type.
- [sysDefineVariableLong](Functions/CAPLfunctionSysDefineVariableLong.md): Defines a variable of the long type.
- [sysDefineVariableLongArray](Functions/CAPLfunctionSysDefineVariableLongArray.md): Defines a variable of the long[] type.
- [sysDefineVariableLongLong](Functions/CAPLfunctionSysDefineVariableLongLong.md): Defines a variable of the Int64 type.
- [sysDefineVariableString](Functions/CAPLfunctionSysDefineVariableString.md): Defines a variable of the String (char[]) type.

## General Functions

- [sysDefineNamespace](Functions/CAPLfunctionSysDefineNameSpace.md): Defines a namespace.
- [sysUndefineNamespace](Functions/CAPLfunctionSysUndefineNameSpace.md): Deletes a namespace.
- [sysUndefineVariable](Functions/CAPLfunctionSysUndefineVariable.md): Deletes a variable.

## Return Data of a Variable

- [SysGetOrigTimeNS](Functions/CAPLfunctionSysGetOrigTimeNS.md): Returns the original time stamp of the last update to the variable value.
- [sysGetVariableArrayLength](Functions/CAPLfunctionSysGetVariableArrayLength.md): Returns the length of an array system variable.
- [sysGetVariableArraySize](Functions/CAPLfunctionSysGetVariableArraySize.md): Returns the current array size of a system variable (element) of a generic array type.
- [sysGetVariableData](Functions/CAPLfunctionSysGetVariableData.md): Returns the value of a variable of the data type.
- [sysGetVariableDescriptionForValue](Functions/CAPLfunctionSysGetVariableDescriptionForValue.md): Retrieves a description for a value of a system variable of type long or long array.
- [sysGetVariableDWord](Functions/CAPLfunctionSysGetVariableDWord.md): Returns the value of a variable of the word type.
- [sysGetVariableFloat](Functions/CAPLfunctionSysGetVariableFloat.md): Returns the value of a variable of the float type.
- [sysGetVariableFloatArray](Functions/CAPLfunctionSysGetVariableFloatArray.md): Returns the value of a variable of the float[] type.
- [sysGetVariableLong](Functions/CAPLfunctionSysGetVariableLong.md): Returns the value of a variable of the long type.
- [sysGetVariableLongArray](Functions/CAPLfunctionSysGetVariableLongArray.md): Returns the value of a variable of the long [] type.
- [sysGetVariableLongLong](Functions/CAPLfunctionSysGetVariableLongLong.md): Returns the value of a variable of the int64.
- [sysGetVariableMax](Functions/CAPLfunctionSysGetVariableMax.md): Retrieves the maximum of a variable.
- [sysGetVariableMin](Functions/CAPLfunctionSysGetVariableMin.md): Retrieves the minimum of a variable.
- [sysGetVariableQWord](Functions/CAPLfunctionSysGetVariableQWord.md): Returns the value of a variable of the qword type.
- [sysGetVariableString](Functions/CAPLfunctionSysGetVariableString.md): Returns the value of a variable of the string (char[]) type.
- [sysGetVariableSVType](Functions/CAPLfunctionsysGetVariableSVType.md): Gets the type of a system variable encoded as a long integer.
- [sysGetVariableTimeNS](Functions/CAPLfunctionSysGetVariableTimeNS.md): Returns the time stamp of the last update to the variable value.
- [sysGetVariableValueForDescription](Functions/CAPLfunctionSysGetVariableValueForDescription.md): Retrieves the value for a value description of a system variable of type long or long array.
- [sysIsVariableTypeSigned](Functions/CAPLfunctionSysIsVariableTypeSigned.md): Returns whether the data type of a system variable is signed.

## Set the Value of a Variable

- [sysResetValue](Functions/CAPLfunctionSysResetValue.md): Resets a system variable to its initial value.
- [sysResetValues](Functions/CAPLfunctionSysResetValues.md): Resets all system variables in a namespace to their initial values.
- [sysSetAnalysisOnlyVariable](Functions/CAPLfunctionSysSetAnalysIsOnlyVariable.md): Defines whether the variable shall be used only in the analysis area.
- [sysSetVariableAsync](Functions/CAPLfunctionSysSetVariableAsync.md): Assigns a value to a system variable.
- [SysSetVariableArraySize](Functions/CAPLfunctionSysSetVariableArraySize.md): Sets the current array size of a system variable (element) of a generic array type.
- [sysSetVariableData](Functions/CAPLfunctionSysSetVariableData.md): Sets the value of a variable of the data type.
- [sysSetVariableDescriptionForValue](Functions/CAPLfunctionSysSetVariableDescriptionForValue.md): Sets a description for a particular value of a system variable of type long or long array.
- [sysSetVariableDWord](Functions/CAPLfunctionSysSetVariableDWord.md): Sets the value of a variable of the dword type.
- [sysSetVariableFloat](Functions/CAPLfunctionSysSetVariableFloat.md): Sets the value of a variable of the float type.
- [sysSetVariableFloatArray](Functions/CAPLfunctionSysSetVariableFloatArray.md): Sets the value of a variable of the float[] type.
- [sysSetVariableLong](Functions/CAPLfunctionSysSetVariableLong.md): Sets the value of a variable of the long type.
- [sysSetVariableLongArray](Functions/CAPLfunctionSysSetVariableLongArray.md): Sets the value of a variable of the long[] type.
- [sysSetVariableLongLong](Functions/CAPLfunctionSysSetVariableLongLong.md): Sets the value of a variable of the int64.
- [sysSetVariableQWord](Functions/CAPLfunctionSysSetVariableQWord.md): Sets the value of a variable of the qword type.
- [sysSetVariableString](Functions/CAPLfunctionSysSetVariableString.md): Sets the value of a variable of the string (char[]) type.

## Structs of System Variables

- [sysBeginVariableStructUpdate](Functions/CAPLfunctionSysBeginVariableStructUpdate.md): Starts the update of several elements of a system variable of type struct or generic array.
- [sysEndVariableStructUpdate](Functions/CAPLfunctionSysEndVariableStructUpdate.md): Ends the update of several elements of a system variable of type struct or generic array.
- [sysGetVariableMemberPhys](Functions/CAPLfunctionSysGetVariableMemberPhys.md): Retrieves the physical value of a specific element of a variable of type struct or generic array.
- [sysSetVariableMemberPhys](Functions/CAPLfunctionSysSetVariableMemberPhys.md): Sets the physical value of a specific element of a variable of type struct or generic array.

## Variable Filters

- [sysCreateVariableFilter](Functions/CAPLfunctionSysCreateVariableFilter.md): Creates a new variable filter behind the node calling the function.
- [sysFilterAddNamespace](Functions/CAPLfunctionSysFilterAddNamespace.md): Adds a namespace to the variable filter.
- [sysFilterAddVariable](Functions/CAPLfunctionSysFilterAddVariable.md): Adds a variable a variable filter.
- [sysFilterRemoveNamespace](Functions/CAPLfunctionSysFilterRemoveNamespace.md): Removes a namespace from the variable filter.
- [sysFilterRemoveVariable](Functions/CAPLfunctionSysFilterRemoveVariable.md): Removes a variable from a variable filter.
- [sysSetVariableFilterActive](Functions/CAPLfunctionSysSetVariableFilterActive.md): Activates or deactivates a variable filter.

[System Variables](../../Shared/SystemVariables/SysVar.md) • [Direct Access to Values from System Variables](../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md)
