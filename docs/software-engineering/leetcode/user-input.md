## C#

```c#
using System;
using System.Text;

public class TextInput {
    private StringBuilder value;

    public TextInput()
    {
        value = new StringBuilder();
    }

    public virtual void Add(char c)
    {
        value.Append(c);
    }

    public string GetValue()
    {
        return value.ToString();
    }
}

public class NumericInput : TextInput {
    public override void Add(char c)
    {
        if (Char.IsNumber(c))
        {
            base.Add(c);
        }
    }
}

public class UserInput
{
    public static void Main(string[] args)
    {
        TextInput input = new NumericInput();
        input.Add('1');
        input.Add('a');
        input.Add('0');
        Console.WriteLine(input.GetValue());
    }
}
```
