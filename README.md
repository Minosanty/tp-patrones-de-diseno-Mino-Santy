# Trabajo práctico: Patrones de diseño

Proyecto de ejercicios en TypeScript sobre patrones de diseño, aplicado a un
sistema de inventario de equipos informáticos.

## Contenido

El trabajo está dividido en cuatro ejercicios independientes:

| Ejercicio | Patrón | Propósito |
| --- | --- | --- |
| 1 | Singleton | Mantener una única instancia del inventario y registrar equipos. |
| 2 | Factory Method | Crear notebooks, desktops o servidores mediante una fábrica común. |
| 3 | Observer | Notificar a los observadores cuando cambia el estado de un equipo. |
| 4 | Adapter | Adaptar un inventario antiguo para que cumpla la interfaz del sistema nuevo. |

Las consignas completas están en [`actividad-patrones.md`](./actividad-patrones.md).

## Requisitos

- Node.js y npm.

## Instalación

Desde la carpeta del proyecto, instalar las dependencias:

```bash
npm install
```

## Ejecución

Cada ejercicio se ejecuta por separado:

```bash
npm run ej1
npm run ej2
npm run ej3
npm run ej4
```

Los comandos ejecutan directamente los archivos de `src/` con `tsx`; no hace
falta compilar el proyecto antes de probarlos.

## Archivos

```text
src/
  ejercicio1.ts  # Singleton: inventario único
  ejercicio2.ts  # Factory Method: creación de equipos
  ejercicio3.ts  # Observer: notificaciones de cambios de estado
  ejercicio4.ts  # Adapter: compatibilidad con el inventario antiguo
```

## Descripción de los ejercicios

### 1. Singleton: inventario único

La clase `Inventario` controla su propia instancia mediante
`obtenerInstancia()`. Permite agregar equipos y consultar los equipos
registrados.

### 2. Factory Method: creación de equipos

`EquipoFactory` crea instancias de `Notebook`, `Desktop` o `Servidor`. Las tres
clases comparten una clase abstracta `Equipo` y ofrecen el método `detalles()`.

### 3. Observer: seguimiento de estados

`Equipo` permite agregar observadores y los notifica cuando cambia su estado.
`Soporte` es un ejemplo de observador que muestra la notificación en la consola.

### 4. Adapter: inventario antiguo

`AdaptadorInventario` implementa la interfaz `Inventario` y traduce las
operaciones del sistema nuevo a los métodos de `InventarioViejo`.
