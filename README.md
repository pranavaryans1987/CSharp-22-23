# BCA2022-23CSharp

# 1. Addition Of 2 Numbers'

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.BackgroundColor = ConsoleColor.White;
            Console.ForegroundColor = ConsoleColor.Black;
            Console.Clear();
            int a, b;
            Console.Write("Enter Value For A:");
            a= Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter Value For B:");
            b= Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Total is : "+(a+b));
            Console.Read();
        }
    }
}
```
## OUTPUT
![image](https://user-images.githubusercontent.com/31475304/204727537-03fa383e-f335-4943-860d-7bcfc1d6df60.png)

# 2. Find Max / Equal Using 2 Numbers

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int n1,n2;
            Console.WriteLine("Enter First Value");
            n1= int.Parse(Console.ReadLine());
            Console.WriteLine("Enter Second Value");
            n2= int.Parse(Console.ReadLine());
            if(n1<n2)
            {
                Console.WriteLine("N2 is Max");
            }
            else if(n1 == n2)
            {
                Console.WriteLine("Both Are Equal");
            }
            else
            {
                Console.WriteLine("N1 is Max");
            }
            Console.Read();
        }
    }
}
```

## OUTPUT

![image](https://user-images.githubusercontent.com/31475304/205203888-afe84ab8-8d8b-4326-882f-83678dfe3f95.png)

# 3. Boxing And Unboxing
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int a = 10;

            object obj;

            obj= a;//Boxing
            Console.WriteLine(obj);
            int b = (int)obj;//Unboxing
            Console.WriteLine(b);
            Console.Read();
        }
    }
}
```
## OUTPUT
![image](https://user-images.githubusercontent.com/31475304/205205701-2f97850a-2881-49eb-8843-0a6d9fdfc773.png)
