import java.util.Scanner; // импорт сканера
 
class MainClass {
 
    public static void main(String[] args) throws Exception {
        int num1 = getInt();
        int num2 = getInt();
        String operation = getString();
        int calc = Calculation(num1, num2, operation);
        System.out.println(calc);
    }
 
    public static int getInt() {
        System.out.print("Введите любое целое число от 1 до 10: ");
        Scanner scan = new Scanner(System.in);
        int number = scan.nextInt();
        System.out.println("Вы ввели число " + number);
        return number;
    }
 
 
    public static String getString() {
        System.out.print("Введите любой из символов +, -, *, /: ");
        Scanner scan = new Scanner(System.in);
        String Simbol = scan.nextLine();
        System.out.println("Вы ввели символ " + Simbol);
        return Simbol;
    }
 
    public static int Calculation(int num1, int num2, String operation) throws Exception {
        if (operation.equals("+")) {
            return (num1 + num2);
        } else if (operation.equals("-")) {
            return (num1 - num2);
        } else if (operation.equals("*")) {
            return (num1 * num2);
        } else if (operation.equals("/")) {
            if (num2 == 0) {
                throw new Exception("Division by zero is not allowed");
            }
            return (num1 / num2);
        } else {
            throw new Exception("Invalid symbol");
        }
    }
}
