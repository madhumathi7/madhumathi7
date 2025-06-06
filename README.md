import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        TaskManager manager = new TaskManager();
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("Welcome to Task Manager CLI");
        while (true) {
            System.out.print("> ");
            input = scanner.nextLine();

            if (input.startsWith("add ")) {
                manager.addTask(input.substring(4));
            } else if (input.equals("list")) {
                manager.listTasks();
            } else if (input.startsWith("done ")) {
                manager.markTaskDone(Integer.parseInt(input.substring(5)));
            } else if (input.startsWith("del ")) {
                manager.deleteTask(Integer.parseInt(input.substring(4)));
            } else if (input.equals("exit")) {
                break;
            } else {
                System.out.println("Unknown command. Use add/list/done/del/exit.");
            }
        }
        scanner.close();
    }
}
