$("#run").click(() => tryCatch(run));
async function run() {
  await Excel.run(async (context) => {
    const sheet = context.workbook.worksheets.getActiveWorksheet();
    var celdaAF = sheet.getRange("AF1");
    celdaAF.load("values");
    await context.sync();
    var fila = celdaAF.values;
    var celda = sheet.getRange("a" + fila);
    celda.values = document.getElementById("folio").value;
    celda.getOffsetRange(0, 1).values = document.getElementById("tipodocumento").value;
    celda.getOffsetRange(0, 2).values = document.getElementById("documento").value;
    celda.getOffsetRange(0, 3).values = document.getElementById("fecha").value;
    celda.getOffsetRange(0, 4).values = document.getElementById("fecha").value;
    celda.getOffsetRange(0, 5).values = document.getElementById("organismoconcentra").value;
    celda.getOffsetRange(0, 6).values = document.getElementById("catalogo").value;
    celda.getOffsetRange(0, 7).values = document.getElementById("inventario").value;
    celda.getOffsetRange(0, 8).values = document.getElementById("categoria").value;
    celda.getOffsetRange(0, 9).values = document.getElementById("modelo").value;
    celda.getOffsetRange(0, 10).values = document.getElementById("serie").value;
    celda.getOffsetRange(0, 11).values = document.getElementById("marca").value;
    celda.getOffsetRange(0, 12).values = document.getElementById("diagnostico").value;
    celda.getOffsetRange(0, 13).values = document.getElementById("obge").value;
    celda.getOffsetRange(0, 24).values = document.getElementById("bien").value;
    celda.getOffsetRange(0, 25).values = document.getElementById("mat").value;
    celda.getOffsetRange(0, 26).values = document.getElementById("telefono").value;
    celda.getOffsetRange(0, 27).values = document.getElementById("grados").value;
    celda.getOffsetRange(0, 28).values = document.getElementById("nombrequienrecibe").value;
    celda.getOffsetRange(0, 29).values = document.getElementById("matricula4").value;

    celda.getOffsetRange(0, 29).values = document.getElementById("fecha").value;

    var d = document.getElementById("grado");
    var grado = d.options[d.selectedIndex].value;
    celda.getOffsetRange(0, 14).values = grado;

    var f = document.getElementById("verifico");
    var verifico = f.options[f.selectedIndex].value;
    celda.getOffsetRange(0, 15).values = verifico;

    var g = document.getElementById("matricula");
    var matricula = g.options[g.selectedIndex].value;
    celda.getOffsetRange(0, 16).values = matricula;

    var i = document.getElementById("gra");
    var gra = i.options[i.selectedIndex].value;
    celda.getOffsetRange(0, 17).values = gra;

    var h = document.getElementById("digtamenes");
    var digtamenes = h.options[h.selectedIndex].value;
    celda.getOffsetRange(0, 18).values = digtamenes;

    var j = document.getElementById("matricula2");
    var matricula2 = j.options[j.selectedIndex].value;
    celda.getOffsetRange(0, 19).values = matricula2;

    var e = document.getElementById("grad");
    var grad = e.options[e.selectedIndex].value;
    celda.getOffsetRange(0, 20).values = grad;

    document.getElementById("folio").value = "";
    document.getElementById("tipodocumento").value = "";
    document.getElementById("documento").value = "";
    document.getElementById("fecha").value = "";
    document.getElementById("organismoconcentra").value = "";
    document.getElementById("catalogo").value = "";
    document.getElementById("inventario").value = "";
    document.getElementById("categoria").value = "";
    document.getElementById("modelo").value = "";
    document.getElementById("serie").value = "";
    document.getElementById("marca").value = "";
    document.getElementById("diagnostico").value = "";
    document.getElementById("obge").value = "";
    document.getElementById("bien").value = "";
    document.getElementById("mat").value = "";
    document.getElementById("telefono").value = "";
    document.getElementById("grados").value = "";
    document.getElementById("nombrequienrecibe").value = "";
    document.getElementById("matricula4").value = "";

    await context.sync();
  });
}

$("#play").click(() => tryCatch(play));
async function play() {
  await Excel.run(async (context) => {
    const sheet = context.workbook.worksheets.getActiveWorksheet();
    var celdaAH = sheet.getRange("AH1");
    celdaAH.load("values");
    await context.sync();
    var fila = celdaAH.values;
    var celda = sheet.getRange("a" + fila);
    celda.values = document.getElementById("folio").value;

    var l = document.getElementById("autorizo");
    var autorizo = l.options[l.selectedIndex].value;
    celda.getOffsetRange(0, 21).values = autorizo;

    var m = document.getElementById("matricula3");
    var matricula3 = m.options[m.selectedIndex].value;
    celda.getOffsetRange(0, 22).values = matricula3;

    var n = document.getElementById("gr");
    var gr = n.options[n.selectedIndex].value;
    celda.getOffsetRange(0, 23).values = gr;

    await context.sync();
  });
}

$("#buscar-1").click(() => tryCatch(buscar - 1));
async function run() {
  await Excel.run(async (context) => {
    await context.sync();
  });
}

/** Default helper for invoking an action and handling errors. */
async function tryCatch(callback) {
  try {
    await callback();
  } catch (error) {
    // Note: In a production add-in, you'd want to notify the user through your add-in's UI.
    console.error(error);
  }
}


<div class="login-wrap">
	<div class="login-html">
		<input id="tab-1" type="radio" name="tab" class="sign-in" checked><label for="tab-1" class="tab">RECEPCION DE EQUIPO</label>
		<input id="tab-2" type="radio" name="tab" class="sign-up"><label for="tab-2" class="tab">DICTAMEN TECNICO</label>

		<div class="login-form">

			<div class="sign-in-htm">

				<div class="hr"></div>

				<div class="fondo">
					<label for="buscar" class="label"> BUSCAR </label>
					<input type="text" placeholder="" id="folio" class="sombra">
		</div>
					<br></br>

					<div class="fondo">
						<a href="#" id="buscar-1" class="sombra-2" autocomplete="off"><span>Aceptar</span>
						</a>
					</div>
					<!------------------------------------------------------->

					<br></br>
					<div class="fondo">
						<label for="folio" class="label"> No. DE FOLIO </label>
						<input type="text" placeholder="" id="folio" class="sombra">
		</div>

						<div class="fondo">
							<label for="tipodocumento" class="label"> TIPO DE DOCUMENTO </label>
							<input type="text" placeholder="" id="tipodocumento" class="sombra">
    </div>

							<div class="fondo">
								<label for="documento" class="label">No. DE DOCUMENTO </label>
								<input type="text" placeholder="" id="documento" class="sombra">
		</div>

								<div class="fondo">
									<label for="fecha" class="label">FECHA DE DOCUMENTO </label>
									<input type="date" placeholder="" id="fecha" class="sombra">
		</div>

									<div class="fondo">
										<label for="fecha" class="label">FECHA DE REGISTRO </label>
										<input type="date" placeholder="" id="fecha" class="sombra">
			</div>

										<div class="fondo">
											<label for="organismoconcentra" class="label">ORGANISMO QUE CONCENTRA </label>
											<input type="text" placeholder="" id="organismoconcentra" class="sombra">
		</div>

											<div class="fondo">
												<label for="catalogo" class="label">No. DE CATALOGO </label>
												<input type="text" placeholder="" id="catalogo" class="sombra">
		</div>

												<div class="fondo">
													<label for="inventario" class="label">No. DE CATALOGO </label>
													<input type="text" placeholder="" id="inventario" class="sombra">
		</div>

													<div class="fondo">
														<label for="categoria" class="label">No. DE INVENTARIO </label>
														<input type="text" placeholder="" id="categoria" class="sombra">
		</div>

														<div class="fondo">
															<label for="modelo" class="label">MODELO </label>
															<input type="text" placeholder="" id="modelo" class="sombra">
		</div>

															<div class="fondo">
																<label for="serie" class="label">SERIE </label>
																<input type="text" placeholder="" id="serie" class="sombra">
		</div>

																<div class="fondo">
																	<label for="marca" class="label">MARCA </label>
																	<input type="text" placeholder="" id="marca" class="sombra">
		</div>

																	<div class="fondo">
																		<label for="diagnostico" class="label">DIAGNOSTICO </label>
																		<input type="text" placeholder="" id="diagnostico" class="sombra">
		</div>

																		<div class="fondo">
																			<label for="obge" class="label">OBSERVACIONES GENERALES </label>
																			<input type="text" placeholder="" id="obge" class="sombra">
		</div>


																			<br> </br>


																			<div class="fondo">
																				<a href="#" id="play"
																					class="sombra-3"><span>REGISTRAR</span>
																				</a>





																			</div>
																		</div>



																		<!--  -----------------------------------------------------------------------------------------------        -->



																		<div class="sign-up-htm">
																			<div class="hr"></div>

																			<div class="fondo">
																				<label for="grado" class="label">GRADO </label>
																				<select id="grado">
				<option	value="Mayor">Mayor
				<option value="Capitan">Capitan
				<option value="Subteniente">Subteniente
				<option value="Teniente">Subteniente
				<option value="Sargento I">SargentoI
				<option value="Sargento II">SargentoI
				<option value="Cabo">Cabo
				<option value="Soldado">Soldado
			</select>
																			</div>

																			<div class="fondo">
																				<label for="verifico" class="label">NOMBRE QUIEN REPARO</label>
																				<select id="verifico">
						<option value="LUIS ERNESTO PADILLA GARCIA">LUIS ERNESTO PADILLA GARCIA
						<option value="ADRIANA HERNANDEZ VAZQUEZ">SBTTE INFTCA ADRIANA HERNANDEZ VAZQUEZ
						<option value="JUDITH PALOMEC ANTONIO">JUDITH PALOMEC ANTONIO
						<option value="ANA KAREN PANTALEON CASTREJON">ANA KAREN PANTALEON CASTREJON
						<option value="FRANCISCO JAVIER AMADOR RAMÍREZ">FRANCISCO JAVIER AMADOR RAMÍREZ
						<option value="JHOVAN ORTEGA MANZANO">JHOVAN ORTEGA MANZANO
						<option value="ALEJANDRO CERNA VARGUEZ">ALEJANDRO CERNA VARGUEZ.
						<option value="LORENZO ANTONIO SANCHEZ ARANDA">LORENZO ANTONIO SANCHEZ ARANDA
						<option value="JORDY EMANUEL GUILLEN ROSARIO">JORDY EMANUEL GUILLEN ROSARIO
						<option value="VICTORIA DE JESUS FIGUEROA MORALES">VICTORIA DE JESUS FIGUEROA MORALES
						<option value="ROSALBA SANCHEZ APOLINAR">ROSALBA SANCHEZ APOLINAR
						<option value="ALEXANDER JOVANNI GONZALEZ DIAZ">ALEXANDER JOVANNI GONZALEZ DIAZ
						<option value="ETHAN HORACIO GARDUÑO VÉLEZ">ETHAN HORACIO GARDUÑO VÉLEZ
						<option value="ALEXIS SANTIAGO MENDOZA">ALEXIS SANTIAGO MENDOZA
						<option value="KEIN JESUS BARRERA DEL PILAR">KEIN JESUS BARRERA DEL PILAR

				</select>

																			</div>


																			<div class="fondo">
																				<label for="matricula" class="label">MATRICULA</label>
																				<select id="matricula">
												<option value="C-5877221">C-5877221
												<option value="A-10031031 ">A-10031031
												<option value="A-10036539">A10036539
												<option value="A-10043931">A-10043931
												<option value="C-7893760">C-7893760
												<option value="C-3895663">C-3895663
												<option value="D-0127000">D-0127000
												<option value="C-9572972">C-9572972
												<option value="D-3368761">D-3368761
												<option value="A-10054316">A-10054316
												<option value="A-10085748">A-10085748
												<option value="D-1154442">D-1154442
												<option value="D-3055043">D-3055043
												<option value="D-2286079">D-2286079
												<option value="D-2863020">D-2863020
						
</select>
																			</div>

																			<div class="fondo">
																				<label for="digtamenes" class="label">NOMBRE QUIEN VERIFICO</label>
																				<select id="digtamenes">
							<option value="LUIS ERNESTO PADILLA GARCIA">LUIS ERNESTO PADILLA GARCIA
							<option value="ADRIANA HERNANDEZ VAZQUEZ">SBTTE INFTCA ADRIANA HERNANDEZ VAZQUEZ
							<option value="JUDITH PALOMEC ANTONIO">JUDITH PALOMEC ANTONIO
							<option value="ANA KAREN PANTALEON CASTREJON">ANA KAREN PANTALEON CASTREJON
							<option value="FRANCISCO JAVIER AMADOR RAMÍREZ">FRANCISCO JAVIER AMADOR RAMÍREZ
							<option value="JHOVAN ORTEGA MANZANO">JHOVAN ORTEGA MANZANO
							<option value="ALEJANDRO CERNA VARGUEZ">ALEJANDRO CERNA VARGUEZ.
							<option value="LORENZO ANTONIO SANCHEZ ARANDA">LORENZO ANTONIO SANCHEZ ARANDA
							<option value="JORDY EMANUEL GUILLEN ROSARIO">JORDY EMANUEL GUILLEN ROSARIO
							<option value="VICTORIA DE JESUS FIGUEROA MORALES">VICTORIA DE JESUS FIGUEROA MORALES
							<option value="ROSALBA SANCHEZ APOLINAR">ROSALBA SANCHEZ APOLINAR
							<option value="ALEXANDER JOVANNI GONZALEZ DIAZ">ALEXANDER JOVANNI GONZALEZ DIAZ
							<option value="ETHAN HORACIO GARDUÑO VÉLEZ">ETHAN HORACIO GARDUÑO VÉLEZ
							<option value="ALEXIS SANTIAGO MENDOZA">ALEXIS SANTIAGO MENDOZA
							<option value="KEIN JESUS BARRERA DEL PILAR">KEIN JESUS BARRERA DEL PILAR
	</select>
																			</div>

																			<div class="fondo">
																				<label for="gra" class="label">GRADO</label>
																				<select id="gra">
					<option	value="Mayor">Mayor
					<option value="Capitan">Capitan
					<option value="Subteniente">Subteniente
					<option value="Teniente">Subteniente
					<option value="SargentoI">SargentoI
					<option value="SargentoII">SargentoI
					<option value="Cabo">Cabo
					<option value="Soldado">Soldado
			</select>
																			</div>

																			<div class="fondo">
																				<label for="matricula2" class="label">MATRICULA</label>
																				<select id="matricula2">
														<option value="C-5877221">C-5877221
														<option value="A-10031031 ">A-10031031
														<option value="A-10036539">A10036539
														<option value="A-10043931">A-10043931
														<option value="C-7893760">C-7893760
														<option value="C-3895663">C-3895663
														<option value="D-0127000">D-0127000
														<option value="C-9572972">C-9572972
														<option value="D-3368761">D-3368761
														<option value="A-10054316">A-10054316
														<option value="A-10085748">A-10085748
														<option value="D-1154442">D-1154442
														<option value="D-3055043">D-3055043
														<option value="D-2286079">D-2286079
														<option value="D-2863020">D-2863020
			</select>
																			</div>



																			<div class="fondo">
																				<label for="grad" class="label">GRADO</label>
																				<select id="grad">
		<option value="Mayor">Mayor
		<option value="Capitan">Capitan
		<option value="Subteniente">Subteniente
		<option value="Teniente">Subteniente
		<option value="Sargento I">Sargento I
		<option value="Sargento II">Sargento I
		<option value="Cabo">Cabo
		<option value="Soldado">Soldado
		</select>
																			</div>


																			<div class="fondo">
																				<label for="autorizo" class="label">NOMBRE QUIEN VERIFICO</label>
																				<select id="autorizo">
									<option value="LUIS ERNESTO PADILLA GARCIA">LUIS ERNESTO PADILLA GARCIA
									<option value="ADRIANA HERNANDEZ VAZQUEZ">SBTTE INFTCA ADRIANA HERNANDEZ VAZQUEZ
									<option value="JUDITH PALOMEC ANTONIO">JUDITH PALOMEC ANTONIO
									<option value="ANA KAREN PANTALEON CASTREJON">ANA KAREN PANTALEON CASTREJON
									<option value="FRANCISCO JAVIER AMADOR RAMÍREZ">FRANCISCO JAVIER AMADOR RAMÍREZ
									<option value="JHOVAN ORTEGA MANZANO">JHOVAN ORTEGA MANZANO
									<option value="ALEJANDRO CERNA VARGUEZ">ALEJANDRO CERNA VARGUEZ.
									<option value="LORENZO ANTONIO SANCHEZ ARANDA">LORENZO ANTONIO SANCHEZ ARANDA
									<option value="JORDY EMANUEL GUILLEN ROSARIO">JORDY EMANUEL GUILLEN ROSARIO
									<option value="VICTORIA DE JESUS FIGUEROA MORALES">VICTORIA DE JESUS FIGUEROA MORALES
									<option value="ROSALBA SANCHEZ APOLINAR">ROSALBA SANCHEZ APOLINAR
									<option value="ALEXANDER JOVANNI GONZALEZ DIAZ">ALEXANDER JOVANNI GONZALEZ DIAZ
									<option value="ETHAN HORACIO GARDUÑO VÉLEZ">ETHAN HORACIO GARDUÑO VÉLEZ
									<option value="ALEXIS SANTIAGO MENDOZA">ALEXIS SANTIAGO MENDOZA
									<option value="KEIN JESUS BARRERA DEL PILAR">KEIN JESUS BARRERA DEL PILAR
			</select>
																			</div>


																			<div class="fondo">
																				<label for="matricula3" class="label">MATRICULA</label>
																				<select id="matricula3">
												<option value="C-5877221">C-5877221
												<option value="A-10031031 ">A-10031031
												<option value="A-10036539">A10036539
												<option value="A-10043931">A-10043931
												<option value="C-7893760">C-7893760
												<option value="C-3895663">C-3895663
												<option value="D-0127000">D-0127000
												<option value="C-9572972">C-9572972
												<option value="D-3368761">D-3368761
												<option value="A-10054316">A-10054316
												<option value="A-10085748">A-10085748
												<option value="D-1154442">D-1154442
												<option value="D-3055043">D-3055043
												<option value="D-2286079">D-2286079
												<option value="D-2863020">D-2863020	
</select>
																			</div>

																			<div class="fondo">
																				<label for="gr" class="label">GRADO</label>
																				<select id="gr">
		<option value="Mayor">Mayor
		<option value="Capitan">Capitan
		<option value="Subteniente">Subteniente
		<option value="Teniente">Subteniente
		<option value="Sargento I">Sargento I
		<option value="Sargento II">Sargento I
		<option value="Cabo">Cabo
		<option value="Soldado">Soldado
		</select>
																			</div>


																			<div class="fondo">
																				<label for="bien" class="label">NOMBRE QUIEN DEJO EL BIEN</label>
																				<input type="text" placeholder="" id="bien" class="sombra">
</div>


																				<div class="fondo">
																					<label for="mat" class="label">MATRICULA</label>
																					<input type="text" placeholder="" id="mat" class="sombra">
</div>


																					<div class="fondo">
																						<label for="telefono" class="label">TELEFONO</label>
																						<input type="text" placeholder="" id="telefono" class="sombra">
																	</div>

																						<div class="fondo">
																							<label for="grados" class="label"> GRADO </label>
																							<input type="text" placeholder="" id="grados" class="sombra">
	</div>


																							<div class="fondo">
																								<label for="nombrequienrecibe" class="label"> NOMBRE QUIEN RECIBE EL BIEN </label>
																								<input type="text" placeholder="" id="nombrequienrecibe" class="sombra">
		</div>
																								<div class="fondo">
																									<label for="matricula4" class="label"> MATRICULA </label>
																									<input type="text" placeholder="" id="matricula4" class="sombra">
	</div>


																									<div class="fondo">
																										<a href="#"
																											id="run"
																											class="sombra-2"><span>Aceptar</span>
																										</a>
																									</div>
																								</div>
																							</div>
                                              
                                              
                                              
                                              
  
  
  
  
  
  body{
	margin:0;
	color:#FBC02D;
	background:#e9d9d9;
	font:600 16px/18px 'Open Sans',sans-serif;
}
*,:after,:before{box-sizing:border-box}
.clearfix:after,.clearfix:before{content:'';display:table}
.clearfix:after{clear:both;display:block}
a{color:inherit;text-decoration:none}


.login-wrap{
	width:100%;
	margin:auto;
	max-width:600px;
	min-height:1300px;
	position:relative;
	background-image: url(../img/HCMlogo.png);
	box-shadow:0 10px 15px 0 rgba(2, 0, 0, 0.20),0 17px 50px 0 rgba(102, 98, 98, 0.19);
}

.login-html{
	width:100%;
	height:110%;
	position:absolute;
	padding:90px 70px 50px 70px;
	background:rgba(85, 2, 2, 0.918);
}
.login-html .sign-in-htm,
.login-html .sign-up-htm{
	top:0;
	left:0;
	right:0;
	bottom:0;
	position:absolute;
	transform:rotateY(180deg);
	backface-visibility:hidden;
	transition:all .4s linear;
}
.login-html .sign-in,
.login-html .sign-up,
.login-form .fondo .check{
	display:none;
}
.login-html .tab,
.login-form .fondo .label,
.login-form .fondo .sombra-2{
	text-transform:uppercase;
}
.login-html .tab{
	font-size:20px;
	margin-right:15px;
	padding-bottom:5px;
	margin:0 15px 10px 0;
	display:inline-block;
	border-bottom:2px solid transparent;
}
.login-html .sign-in:checked + .tab,
.login-html .sign-up:checked + .tab{
	color:#fff;
	border-color:#FBC02D;
}
.login-form{
	min-height:345px;
	position:relative;
	perspective:1000px;
	transform-style:preserve-3d;
}
.login-form .fondo{
	margin-fondo:15px;
}
.login-form .fondo .label,
.login-form .fondo .input,
.login-form .fondo .sombra{
	width:100%;
	color:rgb(32, 28, 28);
	display:block;
}
.login-form .fondo.input,
.login-form .fondo .sombra-2{
	border:none;
	padding:15px 20px;
	border-radius:25px;
	background:rgba(230, 220, 220, 0.1);
}
.login-form .fondo .label{
	color:rgb(243, 234, 234);
	font-size:12px;
}
.login-form .fondo .button{
	background:rgb(207, 107, 13);
}
.login-form .fondo label .icon{
	width:15px;
	height:15px;
	border-radius:2px;
	position:relative;
	display:inline-block;
	background:rgba(158, 20, 20, 0.1);
}
.login-form .fondo label .icon:before,
.login-form .fonfo label .icon:after{
	content:'';
	width:10px;
	height:2px;
	background:rgb(224, 214, 214);
	position:absolute;
	transition:all .2s ease-in-out 0s;
}


.login-form .fondo label .icon:before{
	left:3px;
	width:5px;
	bottom:6px;
	transform:scale(0) rotate(0);
}
.login-form .fondo label .icon:after{
	top:6px;
	right:0;
	transform:scale(0) rotate(0);
}
.login-form .fondo .check:checked + label{
	color:rgb(250, 232, 232);
}
.login-form .fondo .check:checked + label .icon{
	background:#1161ee;
}
.login-form .fondo .check:checked + label .icon:before{
	transform:scale(1) rotate(45deg);
}
.login-form .fondo .check:checked + label .icon:after{
	transform:scale(1) rotate(-45deg);
}
.login-html .sign-in:checked + .tab + .sign-up + .tab + .login-form .sign-in-htm{
	transform:rotate(0);
}
.login-html .sign-up:checked + .tab + .login-form .sign-up-htm{
	transform:rotate(0);
}

.hr{
	height:2px;
	margin:10px 0 20px 0;
	background:rgba(241, 233, 233, 0.2);
}
.foot-lnk{
	text-align:center;
}

























h1{
font-size: 20px;
text-align: center;
color: rgb(33,115,70);
}
form{
  color:black;
  font-size: 15px;
}

.demo{
    content:"$";
}
.sombra {
    position:relative;
    margin:8px;
    height:3px;
    border:none;
    display:inline-block;
    background: #dde1e7;
    text-decoration: none;
    font-weight: 300;
    font-size: 14px;
    color: #5a84a2;
    padding: 15px 10px;
    border-radius: 10px;
    text-align: l;
    
}
.sombra-2:focus{
    box-shadow: inset 4px 4px 8px rgb(175,175,175),
                 inset -8px -8px 16px rgb(243,243,243);
}
.container {
  position: relative;
  padding-left: 35px;
  margin-bottom: 20px;
  cursor: pointer;
  color:rgb(180, 150, 150);
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
/* Hide the browser's default checkbox */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}
/* Create a custom checkbox */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: #eee;
}

/* When the checkbox is checked, add a blue background */
.container input:checked ~ .checkmark {
  background-color: #2196F3;
}
/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}
/* Show the checkmark when checked */
.container input:checked ~ .checkmark:after {
  display: block;
}
/* Style the checkmark/indicator */
.container .checkmark:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}
.container-2 {
  position: relative;
  padding-left: 35px;
  margin-bottom: 20px;
  cursor: pointer;
  color:grey;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
/* Hide the browser's default radio button */
.container-2 input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}
/* Create a custom radio button */
.checkmark-2 {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: rgb(168, 41, 41);
  border-radius: 50%;
}
/* On mouse-over, add a grey background color */
.container-2:hover input ~ .checkmark-2 {
  background-color: #ccc;
}
/* When the radio button is checked, add a blue background */
.container-2 input:checked ~ .checkmark-2 {
  background-color: #2196F3;
}
/* Create the indicator (the dot/circle - hidden when not checked) */
.checkmark-2:after {
  content: "";
  position: absolute;
  display: none;
}
/* Show the indicator (dot/circle) when checked */
.container-2 input:checked ~ .checkmark-2:after {
  display: block;
}
/* Style the indicator (dot/circle) */
.container-2 .checkmark-2:after {
  top: 9px;
  left: 9px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: rgb(170, 120, 120);
}
.focus {
    position:relative;
    margin:0;
    height: 15px;
    border:none;
    display:inline-block;
    background: #dde1e7;
    text-decoration: none;
    font-weight: 300;
    font-size: 14px;
    color: rgb(33,115,70);
    padding: 15px 18px;
    border-radius: 10px;
    box-shadow: 4px 4px 8px #9b989d, 
                -4px -4px 8px rgb(243,243,243);
}
.fondo:hover{
    box-shadow: inset 4px 4px 8px rgb(175, 157, 157),
                 inset -8px -8px 16px rgb(173, 132, 132);
}
.f:hover span{
    display:inline-block;
    transform:scale(0.98)
}
.container .checkmark .container-2 .checkmark-2{
    display: inline-block;
}
#M{
  margin:0px 40px;
}
select{
  
  	width:100%;
	color:rgb(182, 179, 179);
	display:block;
  border:1px solid rgb(184, 178, 178);
  color:rgb(14, 13, 13);
  padding: 6px 18px;
    border-radius: 7px;
    
               


         
}





