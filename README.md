# spam-guard-api
API Spam Guard

## Component diagram

```mermaid
graph TD
    subgraph Frontend móvil
        A[Flutter App (Android/iOS)]
    end
    subgraph Backend
        B(Golang API Server)
        D[GenIA API]
        E[Spam Numbers Database]
    end
    F[Open Source/OSINT Spam Phone DB]
    G[User Data Store (Opcional)]

    A -- Solicita verificación de llamada --> B
    B -- Consulta identificación y reputación --> E
    B -- Llama a procesos IA externos --> D
    E -- Sincroniza y enriquece --> F
    B -- Persiste reportes y nuevas etiquetas --> G
    E -- Actualización periódica <-- F
```
