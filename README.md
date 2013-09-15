# python-javaobj

python-javaobj is a python library that provides functions for reading and writing (writing is WIP currently) Java objects
serialized or will be deserialized by _ObjectOutputStream_. This form of object
representation is a standard data interchange format in Java world.

javaobj module exposes an API familiar to users of the standard library marshal, pickle and json modules.

## Features

 * Java object instance unmarshaling
 * Java classes unmarshaling
 * Primitive values unmarshaling
 * Automatic conversion of Java Collections to python ones (_HashMap_ => dict, _ArrayList_ => list, etc)
 
## Requirements

 * Python >= 2.6, but < 3.0 (porting to 3.0 is in progress)
 * Maven 2+ (for building test data of serialized objects. You can skip it if you do not plan to run tests.py)

## Usage

Unmarshalling of Java serialised object:

```python
import javaobj

jobj = self.read_file("obj5.ser")
pobj = javaobj.loads(jobj)
print pobj
```

Or, you can use Unmarshaller object directly:

```python
import javaobj

marshaller = javaobj.JavaObjectUnmarshaller(open("sunExample.ser"))
pobj = marshaller.readObject()

self.assertEqual(pobj.value, 17)
self.assertTrue(pobj.next)

pobj = marshaller.readObject()
```
