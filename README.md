// Employee.java
public class Employee {
    private String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

// FullTimeEmployee.java
public class FullTimeEmployee extends Employee {
    private double monthlySalary;

    public void setMonthlySalary(double monthlySalary) {
        this.monthlySalary = monthlySalary;
    }

    public double getMonthlySalary() {
        return monthlySalary;
    }
}

// PartTimeEmployee.java
public class PartTimeEmployee extends Employee {
    private double ratePerHour;
    private int hoursWorked;
    private double wage;

    public void setWage(double ratePerHour, int hoursWorked) {
        this.ratePerHour = ratePerHour;
        this.hoursWorked = hoursWorked;
        this.wage = ratePerHour * hoursWorked;
    }

    public double getWage() {
        return wage;
    }
}

// RunEmployee.java
public class RunEmployee {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter employee name: ");
        String name = scanner.nextLine();

        System.out.print("Press F for full time or P for part time: ");
        char empType = scanner.next().charAt(0);

        if (empType == 'F') {
            System.out.print("Enter monthly salary: ");
            double monthlySalary = scanner.nextDouble();

            FullTimeEmployee fullTimeEmployee = new FullTimeEmployee();
            fullTimeEmployee.setName(name);
            fullTimeEmployee.setMonthlySalary(monthlySalary);

            System.out.println("Employee name: " + fullTimeEmployee.getName());
            System.out.println("Monthly salary: " + fullTimeEmployee.getMonthlySalary());
        } else if (empType == 'P') {
            System.out.print("Enter rate per hour and number of hours worked separated by a space: ");
            double ratePerHour = scanner.nextDouble();
            int hoursWorked = scanner.nextInt();

            PartTimeEmployee partTimeEmployee = new PartTimeEmployee();
            partTimeEmployee.setName(name);
            partTimeEmployee.setWage(ratePerHour, hoursWorked);

            System.out.println("Employee name: " + partTimeEmployee.getName());
            System.out.println("Wage: " + partTimeEmployee.getWage());
        } else {
            System.out.println("Invalid input");
        }
    }
}
