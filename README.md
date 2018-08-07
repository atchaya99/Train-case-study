# Train-case-study
import java.util.*;
public class Traincase {
    static void ptdate(int date){
        if(date>=0&&date<=4){
            System.out.print("Monday\t");
        }
        else if(date>=5&&date<=9){
            System.out.print("Tuesday\t");
        }
        else{
            System.out.print("Wednesday\t");
        }
    }
    public static void main(String[] args) {
        String[]dt={"6.04","9.04","12.04","15.04","19.04"};
        int[]pn={22,119,64,177,21,22,111,87,193,22,11,107,93,162,42};
        int j=0,max,min,p=0,p1=0;
        int ch1;
        do{
        System.out.println("Enter Your options");
        System.out.println("1)Display the data\n"+"2)Find the most popular train\n"+"3)Find the least popular train\n"+"4)Find out whether the 6.04 train is more popular than the 9.04 train\n"+"5)Find out whether the 6.04 train on Monday is more popular than the 6.04 train on Tuesday\n"+"6)Find out which of any two trains is more popular where day and time is specified by the user\n"+"7)Display a list of all trains(day,time) where passenger numbers were below 50\n"+"8)Calculate the average number of passengers travelling on the 12.04 train over the three days\n"+"9)Calculate the average number of passengers travelling where day and time is spcified by the user\n"+"10)Quit.");
        Scanner sc=new Scanner(System.in);
        int ch=sc.nextInt();
        switch(ch){
            case 1:
                System.out.println("Day\tTime\tPassengers");
                for(int i=0;i<=14;i++)
                {
                ptdate(i);
                System.out.print(dt[j]+"\t");
                j++;
                if(j==4){j=0;}
                System.out.print(""+pn[i]+"\n");
                }
                break;
            case 2:
                max=pn[0];
                for(int i=0;i<=14;i++)
                {
                if(max<pn[i])
                {
                max=pn[i];
                p=i;
                }
                }
                System.out.println("Find the most popular train");
                ptdate(p);
                System.out.print(""+dt[p%5]+"\n");
                break;
            case 3:
                min=pn[0];
                for(int i=0;i<=14;i++)
                {
                if(min>pn[i])
                {
                min=pn[i];
                p=i;
                }
                }
                System.out.println("Find the least popular train");
                ptdate(p);
                System.out.print(""+dt[p%5]+"\n");
                break;
            case 4:
                if((pn[0]<pn[1])&&(pn[5]<pn[6])&&(pn[10]<pn[11]))
                {System.out.println("No 6.04 is not popular");}
                else
                {System.out.println("Yes 6.04 is popular");}
                break;
            case 5:
                if(pn[0]>pn[5])
                {System.out.println("Yes");}
                else
                {System.out.println("No");}
                break;
            case 6:
                max=pn[0];
                for(int i=0;i<=14;i++)
                {
                if(max<pn[i])
                {
                max=pn[i];
                p1=p;
                p=i;
                }
                }
                ptdate(p);
                System.out.print(""+dt[p%5]+"\n");
                ptdate(p1);
                System.out.print(""+dt[p1%5]+"\n");
                break;
            case 7:
                for(int i=0;i<=14;i++)
                {
                if(pn[i]<50)
                {
                ptdate(i);
                System.out.print(""+dt[i%5]+"\n");
                }
                }
                break;
            case 8:
                System.out.print("Average="+((pn[2]+pn[7]+pn[12])/3)+"\n");
                break;
            
            case 9:
                return;
            }
        System.out.println("Do you want to continue press 1 else 0:");
        ch1=sc.nextInt();
        }while(ch1==1);
    }
}
