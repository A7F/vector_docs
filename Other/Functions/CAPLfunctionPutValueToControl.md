[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionPutValueToControl.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » putValueToControl

# putValueToControl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

**Value & String Output**

- `void putValueToControl(char panel[], char control[], float val);`
- `void putValueToControl(char panel[], char control[], float val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], long val);`
- `void putValueToControl(char panel[], char control[], long val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], long val, long paragraph, long dispHex);`[^1]
- `void putValueToControl(char panel[], char control[], char val[]);`

**Message Output**

- `void putValueToControl(char panel[], char control[], message val);`
- `void putValueToControl(char panel[], char control[], message val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], message val, long paragraph, long dispHex);`[^1]

**PG Output**

- `void putValueToControl(char panel[], char control[], pg val);`
- `void putValueToControl(char panel[], char control[], pg val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], pg val, long paragraph, long dispHex);`[^1]

**LIN Message Output**

- `void putValueToControl(char panel[], char control[], linFrame val);`
- `void putValueToControl(char panel[], char control[], linFrame val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], linFrame val, long paragraph, long dispHex);`[^1]

**GMLAN Message Output**

- `void putValueToControl(char panel[], char control[], gmLanMessage val);`
- `void putValueToControl(char panel[], char control[], gmLanMessage val, long paragraph);`[^1]
- `void putValueToControl(char panel[], char control[], gmLanMessage val, long paragraph, long dispHex);`[^1]

[^1]: This function requires CANoe 7.5 and higher.

## Description

Assigns the value **val** to the **control** in the Panel Designer: [CAPL Output View](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/Elements/PanelDesignerControlsCAPLOutputView.md).

The CAPL Output View is located on the panel with the title **panel**.

Different contents are displayed with the CAPL Output View. In addition to numbers (float and integer) and texts (char[]), different messages (CAN, LIN, and J1939 PGNs) can also be displayed.

## Parameters

- **panel**: Name of the panel, restricted to 128 characters.
- **control**: Name of the control, restricted to 128 characters.
- **val**: Value to be displayed.
- **paragraph**: Indicates if the output shall be written to a new line.
  - **0**: No new paragraph is set. The text will be appended directly to the existing output. This is the default setting.
  - **1**: The output is written to a new line.
- **dispHex**: Indicates if the output is formatted hexadecimal.
  - **0**: The signal/message/value is written in decimal notation. This is the default setting for signals.
  - **1**: The signal/message/value is written in hexadecimal notation. This is the default setting for messages.

**Note**: The physical value of a signal cannot be displayed in hexadecimal format. Only the raw value of a signal can be formatted hexadecimal.

## Return Values

—

## Example

**Example: Output of a string, a message, a signal - no additional function parameters used**

```plaintext
variables
{
   int value;
   message EngineData mEngineData;
}
on sysVar SysVarShowMultiDisplay
{
   value = @this;
   switch(value)
   {
      case 1: putValueToControl("Gateway","DisplayControl","This is a sample!");
              break;
      case 2: putValueToControl("Gateway","DisplayControl",mEngineData);
              break;
      case 3: putValueToControl("Gateway","DisplayControl",mEngineData.EngSpeed.phys);
              break;
   }
}
```

**Example: Output of a message — optional with function parameters**

```plaintext
variables
{
   ...message MyMessage TestMsg;
}

on key 'a'
{
   //Output of a message without additional parameter settings.
   putValueToControl("TestPanel","ControlOutput1", TestMsg);

   //Output of a message, each time in a new paragraph.
   putValueToControl("TestPanel","ControlOutput1", TestMsg, 1);

   //Output of a message, each time with a new paragraph and the message is displayed in decimal notation.
   putValueToControl("TestPanel","ControlOutput1", TestMsg, 1, 0);
}
```

**Example: Output of a signal (raw format) — optional with function parameters**

```plaintext
variables
{
   ...message MyMessage TestMsg;
}

on key 'b'
{
   //Output of a signal (raw) without additional parameter settings.
   putValueToControl("TestPanel","ControlOutput1", "\nSignal raw\n");
   putValueToControl("TestPanel","ControlOutput1", TestMsg.Signal1);

   //Output of a signal (raw), each time in a new paragraph.
   putValueToControl("TestPanel","ControlOutput1", TestMsg.Signal1, 1);

   //Output of a signal (raw), each time in a new paragraph and in hexadecimal notation.
   putValueToControl("TestPanel","ControlOutput1", TestMsg.Signal1, 1, 1);
}
```

**Example: Output of a signal (physical format) — optional with function parameters**

```plaintext
variables
{
   ...message MyMessage TestMsg;
}

on key 'c'
{
   //Output of a signal (physical) without additional parameter settings.
   putValueToControl("TestPanel","ControlOutput1", "\nSignal raw\n");
   putValueToControl("TestPanel","ControlOutput1", TestMsg.Signal1.phys);

   //Output of a signal (physical), each time in a new paragraph.
   putValueToControl("TestPanel","ControlOutput1", TestMsg.Signal1.phys, 1);
}
```
