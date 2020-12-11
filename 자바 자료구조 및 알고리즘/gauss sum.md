```java
import java.util.Scanner;

public class Q8Gauss {

    static int sumGauss(int startNum, int endNum) {
        int result = 0;
        int count = endNum - startNum + 1;

        result = (startNum + endNum) * count / 2;

        return result;
    }

    public static void main(String[] args){

        Scanner sc = new Scanner(System.in);

        System.out.println("a부터 b까지의 정수 합을 구하는 프로그램입니다.");
        System.out.print("a의 값을 입력해주세요 : ");

        int a = sc.nextInt();

        System.out.print("b의 값을 입력해주세요 : ");

        int b = sc.nextInt();

        System.out.println("결과 : " + sumGauss(a, b));
    }
}

```
