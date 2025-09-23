
## Example Selector ID (message identifier)

```plaintext
on message * {
  if (this.ID == 0x600) {
    write("message 0x600 received; triggering logging...");
    trigger();
  }
}
```

- Technical References are only available in English
- © Vector Informatik GmbH
