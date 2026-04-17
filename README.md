# Data Communication Lab

This project is a Java-based simulation of data communication across the OSI model and the physical layer. It reads plain text from `labIn.txt`, applies layer encapsulation and a selected line coding scheme, then decodes the signal and writes the resulting text to `labOut.txt`.

## Features

- Encapsulation through the OSI layers:
  - Application
  - Presentation
  - Session
  - Transport
  - Network
  - Data Link
  - Physical
- Supports multiple physical-layer encoding methods:
  1. NRZ-I
  2. NRZ-L
  3. RZ
  4. Manchester
  5. Differential Manchester
  6. AMI
  7. Pseudoternary
  8. B8ZS
  9. HDB3
  10. 4B5B
- Simulates transmission errors and reports success/error counts
- Uses temporary files to store binary and encoded state data during simulation

## Project Structure

- `src/lab3/Main.java` — program entry point and user menu
- `src/lab3/Sender.java` — reads `labIn.txt`, encapsulates data, converts text to binary, and applies line coding
- `src/lab3/Receiver.java` — decodes the selected line coding, reconstructs the binary stream, decapsulates layers, and writes output to `labOut.txt`
- `labIn.txt` — sample input file for transmission
- `labOut.txt` — decoded output file after simulation
- `tempBinary.txt`, `tempState.txt`, `tempStateBinary.txt` — temporary files used during processing

## Requirements

- Java JDK 8 or later
- A command prompt or terminal in the project root directory

## Build and Run

1. Open a terminal in the project root.
2. Compile the Java sources:

```bash
javac -d out src/lab3/*.java
```

3. Run the application:

```bash
java -cp out lab3.Main
```

4. Choose a transmission method by entering a number from `1` to `10`.

## Input / Output

- Put the text you want to transmit in `labIn.txt`.
- After running the simulation, the decoded result is written to `labOut.txt`.
- The program also prints a simple transmission summary and a signal-to-noise ratio estimate.

## Notes

- The sender adds custom headers for each OSI layer before conversion to binary.
- The receiver introduces randomized error behavior during decoding and then removes headers in reverse order.
- The current implementation uses plain file I/O and temporary files rather than sockets or real network interfaces.

## Example

1. Edit `labIn.txt` to contain a test message.
2. Run the program.
3. Enter `4` to use Manchester encoding.
4. Check `labOut.txt` for the reconstructed message.

## License

This repository contains educational sample code for lab work in data communications.
