[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/CAPLfunctionsRS232Overview.md)

[CAPL Functions](../CAPLfunctions.md) » RS232 CAPL Functions

# RS232 CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## RS232 API

- **RS232Close**: Closes a serial port. [More info](Functions/CAPLfunctionRS232Close.md)
- **RS232Open**: Opens serial port. [More info](Functions/CAPLfunctionRS232Open.md)
- **RS232Configure**: Configures serial port (everything besides handshake). [More info](Functions/CAPLfunctionRS232Configure.md)
- **RS232SetHandshake**: Configures handshake parameters. [More info](Functions/CAPLfunctionRS232SetHandshake.md)
- **RS232Send**: Sends block of data asynchronously on serial port. [More info](Functions/CAPLfunctionRS232Send.md)
- **RS232Receive**: Sets receiver buffer for serial port. [More info](Functions/CAPLfunctionRS232Receive.md)
- **RS232SetSignalLine**: Sets signal line on serial port. [More info](Functions/CAPLfunctionRS232SetSignalLine.md)

## RS232 API Callback Handlers

- **RS232OnSend**: Handler will be called after completion of request issued with RS232Send. [More info](Functions/CAPLfunctionRS232OnSend.md)
- **RS232OnReceive**: Handler will be called regularly if data has been received at port. Starts with RS232Receive. [More info](Functions/CAPLfunctionRS232OnReceive.md)
- **RS232OnError**: Handler will be called if an error has occurred. [More info](Functions/CAPLfunctionRS232OnError.md)

## General Usage

First, open a port, then transmit and receive data, then close it.

**Example:**

```plaintext
byte data[2];
int length = 2;
data[0] = 1;
data[1] = 2;
if ( 1==RS232Open(1) ) write("Port 1 has been opened.");
if ( 1==RS232Send(1,data,length) ) write("Send bytes to port 1.");
if ( 1==RS232Close(1) ) write("Port 1 has been closed.");
```

[Deprecated INI File](CAPLfunctionsRS232DeprecatedIniFiles.md) • [RS232 API: Overview](../../CANoeCANalyzer/Interfaces/RS232/RS232.md)
