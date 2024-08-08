---
title: Turnado
---

# Modulo de Descripción de Actions Turnado
<br></br><br></br>

### Controlador General
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionIndex | Index |  Manda a la pagina principal donde se visualizan los turnados | controllers/turnado/GeneralController.php |
<br></br><br></br>

### Controlador Reasignación Juzgado
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionIndex | Index | Visualización de los Juzgados para reasignar | controllers/turnado/ReasignacionJuzgadoController.php |
| public function actionBuscarExpedientePorCodigo | BuscarExpedientePorCodigo | Obtener los datos del expediente anterior y si no se encuentra se envia un mensaje  | controllers/turnado/ReasignacionJuzgadoController.php |
| public function actionReasignarExpediente | ReasignarExpediente | Valida los datos del expediente anterior, calcula los datos del nuevo expediente, guarda datos del expediente nuevo,<br></br> obtiene una lista de los datos guardados y se envian los datos guardados  | controllers/turnado/ReasignacionJuzgadoController.php |
| public function actionIndex | Index | Visualización de los Juzgados para reasignar | controllers/turnado/ReasignacionJuzgadoController.php |
| private function CalcularDatosNuevoExpediente | CalcularDatosNuevoExpediente |   | controllers/turnado/ReasignacionJuzgadoController.php |
| private function ObtenerExpedientePrincipales | ObtenerExpedientesPrincipales |   | controllers/turnado/ReasignacionJuzgadoController.php |
| private function ObtenerExpedienteAccesorios | ObtenerExpedienteAccesorios |   | controllers/turnado/ReasignacionJuzgadoController.php |
<br></br><br></br>

### Controlador Sin Codigo
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
|  |  |  | controllers/turnado/SinCodigoController.php |
<br></br><br></br>

### Trait Turnado Operaciones
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionConsultarExpedienteEnDemandas | ConsultarExpedienteEnDemandas | Guarda la demanda en una propiedad para actualizar su propiedad id_transferencia <br></br> en la tabla 'demandas' despues de insertar el registro en 'historial_demandas'. <br></br> Evalua si el usuario logueado tiene asignado el expediente para poderlo turnar <br></br> si no es asi. retornara falso y mostrara un mensaje. Posteriormente al insert se realiza <br></br> la actualización en la tabla demandas| controllers/turnado/traitTurnadoOperaciones.php |
| public function actionConsultarExpedientesEnDemandasAccesorios | ConsultarExpedientesEnDemandasAccesorios | Consulta la demanda y se mueve a historial, posteriormente al insert se realiza en tabla 'demandas_accesorios' | controllers/turnado/traitTurnadoOperaciones.php|
| public function actionInsertarMoviEnHistorialDemandas | InsertarMoviEnHistorialDemandas | Se inserta registro con los datos en historial_demandas, una vez insertado, actualizar la <br></br> bd el registro que contenga una consulta, insertar el registro de la transferencia Id o bien el número de transferencia ID <br></br> en tabla demandas | controllers/turnado/traitTurnadoOperaciones.php |
| public function actionInsertarMoviEnHistorialDemandasAccesorios  | InsertarMoviEnHistorialDemandasAccesorios  | Se inserta registro con los datos en historial_demandas_accesorios, | controllers/turnado/traitTurnadoOperaciones.php |
| public function actionCombinaTipoDeExpedienteyDatosdeExpediente | CombinaTipoDeExpedienteyDatosdeExpediente | Retorna datos del expediente y tipo | controllers/turnado/traitTurnadoOperaciones.php  |
| public function actionObtenerMovimientosTurnadosHistDemandas | ObtenerMovimientosTurnadosHistDemandas | Retorna historial de demandas, el movimiento por transferencia y <br></br> tipo de movimiento de la demanda  | controllers/turnado/traitTurnadoOperaciones.php  |
| public function actionObtenerMovimientosTurnadosHistDemandasAccesorios | ObtenerMovimientosTurnadosHistDemandasAccesorios | Retorna historial de demandas accesorios, el movimiento por transferencia y <br></br> tipo de movimiento de la demanda accesorios  | controllers/turnado/traitTurnadoOperaciones.php  |
| private function ActualizaUbicacionExpediente | ActualizaUbicacionExpediente | Ejecuta la actualización de la ubicación del expediente en la base de datos | controllers/turnado/traitTurnadoOperaciones.php |
<br></br><br></br>

### Controlador Tranferencias
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionObtenerCatalogosPuestosJuzgados | ObtenerCatalogosPuestosJuzgados | Obtiene el usuario logueado del juzgado | controllers/turnado/TransferenciaController.php |
| public function actionObtenerCatalogoMotivosTurnado | ObtenerCatalogoMotivosTurnado | Obtiene el tipo de usuario del juzgado para obtener el conjunto de acciones que puede <br></br> realizar el usuario (no se realizaria de momento el filtro) | controllers/turnado/TransferenciaController.php |
| public function actionGuardarTransferencia | GuardarTransferencia | Obtiene los datos del usuario al que se transfiere el expediente, crea dos nuevos registros de transferencias<br></br>min_max para optimizar la consulta que devuelve los expedientesde la transferencia| controllers/turnado/TransferenciaController.php |
| private function ObtenerDatosUsuarioEnvia | ObtenerDatosUsuarioEnvia | Retorna los datos del usuario que envia | controllers/turnado/TransferenciaController.php |
| private function ObtenerDatosUsuarioRecibe | ObtenerDatosUsuarioRecibe | Retorna los datos del usuario que recibe | controllers/turnado/TransferenciaController.php |
| private function ObtenerDatosAdicionalesTransferencia | ObtenerDatosAdicionalesTransferencia | Retorna datos de la transferecnia  | controllers/turnado/TransferenciaController.php |
| private function CrearTransferenciasMinMax | CrearTransferenciasMinMax | Crea la transferencia  | controllers/turnado/TransferenciaController.php |

<br></br><br></br>

### Controlador Turnado
<br></br>

| Función | Action |  Proceso | Ubicación |
|--------------|--------------|--------------|--------------|
| public function actionTurnadoExpedientes | TurnadoExpedientes | Obtiene datos de la transferencia y retorna un mensaje de 'usuario no autorizado', validar si la transferencia <br></br> aun esta pendiente y si la transferencia coincide con la fecha actual o con dias antes | controllers/turnado/TurnadoController.php |
| public function actionInsertarExpedientesTurnado | InsertarTurnadoExpedientes | Realiza una consulta verificando si el usuario logueado y el ID de trasnferencia coincide,<br></br>de ser lo contrario devuelve un mensaje de no autorizado,existe en tabla demandas <br></br> inserta: historial_demandas, devolviendo el id de la Demanda (Expediente), existe en <br></br> tabla demandas_accesorios inserta:historial_demandas_accesorios., devolviendo el id de<br></br> la Demanda_accesorios (expediente_accesorio) y si no encuntra un codigo de barras en alguna<br></br> de las tablas anteriores se envia un mensaje de error, señalado que no <br></br> encuentra el codigo de barras.| controllers/turnado/TurnadoController.php |
| public function actionObtenerDemandasTurnadas | ObtenerDemandasTurnadas | Obtiene demandas turnadas por id_usuario | controllers/turnado/TurnadoController.php |
| public function actionObtenerDemandasAccesoriosTurnadas | ObtenerDemandasAccesoriosTurnadas | Obtiene demandas accesorios turnadas | controllers/turnado/TurnadoController.php |
| public function actionGuardarExpedienteTurnado | GuardarExpedienteTurnado | obtener el codigo de barras, validarlo y limpiarlo, obtener el ID de la transferencia y validarlo<br></br> obtener datos de transferencia, busca datos de la demanda por codigo de barras <br></br> guarda y actualiza el movimiento de la demanda, genera el dato de ususario_asignado_id,<br></br> actualizar la tabla demandas_accesorio para contener el campo de juzgado_id, <br></br> que nos permita tener un inventario de los expedientes accesorios del juzgado. Ademas que<br></br>esto mejoraria la busqueda de expedientes accesorios dentro de las consultas. <br></br>Ademas de agregar el dato del usuario_asignado_id. Se busca datos de la demanda_accesorios<br></br> por código de barras y guarda la demanda en la transferencia, de lo contrario manda mensaje de error. | controllers/turnado/TurnadoController.php |
| public function actionFinalizarTurnadoDeExpediente | FinalizarTurnadoDeExpediente | Obtiene el ID de la transferencia y validarlo, finaliza la transferencia y envia mensaje de exito| controllers/turnado/TurnadoController.php |
| private function ObtenerExpedientePorCodigo | ObtenerExpedientePorCodigo | Se obtiene el expediente de la demanda por código de barras | controllers/turnado/TurnadoController.php |
| private function GuardarMovimientoHistorialDemandas | GuardarMovimientoHistorialDemandas | Guardar los datos del movimiento de la demanda en el historial demandas y actualiza <br></br>la transferencia en la demanda | controllers/turnado/TurnadoController.php |
| private function ObtenerExpedienteAccesorioPorCodigo | ObtenerExpedienteAccesorioPorCodigo | Busca los datos de la demanda_accesorios por codigo de barras| controllers/turnado/TurnadoController.php |
| private function GuadarMovimientosHistorialDemandasAccesorios | GuadarMovimientosHistorialDemandasAccesorios |  Guardar los datos del movimiento de la demanda_accesorios en el <br></br> historial_demandas_accesorios  | controllers/turnado/TurnadoController.php |
| private function ValidacionTransferencia | ValidacionTransferencia | Valida que la transferencia sea exitosa, validar el ID de turnado que el usuario logueado sea el mismo que <br></br>el usuario envia, validar que la transferencia no tenga el flag escaneo_finalizado y verifica que no exista errores | controllers/turnado/TurnadoController.php |
| private function ObtenerJuzgadoDelUsuario | ObtenerJuzgadoDelUsuario |  | controllers/turnado/TurnadoController.php |
<br></br><br></br>