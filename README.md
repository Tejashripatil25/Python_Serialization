### Python_Serialization

Python serialization and implementing it using the pickle module.

### What is Serialization in Python?

Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file.This process is also called pickling or flattening or marshaling. 

And the reverse process of converting the byte stream into object form is called deserialization or unpickling.

#### Python provides the following three modules:

1. Pickle Module
 
2. JSON Module
 
3. Marshal Module

### Pickle Module in Python

Pickle is a module in Python for serializing and deserializing. It is the faster and simpler choice for this purpose if we do not need any human-readable format. To use this we should first import using the following command.

### import pickle

It contains some protocols, the rules that are used to construct and deconstruct objects from/to binary format. This module contains the below five protocol versions:

Protocol Version	       Description 
   
    0	                   Original, human-readable format protocol. It is backward-compatible with earlier versions of Python.
    
    1	                   Old and binary format. It is also compatible with earlier versions of Python.
    
    2	                   It is added in Python 2.3 version. It provides efficient pickling of new-style classes.
    
    3	                   It is introduced in Python 3.0 and works with 3.x versions.  It supports byte objects 
   
    4	                   Introduced in Python 3.4 version. It supports very large objects, more types of objects. It also contains data format optimizations.
