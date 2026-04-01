public class Task {
    private String title;
    private String priority;
    private String status;

    public Task(String title, String priority) {
        this.title = title;
        this.priority = priority;
        this.status = "Pending";
    }

    public void markCompleted() {
        this.status = "Completed";
    }

    public String getTitle() {
        return title;
    }

    public String getPriority() {
        return priority;
    }

    public String getStatus() {
        return status;
    }

    @Override
    public String toString() {
        return "Task: " + title + " | Priority: " + priority + " | Status: " + status;
    }
}
import java.util.ArrayList;

public class TaskManager {
    private ArrayList<Task> tasks = new ArrayList<>();

    public void addTask(String title, String priority) {
        tasks.add(new Task(title, priority));
        System.out.println("Task added successfully!");
    }

    public void viewTasks() {
        if (tasks.isEmpty()) {
            System.out.println("No tasks available.");
            return;
        }

        for (int i = 0; i < tasks.size(); i++) {
            System.out.println((i + 1) + ". " + tasks.get(i));
        }
    }

    public void completeTask(int index) {
        if (index >= 0 && index < tasks.size()) {
            tasks.get(index).markCompleted();
            System.out.println("Task marked as completed!");
        } else {
            System.out.println("Invalid task number.");
        }
    }
}
