#include <iostream>
#include <iomanip>
using namespace std;
int main()
{
    int numUsers; //varaiable to store num of user we want to calculate text for
    cout << "Enter number of users: ";
    cin >> numUsers;
    // loop through each user one by one
    for (int i = 1; i <= numUsers; i++) 
    {
        double income; // variable to store annual income
        double tax = 0; // variabble to store calculated tax
        double netIncome; // variable to store net income after tax
        
        cout << "\n--- User " << i << " ---" << endl; // show which user we are calculating for
        cout <<"Enter annual income (USD): ";
        cin >> income;
        
        if (income <= 12000){ 
          // Case 1: Income up to 12000
            tax = 0;
         }
         else if (income <= 30000){
            // Case 2: Income between 12,001 and 30,000
             //Formula: 10% of amount exceeding 12,000
             tax = (income - 12000) * 0.10; 
         }
         else if (income <= 60000){
            // Case 3: Income between 30,000 and 60,000
             //Formula: 20% of amount exceeding 30,000 + 1,800
             tax = (income - 30000) * 0.20 + 1800;
         }
         else {
             // Case 4: Income above 60,000
              // formula: 30% of amount exceeding 60,000 + 7,800
              tax = (income - 60000) * 0.30 + 7800;
         }
         // Calculate net income (income - tax)
         netIncome = income - tax;
         
         // Display result with 2 decimal places
         cout << fixed << setprecision(2);
         cout << "Tax: $" << tax << endl;
         cout << "Net Income: $" << netIncome << endl;
    }
     
     cout << "\nThank you for using the Income Tax Calculator!" << endl;
     
     return 0;
}
