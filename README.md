//java code
import java.util.Arrays;
import java.util.Scanner;

public class HRsel {

    static int minDiff(int array[], int a, int b)
    {
        int result = Integer.MAX_VALUE;
        Arrays.sort(array);
        for (int i=0; i<= a-b;i++)
            result = Math.min(result, array[i + b - 1] - array[i]);
        return result;
    }

    static int findelements(int r,int array[], int a, int b)
    {
        int result = Integer.MAX_VALUE;
        for(int i=0; i<=a; i++)
        {
            result = Math.min(result, array[i + b - 1] - array[i]);
            if (r==result)
                return i;
        }
        return 0;
    }

    public static void main(String[] args) {

        int array[]={7980,22349,999,2799,229900,11101,9999,2195,9800,4999};
        String items[]={ "MI Band: 999","Sandwich Toaster: 2195" ,"Cult Pass: 2799","Scale: 4999","Fitbit Plus: 7980","Microwave Oven: 9800"  ,"Alexa: 9999","Digital Camera: 11101", "IPods: 22349","Macbook Pro: 229900" };
        int Num = array.length;

        System.out.println("Enter the number of employees");
        Scanner s = new Scanner(System.in);

        int Mem=s.nextInt();
        int res=minDiff(array, Num, Mem);

        System.out.println("Number of the employees:"+Mem);
        int startindex=findelements(res,array,Num,Mem);

        System.out.println("Here the goodies that are selected for distribution are:");
        for(int i=startindex;i<startindex+Mem;i++)

        System.out.println(items[i]);
        System.out.println("\n");
        System.out.println("And the difference between the chosen goodies with highest price and the lowest price is:"+res);
    }
}
