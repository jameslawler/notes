### C#

```c#
using System;
using NUnit.Framework;

[TestFixture]
public class Tester
{
    private double epsilon = 1e-6;

    [Test]
    public void AccountCannotHaveNegativeOverdraftLimit()
    {
        Account account = new Account(-20);

        Assert.AreEqual(0, account.OverdraftLimit, epsilon);
    }

    [Test]
    public void AccountCannotDepositNegativeAmount()
    {
        Account account = new Account(0);

        Assert.AreEqual(false, account.Deposit(-20));
    }

    [Test]
    public void AccountCannotWithdrawNegativeAmount()
    {
        Account account = new Account(0);

        Assert.AreEqual(false, account.Withdraw(-20));
    }

    [Test]
    public void AccountCannotOverstepOverdraftLimit()
    {
        Account account = new Account(20);

        Assert.AreEqual(true, account.Withdraw(15));
        Assert.AreEqual(false, account.Withdraw(10));
    }

    [Test]
    public void AccountDepositIsCorrect()
    {
        Account account = new Account(0);

        Assert.AreEqual(true, account.Deposit(100));
        Assert.AreEqual(100, account.Balance);
    }

    [Test]
    public void AccountWithdrawIsCorrect()
    {
        Account account = new Account(0);

        account.Deposit(100);
        Assert.AreEqual(true, account.Withdraw(60));
        Assert.AreEqual(40, account.Balance);
    }
}
```
