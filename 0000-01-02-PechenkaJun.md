#include<iostream>
#include"constants.h"
double getInitalHeight()
{
	std::cout << "enter a inital height\n ";
	double initalHeight;
	std::cin >> initalHeight;
	return initalHeight;
}

double calculateHeight(double initalHeight,int seconds)
{
	double leight = (constants::gravity * seconds * seconds) / 2;
	double currentLeight = initalHeight - leight;
	return currentLeight;
}
void printHeight(double height,int seconds)
{
	if (height > 0)
		std::cout << "at " << seconds << " seconds the ball at " << height << " metres \n";
	else
		std::cout << " at " << seconds << " seconds the ball is allready on the ground \n";
}
void calculateAndPrint(double initalHeight, int seconds)
{
	double height = calculateHeight(initalHeight, seconds);
	printHeight(height, seconds);
}
int main()
{
	const double initalHeight = getInitalHeight();

	calculateAndPrint(initalHeight, 0);
	calculateAndPrint(initalHeight, 1);
	calculateAndPrint(initalHeight, 2);
	calculateAndPrint(initalHeight, 3);
	calculateAndPrint(initalHeight, 4);
	calculateAndPrint(initalHeight, 5);
	return 0;
}
