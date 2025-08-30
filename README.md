import java.util.Scanner;
import java.util.InputMismatchException;

public class AplicacionDespacho {

    // Método para leer texto
    private static String leerTexto(Scanner sc, String mensaje) {
        System.out.print(mensaje);
        return sc.nextLine().trim();
    }

    // Método para leer números enteros con validación
    private static int leerEntero(Scanner sc, String mensaje) {
        int numero = -1;
        boolean valido = false;
        while (!valido) {
            System.out.print(mensaje);
            try {
                numero = sc.nextInt();
                sc.nextLine(); // limpiar buffer
                valido = true;
            } catch (InputMismatchException e) {
                System.out.println("Error: Ingrese un número válido.");
                sc.nextLine(); // descarta entrada inválida
            }
        }
        return numero;
    }

    // Método que calcula el costo de despacho
    private static int calcularDespacho(int montoCompra, int distancia) {
        if (montoCompra >= 50000 && distancia <= 20) {
            return 0;
        } else if (montoCompra >= 25000 && montoCompra <= 49999) {
            return distancia * 150;
        } else {
            return distancia * 300;
        }
    }

    // Programa principal
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Entrada de datos del vehículo
        String marca = leerTexto(sc, "Ingrese la marca: ");
        String modelo = leerTexto(sc, "Ingrese el modelo: ");
        String cilindrada = leerTexto(sc, "Ingrese la cilindrada: ");
        String combustible = leerTexto(sc, "Ingrese el tipo de combustible: ");
        int pasajeros = leerEntero(sc, "Ingrese la capacidad en pasajeros: ");

        // Entrada de datos de compra
        int montoCompra = leerEntero(sc, "Ingrese el monto de la compra: ");
        int distancia = leerEntero(sc, "Ingrese la distancia en km para el despacho: ");

        // Cálculo del despacho
        int costoDespacho = calcularDespacho(montoCompra, distancia);

        // Salida
        System.out.println("\n=== RESUMEN DE DATOS ===");
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Cilindrada: " + cilindrada);
        System.out.println("Combustible: " + combustible);
        System.out.println("Capacidad: " + pasajeros + " pasajeros");
        System.out.println("Monto de la compra: $" + montoCompra);
        System.out.println("Distancia: " + distancia + " km");
        System.out.println("Costo de despacho: $" + costoDespacho);

        sc.close(); // cerramos el scanner
    }
}
