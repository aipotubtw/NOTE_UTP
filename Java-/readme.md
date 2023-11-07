```java
import java.util.Scanner;//数字加密,将每一位数字加5对十取余后反转

public class class16 {

    public static void main(String[] args) {
        int password = passWord();
        int[] arr = num(password);
        int[] brr = jiaMi(arr);
        for (int i = 0; i < brr.length; i++) {
            System.out.print(brr[i]);
        }
    }

    public static int[] num(int password) {
        int temp = password;
        int count = 0;
        for (int i = 0; temp != 0; i++) {
            temp = temp / 10;
            count++;
        }
        int[] arr = new int[count];
        for (int i = 0; i < arr.length; i++) {
            int ge = password % 10;
            password = password / 10;
            arr[i] = ge;
        }
        return arr;
    }

    public static int[] jiaMi(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            arr[i] = (arr[i] + 5) % 10;
        }
        int[] brr = new int[arr.length];
        for (int i = 0; i < brr.length; i++) {
            brr[i] = arr[i];
        }
        return brr;
    }

    public static int passWord() {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入密码：");
        int password = sc.nextInt();
        return password;
    }
}
```