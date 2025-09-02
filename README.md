import java.util.Scanner;

public class Vehiculo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Solicitar datos
        System.out.print("Ingrese la marca: ");
        String marca = sc.nextLine();

        System.out.print("Ingrese el modelo: ");
        String modelo = sc.nextLine();

        System.out.print("Ingrese la cilindrada: ");
        String cilindrada = sc.nextLine();

        System.out.print("Ingrese el tipo de combustible: ");
        String combustible = sc.nextLine();

        System.out.print("Ingrese la capacidad en pasajeros: ");
        int pasajeros = sc.nextInt();

        // Mostrar datos ingresados
        System.out.println("\nLa marca que ha ingresado es: " + marca);
        System.out.println("El modelo que ha ingresado es: " + modelo);
        System.out.println("La cilindrada que ha ingresado es: " + cilindrada);
        System.out.println("El tipo de combustible es: " + combustible);
        System.out.println("Tiene una capacidad de " + pasajeros + " pasajeros.");
    }
}
