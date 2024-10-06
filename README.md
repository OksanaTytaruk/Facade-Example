# Facade Example

Цей репозиторій містить приклад патерну проектування "Фасад".

## Патерн Фасад (Facade)

Патерн "Фасад" надає спрощений інтерфейс до складної системи, приховуючи її складність.

### Приклад коду:

```csharp
// Підсистема A
public class SubsystemA
{
    public void OperationA()
    {
        Console.WriteLine("Subsystem A: Ready!");
    }
}

// Підсистема B
public class SubsystemB
{
    public void OperationB()
    {
        Console.WriteLine("Subsystem B: Ready!");
    }
}

// Фасад
public class Facade
{
    private SubsystemA _subsystemA;
    private SubsystemB _subsystemB;

    public Facade()
    {
        _subsystemA = new SubsystemA();
        _subsystemB = new SubsystemB();
    }

    public void Operation()
    {
        Console.WriteLine("Facade initializes subsystems:");
        _subsystemA.OperationA();
        _subsystemB.OperationB();
        Console.WriteLine("Facade: Subsystems initialized!");
    }
}

// Клієнтський код
class Program
{
    static void Main(string[] args)
    {
        Facade facade = new Facade();
        facade.Operation();
    }
}
