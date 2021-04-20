


import java.util.Scanner;


interface Discountable {
    
    double discountedPrice(double price);
    
}
 
public class BestForCustomer implements Discountable {
    
    double discount_percentange;
    
    double threshold;
    
    double discount;
    
    BestForCustomer(){
        
        // threshold is 10%
        
        threshold = 10.0;
        
        
        discount_percentange = 0.0;
    
        discount = 0.0;
    }

    public void setDiscount_percetange(double discount_percent) {
       
        this.discount_percentange = discount_percent;
    }

    @Override
    public double discountedPrice(double price) {
        
        
         discount = price*(discount_percentange/100);
         
         
         double price_After_percentageDiscount = price - discount;
         
         double price_Thereshold_Discount = price - (price* (threshold/100));
         
         
         if( price_After_percentageDiscount < price_Thereshold_Discount){
             
             
             return price_After_percentageDiscount;
             
         }else{
             
             return price_Thereshold_Discount;
             
         }
         

    }
    
  public static void main(String[] args){
      
      
      Scanner sc = new Scanner(System.in);
      
      
       BestForCustomer ob = new  BestForCustomer();
      
      System.out.println("Please enter sales price and discount percentage");
      
      
      System.out.print("Price : ");
      
      double price = sc.nextDouble();
      
       System.out.print("Discount percentage  : ");
       
       
       double discount = sc.nextDouble();
       
       
       // calling method to calculate best possible sales price 
       
       ob.setDiscount_percetange(discount);
       
       
      
      
    
       double bestSalesPrice =  ob.discountedPrice(price);
      
      System.out.println("Best possible sales price : "+bestSalesPrice);
      
      
      
      
      
      
      
  }  
    
    
}
