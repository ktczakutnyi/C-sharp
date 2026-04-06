# Interview Study Guide
**Questions + Answers**

---

## Section 1 - Security Fundamentals

### 1. What is the difference between product security and application security?
**Answer:**
**Application security** focuses on protecting software applications, typically web services, APIs, authentication, and data handling.

**Product security** is broader. It covers the entire system lifecycle, including:
* Hardware
* Firmware
* Operating system
* Networking
* Manufacturing process
* Update mechanisms
* Supply chain

For example, in an embedded defense system, **product security** might include:
* Secure boot
* Anti-tamper hardware
* Firmware signing
* Encrypted communications
* Hardware debug lockout

**Application security** would only cover the software running on top.

### 2. What is secure boot and why is it important?
**Answer:**
Secure boot ensures that a device only runs trusted firmware. The boot chain works like this:
1. **Root of trust** stored in hardware
2. **Bootloader** verifies firmware signature
3. **Firmware** verifies OS
4. **OS** verifies applications

Each stage verifies the next using cryptographic signatures. This prevents attackers from:
* Loading modified firmware
* Installing rootkits
* Bypassing security controls

It's critical in embedded and military systems where physical access may occur.

### 3. What is a race condition?
**Answer:**
A race condition occurs when two or more threads access shared resources without proper synchronization, causing unpredictable behavior.

**Example:**
Two threads updating the same counter:
`counter = counter + 1`

If both read the same value before writing, one update is lost.
**Security implications include:**
* Privilege escalation
* Data corruption
* Logic bypass

**Mitigation:**
* Mutexes
* Atomic operations
* Thread-safe design

### 4. What is threat modeling?
**Answer:**
Threat modeling is the process of identifying how a system could be attacked.

**Typical process:**
1. Identify system assets
2. Identify entry points
3. Identify trust boundaries
4. Model threats
5. Design mitigations

**Common frameworks:**
* STRIDE
* Attack Trees
* MITRE ATT&CK

**Example in an embedded device:**
Threats might include firmware extraction, UART debug access, unsigned firmware updates, or network packet injection.

---

## Section 2 - Embedded / Firmware Security

### 5. What are common vulnerabilities in embedded systems?
**Answer:**
Common issues include:
1. **Hardcoded credentials:** e.g., `admin:admin`
2. **Debug interfaces left enabled:** JTAG, UART, SWD
3. **Unsigned firmware updates:** Allows attackers to load malicious firmware.
4. **Buffer overflows:** Due to C/C++ firmware code.
5. **Lack of memory protection:** Some microcontrollers lack MMU/MPU protection.
6. **Weak encryption:** e.g., storing keys in plaintext firmware.

### 6. How would you secure a firmware update system?
**Answer:**
Key design elements:
1. **Firmware signing:** All firmware must be signed with a private key.
2. **Signature verification:** Device verifies signature before installation.
3. **Anti-rollback:** Prevents installing older vulnerable firmware.
4. **Secure transport:** TLS or encrypted channels.
5. **Update validation:** Integrity checks.
6. **Fail-safe update:** Dual firmware slots so device cannot be bricked.

### 7. What is anti-tamper protection?
**Answer:**
Anti-tamper mechanisms prevent attackers from extracting secrets or modifying hardware.

**Examples:**
* **Hardware:** Epoxy encapsulation, tamper switches, voltage glitch detection.
* **Software:** Obfuscation, encrypted firmware, runtime integrity checks.
* **Operational:** Secure manufacturing, controlled debug access.

Defense systems often combine multiple layers.

---

## Section 3 - Reverse Engineering / Exploits

### 8. How would you reverse engineer firmware?
**Answer:**
**Typical workflow:**
1. Extract firmware from device or update package.
2. Identify architecture (ARM, MIPS, etc.).
3. Load into disassembler (**Ghidra** / IDA).
4. Identify boot code, crypto functions, and authentication logic.
5. Analyze memory structures and identify vulnerabilities.

**Dynamic analysis** can include UART console access, emulation (QEMU), or hardware debugging.

### 9. What is a buffer overflow?
**Answer:**
A buffer overflow occurs when a program writes more data than a buffer can hold.

**Example:**
```c
char buf[16];
gets(buf);
```
If input is >16 bytes, memory beyond the buffer is overwritten.

* **Impact:** Code execution, memory corruption, or system crash.
* **Mitigation:** Bounds checking, stack canaries, ASLR, and safer APIs.

### 10. What is the difference between static and dynamic analysis?
**Answer:**
* **Static analysis:** Examining code without running it (source code review, binary disassembly, automated scanners). **Advantage:** Detects logic flaws and is scalable.
* **Dynamic analysis:** Running the program and observing behavior (debugging, fuzzing, runtime tracing). **Advantage:** Detects runtime vulnerabilities.

---

## Section 4 - Systems & Architecture

### 11. How would you design a secure embedded system?
**Answer:**
I would design security in layers:
* **Hardware:** Root of trust, secure element, debug lockout.
* **Boot chain:** Secure boot, firmware signatures.
* **Operating system:** Memory protections, sandboxing.
* **Networking:** TLS communication, authentication.
* **Updates:** Signed firmware updates, anti-rollback.
* **Monitoring:** Logging, anomaly detection.

### 12. What is defense in depth?
**Answer:**
Defense in depth means using multiple independent security controls.

| Layer | Control |
| :--- | :--- |
| **Hardware** | Secure element / TPM |
| **Firmware** | Signed boot / Secure boot |
| **OS** | Memory protection / DAC / MAC |
| **Network** | TLS / mTLS |
| **Application** | Authentication / Role-based access |

---

## Section 5 - Programming Questions

### 13. What is memory safety?
**Answer:**
Memory safety means preventing programs from accessing memory incorrectly. Unsafe operations include buffer overflows, use-after-free, and double free.
* Languages like **Rust** or **Go** provide memory safety by design.
* **C/C++** require careful manual management.

### 14. Difference between stack and heap?
**Answer:**
* **Stack:** Automatic memory, function variables, fast allocation, fixed size.
* **Heap:** Dynamic allocation, managed manually (`malloc`/`free`), slower but flexible size.

**Example:**
```c
int x;                        // stack
int *p = malloc(sizeof(int)); // heap
```
## Section 6 - Behavioral Questions

### 15. Why ...?
**Strong Answer:**
> 


---

## Section 7 - System Design Framework

structured thinking for cyber-physical systems. Use these 7 steps:

1.  **Clarify the Problem:** Ask about constraints (contested environment, MCU vs. Linux, physical access).
2.  **Define Goals:** (e.g., Resilience against tampering, reliable telemetry).
3.  **Identify Threat Model:** Assume the attacker has physical and network access.
4.  **Define Architecture:** Break into layers (Hardware -> Boot -> OS -> App -> Comms).
5.  **Design Security Controls:** (e.g., Secure boot, anti-rollback, mTLS).
6.  **Discuss Failure Modes:** How does it fail safely? (e.g., Fallback to recovery partition).
7.  **Tradeoffs:** Discuss overhead, boot time, and manufacturing costs.

---


