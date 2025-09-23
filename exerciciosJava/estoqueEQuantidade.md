<img src="https://admin.ecommercebrasil.com.br/wp-content/uploads/2023/04/20-estoque-fulfillment.jpg.webp">
    
    package entities;
    
    // Esta classe representa um produto com nome, preço e quantidade em estoque
    public class Product {
        public String name;
        public double price;
        public int quantity;
    
        // Este método calcula o valor total em estoque
        public double totalValueInStock() {
            return price * quantity;
        }
    
        // Este método adiciona produtos ao estoque
        public void addProducts(int quantity) {
            // Incrementa a quantidade de produtos em estoque
            this.quantity += quantity;
            /*  'this' refere-se ao atributo da instância atual, 
            diferenciando-o do parâmetro*/
        }
    
        // Este método remove produtos do estoque
        public void removeProducts(int quantity) {
            // Decrementa a quantidade de produtos em estoque
            this.quantity -= quantity;
        }
    
        // Este método retorna uma representação em string do produto
        public String toString() {
            // String.format("%.2f", price) formata o número para duas casas decimais"
            return "Product: " + name + ", Price: $" + String.format("%.2f", price) + ", " + quantity + " units, Total: $ " + String.format("%.2f", totalValueInStock()); 
        }
    }
    

---

    import java.util.Scanner;
    
    // Importação da classe Product do pacote entities
    import entities.Product;
    
    public class Program {
        public static void main(String[] args) {
            
            Scanner sc = new Scanner(System.in);
    
            Product product = new Product(); // Instanciação de um objeto da classe Product
            System.out.println("Enter product data:");
            
            System.out.print("Name: "); // Leitura dos dados do produto
            product.name = sc.nextLine();
            
            System.out.println("Price: "); // Leitura do preço do produto
            product.price = sc.nextDouble();
            
            System.out.println("Quantity in stock: "); // Leitura da quantidade em estoque do produto
            product.quantity = sc.nextInt();
    
            // Exibição dos dados do produto
            System.out.println(product.toString());
    
            System.out.println("Quantity to add in stock: ");
            int quantity = sc.nextInt(); 
            product.addProducts(quantity); // Adiciona produtos ao estoque
            
            // Exibição dos dados do produto
            System.out.println("Updated value: " + product.toString());
    
            System.out.println("Do you want to remove products from stock? ");
            // Lê a resposta do usuário, considerando o primeiro caractere
            char response = sc.next().charAt(0); 
            if (response == 'y' || response == 'Y' || response == 's' || 
                response == 'S' || response == 't' || response == 'T') {
                System.out.println("Quantity to remove from stock: ");
                quantity = sc.nextInt();
                product.removeProducts(quantity); // Remove produtos do estoque
                // Exibição dos dados do produto
            } else {
                System.out.println("No products were removed from stock.");
            } 
            
            // Exibição dos dados do produto
            System.out.println("Updated value: " + product.toString());
    
            sc.close();
        }
    }
