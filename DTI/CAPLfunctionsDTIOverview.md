# DTI CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

## DTI API

- **TCP/IP**  
  The [DTI API](../../CANoeCANalyzer/Ethernet/DTI/DTIAPI.md) improves accuracy when dealing with time-sensitive Ethernet packets.

### Functions

- [DtiClose](Functions/CAPLfunctionDtiClose.md)  
  Closes the specified pipe.

- [DtiIsValid](Functions/CAPLfunctionDtiIsValid.md)  
  Returns `true` if the specified pipe is valid and ready to be used.

- [DtiOpen](Functions/CAPLfunctionDtiOpen.md)  
  Opens a pipe which allows the deterministic transfer of data. The precision of the pipe depends on the used hardware.

- [DtiSend](Functions/CAPLfunctionDtiSend.md)  
  Sends data using the specified pipe.

- [onDtiSendCallback](EventProcedures/CAPLfunctionOnDtiSendCallback.md)  
  Is called when a pipe that was previously full is now able to accept packets again.

- [DtiWasTxDelayed](Functions/CAPLfunctionDtiWasTxDelayed.md)  
  The function returns true if the provided packet could not be sent at the specified timestamp.
