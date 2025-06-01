🔐 Encrypted Chat App (Python)

This is a terminal-based encrypted chat application built with Python using sockets and threading. 
It allows multiple clients to connect to a server and exchange messages securely using a simple XOR-based encryption method.

---

🚀 Features

- Multi-client chat support using threading
- Basic XOR encryption for message privacy
- Console-based user interface
- Message contents are not readable in packet sniffing tools like Wireshark

---

🛠️ Requirements

- Python 3.x
- No external dependencies (uses built-in libraries only)

---

🕵️‍♂️ Wireshark Analysis

When inspecting network traffic using [Wireshark](https://www.wireshark.org/), plaintext chat applications usually expose every message in raw form.

However, with this app:
- The messages you type are encrypted before being sent.
- When viewed in Wireshark, the packets **do not contain human-readable text**.
- This shows how even simple encryption prevents attackers on the same network from easily reading sensitive messages.

🧪 **To test it yourself**:
1. Run your server and client.
2. Open Wireshark and start a capture on your active network interface.
3. Filter by `tcp.port == 5555` (or the port you're using).
4. Try chatting from the client — you'll see data, but **not readable messages**.
