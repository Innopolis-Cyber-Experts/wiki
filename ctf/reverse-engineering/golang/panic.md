# Panic

{% embed url="https://go.dev/src/runtime/panic.go" %}

Often you can see `panic`s connected to a terminal node. Examples:

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

The terminal node can be easily detected, as it consists from two components:

* call to `runtime.morestack_noctxt.abi0`
* Jump to the start of function

Only unhandled exceptions are being connected to this "panic chain"
