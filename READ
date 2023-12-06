# Practice_project-Fix-Bugs-in-application-
import java.util.ArrayList;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        System.out.println("\n**************************************\n");
        System.out.println("\tWelcome to TheDesk \n");
        System.out.println("**************************************");
        optionsSelection();
    }

    private static void optionsSelection() {
        String[] arr = {"1. I wish to review my expenditure",
                "2. I wish to add my expenditure",
                "3. I wish to delete my expenditure",
                "4. I wish to sort the expenditures",
                "5. I wish to search for a particular expenditure",
                "6. Close the application"
        };
        int[] arr1 = {1,2,3,4,5,6};
        int  slen = arr1.length;
        ArrayList<Integer> arrlist = new ArrayList<>();
        arrlist.add(1000);
        arrlist.add(2300);
        arrlist.add(45000);
        arrlist.add(32000);
        arrlist.add(110);

        System.out.println("\nEnter your choice:\t");
        Scanner sc = new Scanner(System.in);
        int options = sc.nextInt();

        for(int j=1;j<=slen;j++){
            if(options==j){
                switch (options){
                    case 1:
                        System.out.println("Your saved expenses are listed below: \n");
                        System.out.println(arrlist+"\n");
                        optionsSelection();
                        break;
                    case 2:
                        System.out.println("Enter the value to add your Expense: \n");
                        int value = sc.nextInt();
                        arrlist.add(value);
                        System.out.println("Your value is updated\n");
                        System.out.println(arrlist+"\n");
                        optionsSelection();
                        break;
                    case 3:
                        System.out.println("You are about the delete all your expenses! \nConfirm again by selecting the same option...\n");
                        int con_choice = sc.nextInt();
                        if(con_choice==options){
                            arrlist.clear();
                            System.out.println(arrlist+"\n");
                            System.out.println("All your expenses are erased!\n");
                        } else {
                            System.out.println("Oops... try again!");
                        }
                        optionsSelection();
                        break;
                    case 4:
                        sortExpenses(arrlist);
                        optionsSelection();
                        break;
                    case 5:
                        searchExpenses(arrlist);
                        optionsSelection();
                        break;
                    case 6:
                        closeApp();
                        break;
                    default:
                        System.out.println("You have made an invalid choice!");
                        break;
                }
            }
        }
    }

    private static void closeApp() {
        System.out.println("Closing your application... \nThank you!");
    }

    private static void searchExpenses(ArrayList<Integer> arrayList) {
        int leng = arrayList.size();
        System.out.println("Enter the expense you need to search:\t");
        Scanner sc = new Scanner(System.in);
        int searchValue = sc.nextInt();

        int low = 0;
        int high = leng - 1;
        boolean found = false;

        while (low <= high) {
            int mid = (low + high) / 2;
            int midValue = arrayList.get(mid);

            if (midValue == searchValue) {
                found = true;
                break;
            } else if (midValue < searchValue) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }

        if (found) {
            System.out.println("Expense found: " + searchValue);
        } else {
            System.out.println("Expense not found.");
        }
    }

    private static void sortExpenses(ArrayList<Integer> arrayList) {
        int arrLength = arrayList.size();

        for (int i = 0; i < arrLength - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < arrLength; j++) {
                if (arrayList.get(j) < arrayList.get(minIndex)) {
                    minIndex = j;
                }
            }

            int temp = arrayList.get(i);
            arrayList.set(i, arrayList.get(minIndex));
            arrayList.set(minIndex, temp);
        }

        System.out.println("Expenses sorted in ascending order: " + arrayList);
    }
}
