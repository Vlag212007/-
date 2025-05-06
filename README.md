using System;

class Program
{
    static void Main()
    {
        Random random = new Random();
        int secretNumber = random.Next(1, 101); // Загадываем число от 1 до 100
        int guess;
        int attempts = 0;
        
        Console.WriteLine("Я загадал число от 1 до 100. Попробуй угадать!");

        do
        {
            Console.Write("Твоя догадка: ");
            string input = Console.ReadLine();
            
            if (!int.TryParse(input, out guess))
            {
                Console.WriteLine("Пожалуйста, введи число!");
                continue;
            }
            
            attempts++;
            
            if (guess < secretNumber)
            {
                Console.WriteLine("Слишком мало! Попробуй ещё раз.");
            }
            else if (guess > secretNumber)
            {
                Console.WriteLine("Слишком много! Попробуй ещё раз.");
            }
            else
            {
                Console.WriteLine($"Поздравляю! Ты угадал число {secretNumber} за {attempts} попыток.");
            }
        } while (guess != secretNumber);
    }
}
