# PrettyConsoleOutput

A Library for Console apps that provides a prettier and easier experience with output and input parsing/validating 


Includes a InputHelper, ConsoleTable and ConsoleOutput

https://www.nuget.org/packages/PrettyConsoleOutput/
```Install-Package PrettyConsoleOutput -Version 1.0.2```

## How to use
### Console table
1. Create a new table
`var table = new PrettyTable("Id", "Name", "Age");`
2. Add Rows
`foreach (var person in people)
            {
                table.AddRow(person.Id, person.Name, person);
            }`
3. Print `table.Write();`     
[![output.png](https://i.postimg.cc/wMX7tr1c/output.png)](https://postimg.cc/MfGWNdbv)

### Static PrettyConsole
- `Write` and `WriteLine` methods with overloads for printing a char multiple times and color output. Default values are provided
- You can also log an Error which will print the time, message and exception (if provied) ` PrettyConsole.LogError("Bad input", new ArgumentException());` [![errorlog.png](https://i.postimg.cc/nzd3ydF2/errorlog.png)](https://postimg.cc/VrC9MWb0)

### Static InputHelper with methods for validation and parsing 
- Use the Validate method in order to use attributes which you have probably seen before as data annotations. Theres also a generic overload in case you would like to parse in to a specific type. The input message is optional. `   var email = InputHelper.Validate(new EmailAddressAttribute(), "Enter email: ");`[![input.png](https://i.postimg.cc/8CWCj3JK/input.png)](https://postimg.cc/5H4JrsmL)
- Having troubles parsing enums? Use the GetEnumInput() method.`var season = InputHelper.GetEnumInput<Season>();`[![enumexample.png](https://i.postimg.cc/26wgrVBx/enumexample.png)](https://postimg.cc/vg40v8h1)
