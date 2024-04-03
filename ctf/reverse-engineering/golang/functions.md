# Functions

## The \`main\` function

The main function can be located at `main.main` (if the symbols are not stripped).

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Empty main function in not stripped binary</p></figcaption></figure>

Main function is called from `runtime.main`:

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

So, you can find a main address by checking value at qword pointer in runtime:

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

