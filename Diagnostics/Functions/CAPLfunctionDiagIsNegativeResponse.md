[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagIsNegativeResponse.md)

## CAPL Functions » Diagnostics » diagIsNegativeResponse

### Function Syntax

```c
long diagIsNegativeResponse(diagResponse obj);
```

### Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```c
diagResponse::IsNegativeResponse();
```

### Description

Returns value `<> 0` if the object is a negative response to a request.

### Parameters

- **obj**: Diagnostics object

### Return Values

0 or `<> 0`

### Example

```plaintext
on diagResponse *
{
  // Handle the ambiguity of neg responses by treating them as '*'
  if( diagIsNegativeResponse ( this ) )
  {
    write( "Received negative response for service 0x%x, code 0x%x",
    (long) diagGetParameter( this, "SIDRQ_NR" ),
    (long) diagGetParameter( this, "NRC" ) );
  }
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
