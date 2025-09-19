[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTInputAssistant.md)

[CAPL Functions](../CAPLfunctions.md) » [MOST](CAPLfunctionsMOSTOverview.md) » Input Assistance

# MOST: Input Assistance

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

Using the MOST input assistance you can enter symbolic messages in the CAPL Browser.

**Note**  
XML function catalogs must be inserted in the [Simulation Setup](../../CANoeCANalyzer/Windows/SimulationSetup/SimulationSetupWindow.md) to use the MOST input assistance.

The Input assistance can be opened with the **Message input with MOST function catalog...** shortcut menu command or by the key combination `<Ctrl>+<M>`.

You can enter FBlockID, FunctionID and OpType of a MOST message in the opened input assistance window using a selection list. This list contains the current available information from the XML catalogs.

It is also possible to enter the parameters of a MOST message.  
If you enter a left parenthesis, you can - depending on parameter type - manually enter values or select valid parameter values via a selection list. Note, that parameters cannot be set in message and event procedure declarations.

You can enter the single parts of a function address in numeric or symbolic notation. Depending on the first entered sign the list view changes:

- When entering characters the list shows the symbol names followed by the hexadecimal IDs in brackets.
- When entering "0" it is assumed that you want to enter a hexadecimal value. The list shows the hexadecimal IDs followed by the symbolic names in brackets.
- When entering a digit between 1 and 9 it is assumed that you want to enter the ID in decimal format. The list shows the decimal IDs followed by the symbolic names in brackets.

| Function Description                                          | Key Combination                                      |
|---------------------------------------------------------------|------------------------------------------------------|
| Marks an entry of the selection list                          | `<Up Arrow>`, `<Down Arrow>`, `<Page Up>`, `<Page Down>` |
| Handing over the marked entry.                                | `<Tab>`, `<Return>`                                  |
| Handing over FBlockID and FunctionID.                         | `<.>`                                                |
| Handing over OpType, start of parameter entry.                | `<(>`                                                |
| Handing over the current parameter value.                     | `<,>`                                                |
| Finishing parameter entry, handing over the entry and closing the dialog. | `<)>`                                                |
| Closing the selection list.                                   | `<Esc>`                                              |
| Closing the dialog without handing over the entry (with closed selection list) | `<Esc>`                                              |
| Closing the dialog and handing over the entry (with closed selection list). | `<Return>`                                           |
| Switching between input format with or without Instance ID.   | `<F2>`                                               |
| Jumping back or forward within the input filed.               | `<Ctrl> + <Right Arrow>`, `<Ctrl> + <Left Arrow>`    |

[General Tips on XML Function Catalog Support in CAPL](CAPLfunctionsMOSTXMLSupport.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
