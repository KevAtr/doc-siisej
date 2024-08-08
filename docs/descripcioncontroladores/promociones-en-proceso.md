---
title: Promociones en Proceso 
---

# Modulo de Descripción de Actions Promociones en Proceso
<br></br><br></br>

### Controlador General
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionIndex | Index |  Manda a la pagina principal donde se visualiza las promociones | controllers/notificacionesenproceso/GeneralController.php |
<br></br><br></br>

### Controlador Acordadas
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionObtenerPromocionesAcordadas | ObtenerPromocionesAcordadas | Obtiene las promociones pendientes y de igual manera por filtros | controllers/promocionesenproceso/AcordadasController.php |
| public function actionObtenerArchivoPromocionAcordada | ObtenerArchivoPromocionAcordada | Se manda a traer la promoción, comprueba si existe, genera la ruta del archivo y la evalua,<br></br> genera una respuesta finalizando leyendo el archivo y envia el contenido | controllers/promocionesenproceso/AcordadasController.php |
| public function actionObtenerArchivoAcuerdoPromocion | ObtenerArchivoAcuerdoPromocion | Comprueba si el archivo existe, genera la ruta del archivo, evaulua si existe el archivo <br></br> genera una respuesta y finaliza leyendo el archivo y envia el contenido | controllers/promocionesenproceso/AcordadasController.php |
<br></br><br></br>


### Controlador Pendientes
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionObtenerPromocionesPendientes | ObtenerPromocionesPendientes | Se obtiene la promoción pendiente de igual manera por filtros, su estado general de la promoción<br></br> | controllers/promocionespendientes/PendientesController.php |
| public function actionObtenerArchivoPromocionPendiente | ObtenerArchivoPromocionPendiente | Se manda a traer la promoción, comprueba si existe, genera la ruta del archivo y la evalua,<br></br> genera una respuesta finalizando leyendo el archivo y envia el contenido | controllers/promocionespendientes/PendientesController.php |
| public function actionGuardarAcuerdoPromocionPendiente | GuardarAcuerdoPromocionPendiente | Recibe los datos del acuerdo, los datos de la promoción, guarda el acuerdo por sus datos <br></br> guarda el archivo de acuerdo, comprueba si la ruta existe, mueve el archivo a la ruta, actualiza <br></br>la promoción en proceso| controllers/promocionespendientes/PendientesController.php |
<br></br><br></br>

