using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ProjectMahasiswa
{
  public class Mahasiswa
    {
        public string nim { get; set; }
        public string nama { get; set; }
        public string Kelamin { get; set; }
        public string total { get; set; }
    }
    class Program
    {
        // deklarasi objek collection untuk menampung objek mahasiswa
        Mahasiswa Mahasiswa = new Mahasiswa();

        static List<Mahasiswa> daftarMahasiswa = new List<Mahasiswa>();

        static void Main(string[] args)
        {
            Console.Title = "Responsi UAS Matakuliah Pemrograman";

            while (true)
            {
                TampilMenu();

                Console.Write("\nNomor Menu [1..3]: ");
                int nomorMenu = Convert.ToInt32(Console.ReadLine());

                switch (nomorMenu)
                {
                    case 1:
                        TambahMahasiswa();
                        break;

                    case 2:
                        TampilMahasiswa();
                        break;

                    case 3:
                        System.Environment.Exit(0);
                        return;

                    default:
                        break;
                }
            }
        }

        static void TampilMenu()
        {
            Console.Clear();
            Console.Write("\nPilih Menu Aplikasi");
            Console.Write("\n");
            Console.Write("\n1. Tambah Mahasiswa");
            Console.Write("\n2. Tampilkan Mahasiswa");
            Console.Write("\n3. Keluar\n");
            // PERINTAH: lengkapi kode untuk menampilkan menu
        }

        static void TambahMahasiswa()
        {
            Console.Clear();
            Mahasiswa Mahasiswa = new Mahasiswa();

            Console.Write("NIM: ");
            Mahasiswa.nim = Console.ReadLine();
            Console.Write("Nama: ");
            Mahasiswa.nama = Console.ReadLine();
            Console.Write("Jenis Kelamin [L/P] : ");
            Mahasiswa.Kelamin = Console.ReadLine();
            if (Mahasiswa.Kelamin == "L")
            {
                Mahasiswa.Kelamin = "Laki-Laki";
            }
            else if (Mahasiswa.Kelamin == "P")
            {
                Mahasiswa.Kelamin = "Perempuan";
            }

            Console.Write("IPK : ");
            Mahasiswa.total = Console.ReadLine();



            daftarMahasiswa.Add(Mahasiswa);

            // PERINTAH: lengkapi kode untuk menambahkan objek mahasiswa ke dalam collection

            Console.WriteLine("\nTekan ENTER untuk kembali ke menu");
            Console.ReadKey();
        }

        static void HapusMahasiswa()
        {
            Console.Clear();


            // PERINTAH: lengkapi kode untuk menghapus objek mahasiswa dari dalam collection

            Console.WriteLine("\nTekan ENTER untuk kembali ke menu");
            Console.ReadKey();
        }

        static void TampilMahasiswa()
        {
            Console.Clear();
            Console.WriteLine("Data Mahasiswa\n");
            int no = 1;

            foreach (Mahasiswa mahasiswa in daftarMahasiswa)
            {

                Console.WriteLine("{0}. {1}, {2}, {3}, {4}", no, mahasiswa.nim, mahasiswa.nama, mahasiswa.Kelamin, mahasiswa.total);
                no++;
            }
            Console.WriteLine();
            Console.WriteLine("Tekan enter untuk kembali ke menu");
            Console.ReadKey();
        }

    }
}
