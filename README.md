import java.util.*;

class TimetableScheduler {

    private List<String> subjects = new ArrayList<>();
    private Map<String, List<String>> timetable = new LinkedHashMap<>();
    private int periodsPerDay;

    // Add subjects
    public void addSubject(String subject) {
        subjects.add(subject);
    }

    // Set number of periods per day
    public void setPeriodsPerDay(int periods) {
        this.periodsPerDay = periods;
    }

    // Generate automatic timetable
    public void generateTimetable() {
        String[] days = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};

        for (String day : days) {
            timetable.put(day, new ArrayList<>());
        }

        int subjectIndex = 0;

        for (String day : days) {
            for (int p = 0; p < periodsPerDay; p++) {
                timetable.get(day).add(subjects.get(subjectIndex));
                subjectIndex = (subjectIndex + 1) % subjects.size();
            }
        }
    }

    // Print timetable in table format
    public void printTimetable() {
        System.out.println("\n================ TIMETABLE ================\n");

        // Print header row
        System.out.printf("%-12s", "Day");
        for (int p = 1; p <= periodsPerDay; p++) {
            System.out.printf("| %-15s", "Period " + p);
        }
        System.out.println();
        System.out.println("---------------------------------------------------------------"
                + "----------------------------------------");

        // Print rows for each day
        for (String day : timetable.keySet()) {
            System.out.printf("%-12s", day);

            for (String subject : timetable.get(day)) {
                System.out.printf("| %-15s", subject);
            }

            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        TimetableScheduler scheduler = new TimetableScheduler();

        System.out.println("Enter number of subjects:");
        int n = sc.nextInt();
        sc.nextLine();

        System.out.println("Enter subject names:");
        for (int i = 0; i < n; i++) {
            scheduler.addSubject(sc.nextLine());
        }

        System.out.println("Enter number of periods per day:");
        int periods = sc.nextInt();
        scheduler.setPeriodsPerDay(periods);

        scheduler.generateTimetable();
        scheduler.printTimetable();
    }
}
