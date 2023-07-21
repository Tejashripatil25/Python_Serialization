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

#### import pickle

It contains some protocols, the rules that are used to construct and deconstruct objects from/to binary format. This module contains the below five protocol versions:

Protocol Version	        Description 
    0	                   Original, human-readable format protocol. It is backward-compatible with earlier versions of Python.
    
    1	                   Old and binary format. It is also compatible with earlier versions of Python.
    
    2	                   It is added in Python 2.3 version. It provides efficient pickling of new-style classes.
    
    3	                   It is introduced in Python 3.0 and works with 3.x versions.  It supports byte objects 
   
    4	                   Introduced in Python 3.4 version. It supports very large objects, more types of objects. It also contains data format optimizations.

  ### Python Pickle Interfaces
  
The pickle module contains the following constants:

#### 1. pickle.HIGHEST_PROTOCOL:
   This is an integer that represents the highest protocol version available. This is the protocol value that is generally passed to the functions used for pickling and unpickling.

#### 2. pickle.DEFAULT_PROTOCOL:
   This is an integer that represents the default protocol used for pickling. This value may be less than the value of the highest protocol.

We can find these values in the way shown in the below example.

### Example of funding the constants of the pickle module:

import pickle

print("Highest protocol: ",pickle.HIGHEST_PROTOCOL)

print("Default protocol: ",pickle.DEFAULT_PROTOCOL)

Output:

Highest protocol: 5

Default protocol: 4

#### This module provides the following four methods:

1. dump(): This method is used to serialize to an open file object
   
2. dumps(): This method is used for serializing to a string
  
3. load(): This method deserializes from an open-like object.
  
4. loads(): This does deserialization from a string.

### Python Dump Functions

The dump function is used to write a pickled version of the object into a file. The syntax of this function is:

#### Syntax:
pickle.dump(obj, file, protocol = None, *, fix_imports = True) 

1. The obj is the object to be serialized

2. The file is the file name in which the converted result is to be stored

3. The optional argument protocol defines the protocol to be used while processing the object. We can give any version from 0 to the HIGHEST_PROTOCOL. If not mentioned, the default protocol is used.

4. If the fix_imports is True and protocol is less than 3, then the mapping is done from the new Python 3 names to the old module names used in Python 2. This allows the pickle data stream to be readable with Python 2 version.

Example of Python dump():

import pickle

content='ILOVECODING'

f=open('file.txt','wb')  #opened the file in write and binary mode 

pickle.dump(content,f) #dumping the content in the variable 'content' into the file

f.close() #closing the file

#### Output:

In the file we can see the following information:

€• Œ
ILOVECODING".

### Python Dumps Function

This function returns the pickled representation of the given data in bytes object form. The syntax of the function is :

#### Syntax:
pickle.dumps(obj, protocol = None, *, fix_imports = True)

This syntax is similar to the dump() function, except we do not have a file argument here.

#### Example of dumps() in Python:

import pickle

content=[ { 'a':1, 'b':2, 'c':3.0 } ] 

pickle.dumps(content) #dumping the content in the variable 'content' 

#### Output:

b’\x80\x04\x95!\x00\x00\x00\x00\x00\x00\x00]\x94}\x94(\x8c\x01a\x94K\x01\x8c\x01b\x94K\x02\x8c\x01c\x94G@\x08\x00\x00\x00\x00\x00\x00ua.’

### Python Load Function

This function is used to read the information in picked form from a file and reconstruct it into the original form. The syntax of this function is :

#### Syntax:
pickle.load(file, *, fix_imports = True, encoding = “ASCII”, errors = “strict”)

This function takes the file from which the data has to be read. Other arguments are optional and have a default value. Let us see an example of reading the data we stored in the dump() function example.

#### Example of load() in Python:

f=open('file.txt','rb') #opening the file to read the data in the binary form

pickle.load(f)

#### Output:

‘ILOVECODING’

### Python Loads Function

This function is used to read the pickled representation from an object and returns the reconstructed version. The syntax is:

#### Syntax:
pickle.loads(bytes_object, *, fix_imports = True, encoding = “ASCII”, errors = “strict”) 

This is similar to the dumps() function except that here we pass the bytes object rather than a normal object.

#### Example of loads() in Python:

import pickle

content = [ { 'a':1, 'b':2, 'c':3.0 } ] 

print ('Before pickling the content is:',content)
 
pickled_content = pickle.dumps(content) #dumping the content into an object 
 
reconstructed_content  = pickle.loads(pickled_content) #loading back the content

print ('After pickling the content is:',reconstructed_content)

#### Output:

Before pickling the content is: [{‘a’: 1, ‘b’: 2, ‘c’: 3.0}]

After pickling the content is: [{‘a’: 1, ‘b’: 2, ‘c’: 3.0}]
