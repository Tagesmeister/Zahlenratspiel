# Zahlenratspiel-1
```c#
namespace Zahlenratspiel
{

    internal class Program
    {

        static void Main(string[] args)
        {

            var nochmal = "";
            var eingabe = "";
            int raten;
            int versuche = 0;
            raten = 0;

            do
            {
                Console.Clear();

                Random myObject = new Random();
                int geheimzahl = myObject.Next(1, 99);
                do
                {

                    try
                    {
                        Console.WriteLine("Suche eine Zahl zwischen (1-100): ");
                        eingabe = Console.ReadLine();
                        raten = Convert.ToInt32(eingabe);
                    }
                    catch
                    {
                        Console.WriteLine("Falsche Eingabe: Geben Sie eine Zahl ein!!");
                        Thread.Sleep(3200);
                        Console.Clear();
                    }
                    if (raten > 100)
                    {
                        Console.Clear();
                        Console.WriteLine("Suche eine Zahl zwischen (1-100): ");
                        Console.WriteLine("-------------------------------------------");
                    }


                    if (raten < geheimzahl)
                    {
                        Console.Clear();
                        Console.WriteLine("Die Gesuchte zahl ist grösser als " + raten);
                        Console.WriteLine("-------------------------------------------");
                        versuche++;
                    }
                    else if (raten > geheimzahl)
                    {
                        Console.Clear();
                        Console.WriteLine("Die gesuchte zahl ist kleiner als " + raten);
                        Console.WriteLine("-------------------------------------------");
                        versuche++;
                    }


                    else
                    {
                        Console.WriteLine("------------------------------------");
                        Console.WriteLine("Supper deine gesuchte Zahl ist: " + geheimzahl);
                        Console.WriteLine("------------------------------------");
                        Console.ReadKey();
                        Console.WriteLine("---------------------------");
                        Console.WriteLine("Deine Versuche: " + versuche);
                        Console.WriteLine("---------------------------");
                        Console.ReadKey();
                        Console.WriteLine("Willst du noch Einmal spielen? [ja|nein] ");
                        nochmal = Console.ReadLine();
                    }

                } while (raten != geheimzahl);
            } while (nochmal == "ja");
            while (nochmal == "nein")
            {
                Console.WriteLine("Schade  :( ");
                Thread.Sleep(1000);
                Environment.Exit(0);
            }
        }

    }
}```
