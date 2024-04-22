package ecommercesystem;
import java.util.Scanner;
public class EcommerceSystem {

    public static void main(String[] args) {
      
       Scanner input = new Scanner(System.in);
        ElectronicProduct electprod = new ElectronicProduct(1,"smartphone",599.9F,"Samsung",1);
        ClothingProduct clothprod = new ClothingProduct(2,"T-shirt",19.99F,"Medium","Cotton");
        BookProduct bookprod = new BookProduct(3,"OOP",39.99F,"O'Reilly","X Publication");
        System.out.println("Welcome to my E-commerce System!");
        System.out.println("please enter your ID: ");
        int cId = input.nextInt();
        System.out.println("please enter your name: ");
        String cName = input.next();
        System.out.println("please enter your address ");
        String cAddress = input.next();
        Customer customer = new Customer(cId,cName,cAddress);
        System.out.println("How many products you want to add to your cart?");
        int nProducts = input.nextInt();
        Cart cart = new Cart(customer.getCustomerId(), nProducts);
        for (int i = 0; i < nProducts; i++) {
            System.out.println("Which product would you like to add? 1-Smartphone 2- T-shirt 3- OOP ");
            int type = input.nextInt();
            switch (type) {
                case 1 -> cart.addProduct(electprod);
                case 2 -> cart.addProduct(clothprod);
                case 3 -> cart.addProduct(bookprod);
                default -> System.out.println("invalid product type");
            }
        }
       cart.placeOrder();
    }
    
}

public class Product {
    private int productId;
    private String name;
    private float price;
    
    public Product(){}
    
    public Product(int productId , String name , float price){
    this.productId = Math.abs(productId);
    this.name = name;
    this.price = Math.abs(price); }
    
    public void setProductId(int productId){
    this.productId = Math.abs(productId); }
    
    public int getProductId(){
    return productId; }
    
     public void setName(String name){
    this.name = name; }
    
    public String getName(){
    return name; }
    
     public void setPrice(float price){
    this.price = Math.abs(price); }
    
    public float getPrice(){
    return price; }
}

public class ElectronicProduct extends Product {
    
    private String brand;
    private int warrantyPeriod;
    
    public ElectronicProduct(){}
    
    public ElectronicProduct(int productId , String name , float price , String brand , int warrantyPeriod){
    super(productId, name, price);
    this.brand = brand;
    this.warrantyPeriod = Math.abs(warrantyPeriod);
    }
    
    public void setBrand(String brand){
    this.brand = brand; }
    
    public String getBrand(){
    return brand; }
    
    public void setWarrabtyPeriod(int warrantyPeriod){
    this.warrantyPeriod = Math.abs(warrantyPeriod); }
    
    public int getWarrantyPeriod(){
    return warrantyPeriod; }

}

public class ClothingProduct extends Product {
    
    private String size;
    private String fabric;
    
    public ClothingProduct(){}
    
    public ClothingProduct(int productId , String name , float price , String size , String fabric){
    super(productId, name, price);
    this.size = size;
    this.fabric = fabric;
    }
    
    public void setSize(String size){
    this.size = size; }
    
    public String getSize(){
    return size; }
    
    public void setFabric(String fabric){
    this.fabric = fabric; }
    
    public String getFabric(){
    return fabric; }
}

public class BookProduct extends Product {
    
    private String author;
    private String publisher;
    
    public BookProduct(){}
    
    public BookProduct(int productId , String name , float price , String author , String publisher){
    super(productId, name, price);
    this.author = author;
    this.publisher = publisher;
    }
    
    public void setAuthor(String author){
    this.author = author; }
    
    public String getAuthor(){
    return author; }
    
    public void setPublisher(String publisher){
    this.publisher = publisher; }
    
    public String getPublisher(){
    return publisher; }
}

public class Customer {
    
    private int customerId;
    private String name;
    private String address;
    
    public Customer(){}
    
    public Customer(int customerId , String name , String address){
    this.customerId = Math.abs(customerId);
    this.name = name;
    this.address = address;
    }
    
    public void setCustomerId(int customerId){
    this.customerId = Math.abs(customerId); }
    
    public int getCustomerId(){
    return customerId; }
    
    public void setName(String name){
    this.name = name; }
    
    public String getName(){
    return name; }
    
    public void setAddress(String address){
    this.address = address; }
    
    public String getAddress(){
    return address; }
    
}

public class Order {
    
int customerId;
int orderId;
Product[]products;
float totalPrice;

public Order(){}

public Order(int customerId,int orderId,Product[]products, float totalPrice){
this.customerId=customerId;
this.orderId=orderId;
this.products=products;
this.totalPrice=totalPrice;
}

public void printOrderInfo(){
System.out.println("Customer ID: "+customerId);
System.out.println("Order ID: "+orderId);

if(products.length == 0){
System.out.println("There are no products in the cart");
}
else{
System.out.println("Products: ");
    for (Product product : products) {
        System.out.println(product.getName() + " --> " + product.getPrice() + "$");
    }
}
System.out.println("Total price: "+ totalPrice +"$");
}
}

import java.util.Scanner;
import java.util.Random;
public class Cart {
    Scanner input= new Scanner(System.in);
    
    private int customerId;
    private int nProduct;
    protected Product[]products;
    private Random rand = new Random();
    
    public Cart(){}
    
    public Cart(int customerId , int nProduct){
    this.customerId = Math.abs(customerId);
    this.nProduct = Math.abs(nProduct);
    this.products = new Product[nProduct]; }
    
    public void setCustomerId(int customerId){
    this.customerId = Math.abs(customerId); }
    
    public int getCustomerId(){
    return customerId; }
    
     public void setNproduct(int nProduct){
    this.nProduct = Math.abs(nProduct); }
    
    public int getNproduct(){
    return nProduct; }
    
   public void addProduct(Product newP){
        for(int i=0; i< products.length; i++){
            if(products[i]==null){
                products[i]=newP;
                return;
            }}
        }
    
   public void removeProduct(Product pToRemove){
   int indexToremove = -1;
   Product[]newProducts = new Product[nProduct-1];
   for(int i=0; i< products.length; i++){
   if (products[i] == pToRemove) {
          indexToremove=i;
           break;}
   }
   if(indexToremove != -1){
       for(int i=0,j=0; i<products.length; i++){
       if(i!= indexToremove){
       newProducts[j]= products[i];
       j++;}}
       System.out.println(pToRemove.getName()+" is removed from the cart");
       
        }
   else
      System.out.println("Product not found in the cart.");
   
   if(indexToremove != -1){
   for(int i=0; i<newProducts.length; i++){
   products[i]=newProducts[i];}
       } 
   }
   
    public float calculateTotalPrice() {
        float totalPrice = 0;
        for (int i = 0; i < nProduct; i++) {
            totalPrice += products[i].getPrice();
        }
        return totalPrice; }
    
    public Order placeOrder() {
        System.out.println("Would you like to place the order? (1-yes, 2-no)");
        int choice = input.nextInt();
        switch(choice) {
            case 1 -> {
                Order order = new Order(customerId, rand.nextInt(10000), products, calculateTotalPrice());
                System.out.println("Order placed successfully!");
                return order;
            }
            case 2 -> {
                System.out.println("Order canceled.");
                return null;
            }
            default -> {
                System.out.println("Invalid choice.");
                return null;
            }
        }    
    }
}


