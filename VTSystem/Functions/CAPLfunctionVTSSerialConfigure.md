[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSerialConfigure.md)

**CAPL Functions** » **VT System** » **SerialConfigure**

# SerialConfigure

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**

The function can only be called on system variable namespaces of channels that represent an external power supply in a power module **VT7001** respectively the system variable namespace that represents functionality common for the entire **VT7001** module. To make sure the correct settings are used execute a wait command between the call of this function and the following sending or receiving of data.

## Method Syntax

```plaintext
long SysVarNamespace.SerialConfigure(eVTSBaudRate baudrate, eVTSDataBits numberOfDataBits, eVTSStopBits numberOfStopBits, eVTSParity parity );
```

## Description

Configures the serial port of the VT System channel that is specified by the system variable namespace.

Without setting up a configuration explicitly, the default configuration is used.

Default baudrate: 1200, 8 data bits, 1 stop bit, no parity.

## Parameters

- **baudrate**: The symbol rate to use for reception and transmission. Serial ports of the **VT7001**: Values see [eVTSBaudRate](../CAPLfunctionsVTSystemEnumeration.md#eVTSBaudRate)
- **numberOfDataBits**: The number of data bits within a transmission frame. Serial ports of the **VT7001**: Values see [eVTSDataBits](../CAPLfunctionsVTSystemEnumeration.md#eVTSDataBits)
- **numberOfStopBits**: The number of stop bits within a transmission frame. Serial ports of the **VT7001**: Values see [eVTSStopBits](../CAPLfunctionsVTSystemEnumeration.md#eVTSStopBits)
- **parity**: Specifies which parity mode should be used. Values see [eVTSParity](../CAPLfunctionsVTSystemEnumeration.md#eVTSParity)

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: One of the parameters has an invalid value.

## Example

This example shows how to use the RS232 functionality of the **VT7001** module. It is assumed, that power supply 1 of the **VT7001** is connected to a proper counterpart (e.g. a computer) via a serial connection. In this example the string "**Hello World!**" is sent by the **VT7001**. After that all incoming characters are output to the Write Window. After 10 seconds the connection is closed.

### CAPL

```plaintext
RS232Example ()
{
    // Declare variables for RS232 communication
    char stringToSend[20] = "Hello World !"; // String to send
    byte sendBuffer[20]; // Byte array to hold send data
    byte receiveBuffer[20]; // Buffer for received data
    int i; // Counter variable

    // Register the RS232 callback functions
    sysvar::VTS::ECUPowerSupply.SerialSetOnErrorHandler("OnRS232Error");
    sysvar::VTS::ECUPowerSupply.SerialSetOnReceiveHandler("OnRS232Receive");
    sysvar::VTS::ECUPowerSupply.SerialSetOnSendHandler("OnRS232Sent");

    // Configure the serial port i.e. for communication with an external
    // ECU power supply to 9600 baud, 8 data bits, 1 stop bit, no parity
    sysvar::VTS::ECUPowerSupply.SerialConfigure(eVTSBaudRate9600, eVTSDataBitsEight, eVTSStopBitsOne, eVTSParityNone);

    // Open the serial port i.e. for communication with an external ECU power supply
    sysvar::VTS::ECUPowerSupply.SerialOpen();

    // Wait briefly to make sure settings are applied and port is ready
    TestWaitForTimeOut(10);

    // **** Send data ****

    // Copy the string to a byte array and send it
    for (i=0; i<strlen(stringToSend); ++i) sendBuffer[i] = stringToSend[i];
    sysvar::VTS::ECUPowerSupply.SerialSend(sendBuffer, strlen(stringToSend));

    // **** Receive data ****

    // For 10s output all received data to the Write Window
    Write("Waiting for incoming data...");
    sysvar::VTS::ECUPowerSupply.SerialReceive(receiveBuffer, elcount(receiveBuffer));
    TestWaitForTimeOut(10000);

    // Close the serial port
    sysvar::VTS::ECUPowerSupply.SerialClose();
}

void OnRS232Error(dword flags)
{
    // Write error details to the Write Window
    if((flags & (dword) eVTSSerialErrorsSendOperationFailed) != 0)
    {
        Write("Error occurred on serial port of VT7001 module: eVTSSerialErrorsSendOperationFailed");
    }
    if((flags & (dword) eVTSSerialErrorsFrameError) != 0)
    {
        Write("Error occurred on serial port of VT7001 module: eVTSSerialErrorsFrameError");
    }
}

void OnRS232Receive(byte buffer[], dword number)
{
    long i;
    char string[256];
    // Create a string from the given byte array
    for(i=0; i<elcount(buffer); ++i)
        string[i] = buffer[i];

    // Write received data to the Write Window
    Write("Received '%s' (%d bytes) on ECU power supply port.", string, number);
}

void OnRS232Sent(byte buffer[], dword number)
{
    long i;
    char string[256];

    // Create a string from the given byte array
    for(i=0; i<elcount(buffer); ++i)
        string[i] = buffer[i];

    // Write sent data to the Write Window
    Write("Sent '%s' (%d bytes) on ECU power supply port.", string, number);
}
```

### .NET (C#)

```csharp
public void RS232Example()
{
    // Get VTS interface and external power supply 1
    IVTSystem vts = VTSystem.Instance;
    IVT7001Supply1 ecuPowerSupply = vts.GetChannel("ECUPowerSupply") as IVT7001Supply1;

    // Register the event handlers
    ecuPowerSupply.OnSerialSentEvent += new OnSerialSentHandler(this.SendHandler);
    ecuPowerSupply.OnSerialReceivedEvent += new OnSerialReceivedHandler(this.ReceiveHandler);
    ecuPowerSupply.OnSerialErrorEvent += new OnSerialErrorHandler(this.ErrorHandler);

    // Configure the serial port i.e. for communication with an external
    // ECU power supply to 9600 baud, 8 data bits, 1 stop bit, no parity
    ecuPowerSupply.SerialConfigure(BaudRate.BaudRate9600, DataBits.Eight, StopBits.One, Parity.None);
    // Open the serial port i.e. for communication with an external ECU power supply
    ecuPowerSupply.SerialOpen();

    // Wait briefly to make sure settings are applied and port is ready
    Vector.CANoe.Threading.Execution.Wait(10);

    // **** Send data ****

    // Send a string via RS232
    ecuPowerSupply.SerialSend("Hello world!");

    // **** Receive data ****

    // For 10s output all received data to the Write Window
    byte[] receiveBuffer = new byte[32];
    ecuPowerSupply.SerialReceive(receiveBuffer);
    Vector.CANoe.Threading.Execution.Wait(10000);

    // Close the serial port
    ecuPowerSupply.SerialClose();
}

public void SendHandler(object sender, SerialSentEventArgs e)
{
    // Print sent data to Write Window
    System.Text.ASCIIEncoding enc = new System.Text.ASCIIEncoding();
    Vector.Tools.Output.WriteLine("The following data was sent: " + enc.GetString(e.Buffer));
}

public void ReceiveHandler(object sender, SerialReceivedEventArgs e)
{
    // Print received data to Write Window
    System.Text.ASCIIEncoding enc = new System.Text.ASCIIEncoding();
    Vector.Tools.Output.WriteLine("Received the following data: " + enc.GetString(e.Buffer));
}

public void ErrorHandler(object sender, SerialErrorEventArgs e)
{
    // Print error to Write Window
    Vector.Tools.Output.WriteLine("An error occurred in the serial connection: " + e.ErrorFlags.ToString());
}
```

[VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

[vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)
