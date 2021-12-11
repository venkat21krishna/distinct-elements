# distinct-elements

import java.util.*;
public class Main
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        int tc = sc.nextInt();
        while(tc -- > 0)
        {
            int n = sc.nextInt();
            HashMap<Integer,Integer> mp = new HashMap<>();
            for(int i=0; i<n; i++)
            {
                int arr = sc.nextInt();
                mp.put(arr,mp.getOrDefault(arr,0)+1);
            }
            long result=1;
            for(Map.Entry e : mp.entrySet())
            {
                int y = (int) e.getValue();
                if(y==1) result=result*2;
                else result=result*(1+ y);
                result%=1000000007;
            }
            System.out.println(result-1);
        }
    }
}
