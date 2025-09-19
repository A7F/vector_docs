[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnKey.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » on key

# on key

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

With `on key` procedure you can execute defined actions with a key press.

E.g. write

```
message 100 msg;
...
on key 'a' {
    output(msg);
}
```

to transmit message 100 on the bus with every keypress `on key 'a'`. The code for a key press can be entered either as a character, a number or a predefined identifier for function keys. The event procedure `on key *` reacts to all key presses.

In `on key` procedures the keyword [this](CAPLfunctionKeywordThis.md) serves to determine the active key code. For example, if you wish to incorporate the handling of keyboard entries in an event procedure you could write it as the following code:

```
on key * {
    switch(this) {
        case 'a' : ... break;
        case F10: ... break;
        ...
    }
}
```

**Note**

If for example a CAPL program contains the `on key` procedures `on key 'a'` and `on key *`, the procedure `on key 'a'` will be called up, when key 'a' is used. With all other keys the procedure `on key *` will be called up.

**The keys `<ESC>`, `<F7>`, `<F8>` and `<F9>` are not supported of on key procedures.**

In CAPL the different keys have to be called as follows:

- **Key**: `<F1>` - `<F12>` (`<F7>`, `<F8>` and `<F9>` are not supported)
  - **CAPL code**: `F1 - F12`
- **Key**: `<Shift>`+`<F1>` - `<Shift>`+`<F12>`
  - **CAPL code**: `shiftF1 - shiftF12`
- **Key**: `<Ctrl>`+`<F1>` - `<Ctrl>`+`<F12>`
  - **CAPL code**: `ctrlF1 - ctrlF12`
- **Key**: `<Ctrl>`+`<Page up>` / `<Ctrl>`+`<Page down>`
  - **CAPL code**: `ctrlPageUp / ctrlPageDown`
- **Key**: `<Page up>` / `<Page down>`
  - **CAPL code**: `PageUp / PageDown`
- **Key**: `<End>`
  - **CAPL code**: `End`
- **Key**: `<Home>`
  - **CAPL code**: `Home`
- **Key**: `<Insert>`
  - **CAPL code**: `InsertKey`
- **Key**: `<Delete>`
  - **CAPL code**: `DeleteKey`
- **Key**: `<Left Arrow>`, `<Right Arrow>`, `<Up Arrow>`, `<Down Arrow>`
  - **CAPL code**: `CursorLeft, CursorRight, CursorUp, CursorDown`
- **Key**: `<Ctrl>`+`<Left Arrow>`, `<Ctrl>`+`<Right Arrow>`, `<Ctrl>`+`<Up Arrow>`, `<Ctrl>`+`<Down Arrow>`
  - **CAPL code**: `ctrlCursorLeft, ctrlCursorRight, ctrlCursorUp, ctrlCursorDown`

**Example**

To react to activation of character keys you would write the particular character, enclosed in single quotation marks, or enter the character code:

- **Code**: `on key 'a'`
  - **Description**: Reacts on pressing key 'a'
- **Code**: `on key ' '`
  - **Description**: Reacts on pressing the spacebar
- **Code**: `on key 0x20`
  - **Description**: Reacts on pressing the spacebar

You would use symbolic identifiers to react to activation of function keys:

- **Code**: `on key F1`
  - **Description**: Reacts on pressing `<F1>`
- **Code**: `on key shiftF3`
  - **Description**: Reacts on pressing `<Shift>`+`<F3>`
- **Code**: `on key ctrlF12`
  - **Description**: Reacts on pressing `<Ctrl>`+`<F12>`
- **Code**: `on key PageUp`
  - **Description**: Reacts on pressing `<Page up>`
- **Code**: `on key ctrlPageDown`
  - **Description**: Reacts on pressing `<Ctrl>`+`<Page down>`
- **Code**: `on key Home`
  - **Description**: Reacts on pressing `<Home>`
- **Code**: `on key End`
  - **Description**: Reacts on pressing `<End>`

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
