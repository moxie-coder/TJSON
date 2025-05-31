Use in your code

### This is the old Usage page for people who don't understand FNF, you might wanna [check this out](../README.md#-usage) otherwise

----------------

Import TJSON class with:

	import tjson.TJSON;

Then you can read JSON data with:

```haxe
var jsonData = "{key:'value'}";
var object = TJSON.parse(jsonData);
trace(object.key); // outputs 'value'
```

It's that easy!

**New in 1.1.0** - Encode Haxe objects into a JSON string with:

```haxe
var objectToEncode={
	myKey:'myValue'
};
var json = TJSON.encode(objectToEncode);  // {"myKey":"myValue"}
```

The encoder currently supports two different encoding styles. The default is 'simple', which contains no whitespace. If you want more human-readable output, try the 'fancy' style:

```haxe
var objectToEncode={
	myKey:'myValue'
};
var json = TJSON.encode(objectToEncode, 'fancy');
/*
{
	"myKey" : "myValue"
}
*/
```

Of course, the encoder can also encode arrays:

	var myArray = [1,32,43,54];
	var json = TJSON.encode(myArray);


**New in 1.3.0** - Class objects can now be serialized and unserialized with TJSON!

TJSON will add a '_hxcls' key to the serialized JSON code so it know what class it came from.


**New in 1.4.0** - Class object serialization features

If a class object being unserialized has a function named 'TJ_unserialize', it will be called after the object is unserialized.

You can specify properties that should not be serialized by defining a function called 'TJ_noEncode' that returns an array of property names not to serialize.

In this example, TJSON will skip the property called 'dontSerialize':

```haxe    
public function TJ_noEncode():Array<String>{
	return ['dontSerialize'];
}
```
