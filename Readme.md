# Roll-a-Ball – Personalización del tablero

Proyecto de Unity basado en Roll-a-Ball con un escenario personalizado, elevaciones, obstáculos y enemigos que persiguen al jugador.

## ¿Qué se implementó?

- **Terreno personalizado:** se añadieron rampas y zonas elevadas para aumentar dificultad y crear rutas de escape.
- **Recolectables:** los objetos `PickUp` giran continuamente y deben ser recolectados para ganar.
- **Condición de victoria:** al recolectar **12 pickups**, se muestra mensaje de victoria y se elimina el enemigo.
- **Condición de derrota:** al colisionar con un enemigo, el jugador se destruye y aparece el texto **"You Lose!"**.
- **IA enemiga con NavMesh:** el enemigo persigue al jugador en todo momento y aumenta su velocidad al acercarse a 10 unidades, depués vuelve a mantener su velocidad normal si el player vuelve a alejarse.
- **Cámara de seguimiento:** la cámara mantiene un `offset` fijo respecto al jugador.

## Estructura relevante en Assets

- `Assets/Scenes/MainGame.unity`: escena principal del juego.
- `Assets/Scripts/PlayerController.cs`: movimiento, recolección, UI y estados de victoria/derrota.
- `Assets/Scripts/EnemyMovement.cs`: persecución con `NavMeshAgent` y cambio dinámico de velocidad.
- `Assets/Scripts/CamaraController.cs`: seguimiento de cámara.
- `Assets/Scripts/rotate.cs`: rotación de pickups.
- `Assets/Prefabs/Enemy.prefab`, `PickUp.prefab`, `DynamicBox.prefab`: prefabs principales.
- `Assets/Materials/`: materiales usados para jugador, enemigo, pickups y entorno.

## Cómo jugar

1. Abre `MainGame.unity`.
2. Ejecuta la escena desde Unity.
3. Mueve la esfera con los controles configurados en el Input System.
4. Recolecta los 12 pickups evitando el contacto con los enemigos.

## Notas técnicas

- El proyecto usa el **Input System** (`InputSystem_Actions.inputactions`).
- El seguimiento de enemigos requiere superficie de navegación configurada para que el `NavMeshAgent` recorra elevaciones y obstáculos.