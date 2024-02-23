# VerificaFibonacci


package verificafibonacci;

import java.util.Scanner;

public class VerificaFibonacci {

    
    public static void main(String[] args) {
        
                Scanner scanner = new Scanner(System.in);

        // Solicita ao usuário que insira o número
        System.out.println("Digite um número inteiro:");
        int numero = scanner.nextInt();

        // Verifica se o número é uma sequência de Fibonacci
        boolean ehFibonacci = verificaSequenciaFibonacci(numero);

        // Exibe o resultado
        if (ehFibonacci) {
            System.out.println(numero + " faz parte da sequência de Fibonacci.");
        } else {
            System.out.println(numero + " não faz parte da sequência de Fibonacci.");
        }

        // Fecha o scanner
        scanner.close();
    }

    // Método para verificar se um número está na sequência de Fibonacci
    public static boolean verificaSequenciaFibonacci(int numero) {
        // Condição especial para os primeiros números da sequência de Fibonacci
        if (numero == 0 || numero == 1) {
            return true;
        }

        // Inicializa os primeiros dois números da sequência de Fibonacci
        int anterior = 0;
        int atual = 1;

        // Percorre a sequência de Fibonacci até encontrar um número maior ou igual ao número dado
        while (atual <= numero) {
            // Se o número for encontrado, retorna true
            if (atual == numero) {
                return true;
            }
            // Calcula o próximo número da sequência de Fibonacci
            int proximo = anterior + atual;
            // Atualiza os números anteriores para o próximo cálculo
            anterior = atual;
            atual = proximo;
        }

        // Se o número não for encontrado, retorna false
        return false;

        
    }
    
}
