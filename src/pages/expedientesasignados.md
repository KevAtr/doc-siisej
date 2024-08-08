---
title: Siisej 
---

# Modulo de Descripción de Actions Expedientes en Proceso
<br></br><br></br>

### Controlador General
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionIndex | Index |  Manda a la pagina principal donde se visualiza una tabla los expedientes | controllers/expedientesasignados/GeneralController.php |
<br></br><br></br>


### Controlador Inventario
<br></br>

| Función | Action | Proceso  | Ubicación |
|--------------|--------------|--------------|--------------|
| public funtion actionObtenerExpedientesAsignados | ObtenerExpedientesAsignados  | Obtiene el id del usuario logueado, obtiene las demandas asignadas al usuario logueado  | controllers/expedientesasignados/InventarioController.php |
| public funtion actionObtenerExpedientesTurnadosRecientemente | ObtenerExpedientesTurnadosRecientemente  | Obtiene todos los expedientes en turno que tiene asignado el usuario  | controllers/expedientesasignados/InventarioController.php |
<br></br><br></br>


