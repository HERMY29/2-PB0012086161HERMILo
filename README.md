# 2-PB0012086161HERMILo
// HERMILO PALOMEQUE GOMEZ // GRUPO 001 16/03/21  #include &lt;iostream> #include &lt;stdlib.h> #include &lt;string.h> #include &lt;string> #include &lt;fstream> using namespace std;  struct cita {     char NdP[100], HdT[100], tratamiento[100], desc[100];     float T = 0, PreU, PUT;     int CdT;  };  int main() {     int opcion = 1, op, i, j;     cita cliente[3];      while (opcion == 1)     {         cout &lt;&lt; "-----Elija una opcion segun el numero-----" &lt;&lt; endl;         cout &lt;&lt; " 1 Agendar cita " &lt;&lt; endl;         cout &lt;&lt; " 2 Modificar cita " &lt;&lt; endl;         cout &lt;&lt; " 3 Eliminar cita" &lt;&lt; endl;         cout &lt;&lt; " 4 Lista de citas vigentes" &lt;&lt; endl;         cout &lt;&lt; " 5 Salir" &lt;&lt; endl;         cin >> opcion;          system("CLS");          switch (opcion)         {          case 1:              for (i = 0; i &lt; 3; i++)             {                 cout &lt;&lt; " --- Agendar cita --- " &lt;&lt; endl;                 cout &lt;&lt; "Numero de registro: " &lt;&lt; i + 1 &lt;&lt; endl;                 cout &lt;&lt; " Ingrese el nombre del paciente" &lt;&lt; endl;                 cin >> cliente[i].NdP;                   cout &lt;&lt; " Ingrese el tratamiento" &lt;&lt; endl;                 cin >> cliente[i].tratamiento;                   cout &lt;&lt; " Ingrese la hora de tratamiento" &lt;&lt; endl;                 cin >> cliente[i].HdT;                   cout &lt;&lt; " Ingrese la descripcion del tratamiento" &lt;&lt; endl;                 cin >> cliente[i].desc;                   cout &lt;&lt; " Ingrese el precio unitario del tratamiento" &lt;&lt; endl;                 cin >> cliente[i].PUT;                   cout &lt;&lt; " Ingrece el precio unitario" &lt;&lt; endl;                 cin >> cliente[i].PreU;                   cout &lt;&lt; " Ingrese la cantidad del tratamiento" &lt;&lt; endl;                 cin >> cliente[i].CdT;                   cout &lt;&lt; " ---------------------- " &lt;&lt; endl;                 cliente[i].T = cliente[i].PreU * cliente[i].CdT;                 cout &lt;&lt; "El total es:" &lt;&lt; cliente[i].T &lt;&lt; endl;                  system("CLS");              }              break;          case 3:             cout &lt;&lt; "ingrese el numero registro";             cin >> j;             j = j - 1;             cout &lt;&lt; "ingrese que desea modificar: " &lt;&lt; endl;              cin >> op;           case 4:             for (i = 0; i &lt; 3; i++)             {                 cout &lt;&lt; "------------------------" &lt;&lt; endl;                 cout &lt;&lt; "Numero de registro: " &lt;&lt; i + 1 &lt;&lt; endl;                 cout &lt;&lt; "Nombre del paciente: " &lt;&lt; cliente[i].NdP &lt;&lt; endl;                 cout &lt;&lt; "Tratamiento: " &lt;&lt; cliente[i].tratamiento &lt;&lt; endl;                 cout &lt;&lt; "Hora de tratamiento: " &lt;&lt; cliente[i].HdT &lt;&lt; endl;                 cout &lt;&lt; "Descripcion: " &lt;&lt; cliente[i].desc &lt;&lt; endl;                 cout &lt;&lt; "Precio unitario de Tratamiento: " &lt;&lt; cliente[i].PUT &lt;&lt; endl;                 cout &lt;&lt; "Precio unitario: " &lt;&lt; cliente[i].PreU &lt;&lt; endl;                 cout &lt;&lt; "Cantidad de tratamiento: " &lt;&lt; cliente[i].CdT &lt;&lt; endl;                 cout &lt;&lt; "Total: " &lt;&lt; cliente[i].T &lt;&lt; endl;               }              break;          }           cout &lt;&lt; "Desea volver al menu?" &lt;&lt; endl;         cout &lt;&lt; "1 Para Sí,2 para no" &lt;&lt; endl;         cin >> opcion;          system("CLS");      }      return 0;
