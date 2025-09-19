[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/CAPLfunctionsISONLErrorCodesPDDOnError.md)

**CAPL Functions** » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../ISOInteractionLayer/CAPLfunctionsISOILOverview.md) » ISO11783 Node Layer Error Codes: Process Data API

# ISO11783 Node Layer Error Codes: Process Data API

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## API Error

- **0**: OK - Function has been executed successfully.  
  Additional Parameter: —

- **-100**: General error - An unspecified error has occurred.  
  Additional Parameter: —

- **-101**: Invalid ECU handle - A function was given an invalid ECU handle.  
  Additional Parameter: —

- **-102**: Invalid parameter - A function was given an invalid parameter.  
  Additional Parameter: —

- **-103**: ECU handle is not a local ECU - The function needs an ECU handle of a local ECU. Local ECUs are created with [Iso11783CreateECU()](Functions/CAPLfunctionIso11783CreateECU.md).  
  Additional Parameter: —

- **-104**: Invalid node layer context - A node layer function was not used in the right context.  
  Additional Parameter: —

## CAN Error

- **-400**: Message cannot be sent  
  Additional Parameter: —

## Process Data Error

- **-600**: Process variable not found: an attempt was made to use a process variable that does not exist.  
  Additional Parameter: —

- **-601**: Task Controller not answering any more: the status message of the Task Controller is no longer received.  
  Additional Parameter: —

- **-602**: Invalid Data Log Command: the function [Iso11783PDDSetLogTrigger](Functions/CAPLfunctionIso11783PDDSetLogTrigger.md) has been called up with an invalid logging command.  
  Additional Parameter: —

- **-603**: A process variable could not be created.  
  Additional Parameter: —

- **-604**: Error while consistency check of the device description file: the device description file is invalid.  
  Additional Parameter: —

- **-605**: Action not valid in current state: the selected action could not be executed in the current state.  
  Additional Parameter: current state
  - 0: not initialized, device description file not load
  - 1: description file loaded, ready for initialization procedure
  - 2: wait 6 seconds (start-up delay)
  - 3: wait until task controller sends the status message
  - 4: query information from the task controller
  - 5: transfer device description
  - 6: activate object pool
  - 7: start up is complete
  - 8: task is active

- **-606**: Version Request was not answered  
  Additional Parameter: —

- **-607**: Localization Label Request was not answered  
  Additional Parameter: —

- **-608**: Structure Label Request was not answered  
  Additional Parameter: —

- **-609**: Object Pool Transfer Request failed  
  Additional Parameter: —

- **-610**: Object Pool Transfer failed  
  Additional Parameter: —

- **-611**: Object Pool contains errors  
  Additional Parameter: —

- **-612**: Activation of Object Pool failed  
  Additional Parameter: —

- **-613**: The database attribute **ISO11783PDDFilename** is defined, but Process Data message is not in the Tx list. The device description will not be sent to the Task Controller or data logger.  
  Additional Parameter: —

- **-614**: The Process Data message is in the Tx list of a database node, but the attribute **ISO11783PDDFilename** is not defined. The device description will not be sent to the Task Controller.  
  Additional Parameter: —

- **-615**: The called function wants to access the Process Data Service of the node but in the current state it is not available.  
  Additional Parameter: —

- **-616**: A Task Controller or data logger reports an error in the Object Pool Delete message.  
  Additional Parameter: —

- **-617**: A message cannot be sent to the Task Controller because no Task Controller is detected in the network.  
  Additional Parameter: —

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
