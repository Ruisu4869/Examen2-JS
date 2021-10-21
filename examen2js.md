# Examen 2 Javascript

## Autor
1. Luis German Henao Ortiz

## Ejercicio examen 2

```javascript

class Invernadero {
	constructor(es_de_sol, tipos_de_farmacos, quimica, tiempo_crecimiento_final, tiempo_crecimiento_actual, plagas, luz, humedad, nutrientes) {
		this.es_de_sol = es_de_sol;
		this.tipos_de_farmacos = [tipos_de_farmacos];
		this.quimica = [quimica];
		this.tiempo_crecimiento_final = tiempo_crecimiento_final;
		this.tiempo_crecimiento_actual = tiempo_crecimiento_actual;
		this.plagas = [plagas];
		this.luz = luz;
		this.humedad = humedad;
		this.nutrientes = nutrientes;
	}

		//'Cochinillas', 'Pulgones', 'Mosca blanca', 'Acaros', 'Gusanos'

	descripcion() {
			
		if (this.es_de_sol = false) {
			console.log('La planta no es de sol');
		}
		else {
			console.log('La planta es de sol');
		}
			
		console.log('Usa los siguientes tipos de farmaco: ' + this.tipos_de_farmacos);
		console.log('Contiene los siguientes quimicos: '+ this.quimica);
		console.log('Su tiempo de crecimiento final es: '+ this.tiempo_crecimiento_final);
		console.log(`Su tiempo de crecimiento actual es: ${this.tiempo_crecimiento_actual}`);
		console.log('La planta ha sufrido las siguientes plagas: '+ this.plagas);
		console.log('Su porcentaje de luz es: '+ this.luz+'%');
		console.log('Su porcentaje de humedad es: '+ this.humedad+'%');
		console.log('Su porcentaje de nutrientes es: '+ this.nutrientes+'%');
	}


	agregar_horas_de_vida() {
		
		if (this.es_de_sol = true) {
			console.log('El porcentaje de luz es '+ this.luz +'%');
			this.tiempo_crecimiento_final = this.tiempo_crecimiento_final + this.luz;
			console.log('El tiempo de crecimiento final es: '+ (this.tiempo_crecimiento_actual*60)+ ' minutos');
			this.tiempo_crecimiento_actual = this.tiempo_crecimiento_actual + this.tiempo_crecimiento_final;
			return this.tiempo_crecimiento_final;
		}

		console.log('El porcentaje de humedad es '+this.humedad + '%');
		this.tiempo_crecimiento_final = this.humedad * this.tiempo_crecimiento_final;
		console.log('El tiempo de crecimiento final es: ' + (this.tiempo_crecimiento_final*3600)+ ' segundos');
		this.tiempo_crecimiento_actual = this.tiempo_crecimiento_actual + tiempo_crecimiento_final;

		console.log('El porcentaje de nutrientes es '+this.nutrientes+'%');
		this.tiempo_crecimiento_final = this.tiempo_crecimiento_final - this.nutrientes;
		console.log('El tiempo de crecimiento final es: '+ this.tiempo_crecimiento_final+' horas');
		this.tiempo_crecimiento_actual = this.tiempo_crecimiento_actual + tiempo_crecimiento_final;

		return this.tiempo_crecimiento_final, this.tiempo_crecimiento_actual;
	}

	agregar_humedad(hum) {
		var cont;
		var humPro = (hum*1)/7;
		if (humPro < 0 || humPro > 100) {
			cont = humPro - 100;
			this.nutrientes = this.nutrientes + cont;
			return this.nutrientes;
		}
		else if (hum < 0) {
			this.nutrientes = this.nutrientes - hum;
			return this.nutrientes;
		}
		console.log('El porcentaje de humedad es '+humPro+'% de '+hum+' g/m^3');
	}

	antidotos() {
		const antid = ['DEFEROXAMINA', 'ANTIDIGITAL', 'ALMIDON', 'FLUMAZENILO', 'TIOSULFATO SODICO'];
		const ven = ['Hierro', 'Digoxina', 'Yodo', 'Benzodiazepinas', 'Cianuro'];

		for (var i=0;i<this.quimica.length;i++) {
			if (this.quimica == ven[i]) {
				console.log('Antidotos: ' + antid);
			}
		}
	}
}

const planta1 = new Invernadero(true, ['Remedio', 'Droga'], ['Vitamina A', 'Vitamina D'], 20, 30, ['Cochinillas', 'Sarna'], 75, 50, 30);

planta1.agregar_horas_de_vida();
planta1.agregar_humedad(35);
planta1.antidotos();
planta1.descripcion();

console.log(' ');
const planta2 = new Invernadero(false, ['veneno', 'antidoto'], ['Vitamina C', 'Vitamina E'], 60, 40, ['Acaros', 'Gusanos'], 30, 10, 50);

planta2.agregar_horas_de_vida();
planta2.agregar_humedad(21);
planta2.antidotos();
planta2.descripcion();

console.log(' ');
const planta3 = new Invernadero(true, ['veneno', 'droga'], ['Vitamina E', 'Vitamina A'], 50, 10, ['Pulgones', 'Mosca blanca', 'Acaros'], 15, 80, 5);

planta3.agregar_horas_de_vida();
planta3.agregar_humedad(12);
planta3.antidotos();
planta3.descripcion();
```