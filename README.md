using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;

namespace Program21
{
    class Vect
    {
        static void Main(string[] args)
        {

            int n, m, i, j;
            int a, c, b, d;
            int[,] A = new int[4, 4]; // вхідні дані
            int[,] B = new int[3, 3];
            int[] vecC = new int[4];
            int[] vecD = new int[3];
            int[] vecA = new int[4];
            int[] vecB = new int[3];
            Random random1 = new Random(); // rand 4 матриці
            Random random2 = new Random();
            Random random3 = new Random();
            Random random4 = new Random();
            
            Console.WriteLine("Матрица А"); // матриця А
                     
            for (n = 0; n < 4; n++)
            {
                for (m = 0; m < 4; m++)
                {
                    a = random1.Next(1, 11);
                    A[n, m] = Convert.ToInt32(a);
                }
            }
            for (n = 0; n < 4; n++)
            {
                for (m = 0; m < 4; m++)
                    Console.Write("{0, 5}", A[n, m]);
                
            }            
            Console.WriteLine("Матрица B");// матриця б
         
            for (i = 0; i < 3; i++)
            {
                for (j = 0; j < 3; j++)
                {
                    b = random3.Next(1, 11);
                    B[i, j] = Convert.ToInt32(b);
                }
            }
            for (i = 0; i < 3; i++)
            {
                for (j = 0; j < 3; j++)
                    Console.Write(" " + B[i, j]);             
            }          
            Console.WriteLine("Вектор С");// матриця с
        

            for (n = 0; n < 4; n++)
            {
                c = random2.Next(1, 11);
                vecC[n] = Convert.ToInt32(c);
            }
            for (n = 0; n < 4; n++)
            {
                Console.Write("{0, 5}", vecC[n]);               
            }
            
            Console.WriteLine("Вектор D");// матриця д
            Console.Write("\n ");

            for (i = 0; i < 3; i++)
            {
                d = random4.Next(1, 11);
                vecD[i] = Convert.ToInt32(d);
            }
            for (i = 0; i < 3; i++)
            {
                Console.Write("{0, 5}", vecD[i]);               
            }
            for (n = 0; n < 4; n++)
            {
                vecA[n] = 0;
                for (m = 0; m < 4; m++)
                    vecA[n] = (A[n, m] * vecC[n]) + vecA[n];
            }
            Console.WriteLine("Вектор A");
            
            for (n = 0; n < 3; n++)
            {
                Console.Write("{0, 5}", vecA[n]);               
            }
            for (i = 0; i < 3; i++)
            {
                vecB[i] = 0;
                for (j = 0; j < 3; j++)
                {
                    vecB[i] = (B[i, j] * vecD[i]) + vecB[i];
                }
            }
            Console.WriteLine("Вектор B");
            
            for (i = 0; i < 3; i++)
            {
                Console.Write("{0, 5}", vecB[i]);               
            }
            Console.ReadKey();
        }
    }
}

