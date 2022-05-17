

// HERMILO PALOMEQUE GOMEZ // GRUPO 001 17/05/21 

#include <iostream>
#include <stdlib.h> 
#include <string> 
#include  <fstream>

using namespace std;

void alta();
void mod();
void eli();
void liv();
void arc();

string *NdP, *NdT, *trat, *desc;
float *T, *PUT, *sT; 
int* CdT, * HdT, * MdT, cc;

int main()
{
	int opcion, respuesta=1;


	do
	{
		cout << "-----Elija una opcion segun el numero-----" << endl;
		cout << " 1 Agendar cita " << endl; cout << " 2 Modificar cita " << endl;
		cout << " 3 Eliminar cita" << endl;
		cout << " 4 Lista de citas vigentes" << endl;
		cout << " 5 Limpiar pantalla" << endl;
		cout << " 6 Salir" << endl; 
		cin >> opcion;

		switch (opcion)
		{
		case 1:
			alta();
			return main();
			break;

		case 2:
			mod();
			return main();
			break;

		case 3:
			eli();
			return main();
			break;
		case 4:
			liv();
			return main();
			break;
		case 5:
			system("cls");
			return main();
			break;
		case 6:
			arc();
			respuesta = 2;
			break;

		default:
			cout << "Ingrese opcion valida" << endl;
			return main();
		}

	} while (respuesta == 1);
}

void alta()
{
	cout << "Ingrese la cantidad de personas que desea registrar: " << endl;
	cin >> cc;

	NdP = new string[cc];
	NdT = new string[cc];
	trat = new string[cc];
	desc = new string[cc];
	T = new float[cc];
	PUT = new float[cc];
	sT = new float[cc];
	CdT = new int[cc];
	HdT = new int[cc];
	MdT = new int[cc];

	for (int i = 0; i < cc; i++)
	{
		cout << " --- Agendar cita --- " << endl;
		cout << "Numero de registro: " << i + 1 << endl;

		while (getchar() != '\n');
		cout << " Ingrese el nombre del paciente" << endl;
		getline(cin, NdP[i]);

		while (getchar() != '\n');
		cout << " Ingrese el tratamiento" << endl;
		getline(cin, NdT[i]);
		do {
			cout << " Ingrese la hora de tratamiento en formato 24 horas" << endl;
			cin >> HdT[i];

			cout << " Ingrese los minutos" << endl;
			cin >> MdT[i];
		} while ((HdT[i] < 0 || HdT[i] > 24) || (MdT[i] < 0 || MdT[i] >= 60));

		while (getchar() != '\n');
		cout << " Ingrese la descripcion del tratamiento" << endl;
		getline(cin, desc[i]);

		cout << " Ingrese el precio unitario" << endl;
		cin >> PUT[i];

		cout << " Ingrese la cantidad del tratamiento" << endl;
		cin >> CdT[i];

		cout << " ---------------------- " << endl;
		sT[i] = PUT[i] * CdT[i];
		cout << "El subtotal es:" << sT[i] << endl;

		cout << "-se le aplicara un iva del 16%-" << endl;
		T[i] = (sT[i] * .16) + sT[i];
		cout << "El total con iva es:" << T[i] << endl;

	}

}

void mod()
{
	int j, op;

	cout << "ingrese el  numero del registro a modificar" << endl;
	cin >> j;
	j = j - 1; cout << "¿Que desea modificar?" << endl;
	cout << "1.- nombre del paciente" << endl;
	cout << "2.- tratamiento " << endl;
	cout << "3.- hora de tratamiento" << endl;
	cout << "4.- descripcion" << endl;
	cout << "5.- precio unitario" << endl;
	cout << "6.- cantidad de tratamiento" << endl;
	cin >> op;

	switch (op)
	{
	case 1:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese nombre del paciente" << endl;
			getline(cin, NdP[i]);
		}
	break; 
	case 2:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese nombre del tratamiento" << endl;
			getline(cin, NdT[i]);
		}
	break; 
	case 3:
		for (int i = j; i <= j; i++)
		{
			
			cout << "No. cita: " << i + 1 << endl;
			do 
			{
				cout << " Ingrese la hora de tratamiento en formato 24 horas" << endl;
				cin >> HdT[i];

				cout << " Ingrese los minutos" << endl;
				cin >> MdT[i];
			} 
			while ((HdT[i] < 0 || HdT[i] > 24) || (MdT[i] < 0 || MdT[i] >= 60));
		}
		break;

	case 4:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese la descripcion" << endl;
			getline(cin, desc[i]);
		}
		break;

	case 5:
		for (int i = j; i <= j; i++)
		{
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese el precio unitario" << endl;
			cin >> PUT [i];
			sT[i] = PUT[i] * CdT[i];
			T[i] = (sT[i] * .16) + sT[i];
		}
	break; case 6:
		for (int i = j; i <= j; i++)
		{
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese la cantidad de tratamiento" << endl;
			cin >> CdT[i];

			sT[i] = PUT[i] * CdT[i];
			T[i] = (sT[i] * .16) + sT[i];
		}
		break;
	default:
		cout << "INGRESE OPCION VALIDA" << endl;
	}


}

void eli()
{
	int j;

	cout << "Ingrese cita a eliminar" << endl;
	cin >> j;
	j = j - 1;
	for (int i = j; i == j; i++)
	{
		cout << "Eliminando registro " << j + 1 << endl;
		NdP[i] = " ";
		HdT[i] = 0;
		MdT[i] = 0;
		trat[i] = " ";
		desc[i] = " ";
		CdT[i] = 0;
		PUT[i] = 0;
		sT[i] = 0;
		T[i] = 0;
	}

}

void liv()
{

	for (int i = 0; i < cc; i++)
	{
		if (NdP[i] == " ")
		{
			cout << "CITA " << i + 1 << " ELIMINADA" << endl;
		}
		else
		{
			cout << "------------------------" << endl;
			cout << "Numero de registro: " << i + 1 << endl;
			cout << "Nombre del paciente: " << NdP[i] << endl;
			cout << "Tratamiento: " << NdT[i] << endl;
			cout << "Hora de tratamiento: " << HdT[i] << ":" << MdT[i] << endl;
			cout << "Descripcion: " << desc[i] << endl;
			cout << "Precio unitario de Tratamiento: " << PUT[i] << endl;
			cout << "Cantidad de tratamiento: " << CdT[i] << endl;
			cout << "Subtotal: " << sT[i] << endl;
			cout << "Total: " << T[i] << endl;
		}
	}

}

void arc()
{
	ofstream archivo;
	string nombrearchivo;
	string texto;
	int texto2;

	nombrearchivo = "Archivo de citas";

	archivo.open(nombrearchivo.c_str(), ios::out);

	if (archivo.fail())
	{
		cout << "ERROR NO SE PUDO CREAR EL ARCHIVO";
		exit(1);
	}

	

	for (int i = 0; i < cc; i++)
	{

		if (NdP[i] == " ")
		{

		}
		else
		{
			archivo << "NO. REGISTRO: " << i+1 << endl;
			
			texto = NdP[i];
			archivo <<"Paciente: " << texto << endl;
			texto = NdT[i];
			archivo << "TRATAMIENTO: " << texto << endl;
			texto2 = HdT[i];
			archivo << "HORA: " << texto2 << endl;
			texto2 = MdT[i];
			archivo << "MINUTOS: " << texto2 << endl;
			texto = desc[i];
			archivo << "DESCRIPCION: " << texto << endl;
			texto2 = PUT[i];
			archivo << "PRECIO U.: "<<texto2 << endl;
			texto2 = CdT[i];
			archivo << "CANTIDAD: " << texto2 << endl;
			texto2 = sT[i];
			archivo << "SUBTOTAL: " << texto2 << endl;
			texto2 = T[i];
			archivo << "TOTAL: " << texto2 << endl;
			archivo << "--------------------------------------------------------------------------------------------" << endl;
		}
	}
	archivo.close();
}


		
	
