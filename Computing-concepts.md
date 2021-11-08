## ACID:

-Atomicidad:Poder garantizar que todas las las transacciones sucedan, en un conjunto o ninguna. Evita ejecuciones parciales.
-Consistencia:Garantiza a que los datos no quedaran en un estado inconsistente.
-Isolation:Signfica que una transacción no puede ser leida ni manipulada por otra.
-Durability:Significa que la transaccion es completa y sus resultados seran persistidos.

## Concurrencia:
Se refiere a la capacidad de un CPU de ejecutar diversos procesos al mismo tiempo, estos procesos son independientes.

## Paralelismo:
Se refiere a poder ejecutar un proceso pero separarlo en partes se basa en **divide y venceras** que se ejecuta cada una a la vez aqui se relaciona con concurrencia.

### Emergencias - metricas
- MTBF (Mean time between fail):
Esta métrica se refiere al tiempo promedio transcurrido entre una falla y la siguiente. Estas fallas deben estar relacionadas con factores de mantenimiento directo.

- MTTR (Mean time to resolve):
El MTTR se calcula utilizando el tiempo promedio que lleva realizar una reparación después de que se haya producido la falla.
