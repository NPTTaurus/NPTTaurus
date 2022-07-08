using System;

namespace Game_Keo_Bua_Bao
{
    class Program
    {
        static void Main(string[] args)
        {
            
            Console.OutputEncoding = System.Text.Encoding.UTF8;
            char check;
            do {
            Console.WriteLine("Mời bạn chọn:");
            Console.WriteLine("(1).Kéo (2).Búa (3).Bao (4).Thoát");
            Random r = new Random();
            int ComputerChoice = r.Next(1, 3);
            bool SuccesPYchoice = int.TryParse(Console.ReadLine(), out int PlayerChoice);
            string ComputerChoiceName = ComputerChoice == 1 ? "Kéo" : ComputerChoice == 2 ? "Búa" : "Bao";
            string PlayerChoiceName = PlayerChoice == 1 ? "Kéo" : PlayerChoice == 2 ? "Búa" : "Bao";
            void Win() { Console.WriteLine("Lựa chọn của bạn là {0}, lựa chọn của máy là {1}, Bạn Thắng !!", PlayerChoiceName, ComputerChoiceName); }
            void Lose() { Console.WriteLine("Lựa chọn của bạn là {0}, lựa chọn của máy là {1}, Bạn Thua !!", PlayerChoiceName, ComputerChoiceName); }
            
                if (SuccesPYchoice && PlayerChoice <= 4 && PlayerChoice > 0)
                {
                    if (PlayerChoice == 1 && ComputerChoice == 2)
                    {
                        Lose();
                    }
                    else if (PlayerChoice == 1 && ComputerChoice == 3)
                    {
                        Win();
                    }
                    else if (PlayerChoice == 2 && ComputerChoice == 3)
                    {
                        Lose();
                    }
                    else if (PlayerChoice == 2 && ComputerChoice == 1)
                    {
                        Win();
                    }
                    else if (PlayerChoice == 3 && ComputerChoice == 1)
                    {
                        Lose();
                    }
                    else if (PlayerChoice == 3 && ComputerChoice == 2)
                    {
                        Win();
                    }
                    else if (PlayerChoice == ComputerChoice)
                    {
                        Console.WriteLine("Game Hòa");
                    }
                    else if (PlayerChoice == 4)
                    {
                        break;
                    }
                }
                else
                {
                    Console.WriteLine("Mời bạn Nhập Lại sô từ [1 - 4] !!!");
                }
                Console.WriteLine("Ấn Y để tiếp tục");
                check = char.Parse(Console.ReadLine());

            } while (check =='Y'|| check == 'y') ;
        }
    }
}

