# ipsecPolicyGetParameter

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecPolicyGetParameter.md)

**CAPL Functions** » **TCP/IP API** » **ipsecPolicyGetParameter**

**Valid for**: CANoe DE • CANoe4SW DE

## Note
- The function is dependent on the selected stack.
- This functionality cannot be used in connection with the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecPolicyGetParameter(long policy, char[] parameter, char[] value); // form 1
long ipsecPolicyGetParameter(long policy, char[] parameter, IP_Endpoint value); // form 2
long ipsecPolicyGetParameter(long policy, char[] parameter, dword value); // form 3
```

## Description

Get a parameter from a security policy record.

## Parameters

- **policy**: Handle to a security policy record object.
- **parameter**: Name of the parameter. Possible values are:
  - **Source**: Returns the source selector.
  - **Destination**: Returns the destination selector.
  - **Protocol**: Returns the protocol of the policy. Possible values are:
    - **UNSPEC**: 0
    - **ESP**: 1
    - **AH**: 2
  - **Mode**: Returns the mode of the policy. Possible values are:
    - **ANY**: 0
    - **TRANSPORT**: 1
    - **TUNNEL**: 2
  - **Level**: Returns the level of the policy. Possible values are:
    - **DEFAULT**: 0
    - **USE**: 1
    - **REQUIRE**: 2
  - **Policytype**: Returns the type of the policy. Possible values are:
    - **DISCARD**: 0
    - **NONE**: 1
    - **IPSEC**: 2
    - **ENTRUST**: 3
    - **BYPASS**: 4
- **value**: The returned value of the parameter.

## Return Values

### Form 1

- **>0**: Success: count of characters returned.
- **-1**: Failed

### Form 2-3

- **0**: Success
- **-1**: Failed

## Example

```plaintext
on start
{
  dword socket;

  // add a policy
  IpSecPolicyDatabaseAdd(ip_Endpoint(0.0.0.0:0), 0, ip_Endpoint(192.168.1.0:0), 24, "any", "out ipsec ah/transport//require");

  // try to send data which matches the policy -> this will trigger OnIpsecSadbAcquire
  socket = udpOpen(ip_Endpoint(0.0.0.0:0));
  udpSendTo(socket, ip_Endpoint(192.168.1.10:12345), "hello world", 11);
}

void PrintSecurityPolicyParameter(long handle, char parameterName[])
{
  char value[100];
  ip_Endpoint ep;
  if(ipsecPolicyGetParameter(handle, parameterName, value) >= 0)
  {
    write("%s: %s", parameterName, value);
  }
  else if(ipsecPolicyGetParameter(handle, parameterName, ep) >= 0)
  {
    ep.PrintEndpointToString(value);
    write("%s: %s", parameterName, value);
  }
}

void OnIpsecSadbAcquire(ip_Endpoint source, ip_Endpoint destination, long policyHandle)
{
  PrintSecurityPolicyParameter(policyHandle, "source");
  PrintSecurityPolicyParameter(policyHandle, "destination");
  PrintSecurityPolicyParameter(policyHandle, "protocol");
  PrintSecurityPolicyParameter(policyHandle, "mode");
  PrintSecurityPolicyParameter(policyHandle, "level");
  PrintSecurityPolicyParameter(policyHandle, "policytype");
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
