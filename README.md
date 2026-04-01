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
