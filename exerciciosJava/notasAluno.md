<img src="https://edsurge.imgix.net/uploads/post/image/14200/grading-1622052736.png?auto=compress%2Cformat&crop=true&h=486&w=1200"> 
      
      package entities;
      
      public class notasaluno {
          public String nome;
          public double nota1;
          public double nota2;
          public double nota3;
          
          public double notaFinal() {
              return nota1 + nota2 + nota3;
          }
      }
      
---

      import entities.notasaluno;
      
      import java.util.Scanner;
      
      public class Student {
          public static void main(String[] args) {
              Scanner sc = new Scanner(System.in);
      
              notasaluno n1 = new notasaluno();
              
              System.out.println("Digite o nome do aluno:");
              n1.nome = sc.nextLine();
      
              System.out.println("Digite a primeira nota:");
              n1.nota1 = sc.nextDouble();
              if (n1.nota1 < 0 || n1.nota1 > 30) {
                  System.out.println("Nota inválida! A nota deve estar entre 0 e 30.");
                  sc.close();
                  return;
              }  
      
              System.out.println("Digite a segunda nota:");
              n1.nota2 = sc.nextDouble(); 
              if (n1.nota2 < 0 || n1.nota2 > 35) {
                  System.out.println("Nota inválida! A nota deve estar entre 0 e 35.");
                  sc.close();
                  return;
              }
      
              System.out.println("Digite a terceira nota:");
              n1.nota3 = sc.nextDouble();
              if (n1.nota3 < 0 || n1.nota3 > 35) {
                  System.out.println("Nota inválida! A nota deve estar entre 0 e 35.");
              }
      
              double notaFinal = n1.notaFinal();
              System.out.println("Nota final do aluno: " + notaFinal);
              if(n1.notaFinal() >=60) {
                  System.out.println("Aluno aprovado");
              } else {
                  System.out.println("Aluno reprovado");
                  // "faltam é uma variável local, estando fora da classe notasaluno"
                  double faltam = 60 - notaFinal;
                  System.out.println("Faltam " + faltam + " pontos para a aprovação.");
              }
              sc.close();
          }
      }
