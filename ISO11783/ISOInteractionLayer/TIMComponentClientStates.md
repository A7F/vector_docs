[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/TIMComponentClientStates.md)

[CAPL Functions](../../CAPLfunctions.md) » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](CAPLfunctionsISOILOverview.md) » Client States (TIM Component - ISO11783)

# TIM Component Client States

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

The following table contains the states of a connection from the TIM client to the TIM server. The state is used by the CAPL functions [Iso11783IL_TIMConnectSysVarToState](Functions/CAPLfunctionIso11783ILtimConnectSysVarToState.md), [Iso11783IL_TIMFreezeConnection](Functions/CAPLfunctionIso11783ILtimFreezeConnection.md) and [Iso11783IL_TIMContinueConnection](Functions/CAPLfunctionIso11783ILtimContinueConnection.md).

- **State 0: Offline**
  - **Pre Condition:**
    - Client is not started.
    - Client is stopped ([ISO11783IL_ControlStop](Functions/CAPLfunctionIso11783ILControlStop.md)).
  - **Action when State is Entered:** —

- **State 10: Automation Unavailable**
  - **Pre Condition:**
    - Address Claim succeeded.
    - [Iso11783IL_TIMConnectToServer](Functions/CAPLfunctionIso11783ILtimConnectToServer.md) is called to connect client a server.
  - **Action when State is Entered:** Wait for **TIM_ServerStatus_Msg** of a server. If received switches to state **Tim Server Status is received**.

- **State 11: Tim Server Status is received**
  - **Pre Condition:** **TIM_ServerStatus_Msg** is received.
  - **Action when State is Entered:** Send **TIM_ConnectionVersionRequest** to the server and switch to state **Connection Version request is sent**.

- **State 12: Connection Version request is sent**
  - **Pre Condition:** **TIM_ConnectionVersionRequest** is sent.
  - **Action when State is Entered:** Wait for the **TIM_ConnectionVersionResponse** of the server. If the response is received validate content and switch to state **Connection Version is valid** or **Initialization error**.

- **State 13: Connection Version is valid**
  - **Pre Condition:** Check of the connection version succeeded.
  - **Action when State is Entered:**
    - Start sending cyclic **TIM_ClientStatus_Msg**.
    - Send **TIM_FunctionsSupportRequest** to server and switch to state **Supported functions request is sent**.

- **State 14: Supported functions request is sent**
  - **Pre Condition:** **TIM_FunctionsSupportRequest** is sent to server.
  - **Action when State is Entered:** Wait for **TIM_FunctionsSupportResponse** of the server. If response is received then switch to state **Supported functions response is received** if the required functions are supported else switch to state **Initialization error**.

- **State 15: Supported functions response is received**
  - **Pre Condition:** **TIM_FunctionsSupportRequest** is received.
  - **Action when State is Entered:** If response contains the desired functions switch to state **Automation not ready** else switch to state **Initialization error**.

- **State 16: Initialization succeeded (equivalent to state ‘Automation not ready’ of the standard)**
  - **Pre Condition:** Initialization succeeded.
  - **Action when State is Entered:** Switch to state **Start authentication**.

- **State 19: Initialization error**
  - **Pre Condition:** Initialization has been stopped due to timeout or unexpected response.
  - **Action when State is Entered:** No action. You can switch to state **Automation Unavailable** by calling [Iso11783IL_TIMConnectToServer](Functions/CAPLfunctionIso11783ILtimConnectToServer.md).

- **State 20: Start authentication**
  - **Pre Condition:**
    - Initialization succeeded.
    - [ISO1783IL_TIMRestartAuthentication](Functions/CAPLfunctionIso11783ILtimRestartAuthentication.md) Authentication is called after an authentication error.
  - **Action when State is Entered:**
    - Send **Auth_ClientAuthenticationStatus** with **(Re)Start authentication** bit.
    - If **Auth_ServerAuthenticationStatus** with **(Re)Start authentication** Status bit set (to **1**) is received then check if LwA is possible, calculate random challenge and reset **(Re)Start authentication** bit of **Auth_ClientAuthenticationStatus**.

- **State 21: Server starts authentication**
  - **Pre Condition:** **Auth_ServerAuthenticationStatus** with **(Re)Start authentication** Status bit set is received.
  - **Action when State is Entered:** Send **Auth_ServerRandomChallengeRequest** and switch to state **Server Random Challenge request is sent**.

- **State 22: Server Random Challenge request is sent**
  - **Pre Condition:** **Auth_ServerRandomChallengeRequest** is sent.
  - **Action when State is Entered:** Wait for **Auth_ServerRandomChallengeResponse**.

- **State 23: Server Random Challenge response is received**
  - **Pre Condition:** **Auth_SererRandomChallengeResponse** is received.
  - **Action when State is Entered:**
    - If full authentication (FwA) is necessary then send **Auth_ServerCertificateRequest** to the server to request the testlab certificate and switch to state **Server testlab certificate request is sent**.
    - Else if lightweight authentication (LwA) is possible switch to state **Calculate CMCA over received challenge**.

- **State 24: Server testlab certificate request is sent**
  - **Pre Condition:** **Auth_ServerCertificateRequest** for testlab certificate is sent to the server.
  - **Action when State is Entered:** Wait for the **Auth_ServerCertificateResponse** of the server. If the response is received and the authentication type, the certification format as well as the certification type is valid then the store the testlab certificate and switch to state **Server testlab certificate response is received** is received. Otherwise switch to state **Authentication error**.

- **State 25: Server testlab certificate response is received**
  - **Pre Condition:** **Auth_ServerCertificateResponse** with a testlab certificate is received
  - **Action when State is Entered:** Send **Auth_ServerCertificateRequest** to the server to request the stored manufacturer certificate. Switch to state **Server manufacturer certificate request sent**.

- **State 26: Server manufacturer certificate request is sent**
  - **Pre Condition:** **Auth_ServerCertificateRequest** for manufacturer certificate is sent to the server.
  - **Action when State is Entered:** Wait for the **Auth_ServerCertificateResponse** of the server. If the response is received and the authentication type, the certification format as well as the certification type is valid then the store the manufacturer certificate and switch to state **Server manufacturer certificate response is received** is received. Otherwise switch to state **Authentication error**.

- **State 27: Server manufacturer certificate response is received**
  - **Pre Condition:** **Auth_ServerCertificateResponse** with a manufacturer certificate is received.
  - **Action when State is Entered:** Send **Auth_ServerCertificateRequest** to the server to request the stored manufacturer series certificate. Switch to state **Server manufacturer series certificate request sent**.

- **State 28: Server manufacturer series certificate request is sent**
  - **Pre Condition:** **Auth_ServerCertificateRequest** for manufacturer series certificate is sent to the server.
  - **Action when State is Entered:** Wait for the **Auth_ServerCertificateResponse** of the server. If the response is received and the authentication type, the certification format as well as the certification type is valid then the store the manufacturer series certificate and switch to state **Server manufacturer series certificate response is received** is received. Otherwise switch to state **Authentication error**.

- **State 29: Server manufacturer series certificate response is received**
  - **Pre Condition:** **Auth_ServerCertificateResponse** with a manufacturer series certificate is received.
  - **Action when State is Entered:** Send **Auth_ServerCertificateRequest** to the server to request the stored device certificate. Switch to state **Server device certificate request sent**.

- **State 30: Server device certificate request is sent**
  - **Pre Condition:** **Auth_ServerCertificateRequest** for device is sent to the server.
  - **Action when State is Entered:** Wait for the **Auth_ServerCertificateResponse** of the server. If the response is received and the authentication type, the certification format as well as the certification type is valid then the store the device certificate and switch to state **Server device certificate response is received** is received. Otherwise switch to state **Authentication error**.

- **State 31: Server device certificate response is received**
  - **Pre Condition:** **Auth_ServerCertificateResponse** with a device certificate is received.
  - **Action when State is Entered:** Send a request for the ISOBUS compliance certification notification (PGN FD42h) and switch to state **Request for ISOBUS compliance certification is sent**.

- **State 32: Request for ISOBUS compliance certification status is sent**
  - **Pre Condition:** Request for ISOBUS compliance certification notification is sent.
  - **Action when State is Entered:** Wait for **ISOBUS compliance certification** notification.

- **State 33: ISOBUS compliance certification message is received**
  - **Pre Condition:** **ISOBUS compliance certification** notification is received.
  - **Action when State is Entered:** Switch to state **Start validating client certificates**.

- **State 34: Start validating server certificates**
  - **Pre Condition:** All stored certificates of the server are requested by this client and all certificates which are added via [Iso11783IL_TIMAddCertificate](Functions/CAPLfunctionIso11783ILtimAddCertificate.md) are requested by the server.
  - **Action when State is Entered:**
    - Check if received server certificates are listed on CRL and if they are valid. Furthermore, check the ISO NAME in the certificates as well as the ISO Version.
    - If all check succeeded switch to state **Authentication succeeded**. Else switch to state **Authentication Error**.

- **State 35: Validation of server certificates succeeded**
  - **Pre Condition:** Check of the received server certificates succeeded.
  - **Action when State is Entered:** Wait for a **Auth_ServerAuthenticationStatus** which signals that all certificates are valid.

- **State 40: Start key exchange**
  - **Pre Condition:** Server has successfully validated the certificates.
  - **Action when State is Entered:** Switch to state **Start calculating common secret**.

- **State 41: Start calculating common secret**
  - **Pre Condition:** Random challenge of the server is received and full authentication (FwA) is necessary.
  - **Action when State is Entered:** Client calculates a common secret using ECDH, use KDF to calculate a LwA key and store the LwA key in the key table. Then switch to state **Calculate CMCA over received challenge**.

- **State 50: Calculate CMCA over received challenge**
  - **Pre Condition:** —
  - **Action when State is Entered:**
    - Sign received challenge and send acknowledge for challenge signed to the server.
    - Wait for acknowledgment for challenge signed of the server. Then switch to state **Start CMCA Challenge Response**.

- **State 51: Start CMAC challenge response**
  - **Pre Condition:** Both challenges are signed.
  - **Action when State is Entered:** Send **Auth_ServerSignedChallengeRequest** to the server and switch to state **Server Signed Challenge request is sent**.

- **State 52: Server Signed Challenge request is sent**
  - **Pre Condition:** **Auth_ServerSignedChallengeRequest** is sent.
  - **Action when State is Entered:** Wait for **Auth_ServerSignedChallengeResponse**.

- **State 53: Server Signed Challenge response is received**
  - **Pre Condition:** **Auth_ServerSignedChallengeResponse** is sent.
  - **Action when State is Entered:** Wait for **Auth_ClientSignedChallengeRequest**.

- **State 54: Authentication succeeded**
  - **Pre Condition:** Authentication of client succeeded.
  - **Action when State is Entered:** Stop sending **Auth_ClientAuthenticationStatus** after three more times.

- **State 60: Automation enabled**
  - **Pre Condition:** First **TIM_FunctionsAssignmentResponse** with status **1** (is assigned to requesting TIM client) and reason **0** (all clear/no reason) is received.
  - **Action when State is Entered:**
    - Send **TIM_ClientStatus_Msg** with State **Automation Enable**.
    - Send **TIM function request** with value **Ready to Control**.

- **State 70: Automation active**
  - **Pre Condition:** First TIM function status with function automation status **5** (active, not limited), **6** (active, limited high) or **7** (active, limited low) is received.
  - **Action when State is Entered:** —

- **State 99: Authentication error**
  - **Pre Condition:**
    - **Authentication Status** notification with an error code is received.
    - No **Authentication Status** notification is received for more than 3 seconds.
  - **Action when State is Entered:** Depends on post condition.

[TIM Component](../../../CANoeCANalyzer/ISO11783/ISO11783IL/TIMComponent/TIMComponent.md)
