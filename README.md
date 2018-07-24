# Visual Studio snippets

## C# Snippets

### ArrangeActAssert

By typing `a` + `TAB` + `TAB` (or `aaa` + `TAB` for long) you end up with an empty failing test method.

```CSharp
// Arrange
$end$

// Act


// Assert
throw new NotImplementedException();
```

### GuardClause (field)

I think that this is by far my favorite snippet.

If you define your field following the `private readonly ISomeService _fieldName;` and inject it in the controller like this `public MyController(ISomeService fieldName){}`, this snippet is for you!

```CSharp
public class MyClass
{
    private readonly ISomeService _fieldName;
    public MyClass(ISomeService fieldName){
        // Place your cursor here
    }
}
```

From there, copy (`ctrl+c`) **fieldName**, place your cursor in the constructor body and type `g` + `TAB` + `TAB` (or `guard` + `TAB` for long) then paste (`ctrl+v`). You should endup with the following in less than a second:

```CSharp
public class MyClass
{
    private readonly ISomeService _fieldName;
    public MyClass(ISomeService fieldName){
        _fieldName = fieldName ?? throw new ArgumentNullException(nameof(fieldName));
    }
}
```

**The complete sequence (this should take ±2sec):**

1.  `dbl-click` OR `ctrl+click` **fieldName**
1.  `ctrl+c`
1.  `click` inside the constructor body
1.  Type `g`
1.  Hit `TAB` twice
1.  `ctrl+v`
1.  `ENTER`

### GuardClause (old)

Create a guard clause for an injected dependency.

```csharp
if ($paramName$ == null) { throw new ArgumentNullException(nameof($paramName$)); }
```

### GuardClause (property)

Create a guard clause for an injected dependency using the 2017 construct.
This snippet offers two parameters: the property name and the parameter name.

```csharp
$propName$ = $paramName$ ?? throw new ArgumentNullException(nameof($paramName$));
```

### GuardClause (string)

Create a guard clause for an injected string dependency.

```csharp
if (string.IsNullOrWhiteSpace($paramName$)) { throw new ArgumentNullException(nameof($paramName$)); }
```

### ShouldBeTested

Create a failing XUnit test method named Should_be_tested. Shortcut: `sbt`.

```csharp
[Fact]
public void Should_be_tested()
{
    throw new NotImplementedException();
}
```

## JavaScript Snippets

### JSModuleDomRdy

Allow to create a jQuery ready JavaScript module.

```JavaScript
; (function ($, window, document, undefined) {
    "use strict"
    $(function () {
        // DOM READY CODE HERE...
        ~end~
    });
}(jQuery, window, document));
```
