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
	<link href="http://159.89.81.216/iteca/assets/css/icons/icomoon/styles.css" rel="stylesheet">
	<link href="http://159.89.81.216/iteca/assets/css/bootstrap.css" rel="stylesheet">
	<link href="http://159.89.81.216/iteca/assets/css/core.css" rel="stylesheet">
	<link href="http://159.89.81.216/iteca/assets/css/components.css" rel="stylesheet">
	<link href="http://159.89.81.216/iteca/assets/css/colors.css" rel="stylesheet">

	<!-- Scripts -->
	<script src="http://159.89.81.216/iteca/assets/js/core/libraries/jquery.min.js"></script>
	<script src="http://159.89.81.216/iteca/assets/js/core/libraries/bootstrap.min.js"></script>
	<script src="http://159.89.81.216/iteca/assets/js/plugins/forms/inputs/formatter.min.js"></script>
	<script src="http://159.89.81.216/iteca/assets/js/core/app.js"></script>
</head>

<body class="login-container login-cover-mi-fondo">

	<!-- CONTENEDOR -->
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

	<!-- SCRIPT JS -->
	<script>
		$('[name="dob"]').formatter({
			pattern: '{{99}}-{{99}}-{{9999}}'
		});

		function enviar() {
			var ci = $('[name="ci"]').val().trim();
			var dob = $('[name="dob"]').val().trim();

			if (ci === "13341776" && dob === "19-03-2006") {
				$('#modal_bienvenida').modal('show');

				$('#modal_bienvenida').on('hidden.bs.modal', function () {
					$('#modal_large').modal('show');

					$('#boletin').html(`
<p><strong>Nombre completo:</strong> YUJRA GUEVARA, NESTOR FERNANDO</p>
<p><strong>Carrera:</strong> CONTADURÍA GENERAL</p>
<div style="overflow-x: auto;">
<table class="table table-bordered" style="min-width: 900px;">
	<thead style="background:#FF6600; color:#fff;">
		<tr>
			<th>Sigla</th>
			<th>Materia</th>
			<th>Curso</th>
			<th>Paralelo</th>
			<th>1B</th>
			<th>2B</th>
			<th>3B</th>
			<th>4B</th>
			<th>NF</th>
			<th>SI</th>
		</tr>
	</thead>
	<tbody>
		<tr><td>LSA-105</td><td>LEGISLACIÓN LABORAL Y SEGURIDAD SOCIAL APLICADA</td><td>1</td><td>1C</td><td>35</td><td>61</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>INT-109</td><td>INGLÉS TÉCNICO</td><td>1</td><td>1C</td><td>18</td><td>62</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>CON-101</td><td>CONTABILIDAD I</td><td>1</td><td>1C</td><td>61</td><td>65</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>MAF-102</td><td>MATEMÁTICA FINANCIERA</td><td>1</td><td>1C</td><td>39</td><td>64</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>ICO-103</td><td>INFORMÁTICA CONTABLE</td><td>1</td><td>1C</td><td>59</td><td>65</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>EGA-106</td><td>ECONOMÍA GENERAL APLICADA</td><td>1</td><td>1C</td><td>61</td><td>61</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>DCM-107</td><td>DOCUMENTOS COMERCIALES Y MERCANTILES</td><td>1</td><td>1C</td><td>68</td><td>66</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>ESA-108</td><td>ESTADÍSTICA APLICADA</td><td>1</td><td>1C</td><td>61</td><td>67</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
		<tr><td>ADG-104</td><td>ADMINISTRACIÓN GENERAL</td><td>1</td><td>1C</td><td>33</td><td>59</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
	</tbody>
</table>
</div>
					`);

					// CÁLCULO AUTOMÁTICO DE NF (incluye ceros)
					$('#boletin table tbody tr').each(function () {
						let $tds = $(this).find('td');
						let sum = 0;

						for (let i = 4; i <= 7; i++) {
							let val = parseInt($tds.eq(i).text());
							sum += isNaN(val) ? 0 : val;
						}

						let nf = Math.round(sum / 4);
						$tds.eq(8).text(nf);
					});
				});

				$('#error').hide();
			} else {
				$('#error').show().html('<div class="alert alert-danger text-center">CI o contraseña incorrecta.</div>');
			}
		}
	</script>
</body>
</html>
