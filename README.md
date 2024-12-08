# Naming Case Convention 
Current Version 1.0

### Features
- 11 known case kinds (see list below) 
- Custom case support `CustomNamingCase`
- Convention options `NamingOptions`
- Extension support `NamingExtensions`
- Designation using non-Latin characters, symbols, etc... also possible (if Ascii is false)

### Support Naming Cases

```
Tobias says Hello World

Camel:		tobiasSaysHelloWorld
Constant:	TOBIAS_SAYS_HELLO_WORLD
Dot:		tobias.says.hello.world
Flat:		tobiassayshelloworld
Kebab:		tobias-says-hello-world
Pascal:		TobiasSaysHelloWorld
Path:		Tobias/Says/Hello/World
Sentence:	Tobias says hello world
Snake:		tobias_says_hello_world
Title:		Tobias Says Hello World
Train:		Tobias-Says-Hello-World
```

### Uses

- Properties
    - Example C# to JSON: "YourPropertyName" -> "your-property-name"
- Autogenerate scripts
- Dictionaries
  - Resources
  - Styles
  - Languages
  - ...
- Tags
- Databases
- ...

### Examples
```
var example0 = "Hello World";
var example1 = "GitHub Examples";
var example2 = "Österreich ist ein schönes Land";
var example3 = "WhatIsYourName?";
var example4 = "EverythingOK?";

var examples = new[] { example0, example1, example2, example3, example4 };

foreach (var example in examples)
{
    var str = example.ConvertNamingCase<SnakeCase>(new NamingOptions()
    {
        AsciiOnly = true,
        KeepPunctuations = false,
        KeepSymbols = false,
        IgnoreIfInvalidCharacters = true,
        SeparateIfUpperCase = true,
        KeepUpperCaseWord = true
    });

    Console.WriteLine(str);
}

// Output:

// hello_world
// git_hub_examples
// sterreich_ist_ein_schnes_land
// what_is_your_name
// everything_ok
```

### License
See MIT License
