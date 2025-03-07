[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/CAPLfunctionsDiagnosticsProcessingDiagnosticRequests.md)

# Diagnostics: Processing Functional Diagnostic Requests in ECU Simulations

[CAPL Functions](../CAPLfunctions.md) » [Diagnostics](CAPLfunctionsDiagnosticsOverview.md) » Processing Functional Diagnostic Requests in ECU Simulations

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

An ECU simulation can respond to functional diagnostic requests sent in an individual CAN message by the tester. To implement such a response, proceed as follows:

- When the communication parameters are configured in callback [diag_SetChannelParameters](Functions/CAPLfunctionDiagSetChannelParameters.md), the values for functional requests have to be polled and saved.
- On receipt of a CAN message, a check must be carried out to determine whether it matches the saved values. If it does, the data received has to be transferred to the diagnostic layer (see [diag_DataInd](Functions/CAPLfunctionDiagDataInd.md)).

**Example Implementation**

```plaintext
variables
{
   [...]
   DWORD gFunctionalRequestId = 0;
   DWORD gFunctionalRequestIdMask = 0;
   long gFunctionalRequestExt = -1;
   long gCANchannel = -1;
}
_Diag_SetChannelParameters()
{
   [...]
   // Configure functional request ids
   gCANchannel = DiagGetCommParameter( "CANoe.ChannelNumber");
   gFunctionalRequestId = DiagGetFunctionalGroupId();
   if( gFunctionalRequestId != -1)
   {
      gFunctionalRequestIdMask = DiagGetFunctionalGroupIdMask();
      gFunctionalRequestExt = DiagGetFunctionalGroupExt();
   }
}
on message *
{
   int i, dataStart, requestLength;
   BYTE requestData[7];
   // Check if the message received has the functional request id,
   // and if extended addresses are used, if the extension matches
   if( gCANchannel != this.can
      || (this.id & gFunctionalRequestIdMask) != gFunctionalRequestId
      || gFunctionalRequestExt >= 0 && this.byte(0) != gFunctionalRequestExt)
      return;
   // This is a functional request, so indicate the data to the diagnostic layer.
   // The length of the data is found in the first byte of data
   dataStart = (gFunctionalRequestExt >= 0) ? 1 : 0;
   requestLength = this.byte(dataStart);
   ++dataStart;
   writeDbgLevel(1, "%s: Functional request received, %d byte: %02x...",
                 gECU, requestLength, this.byte( dataStart));
   for( i = 0; i < requestLength; ++i)
   {
      requestData[ i] = this.byte( dataStart + i);
   }
   Diag_DataInd( requestData, requestLength, gFunctionalRequestExt);
}
```

[diagGetFunctionalGroupExt](Functions/CAPLfunctionDiagGetFunctionalGroupExt.md) • [diagGetFunctionalGroupId](Functions/CAPLfunctionDiagGetFunctionalGroupID.md) • [diagGetFunctionalGroupIdMask](Functions/CAPLfunctionDiagGetFunctionalGroupIdMask.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)