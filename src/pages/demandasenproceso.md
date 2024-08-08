---
title: Siisej 
---

# Modulo de Descripción de Actions Demandas en Proceso
<br></br><br></br>

### Controlador General
<br></br>

|  Función  | Action  | Proceso | Ubicación |
|--------------|--------------|-------------|--------------|
|  public function actionIndex  | Index | Manda a la pagina principal donde se visualiza una tabla con las demandas | controllers/demandasenprocesos/GeneralController.php |
<br></br><br></br>


### Controlador Pedientes
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|-----------|--------------|
| public funtion actionObtenerDemandasPendientes | ObtenerDemandasPendientes | Obtendra las demandas pendientes por el filtro pagina actual, <br></br> nombre y valor al mismo tiempo si esta en estado pendiente o no | controllers/demandasenprocesos/PendientesController.php |
| public funtion actionObtenerArchivoDemandaPendiente | ObtenerArchivoDemandaPendiente | Manda a traer la demanda pendiente en formato PDF comprobando si esta <br></br> existe, devuelve el archivo mientras lee y envia el contenido del archivo |controllers/demandasenprocesos/PendientesController.php | 
|public function actionGuardarRadicacionDemanda|GuardarRadicacionDemanda|Se guardara la demanda con su descripción, su id y su archivo de radicación, obtendra los datos de la demanda, el acuerdo de radicación guardara los siguientes datos: <br></br> tipo de expediente, demanda, id_juzgado, nombre del juzgado, id_materia, nombre de la materia, nombre del acuerdo pero dentro de este se añade juzgado_id, folio_anual <br></br>y anio en pdf, contenido de acuerdo, fecha y hora de acuerdo y ruta de acuerdo.Posteriormente se guarda, se comprueba si la ruta existe y se mueve el archivo a la ruta,<br></br> se actualiza la demanda en proceso y se modifica el estado de radicación.|controllers/demandasenprocesos/PendientesController.php|


<br></br><br></br>

### Controlador Radicadas
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
|  public function actionObtenerDemandasRadicadas | ObtenerDemandasRadicadas | Se obtendra la demanda radicada por filtros, se tendra el juzgado de la autoridad <br></br>logueada mostrando los estados generales de la demanda "Radicada"   | controllers/demandasenprocesos/RadicadasController.php|
|  public function actionObtenerArchivoDemandaRadicada | ObtenerArchivoDemandaRadicada | Se obtendra la ruta del archivo, se reconstruye la ruta y se comprueba si el <br></br> archivo existe, devuelve el archivo mientras lee y envia el contenido del archivo   | controllers/demandasenprocesos/RadicadasController.php|
|  public function actionObtenerArchivoAcuerdoRadicacion | ObtenerArchivoAcuerdoRadicacion | Se obtendra el id de la demanda y se tendra el acuerdo de radicación se reconstruye la ruta <br></br>absoluta, si existe el archivo, devuelve el archivo mientras lee y envia el contenido del archivo  | controllers/demandasenprocesos/RadicadasController.php|


