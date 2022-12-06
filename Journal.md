# BCA2022-23 Journam Programs

# 1. Addition Of 2 Numbers
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
