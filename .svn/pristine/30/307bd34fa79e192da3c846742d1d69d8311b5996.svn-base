using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace TemperatureConverter
{
    class Program
    {
        private const char MENU_CELSIUS = 'c';
        private const char MENU_FAHRENHEIT = 'f';
        private const char MENU_KELVIN = 'k';
        private const char MENU_REAMUR = 'r';

        static void Main(string[] args)
        {
            do
            {
                PrintMenu();
                char cSelection = Console.ReadKey().KeyChar;

                if (cSelection != MENU_CELSIUS
                    && cSelection != MENU_FAHRENHEIT
                    && cSelection != MENU_KELVIN
                    && cSelection != MENU_REAMUR)
                {
                    break;
                }

                float fTemperature = 0;

                Console.Write("\nEnter temperature: ");
                bool bCheckInput = float.TryParse(Console.ReadLine(), out fTemperature);

                if (!bCheckInput)
                {
                    // input is not a decimal number
                    Console.WriteLine("Entered value is not a valid number. Exiting now!");
                    break;
                }

                float fCelsius = 0;
                float fKelvin = 0;
                float fFahrenheit = 0;
                float fReamur = 0;

                // convert temperature to celsius as basis to calculate other units
                switch (cSelection)
                {
                    case MENU_CELSIUS: fCelsius = fTemperature;
                        break;
                    case MENU_FAHRENHEIT: fCelsius = ConvertFahrenheitToCelsius(fTemperature);
                        break;
                    case MENU_KELVIN: fCelsius = ConvertKelvinToCelsius(fTemperature);
                        break;
                    case MENU_REAMUR: fCelsius = ConvertReamurToCelsius(fTemperature); ;
                        break;
                }

                // convert celsius to other units
                fFahrenheit = ConvertCelsiusToFahrenheit(fCelsius);
                fReamur = ConvertCelsiusToReamur(fCelsius);
                fKelvin = ConvertCelsiusToKelvin(fCelsius);

                PrintResult(fCelsius, fFahrenheit, fReamur, fKelvin);

                Console.Write("\nConvert another temperature (y/n)? ");

            } while(Console.ReadKey().KeyChar.Equals("n"));

            Console.WriteLine("\nThanks for using TemperatureConverter! Bye");
            Console.ReadLine();
        }

        private static void PrintResult(float fCelsius, float fFahrenheit, float fReamur, float fKelvin)
        {
            Console.WriteLine("\nConversion results");
            Console.WriteLine("\t{0}° Celsius", fCelsius);
            Console.WriteLine("\t{0}° Fahrenheit", fFahrenheit);
            Console.WriteLine("\t{0}° Reamur", fReamur);
            Console.WriteLine("\t{0} Kelvin", fKelvin);
        }

        public static void PrintMenu()
        {
            Console.WriteLine("\nConvert from");
            Console.WriteLine("\t{0}: Celsius", MENU_CELSIUS);
            Console.WriteLine("\t{0}: Fahrenheit", MENU_FAHRENHEIT);
            Console.WriteLine("\t{0}: Reamur", MENU_REAMUR);
            Console.WriteLine("\t{0}: Kelvin", MENU_KELVIN);
            Console.WriteLine("\tPress any other key to exit");
            Console.Write("Your selection: ");
        }

        public static float ConvertFahrenheitToCelsius(float temperature)
        {
            return (temperature - 32) * (5f / 9f);
        }

        public static float ConvertReamurToCelsius(float temperature)
        {
            return temperature * 1.25f;
        }

        public static float ConvertKelvinToCelsius(float temperature)
        {
            return temperature - 273.15f;
        }

        public static float ConvertCelsiusToFahrenheit(float temperature)
        {
            return temperature * 1.8f + 32;
        }

        public static float ConvertCelsiusToReamur(float temperature)
        {
            return temperature * 0.8f;
        }

        public static float ConvertCelsiusToKelvin(float temperature)
        {
            return temperature + 273.15f;
        }
    }
}
