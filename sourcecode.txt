#include <iostream>

using namespace std;
/*
Employees of JB and sons Consultants Ltd are paid on an hourly basis
at the end of every week.
If an employee works for not more than 40 hours a week, it is considered
regular and overtime for hours worked in excess of 40.
Regular hours are paid at 500 cedis and 550 per hours for males and females
respectively while the overtime rate is one and a half times the regular
rate per hour for the different sexes
All employees are to pay 15% of their gross pay as income Tax, 2.5%
as National Health Contribution Levy, 1% as District Tax.
Employees who have more than three children are to pay 10 and 20 cedis
per child in excess of three towards Education Fund For All for males and
females respectively.
Device a computer solution that can be used to calculate the net pay of
Employees.
*/
int main()
{
    int numHours;
    char gender;
    int numChildren;
    int excessChildren;
    int grossPay;
    string workerType;
    float incomeTax;
    float natHealthContLevy;
    float districtTax;
    float educationFundForAll;
    float netPay;
    string firstName;
    string lastName;

    cout<<"What is your first name?" <<endl;
    cin>>firstName;
    cout<<"\nWhat is your last name?" <<endl;
    cin>>lastName;
    cout<<"How many children do you have?" <<endl;
    cin>>numChildren;
    cout<<"Are you a male or a female?\t(Indicate using m or f)" <<endl;
    cin>>gender;

    cout<<"How many hours do you work? " <<endl;
    cin>>numHours;

    if (numHours<=40 && gender=='m')
    {
        grossPay=500*numHours;

    }
    else if (numHours<=40 && gender=='f')
    {
        grossPay=550*numHours;

    }
    else if (numHours>40 && gender=='m')
    {
        grossPay=(500*1.5)*numHours;

    }
    else if (numHours>40 && gender=='f')
    {
        grossPay=(550*1.5)*numHours;

    }
    else
    {
        cout<<"Your input is invalid" <<endl;
    }

    if (numChildren>3 && gender=='m')
    {
        excessChildren=numChildren - 3;
        educationFundForAll=excessChildren*10;
    }
    else if (numChildren>3 && gender=='f')
    {
        excessChildren=numChildren - 3;
        educationFundForAll=excessChildren*20;
    }
    else if (numChildren<=3)
    {
        educationFundForAll=0;
    }
    else
    {
        cout<<"Your input is invalid.";
    }

    incomeTax=grossPay*0.15;
    natHealthContLevy=grossPay*0.025;
    districtTax=grossPay*0.01;

    netPay=grossPay - (incomeTax + natHealthContLevy + districtTax + educationFundForAll);

    cout<<"\n\nDear "<<firstName <<" " <<lastName <<", Per Each Week, \n";
    cout<<"Your gross pay is equal to " <<grossPay <<" cedis.\n";
    cout<<"Your income tax is equal to " <<incomeTax <<" cedis.\n";
    cout<<"Your National Health Contribution Levy is equal to " <<natHealthContLevy <<" cedis.\n";
    cout<<"Your District Tax is equal to " <<districtTax <<" cedis.\n";
    cout<<"Your Education Fund For All is equal to " <<educationFundForAll <<" cedis.\n\n";
    cout<<"Therefore, your net pay is equal to " <<netPay <<" cedis.\n";

    return 0;
}
