
<img src="https://conhecimentocientifico.r7.com/wp-content/uploads/2019/10/numero-pi-conceito-historia-e-calculo-1.jpg">
  
    package application;
    
    import java.util.Scanner;
    
    public class Program {
        
        // Declarando PI como uma constante utilizando 'final'
        public static final double PI = 3.14159;
        
        public static void main(String[] args) {
            
            Scanner sc = new Scanner(System.in);
        
            System.out.println("Enter the radius: ");
            double radius = sc.nextDouble();
    
            // Chamando os métodos para calcular circunferência e volume
            double c = circumference(radius); // Gua
    
            // Chamando o método para calcular volume
            double v = volume(radius);
    
            System.out.printf("circumference: %.2f%n", c);
            System.out.printf("volume: %.2f%n", v);
            System.out.printf("PI value: %.2f%n", PI);
    
            sc.close();
        }
    
        public static double circumference(double radius) {
            return 2.0 * PI * radius;
        }
    
        public static double volume(double radius) {
            return (4.0 / 3.0) * PI * radius * radius * radius;
        }
    
    }
