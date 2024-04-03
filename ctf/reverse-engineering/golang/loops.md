# Loops

An example of for loop.

In source code:

```go
for pos := 0; pos < len(hexString); pos += 2 {
	higherDigit := hexString[pos]
	lowerDigit := hexString[pos+1]

	value := hexValues[lowerDigit] + hexValues[higherDigit]*0x10

	data = append(data, byte(value))
}
```

In disassembly graph:

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The loop check condition:

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

The loop increment:

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
