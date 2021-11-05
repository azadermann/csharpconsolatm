# csharpconsolatm
C# İf döngüsü ile basit atm örneği (Consol)


using System;
using System.Threading;

namespace BasitAtmUygulamsı
{
    class Program
    {
        static void Main(string[] args)
        {
            //consolun başlığını değiştirme
            Console.Title = "Zear Bank Atm";
            double bakiye = 1000.00;
            int CekilecekTutar = 0;
            int EklenecekTutar = 0;
            Console.ForegroundColor = ConsoleColor.Blue;
            Console.WriteLine("1-Bakiye Sorgulama");
            Console.WriteLine("2-Para Çekme");
            Console.WriteLine("3-Para Yatırma");
            Console.WriteLine("q-Çıkış Yapma");
            Console.ForegroundColor = ConsoleColor.White;
            Console.WriteLine("***************************************");
            Console.Write("Yapmak İstediğiniz İşlemi Seçiniz = ");
            string secim = Console.ReadLine();

            if (secim == "1")
            {
                Console.WriteLine("***************************************");
                Console.WriteLine("Bakiye Sorgulama İşlemi Yapılıyor......");
                Thread.Sleep(1500);
                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("***************************************");
                Console.WriteLine("Hesabınızdaki Tutar = {0} TL", bakiye);
            }
            else if (secim == "2")
            {
                Console.WriteLine("***************************************");
                Console.WriteLine("Hesabınızdaki Tutar = {0} TL", bakiye);
                Console.WriteLine("***************************************");
                Console.Write("Çekmek İstediğiniz Tutar = ");
                CekilecekTutar = Convert.ToInt32(Console.ReadLine());
                Console.ForegroundColor = ConsoleColor.Red;
                if (CekilecekTutar<=bakiye)
                {
                    Console.WriteLine("***************************************");
                    Console.WriteLine("Çekilen Tutar = {0} TL", CekilecekTutar);
                    Console.ForegroundColor = ConsoleColor.Green;
                    Console.WriteLine("***************************************");
                    bakiye = bakiye - CekilecekTutar;
                    Console.Write("Yeni Bakiyeniz = {0} TL", bakiye);
                }
                else
                {
                    Console.WriteLine("***************************************");
                    Console.WriteLine("Yetersiz Bakiye !!");
                }
            }
            else if (secim == "3")
            {
                
                Console.WriteLine("***************************************");
                Console.WriteLine("Hesabınızdaki Tutar = {0} TL", bakiye);
                Console.WriteLine("***************************************");
                Console.Write("Yatırmak İstediğiniz Tutar = ");
                EklenecekTutar = Convert.ToInt32(Console.ReadLine());
                Console.ForegroundColor = ConsoleColor.Red;
                Console.WriteLine("***************************************");
                Console.WriteLine("Yatırılan Tutar = {0} TL", EklenecekTutar);
                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("***************************************");
                bakiye = bakiye + EklenecekTutar;
                Console.Write("Yeni Bakiyeniz = {0} TL", bakiye);
            }
            else if (secim=="q")
            {
                Thread.Sleep(1000);
                Console.WriteLine("Atm'den Çıkış Yapılıyor.......");
                Thread.Sleep(1050);
                Console.WriteLine("İyi Günler.......");
                Thread.Sleep(900);
                Console.Clear();
                
               
            }
            else
            {
                Console.WriteLine("***************************************");
                Console.ForegroundColor = ConsoleColor.Red;
                Console.WriteLine("Hatalı Giriş !!!!!!!!!!! ");
            }

            Console.ReadKey();
        }
    }
}

