import java.util.ArrayList;

public class StudentSort {

    // Student class
    static class Student {
        int rollno;
        String name;
        String address;

        // Constructor
        Student(int rollno, String name, String address) {
            this.rollno = rollno;
            this.name = name;
            this.address = address;
        }

        public String toString() {
            return rollno + " - " + name + " - " + address;
        }
    }

    // Sort by name using selection sort
    public static void sortByName(ArrayList<Student> list) {
        for (int i = 0; i < list.size() - 1; i++) {
            int min = i;
            for (int j = i + 1; j < list.size(); j++) {
                if (list.get(j).name.compareToIgnoreCase(list.get(min).name) < 0) {
                    min = j;
                }
            }
            Student temp = list.get(i);
            list.set(i, list.get(min));
            list.set(min, temp);
        }
    }

    // Sort by roll number using selection sort
    public static void sortByRoll(ArrayList<Student> list) {
        for (int i = 0; i < list.size() - 1; i++) {
            int min = i;
            for (int j = i + 1; j < list.size(); j++) {
                if (list.get(j).rollno < list.get(min).rollno) {
                    min = j;
                }
            }
            Student temp = list.get(i);
            list.set(i, list.get(min));
            list.set(min, temp);
        }
    }

    // Main ArrayList with their roll number, name, and their state
    public static void main(String[] args) {
        ArrayList<Student> students = new ArrayList<>();

        students.add(new Student(5, "Brett", "New York"));
        students.add(new Student(2, "Karen", "California"));
        students.add(new Student(9, "Ericka", "Texas"));
        students.add(new Student(1, "Dalton", "Florida"));
        students.add(new Student(7, "Thelma", "Nevada"));
        students.add(new Student(6, "Sandra", "Ohio"));
        students.add(new Student(3, "Mary", "Missouri"));
        students.add(new Student(10, "Jim", "Georgia"));
        students.add(new Student(4, "Lauren", "Utah"));
        students.add(new Student(8, "Julia", "Alaska"));

        System.out.println("Original List:");
        for (Student s : students) {
            System.out.println(s);
        }

        sortByName(students);
        System.out.println("\nSorted by Name:");
        for (Student s : students) {
            System.out.println(s);
        }

        sortByRoll(students);
        System.out.println("\nSorted by Roll Number:");
        for (Student s : students) {
            System.out.println(s);
        }
    }
}
