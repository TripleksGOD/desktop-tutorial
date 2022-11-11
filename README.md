
#include <iostream>
#include <stdio.h>
#include <windows.h>
#include <conio.h>
#include <math.h>

using namespace std;

int main()
{
	int day, month, year; //створюємо смінні
	
	cout << "Enter date day, month, year: " << endl; //просимо ввести дату
	cin >> day >> month >> year;
	
	if (day > 0 && day < 28) //перевірка доби від 0 до 27 днів
		day += 1;
	
	if (day == 28) //коли день = 28
	{
		if (month == 2)	//перевірка лютого
		{
			if ((year % 400 == 0) || (year % 100 != 0 || year % 4 == 0))	//перевірка лютого, якщо високосний рік
			{
				day = 29;
			}
			
			else
			{
				day = 1;
				month = 3;
			}
		}
		
		else	//коли це не лютий
			day += 1;
	}
	if (day == 29)	//коли день = 29
	{
		if (month == 2) //перевірка останнього дня лютого
		{
			day = 1;
			month = 3;
		}
		
		else
			day += 1;
	}
	if (day == 30)	//коли день 30
	{
		if (month == 1 || month == 3 || month == 5 || month == 7 || month == 8 || month == 10 || month == 12) //перевірка останнього для квітня, червня, листопада та вересня
			day += 1;
		
		else
		{
			day = 1;
			month += 1;
		}
	}
	if (day == 31)	//коли день = 31, останній день місяця
	{
		day = 1;
		
		if (month == 12)	//перевірка останнього дня лютого
		{
			year += 1;
			month = 1;
		}
		
		else
			month += 1;
	}
	
	cout << "Tomorrow date: " << endl; //виводимо результат, тобто завтрішню дату

	cout << day << " " << month << " " << year;
	
	return 0;
}