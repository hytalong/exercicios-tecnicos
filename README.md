# exercicios-tecnicos
exercicios-tecnicos


1 ------------------------------------------------------------------
 using System;

class Program
{
    static void Main()
    {
        int INDICE = 13, SOMA = 0, K = 0;

        while (K < INDICE)
        {
            K = K + 1;
            SOMA = SOMA + K;
        }

        Console.WriteLine("O valor de SOMA é: " + SOMA);
    }
}

O valor de SOMA ao final será 91

2--------------------------------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Informe um número: ");
        int numero = int.Parse(Console.ReadLine());
        int a = 0, b = 1, fibonacci = 0;

        while (fibonacci < numero)
        {
            fibonacci = a + b;
            a = b;
            b = fibonacci;
        }

        if (fibonacci == numero || numero == 0)
        {
            Console.WriteLine($"O número {numero} pertence à sequência de Fibonacci.");
        }
        else
        {
            Console.WriteLine($"O número {numero} NÃO pertence à sequência de Fibonacci.");
        }
    }
}

3 ----------------------------------------------------------
{
  "faturamento": [200.5, 0.0, 150.75, 0.0, 300.0, 400.0, 0.0, 600.0, 0.0]
}

using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using Newtonsoft.Json;

class Program
{
    static void Main()
    {
        string json = File.ReadAllText("faturamento.json");
        var dados = JsonConvert.DeserializeObject<FaturamentoMensal>(json);

        var faturamento = dados.Faturamento.Where(x => x > 0).ToList();
        double menorValor = faturamento.Min();
        double maiorValor = faturamento.Max();
        double mediaMensal = faturamento.Average();
        int diasAcimaDaMedia = faturamento.Count(x => x > mediaMensal);

        Console.WriteLine($"Menor valor: {menorValor}");
        Console.WriteLine($"Maior valor: {maiorValor}");
        Console.WriteLine($"Dias acima da média: {diasAcimaDaMedia}");
    }
}

class FaturamentoMensal
{
    public List<double> Faturamento { get; set; }
}


4------------------------------------------------------------------------


using System;

class Program
{
    static void Main()
    {
        double[] valores = { 67836.43, 36678.66, 29229.88, 27165.48, 19849.53 };
        string[] estados = { "SP", "RJ", "MG", "ES", "Outros" };
        double total = 0;

        foreach (var valor in valores)
            total += valor;

        Console.WriteLine("Percentual de representação por estado:");
        for (int i = 0; i < valores.Length; i++)
        {
            double percentual = (valores[i] / total) * 100;
            Console.WriteLine($"{estados[i]}: {percentual:F2}%");
        }
    }
}


5---------------------------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Informe uma string: ");
        string texto = Console.ReadLine();
        char[] invertida = new char[texto.Length];

        for (int i = 0; i < texto.Length; i++)
        {
            invertida[i] = texto[texto.Length - 1 - i];
        }

        Console.WriteLine("String invertida: " + new string(invertida));
    }
}


