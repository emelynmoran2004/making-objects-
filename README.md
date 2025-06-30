public class Main {
    public static void main(String[] args) {
        Car car = new Car(120, 50.5, 4);
        System.out.println(" Car Object");
        car.start();
        car.displayFuel();
        car.honk();
        car.stop();

        System.out.println();

        Bicycle bike = new Bicycle(20, 0.0, true);
        System.out.println(" Bicycle Object");
        bike.start();
        bike.displayFuel();
        bike.ringBell();
        bike.stop();
    }
}

class Vehicle {
    protected int speed;
    private double fuel;

    public Vehicle(int speed, double fuel) {
        this.speed = speed;
        this.fuel = fuel;
    }

    public void start() {
        System.out.println("The vehicle has started.");
    }

    public void stop() {
        System.out.println("The vehicle has stopped.");
    }

    public final void displayFuel() {
        System.out.println("Fuel level: " + fuel + " liters");
    }

    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }

    public double getFuel() {
        return fuel;
    }

    public void setFuel(double fuel) {
        this.fuel = fuel;
    }
}

class Car extends Vehicle {
    private int numberOfDoors;

    public Car(int speed, double fuel, int numberOfDoors) {
        super(speed, fuel);
        this.numberOfDoors = numberOfDoors;
    }

    
    public void start() {
        System.out.println("The car has started. Vroom Vroom!");
    }

    public void honk() {
        System.out.println("Beep Beep!");
    }

    public int getNumberOfDoors() {
        return numberOfDoors;
    }

    public void setNumberOfDoors(int numberOfDoors) {
        this.numberOfDoors = numberOfDoors;
    }
}

class Bicycle extends Vehicle {
    private boolean hasBell;

    public Bicycle(int speed, double fuel, boolean hasBell) {
        super(speed, fuel);
        this.hasBell = hasBell;
    }

    
    public void start() {
        System.out.println("The bicycle has started. Pedal away!");
    }

    public void ringBell() {
        if (hasBell) {
            System.out.println("Ring Ring!");
        } else {
            System.out.println("This bicycle has no bell.");
        }
    }

    public boolean getHasBell() {
        return hasBell;
    }

    public void setHasBell(boolean hasBell) {
        this.hasBell = hasBell;
    }
}
