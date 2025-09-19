[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/TIMComponentServerStates.md)

[CAPL Functions](../../CAPLfunctions.md) » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](CAPLfunctionsISOILOverview.md) » Server States (TIM Component - ISO11783)

# TIM Component Server States

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

The following table contains the states of a connection from the TIM server to the TIM client. The state is used by the CAPL functions [Iso11783IL_TIMConnectSysVarToState](Functions/CAPLfunctionIso11783ILtimConnectSysVarToState.md), [Iso11783IL_TIMFreezeConnection](Functions/CAPLfunctionIso11783ILtimFreezeConnection.md) and [Iso11783IL_TIMContinueConnection](Functions/CAPLfunctionIso11783ILtimContinueConnection.md).

- **State 0: Offline**
  - **Pre Condition:**
    - Server is not activated.
    - Server is stopped ([ISO11783IL_ControlStop](Functions/CAPLfunctionIso11783ILControlStop.md)).
  - **Action when State is Entered:** —

- **State 5: Automation unavailable**
  - **Pre Condition:** **Address Claim** succeeded.
  - **Action when State is Entered:** —

- **State 10: Automation not ready**
  - **Pre Condition:** Server is activated ([Iso11783IL_TIMActivateServer](Functions/CAPLfunctionIso11783ILtimActivateServer.md)).
  - **Action when State is Entered:** Waits for **TIM_ConnectionVersionRequest** of a client.

- **State 11: Connection Version request received**
  - **Pre Condition:** **TIM_ConnectionVersionRequest** is received.
  - **Action when State is Entered:** Calculate the connection version which is used for the client and server connection and send **TIM_ConnectionVersionResponse**.

- **State 12: Connection Version response is sent**
  - **Pre Condition:** **TIM_ConnectionVersionResponse** is sent.
  - **Action when State is Entered:** If TIM server and TIM client versions are incompatible switch to state **Initialization error**. Else switch to state **Connection Version is valid**.

- **State 13: Connection Version is valid**
  - **Pre Condition:** Valid connection version is found.
  - **Action when State is Entered:** Wait for **TIM_ClientStatus_Msg** of the client with state **Automation not ready** or wait for **Auth_ClientAuthenticationStatus** message of the client. If one of the status notifications is received switch to state **Initialization succeeded**.

- **State 16: Initialization succeeded**
  - **Pre Condition:** Initialization has been finished successfully for the server.
  - **Action when State is Entered:** Wait for **Auth_ClientAuthenticationStatus** with the **(Re) Start authentication** status bit set (to **1**).

- **State 19: Initialization error**
  - **Pre Condition:** Initialization has been stopped due to timeout or unexpected response.
  - **Action when State is Entered:** Wait for **TIM_ConnectionVersionRequest** to restart initialization.

- **State 20: Start authentication**
  - **Pre Condition:** Initialization succeeded.
  - **Action when State is Entered:**
    - Start sending **Auth_ServerAuthenticationStatus** with the **(Re) Start authentication** status bit set (to **1**).
    - If **Auth_ClientAuthenticationStatus** with the **(Re) Start authentication** status bit reset (to **0**) is received then check if LwA is possible for this connection, calculate random challenge and reset **(Re)Start authentication** bit of **Auth_ServerAuthenticationStatus**.
    - Switch to state **Server starts authentication**.

- **State 21: Server starts authentication**
  - **Pre Condition:** **Auth_ClientAuthenticationStatus** with reset **(Re)Start authentication** status bit is received.
  - **Action when State is Entered:** Send **Auth_ClientRandomChallengeRequest** and switch to state **Client Random Challenge request is sent**.

- **State 22: Client Random Challenge request is sent**
  - **Pre Condition:** **Auth_ClientRandomChallengeRequest** is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientRandomChallengeResponse**.

- **State 23: Client Random Challenge Response is received**
  - **Pre Condition:** **Auth_ClientRandomChallengeResponse** is received.
  - **Action when State is Entered:**
    - If full authentication (FwA) is necessary then send **Auth_ClientCertificateRequest** for the testlab certificate and switch to state **Client Testlab certificate request is sent**.
    - Else if lightweight authentication (LwA) is necessary switch to state **Calculate CMCA over received challenge**.

- **State 24: Client Testlab certificate request is sent**
  - **Pre Condition:** **Auth_ClientCertificateRequest** for the Testlab certificate is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientCertificateResponse** with the Testlab certificate.

- **State 25: Client Testlab certificate response is received**
  - **Pre Condition:** **Auth_ClientCertificateResponse** with the Testlab certificate is received.
  - **Action when State is Entered:** Send **Auth_ClientCertificateRequest** for the manufacturer certificate.

- **State 26: Client manufacturer certificate request is sent**
  - **Pre Condition:** **Auth_ClientCertificateRequest** for the manufacturer certificate is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientCertificateResponse** with the manufacturer certificate.

- **State 27: Client manufacturer certificate is response received**
  - **Pre Condition:** **Auth_ClientCertificateResponse** with the manufacturer certificate is received.
  - **Action when State is Entered:** **Send Auth_ClientCertificateRequest** for the manufacturer series certificate.

- **State 28: Client manufacturer series certificate request is sent**
  - **Pre Condition:** **Auth_ClientCertificateRequest** for the manufacturer series certificate is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientCertificateResponse** with the manufacturer series certificate.

- **State 29: Client manufacturer series certificate response is received**
  - **Pre Condition:** **Auth_ClientCertificateResponse** with the manufacturer series certificate is received.
  - **Action when State is Entered:** Send **Auth_ClientCertificateRequest** for the device certificate.

- **State 30: Client device certificate request is sent**
  - **Pre Condition:** **Auth_ClientCertificateRequest** for the device certificate is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientCertificateResponse** with the device certificate.

- **State 31: Client device certificate response is received**
  - **Pre Condition:** **Auth_ClientCertificateResponse** with the device certificate is received.
  - **Action when State is Entered:** Send a request for ECU Identification Information notification (PGN FDC5h).

- **State 32: Request for ISOBUS compliance certification status is sent**
  - **Pre Condition:** Request for **ISOBUS compliance certification** notification is sent.
  - **Action when State is Entered:** Wait for **ISOBUS compliance certification** notification.

- **State 33: ISOBUS compliance certification message is received**
  - **Pre Condition:** **ISOBUS compliance certification** notification is received.
  - **Action when State is Entered:** Switch to state **Start validating client certificates**.

- **State 34: Start validating client certificates**
  - **Pre Condition:** All certificates which are added via [Iso11783IL_TIMAddCertificate](Functions/CAPLfunctionIso11783ILtimAddCertificate.md) are requested by the client and all stored certificates of the client are requested by this server.
  - **Action when State is Entered:**
    - Check if received client certificates are listed on CRL and if they are valid. Furthermore, check the ISO NAME in the certificates as well as the ISO Version.
    - If all check succeeded switch to state **Validation of client certificates succeeded**.

- **State 35: Validation of client certificates succeeded**
  - **Pre Condition:** Check of the received client certificates succeeded.
  - **Action when State is Entered:** Wait for a **Auth_ClientAuthenticationStatus** which signals that all certificates are valid.

- **State 40: Start key exchange**
  - **Pre Condition:** Server has successfully validated the certificates.
  - **Action when State is Entered:** —

- **State 41: Start calculating common secret**
  - **Pre Condition:** Random challenge of the client is received and full authentication (FwA) is necessary.
  - **Action when State is Entered:** Server calculates a common secret using ECDH, use KDF to calculate a LwA key and store the LwA key in the key table. Then switch to state **Calculate CMCA over received challenge**.

- **State 50: Calculate CMCA over received challenge**
  - **Pre Condition:** —
  - **Action when State is Entered:**
    - Sign received challenge and send acknowledge for challenge signed to the client.
    - Wait for acknowledgment for challenge signed of the client. Then switch to state **Start CMCA Challenge Response**.

- **State 51: Start CMCA Challenge Response**
  - **Pre Condition:** Both challenges are signed.
  - **Action when State is Entered:** Wait for **Auth_ServerSignedChallengeRequest**.

- **State 52: Client Signed Challenge Request is sent**
  - **Pre Condition:** **Auth_ClientSignedChallengeRequest** is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientSignedChallengeResponse**.

- **State 53: Client Signed Challenge Response is received**
  - **Pre Condition:** **Auth_ClientSignedChallengeResponse** is received.
  - **Action when State is Entered:**
    - Validate signed challenge response. If validation succeeded and **Auth_ClientAuthenticationStatus** notification with status **Authenticated** is received then switch to state **Authentication succeeded**. If validation failed, switch to state **Authentication error**.

- **State 54: Authentication succeeded**
  - **Pre Condition:** Authentication of server succeeded.
  - **Action when State is Entered:** Stop sending **Auth_ServerAuthenticationStatus** after three more times.

- **State 99: Authentication error**
  - **Pre Condition:** Authentication has been stopped due to timeout or unexpected response.
  - **Action when State is Entered:** —

[TIM Component](../../../CANoeCANalyzer/ISO11783/ISO11783IL/TIMComponent/TIMComponent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
