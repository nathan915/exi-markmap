# EXI

## Encoding

- Parse the XML document, generating a sequence of EXI events.
- For each event, encoder consults current grammar to determine appropriate event code.
- Event code is then represented in EXI stream.

## Decoding

- Parse EXI stream
- For each encoded event, decoder reads event code and uses current grammar to determine type of event.
- Decoder reconstructs corresponding XML Information Set from sequence of decoded events.
