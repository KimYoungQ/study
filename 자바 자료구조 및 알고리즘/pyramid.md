```java
import java.util.Scanner;

public class Q16pyramid {

    static void spira(int n) {

        for(int i = 1; i <= n; ++i) {
            for(int j = 0; j < n-i; ++j)
                System.out.print(' ');
            for(int j = 0; j < 2*i-1; ++j)
                System.out.print('*');
            System.out.println();
        }
    }

    public static void main(String[] args)  {

        Scanner sc = new Scanner(System.in);
        System.out.print("n단의 피라미드를 출력하는 n을 입력하세요 : ");
        int n = sc.nextInt();

        spira(n);
    }
}
```
