// HERMILO PALOMEQUE GOMEZ // GRUPO 001 16/05/21 

#include <stdlib.h>
#include <string.h>
#include <iostream>
#include <conio.h>
#include <fstream>
#include <string>

using namespace std;

string NdP[100], NdT[100], HdT[100], tratamiento[100], desc[100];
float* T, * sT, * PUT;
int* CdT, * cc; 
void c1();
void c2();
void c3();
void c4();
void c6();
int main()
{
	system("cls"); int opcion = 1, op, i, j, cc; cout << "-----Elija una opcion segun el numero-----" << endl;
	cout << " 1 Agendar cita " << endl; cout << " 2 Modificar cita " << endl;
	cout << " 3 Eliminar cita" << endl;
	cout << " 4 Lista de citas vigentes" << endl;
	cout << " 5 Limpiar pantalla" << endl;
	cout << " 6 Salir" << endl; cin >> opcion;
	switch (opcion)
	{
	case 1:
		c1();
		return main();
		break; 
	case 2:
		c2();
		return main();
		break; 
	case 3:
		c3();
		return main();
		break; 
	case 4:
		c4();
		return main();
		break; 
	case 5:
		system("cls");
		return main();
		break; 
	case 6:
	c6(); 
	break;

	default:
		cout << "Ingrese opcion valida" << endl;
		return main();
	}
}
void c1()
{
	string NdP[100], * NdT[100], HdT[100], tratamiento[100], desc[100];
	float* sT, * T, PreU, * PUT;
	int* CdT;
	int cc; cout << "Ingrese la cantidad de personas que desea registrar: " << endl;
	cin >> cc;
	for (int i = 0; i < cc; i++)
	{
		cout << " --- Agendar cita --- " << endl;
		cout << "Numero de registro: " << i + 1 << endl; while (getchar() != '\n');
		cout << " Ingrese el nombre del paciente" << endl;
		getline(cin, NdP[i]); while (getchar() != '\n');
		cout << " Ingrese el tratamiento" << endl;
		getline(cin, tratamiento[i]); while (getchar() != '\n');
		cout << " Ingrese la hora de tratamiento" << endl;
		getline(cin, HdT[i]); while (getchar() != '\n');
		cout << " Ingrese la descripcion del tratamiento" << endl;
		getline(cin, desc[i]);
		cout << " Ingrese el precio unitario del tratamiento" << endl;
		cin >> PUT[i];
		cout << " Ingrese la cantidad del tratamiento" << endl;
		cin >> CdT[i];
		cout << " ---------------------- " << endl;
		sT[i] = PUT[i] * CdT[i];
		cout << "El subtotal es:" << sT[i] << endl; T[i] = (sT[i] * .16) + sT[i];
	}
}
void c2()
{
	string* NdP, * NdT, HdT[100], tratamiento[100], desc[100];
	float* T, * PreU, PUT;
	int CdT;
	int j, op; cout << "ingrese el registro a modificar" << endl;
	cin >> j;
	j = j - 1; cout << "¿Que desea modificar?" << endl;
	cout << "1.- nombre del paciente" << endl;
	cout << "2.- tratamiento " << endl;
	cout << "3.- hora de tratamiento" << endl;
	cout << "4.- descripcion" << endl;
	cout << "5.- precio unitario" << endl;
	cout << "6.- cantidad de tratamiento" << endl;
	cin >> op; switch (op)
	{
	case 1:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese nombre del paciente" << endl;
			getline(cin, NdP[i]);
		}
	break; case 2:
		for (int i = j; i <= j; i++)
		{
			cin.ignore();
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese nombre del tratamiento" << endl;
			getline(cin, NdT[i]);
		}
	break; case 3:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese hora" << endl;
			getline(cin, HdT[i]);
		}
	break; 

	case 4:
		for (int i = j; i <= j; i++)
		{
			while (getchar() != '\n');
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese nombre del paciente" << endl;
			getline(cin, desc[i]);
		}
	break; 

	case 5:
		for (int i = j; i <= j; i++)
		{
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese el precio unitario" << endl;
			cin >> PUT;
		}
	break; case 6:
		for (int i = j; i <= j; i++)
		{
			cout << "No. cita: " << i + 1 << endl;
			cout << "Ingrese la cantidad de tratamiento" << endl;
			cin >> CdT;
		}
		break;
	}
}void c3()
{
	string NdP[100], NdT[100], HdT[100], tratamiento[100], desc[100];
	float* sT, * T, * PUT;
	int* CdT;
	int cc; int j; cout << "Ingrese cita a eliminar" << endl;
	cin >> j;
	j = j - 1;
	for (int i = j; i == j; i++)
	{
		cout << "Eliminando registro " << j + 1 << endl;
		NdP[i] = " ";
		HdT[i] = " ";
		tratamiento[i] = " ";
		desc[i] = " ";
		CdT[i] = 0;
		PUT[i] = 0;
		sT[i] = 0;
		T[i] = 0;
	}
}void c4()
{
	string* NdP, NdT, HdT[100], tratamiento[100], desc[100];
	float* T, * sT, * PreU, * PUT;
	int* CdT, cc; for (int i = 0; i < cc; i++)
	{
		cout << "------------------------" << endl;
		cout << "Numero de registro: " << i + 1 << endl;
		cout << "Nombre del paciente: " << NdP[i] << endl;
		cout << "Tratamiento: " << tratamiento[i] << endl;
		cout << "Hora de tratamiento: " << HdT[i] << endl;
		cout << "Descripcion: " << desc[i] << endl;
		cout << "Precio unitario de Tratamiento: " << PUT[i] << endl;
		cout << "Cantidad de tratamiento: " << CdT[i] << endl;
		cout << "Subtotal: " << sT[i] << endl;
		cout << "Total: " << T[i] << endl;
	}
}void c6()
{
	string* NdP, NdT, HdT[100], tratamiento[100], desc[100];
	float* T, * sT, * PreU, * PUT;
	int* CdT, cc;
	ofstream imp("Datos.txt");
	for (int i = 0; i < cc; i++)
	{
		if (NdP[i] == " ")
		{
		}
		else
		{
			imp << "Nombre: " << NdP[i] << endl;
			imp << "Hora: " << HdT[i] << endl;
			imp << "Nombre del tratamiento: " << tratamiento[i] << endl;
			imp << "Descripcion: " << desc[i] << endl;
			imp << "Cantidad del tratamiento: " << CdT[i] << endl;
			imp << "Precio unitario: " << PUT[i] << endl;
			imp << "Total a pagar: " << T[i] << endl;
			imp << "----------------------------------------------------------------------------------------------------------------" << endl;
		}
	}
}


