# iteca_boletin
<!DOCTYPE html>
<html lang="es">
<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>Boletín</title>

	<!-- Estilos -->
	<link href="https://fonts.googleapis.com/css?family=Roboto:400,300,100,500,700,900" rel="stylesheet">
	<link href="css/estilos.css" rel="stylesheet">
	



	<!-- Scripts locales -->
	<script src="js/jquery.min.js"></script>
	<script src="js/bootstrap.min.js"></script>
	<script src="js/formatter.min.js"></script>
	<script src="js/app.js"></script>
	<script src="js/boletin.js" defer></script>
</head>

<body class="login-container login-cover-mi-fondo">
	<div class="page-container">
		<div class="page-content">
			<div class="content-wrapper">
				<div class="content pb-20">
					<div class="panel panel-body login-form">
						<form class="form-validate" id="frm_boletin">
							<div class="text-center">
								<div class="icon-object border-slate-300 text-slate-300">
									<i class="icon-reading"></i>
								</div>
								<h5 class="content-group">Busca tu boletín <small class="display-block">CI y fecha de nacimiento</small></h5>
							</div>

							<div class="form-group has-feedback has-feedback-left">
								<label>Carnet de identidad:</label>
								<input type="text" class="form-control" placeholder="CI" name="ci" required>
								<div class="form-control-feedback">
									<i class="icon-user text-muted"></i>
								</div>
							</div>

							<div class="form-group has-feedback has-feedback-left">
								<label>Fecha de nacimiento:</label>
								<input type="text" class="form-control" placeholder="DD-MM-YYYY" name="dob" required>
								<div class="form-control-feedback">
									<i class="icon-calendar3 text-muted"></i>
								</div>
							</div>
						</form>

						<div class="form-group">
							<button type="button" onclick="enviar()" class="btn bg-pink-400 btn-block">
								Buscar <i class="icon-arrow-right14 position-right"></i>
							</button>
						</div>

						<div id="error"></div>

					</div>
				</div>
			</div>
		</div>
	</div>

	<!-- MODAL DE BOLETÍN -->
	<div id="modal_large" class="modal fade">
		<div class="modal-dialog modal-lg">
			<div class="modal-content">
				<div class="modal-header">
					<button type="button" class="close" data-dismiss="modal">&times;</button>
					<h5 class="modal-title">Boletín de notas</h5>
				</div>
				<div class="modal-body">
					<div id="boletin"></div>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-link" data-dismiss="modal">Cerrar</button>
				</div>
			</div>
		</div>
	</div>

	<!-- MODAL DE BIENVENIDA -->
	<div id="modal_bienvenida" class="modal fade">
		<div class="modal-dialog modal-sm">
			<div class="modal-content">
				<div class="modal-header bg-success">
					<h5 class="modal-title text-white">✅ Acceso correcto</h5>
					<button type="button" class="close text-white" data-dismiss="modal">&times;</button>
				</div>
				<div class="modal-body text-center">
					<p><strong>Bienvenido:</strong></p>
					<p>YUJRA GUEVARA NESTOR FERNANDO</p>
					<p>Su boletín ha sido encontrado correctamente.</p>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-success btn-sm" data-dismiss="modal">Continuar</button>
				</div>
			</div>
		</div>
	</div>
</body>
</html>

