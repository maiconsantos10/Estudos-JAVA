<img src="https://imgs.jusbr.com/publications/images/c77eb1287b2e0078bbd02992fa88247a">
    
    package entities;
    
    public class Funcionario {
        public String nome;
        public double salarioBruto;
        public double imposto;
    
        public double salarioLiquido() {
            return salarioBruto - imposto;
        }
        
        public void aumentarSalario(double porcentagem) {
            salarioBruto += salarioBruto * porcentagem / 100.0;
        }
    }
    
---
    
    import java.util.Scanner;
    
    import entities.Funcionario;
    
    public class Program {
        public static void main(String[] args) {
            
            Scanner sc = new Scanner(System.in);
    
            // Entrando com os dados do funcionário
            Funcionario salario = new Funcionario();
           
           System.out.println("Digite o nome do funcionário: ");
           salario.nome = sc.nextLine();
    
           System.out.println("Digite o salário bruto do funcionário: ");
           salario.salarioBruto = sc.nextDouble();
    
           System.out.println("Digite o valor do imposto: ");
           salario.imposto = sc.nextDouble();
           while (salario.imposto > salario.salarioBruto) {
            System.out.println("Imposto não pode ser maior que o salário bruto. Digite novamente: ");
            salario.imposto = sc.nextDouble();
            }  
    
            
    
           System.out.println("Salário líquido atual: " + String.format("%.2f", salario.salarioLiquido()));
    
           System.out.println("Qual o aumento salarial em porcentagem? ");
           salario.aumentarSalario(10.0); 
    
           System.out.println("Salário líquido atualizado: " + String.format("%.2f", salario.salarioLiquido()));
    
    
            sc.close();
        }
    }
