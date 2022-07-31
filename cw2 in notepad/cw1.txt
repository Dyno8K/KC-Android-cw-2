import static java.lang.System.*;
import java.util.Scanner;  

public class App {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(in);
        //task 1
        String name = "Mohammed";
        int age = 17;

        out.printf("Hello my name is %s and I am %d years old", name, age);


        //task 2
        out.println("\n\nWelcome to the rollercoaster of death!");

        int riders;
        boolean valid = false;
        do{
            
            out.println("How many heights are you going to test?");
            riders = sc.nextInt();
            
            if (riders>6 || riders < 1){
                valid = false;
                out.println("Please enter a number up to 6\n");
            }
            else if (riders <= 6){
                valid = true;
            }        

        } while (!valid);
        
        int[] riderHeights;
        riderHeights = new int[riders];
        
        for(int i=0;i<riders;i++ ){
            int height;
            do{
                out.println("Please enter the height of rider "+ (i+1));
                height = sc.nextInt();

                if(height >300 || height < 0){
                    valid = false;
                    out.println("Please enter a realistic height\n");
                }
                else{
                    valid = true;
                }

            } while (!valid);
            
            riderHeights[i] = height;
        }
        for (int i = 0; i<riders;i++){
            if(riderHeights[i] < 160){
                out.println("Rider "+(i+1)+" INVALID");
            }
            else{
                out.println("Rider "+(i+1)+" VALID");
            }
        }
        sc.close();
    }
}
