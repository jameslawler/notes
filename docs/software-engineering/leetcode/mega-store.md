## C#

```c#
using System;

public class MegaStore
{
    public enum DiscountType
    {
        Standard,
        Seasonal,
        Weight
    }

    public static double GetDiscountedPrice(double cartWeight,
                                            double totalPrice,
                                            DiscountType discountType)
    {
        const double STANDARD_DISCOUNT = 0.06;
        const double SEASONAL_DISCOUNT = 0.12;
        const double WEIGHT_UNDER_DISCOUNT = 0.06;
        const double WEIGHT_OVER_DISCOUNT = 0.18;
        const double WEIGHT = 10;

        double discountedPrice = 0.0;

        switch (discountType)
        {
            case DiscountType.Standard:
                discountedPrice = totalPrice * (1 - STANDARD_DISCOUNT);
                break;
            case DiscountType.Seasonal:
                discountedPrice = totalPrice * (1 - SEASONAL_DISCOUNT);
                break;
            case DiscountType.Weight:
                discountedPrice = cartWeight <= WEIGHT ? totalPrice * (1 - WEIGHT_UNDER_DISCOUNT) : totalPrice * (1 - WEIGHT_OVER_DISCOUNT);
                break;
        }

        return discountedPrice;
    }

    public static void Main(string[] args)
    {
        Console.WriteLine(GetDiscountedPrice(12, 100, DiscountType.Weight));
    }
}
```
