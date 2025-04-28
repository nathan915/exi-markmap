#   EXI (Efficient XML Interchange)
    
##  Introduction

-   Compact representation of XML Information Set
    <!-- EXI aims to reduce the size of XML documents and improve the speed of parsing and processing them. This is achieved through various techniques, including using efficient encodings and grammars. -->
-   -   Optimize performance
        <!-- EXI is designed to be faster to process than standard XML, especially on resource-constrained devices. -->
    -   Reduce resource utilization
        <!-- EXI minimizes memory footprint and bandwidth consumption, making it suitable for mobile devices and network communication. -->
-   Hybrid (information & formal language theories + practical techniques)
    <!-- EXI combines theoretical concepts like entropy encoding with practical optimizations derived from empirical testing. -->
-   Grammar-driven encoding
    <!-- EXI uses grammars to predict the structure of XML documents, enabling more efficient encoding of events. -->
-   EXI Processors (encode/decode)
    <!-- EXI processors are software or hardware components that convert between XML and EXI formats. -->

##  EXI Stream

-   -   Header (information about encoding options)
        <!-- The header contains metadata that describes how the EXI stream is encoded. This allows decoders to correctly interpret the data. -->
        -   -   EXI Cookie (optional)
                <!-- A magic number to identify the stream as EXI. -->
            -   Distinguishing Bits
                <!-- Bits to differentiate EXI from XML. -->
            -   EXI Format Version
                <!-- Indicates the version of the EXI specification used. -->
            -   EXI Options
                <!-- Settings that control encoding parameters (e.g., compression, schema usage). -->
    -   Body (the actual data)
        <!-- The body contains the encoded XML data as a sequence of EXI events. -->
        -   Sequence of EXI Events
            <!-- Each event represents a part of the XML structure (e.g., start element, end element, attribute). -->
        -   Whole or fragment of XML
            <!-- EXI can encode complete XML documents or portions of documents. -->

##  EXI Grammars

-   -   Structure of EXI Stream
        <!-- Grammars specify the allowed sequence of EXI events. -->
    -   Allowed Events and their order
        <!-- Grammars dictate which events can occur at any given point in the stream. -->
-   Event Codes
    <!-- Grammars are used to determine the appropriate event codes for encoding. -->
-   -   Built-in XML Grammars (default rules)
        <!-- Basic grammars used when no schema is provided. -->
    -   Schema-informed Grammars (optimized using XML Schema)
        <!-- More efficient grammars generated from XML schemas. -->

##  EXI Options

-   -   Encoding
        <!-- Options influence how XML data is converted to EXI. -->
    -   Decoding
        <!-- Options determine how EXI data is converted back to XML. -->
-   -   Alignment (bit-packing, byte-alignment, pre-compression)
        <!-- Controls how encoded data is aligned in bytes. -->
    -   Compression (enable/disable)
        <!-- Enables or disables built-in EXI compression. -->
    -   Schema information (presence/absence)
        <!-- Indicates whether a schema is used for encoding. -->
    -   Datatype representation map (custom data type handling)
        <!-- Allows specifying custom encoding for data types. -->
    -   String tables (configuration)
        <!-- Controls string table behavior (e.g., size). -->
    -   Fidelity options (preserve non-essential XML info)
        <!-- Determines whether to preserve comments, processing instructions, etc. -->

##  EXI Events

-   -   Start Document (SD)
    -   End Document (ED)
    -   Start Element (SE)
    -   End Element (EE)
    -   Attribute (AT)
    -   Characters (CH)
    -   DOCTYPE (DT)
    -   Comment (CM)
    -   Processing Instruction (PI)
    -   Namespace Declaration (NS)
-   Event Codes
    <!-- Each event type is represented by a numeric code. -->

##  Encoding EXI Streams

-   -   Determining Event Codes (using grammars)
        <!-- The encoder uses grammars to find the appropriate code for each event. -->
    -   Representing Event Codes (variable-length encoding)
        <!-- Codes are encoded efficiently, with shorter codes for more frequent events. -->
    -   Applying Fidelity Options (controlling information preservation)
        <!-- The encoder decides which non-essential XML data to include based on the fidelity options. -->

##  Representing Event Content

-   -   Built-in EXI Datatype Representations (e.g., string, integer, decimal)
        <!-- EXI has built-in ways to encode common data types efficiently. -->
    -   Enumerations (efficient encoding of limited value sets)
        <!-- Optimizes encoding when values are restricted to a predefined set. -->
    -   String Table (for string reuse)
        <!-- Stores strings to avoid repetition. -->
    -   Datatype Representation Map (custom data type handling)
        <!-- Allows applications to specify how data types are encoded. -->

##  EXI Compression

-   Block-based compression
    <!-- EXI can optionally compress the encoded data. -->
-   Units of compression
    <!-- The EXI stream is divided into blocks for compression. -->
-   -   Structure Channel (event codes)
        <!-- Contains codes representing the XML structure. -->
    -   Value Channels (data values, separated by element/attribute name)
        <!-- Contains the actual data content. -->
-   Grouped channels for efficient compression
    <!-- Channels are grouped and compressed together. -->

##  Conformance

-   -   EXI Streams (validity rules)
        <!-- Rules that an EXI stream must follow to be valid. -->
    -   EXI Processors (implementation rules)
        <!-- Rules that EXI encoders and decoders must follow. -->
