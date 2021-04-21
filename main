import java.io.*;
import java.util.*;
 
public class GFG 
{
    public String str="";
    
    public static int[][] generateSquare(int n)
    {
        int[][] magicSquare = new int[n][n];
 
        // Initialize position for 1
        int i = n / 2;
        int j = n - 1;
 
        // One by one put all values in magic square
        for (int num = 1; num <= n * n;) {
            if (i == -1 && j == n) // 3rd condition
            {
                j = n - 2;
                i = 0;
            }
            else {
                // 1st condition helper if next number
                // goes to out of square's right side
                if (j == n)
                    j = 0;
 
                // 1st condition helper if next number is
                // goes to out of square's upper side
                if (i < 0)
                    i = n - 1;
            }
 
            // 2nd condition
            if (magicSquare[i][j] != 0) {
                j -= 2;
                i++;
                continue;
            }
            else
                // set number
                magicSquare[i][j] = num++;
 
            // 1st condition
            j++;
            i--;
        }
 
        // print magic square
        return magicSquare;
    }

    public static int[][] shuffle(int[][] m,int n)
    {
        int min = 0;
      int max = n-2;
      int i,j,a,b,k=1,t;
        
      //Generate random int value from 0 to n-2
      while(k!=n*n)
      {
        i = (int)Math.floor(Math.random()*(max-min+1)+min);
        j= (int)Math.floor(Math.random()*(max-min+1)+min);
      
        while(i==j)
        {
            i = (int)Math.floor(Math.random()*(max-min+1)+min);
            j= (int)Math.floor(Math.random()*(max-min+1)+min);
        }
        if(k%2==0)
        {
        a=i;
        b=j+1;
        
        if(a==b)
        {
            a=i+1;
            b=j;
        }
        }
        else
        {
            a=i+1;
            b=j;
            if(a==b)
        {
           a=i;
             b=j+1;
        }
        }
        t=m[i][j];
        m[i][j]=m[a][b];
        m[a][b]=t;
        k++;
      }
      return m;
    }
    
    public static void game(int[][] m,int[][] r,int n)
    {
        int i,j,a,b,t,count=0;
        char c;
        String s="",in;
        Scanner sc= new Scanner(System.in);
        System.out.println("The Square for " + n
                           + ":");
        for (i = 0; i < n; i++)
        {
            for (j = 0; j < n; j++)
                System.out.print(m[i][j] + " ");
            System.out.println();
        }
        while(true)
        {
            
            System.out.println("ENTER THE COMMAND");
            i=sc.nextInt();
            j=sc.nextInt();
            c = sc.next().charAt(0);
            
            if(i<=0 || j<=0 || i>=n+1 || j>=n+1)
            {
                System.out.println("INVALID COMMAND");
                continue;
            }
i=i-1;
j=j-1;
            switch(c)
            {
                case 'D':
                    if((i+1)==n)
                    {
                       System.out.println("INVALID COMMAND");
                        continue; 
                    }
                    else
                    {
                       a=i+1;
                        b=j; 
                    }
                    t=m[i][j];
                    m[i][j]=m[a][b];
                    m[a][b]=t;
                    break;
                
                case 'U':
                    if((i-1)==-1)
                    {
                       System.out.println("INVALID COMMAND");
                        continue; 
                    }
                    else
                    {
                       a=i-1;
                        b=j; 
                    }
                    t=m[i][j];
                    m[i][j]=m[a][b];
                    m[a][b]=t;
                    break;   
                
                case 'L':
                    if((j-1)==-1)
                    {
                       System.out.println("INVALID COMMAND");
                        continue; 
                    }
                    else
                    {
                       a=i;
                        b=j-1; 
                    }
                    t=m[i][j];
                    m[i][j]=m[a][b];
                    m[a][b]=t;
                    break;   
                    
                case 'R':
                    if((j+1)==n)
                    {
                       System.out.println("INVALID COMMAND");
                        continue; 
                    }
                    else
                    {
                       a=i;
                        b=j+1; 
                    }
                    t=m[i][j];
                    m[i][j]=m[a][b];
                    m[a][b]=t;
                    break;
                    
            }
            s=s+i+j+c+"\n";
            count++;
            System.out.println("The Square for " + n
                           + ":");
        for (i = 0; i < n; i++)
        {
            for (j = 0; j < n; j++)
                System.out.print(m[i][j] + " ");
            System.out.println();
        }
            int co=0;
            for (i = 0; i < n; i++)
            {
                for (j = 0; j < n; j++)
                {
                    if(m[i][j]!=r[i][j])
                    {
                        continue;
                    }
                    else
                    {
                        co++;
                    }
                }
                
                
            }
            if(co==n*n)
            {
                System.out.println("YOU WON IN "+count+" MOVES");
                System.out.println("YOUR commands are:");
                System.out.println(s);
                break;
            }
            
        }
        
    }   
      
    public static void main(String[] args) 
    {
        int n,i,j;
        int[][] m,r;
        Scanner sc= new Scanner(System.in);
        System.out.println("ENTER A ODD NUMBER");
        n=sc.nextInt();
        m=new int[n][n];
        r=generateSquare(n);
        for (i = 0; i < n; i++)
            {
                for (j = 0; j < n; j++)
                {
                    m[i][j]=r[i][j];
                }
            }
            m=shuffle(m,n);
            game(m,r,n);
    }
        
        
        
        
      
      
}
