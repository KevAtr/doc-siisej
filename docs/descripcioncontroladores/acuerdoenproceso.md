---
title: Acuerdo en Proceso
---

# Modulo de Descripción de Actions Acuerdo en Proceso
<br></br><br></br>

### Controlador General
<br></br>

| Función | Action |  Ubicación | Proceso |
|--------------|--------------|--------------|--------------|
| public function actionIndex | Index | controllers/acuerdosenprocesos/GeneralController.php | Manda a la pagina principal donde se visualiza una tabla con acuerdos |
<br></br><br></br>


### Controlador Pedientes
<br></br>

| Función | Action |  Ubicación | Proceso |
|--------------|--------------|--------------|--------------|
| public funtion actionObtenerAcuerdosPendientes | ObtenerAcuerdosPendientes | controllers/acuerdosenprocesos/PendientesController.php | Obtendra los acuerdos pendientes |
| public funtion actionGuardarAcuerdoPendiente | GuardarAcuerdoPendiente | controllers/acuerdosenprocesos/PendientesController.php | Guardara el acuerdo pendiente |
| public funtion actionModificarAcuerdoPendiente | ModificarAcuerdoPendiente | controllers/acuerdosenprocesos/PendientesController.php | Podra modificar el acuerdo pendiente |
<br></br><br></br>

### Controlador Realizados
<br></br>

| Función | Action |  Ubicación | Proceso |
|--------------|--------------|--------------|--------------|
| public funtion actionObtenerAcuerdosRealizados | ObtenerAcuerdosPendientes | controllers/acuerdosenprocesos/RealizadosController.php | Obtendra los acuerdos pendientes |
| public funtion actionObtenerAcuerdoRealizado | ObtenerAcuerdoRealizado | controllers/acuerdosenprocesos/RealizadosController.php | Obtendra el acuerdo pendiente |
