<img src="https://study.com/cimages/multimages/16/222224971011527207636336.jpg">

    package entities;

    public class Rectangle {
      public double width;
      public double height;
      public double area;
      public double perimeter;
      public double diagonal; 

      public double area () {
        return area = width * height;
      }

      public double perimeter () {
        return perimeter = 2 * (width + height);
      }

      public double diagonal () {
        return diagonal = Math.sqrt((width * width) + (height * height));   
        }
      }


- - -

    import java.util.Scanner;

    import entities.Rectangle;

    public class Program {
      public static void main(String[] args) {
          Scanner sc = new Scanner(System.in);
       
          // Instanciando o objeto
          Rectangle rectangle = new Rectangle();
        
          System.out.println("Enter rectangle width: ");
          rectangle.width = sc.nextDouble();
     
          System.out.println("Enter rectangle height: ");
          rectangle.height = sc.nextDouble();
        
          System.out.println(rectangle.area());
          System.out.println(rectangle.perimeter());
          System.out.println(rectangle.diagonal());
        
        
          System.out.println("Rectangle perimeter is: " + rectangle.perimeter);
        
          System.out.println("Rectangle diagonal is: " + rectangle.diagonal);

           
          System.out.println("Area: " + String.format("%.2f", rectangle.area()) 
                            + "\nPerimeter: " 
                            + String.format("%.2f", rectangle.perimeter()) 
                            + "\nDiagonal: " 
                            + String.format("%.2f", rectangle.diagonal()));
          sc.close();
        } 
      }
