
Nombre del Programa: ¡Que dias aquellos!
Autor: Mirka Galilea Dennis Vargas
Fecha: 11 de Septiembre del 2022
Descripcion: Dada una fecha se puede determinar que dia de la semana fue o sera.
*/

#include <iostream>
#include <conio.h>
 
using namespace std;
 
int DiaDeLaSemana( int dia, int mes, int anyo )
{
    int A = (14 - mes) / 12;
	int Y = anyo - A;
	int M =  mes + (12 * A) - 2;
    int diaSemana;
 	
    if (anyo >=  1582) /// Inicio del calendario Gregoriano
        diaSemana = ( dia + Y + Y/4 - Y/100 + Y/400 + (31 * M)/12 ) % 7;
	if (diaSemana > 0) diaSemana--;
	else  diaSemana = 6;
 
	return diaSemana;
}


int main()
{ 
	cout<< "Ingrese una fecha: \n"; 

    int dia, mes, anyo;
 	setlocale(LC_ALL, "spanish");
    cout << "Dia: "; cin >> dia;
    cout << "Mes: "; cin >> mes;
    cout << "Año: "; cin >> anyo;
 
 	string mesA[13]  = {"","Enero","Febrero", "Marzo","Abril","Mayo","Junio","Julio","Agosto","Septiembre","Octubre","Noviembre","Diciembre"};
	cout << "Por lo tanto, el "<< dia << " de " << mesA[mes] << " del " << anyo << " fue ";
    switch(DiaDeLaSemana(dia, mes, anyo)) {
 
        case 0: cout << "Lunes." << endl; break;
        case 1: cout << "Martes." << endl; break;
        case 2: cout << "Miercoles." << endl; break;
        case 3: cout << "Jueves." << endl; break;
        case 4: cout << "Viernes." << endl; break;
        case 5: cout << "Sabado." << endl; break;
        case 6: cout << "Domingo." << endl; break;
       
    }
        
 	
    return 0;
}
