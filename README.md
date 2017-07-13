# Hotel
Just another repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Hotel
{
    class Hotel
    {
        static void Main(string[] args)
        {
            string month = Console.ReadLine();
            int nights = int.Parse(Console.ReadLine());

            double studio = 0.00;
            double doubleRoom = 0.00;
            double suite = 0.00;

            if (month == "May" || month == "October")
            {
                studio = 50;
                doubleRoom = 65;
                suite = 75;
           
                if (nights > 7)
                {
                    studio *= 0.95;
                }
                               
            }
            else if (month == "June" || month == "September")
            {
                studio = 60;
                doubleRoom = 72;
                suite = 82;
           
                if (nights > 14)
                {
                    doubleRoom *= 0.90;
                }
            }
            else if (month == "July" || month == "August" || month == "December")
            {
                studio = 68;
                doubleRoom = 77;
                suite = 89;
           
                if (nights > 14)
                {
                    suite *= 0.85;
                }
            }
           

            double priceForStudio = nights * studio;
            double priceForDouble = nights * doubleRoom;
            double priceForSuite = nights * suite;

            if ((month == "October" || month == "September") && nights > 7)
            {
                priceForStudio -= studio;
            }


            Console.WriteLine($"Studio: {priceForStudio:f2} lv.");
            Console.WriteLine($"Double: {priceForDouble:f2} lv.");
            Console.WriteLine($"Suite: {priceForSuite:f2} lv.");
        }
    }
}
