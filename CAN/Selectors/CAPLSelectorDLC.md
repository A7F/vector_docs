
## Example Selector DLC (data length code)

```plaintext
on message OneByteMessage {
  if (this.DLC != 1) {
    write("error: OneByteMessage has DLC != 1");
    stop();
  }
}
```

- Technical References are only available in English
- Build Time: 2024-10-8T21:20:34
