# 2-PB0012086161HERMILo
// HERMILO PALOMEQUE GOMEZ // GRUPO 001 16/03/21 
#include <iostream>
#include <stdlib.h>
#include <string.h>
#include <string>
#include <fstream>
using namespace std;

struct cita
{
    char NdP[100], HdT[100], tratamiento[100], desc[100];
    float T = 0, PreU, PUT;
    int CdT;

};

int main()
{
    int opcion = 1, op, i, j;
    cita cliente[3];

    while (opcion == 1)
    {
        cout << "-----Elija una opcion segun el numero-----" << endl;
        cout << " 1 Agendar cita " << endl;
        cout << " 2 Modificar cita " << endl;
        cout << " 3 Eliminar cita" << endl;
        cout << " 4 Lista de citas vigentes" << endl;
        cout << " 5 Salir" << endl;
        cin >> opcion;

        system("CLS");

        switch (opcion)
        {

        case 1:

            for (i = 0; i < 3; i++)
            {
                cout << " --- Agendar cita --- " << endl;
                cout << "Numero de registro: " << i + 1 << endl;
                cout << " Ingrese el nombre del paciente" << endl;
                cin >> cliente[i].NdP;


                cout << " Ingrese el tratamiento" << endl;
                cin >> cliente[i].tratamiento;


                cout << " Ingrese la hora de tratamiento" << endl;
                cin >> cliente[i].HdT;


                cout << " Ingrese la descripcion del tratamiento" << endl;
                cin >> cliente[i].desc;


                cout << " Ingrese el precio unitario del tratamiento" << endl;
                cin >> cliente[i].PUT;


                cout << " Ingrece el precio unitario" << endl;
                cin >> cliente[i].PreU;


                cout << " Ingrese la cantidad del tratamiento" << endl;
                cin >> cliente[i].CdT;


                cout << " ---------------------- " << endl;
                cliente[i].T = cliente[i].PreU * cliente[i].CdT;
                cout << "El total es:" << cliente[i].T << endl;

                system("CLS");

            }

            break;

        case 3:
            cout << "ingrese el numero registro";
            cin >> j;
            j = j - 1;
            cout << "ingrese que desea modificar: " << endl;

            cin >> op;


        case 4:
            for (i = 0; i < 3; i++)
            {
                cout << "------------------------" << endl;
                cout << "Numero de registro: " << i + 1 << endl;
                cout << "Nombre del paciente: " << cliente[i].NdP << endl;
                cout << "Tratamiento: " << cliente[i].tratamiento << endl;
                cout << "Hora de tratamiento: " << cliente[i].HdT << endl;
                cout << "Descripcion: " << cliente[i].desc << endl;
                cout << "Precio unitario de Tratamiento: " << cliente[i].PUT << endl;
                cout << "Precio unitario: " << cliente[i].PreU << endl;
                cout << "Cantidad de tratamiento: " << cliente[i].CdT << endl;
                cout << "Total: " << cliente[i].T << endl;


            }

            break;

        }


        cout << "Desea volver al menu?" << endl;
        cout << "1 Para Sí,2 para no" << endl;
        cin >> opcion;

        system("CLS");

    }

    return 0;

}
