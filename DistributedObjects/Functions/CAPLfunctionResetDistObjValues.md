[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Functions/CAPLfunctionResetDistObjValues.md)

**CAPL Functions** » **Distributed Objects** » **resetDistObjValues**

# resetDistObjValues

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void resetDistObjValues(distObjRef * distObj) // form 1`
- `void resetDistObjValues(distObjContainerRef* distObjContainer) // form 2`
- `void resetDistObjValues(distObjMember* distObjMember) // form 3`
- `void resetDistObjValues(char target[]) // form 4`

## Description

Resets the values of distributed objects to their initial values. The values can be selected through a single member, a distributed object, a distributed object container or a namespace.

## Parameters

- **distObj**: A distributed object. All values of the members of the distributed object are reset.
- **distObjContainer**: An array or list of distributed objects. All values of all members of all distributed objects in the container are reset.
- **distObjMember**: A member of a distributed object. The values of the member are reset.
- **target**: A string designating either a distributed object, or a distributed object container, or a distributed object member, or a namespace. The string must contain all namespaces so that the target is fully qualified. If it designates a namespace, all values of all members of all distributed objects in that namespace (including its sub-namespaces) are reset. Otherwise, the effect is the same as in forms 1-3.

## Return Values

—

## Example

```capl
on key 'a'
{
  $SomeObject.i = 100;
}
on key 'b'
{
  Write("%d", $SomeObject.i);
}

// all key handlers below will reset the value of myNamespace::SomeObject.i
on key 'c' {
  resetDistObjValues(SomeObject.i);
}
on key 'd'
{
  resetDistObjValues(SomeObject);
}
on key 'e'
{
  resetDistObjValues("myNamespace");
}
```

```vcdl
version 1.4;
namespace myNamespace {
  object SomeObject {
    internal data int32 i = 42;
  }
}
```

[sysResetValues](../../SystemVariables/Functions/CAPLfunctionSysResetValues.md) • [TestResetNamespaceDistObjValues](../../Test/Functions/CAPLfunctionTestResetNamespaceDistObjValues.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)