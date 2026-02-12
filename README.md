```mermaid
classDiagram

class Calculadora {
    +sumar(a: double, b: double) double
    +restar(a: double, b: double) double
    +multiplicar(a: double, b: double) double
    +dividir(a: double, b: double) double
}

class GestorOperaciones {
    -calculadora: Calculadora
    +GestorOperaciones(calculadora: Calculadora)
    +ejecutarOperacion(simbolo: String, a: double, b: double) double
}

class EntradaDatos {
    +pedirNumero() double
    +pedirOperacion() String
    +validarNumero(valor: String) boolean
}

class SalidaDatos {
    +mostrarResultado(resultado: double) void
    +mostrarError(mensaje: String) void
}

class Main {
    +main(args: String[]) void
}

Main --> EntradaDatos : usa
Main --> SalidaDatos : usa
Main --> GestorOperaciones : usa

GestorOperaciones --> Calculadora : delega
