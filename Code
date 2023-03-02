{
    int account_no;
    char account_holder_name[80];
    int account_holder_phno;
    int balance;
    int age;
};

void accept(struct customer[],int);
void display(struct customer[],int);
int search(struct customer[],int,int);
void deposit(struct customer[],int,int,int);
void withdraw(struct customer[],int,int,int);

int main()
{
    struct customer data[100];
    int n,choice,account_no,amount,i;
    printf("*****************************************************************************************************************************************\n\n");
    printf("\t\t\t\t\t\t\tBanking System\n\n");
    printf("*****************************************************************************************************************************************\n\n");
    printf("Number of customer records you want to enter? : ");
    scanf("%d",&n);
    accept(data,n);
    do
    {
        printf("*************************************");
        printf("\nBanking System Menu :\n");
        printf("Press 1 to display all records.\n");
        printf("Press 2 to search a record.\n");
        printf("Press 3 to deposit amount.\n");
        printf("Press 4 to withdraw amount.\n");
        printf("Press 0 to exit\n");
       printf("**************************************");
        printf("\nEnter choice(0-4) : ");
        scanf("%d",&choice);
        switch (choice)
        {
            case 1:
                display(data,n);
                break;
            case 2:
                printf("Enter account number you want to search : ");
                scanf("%d",&account_no);
                i=search(data,n,account_no);
                if(i== - 1)
                {
                    printf("The account number you entered is invalid !!\n ");
                }
                else
                {
                    printf("Account Number : %d\n",data[i].account_no);
                    printf("Name of the account holder : %s\n",data[i].account_holder_name);
                    printf("Account Holder Age : %d\n",data[i].age);
                    printf("Account Holder phno : %d\n",data[i].account_holder_phno);
                    printf("Balance in the account : %d\n",data[i].balance);
                }
                break;
            case 3:
                printf("Enter account number to deposit money : ");
                scanf("%d",&account_no);
                printf("Enter the amount you want to deposit : ");
                scanf("%d",&amount);
               deposit(data,n,account_no,amount);
                break;
            case 4:
                printf("Enter account number to withdraw money : ");
                scanf("%d",&account_no);
                printf("Enter the amount you want to withdraw : ");
                scanf("%d",&amount);
                withdraw(data,n,account_no,amount);
        }
    }
    while (choice!=0);

    return 0;
}

void accept(struct customer list[80],int a)
{
    int b;
    for(b=0;b<a;b++)
    {
        printf("\nEnter data for Record #%d",b + 1);

        printf("\nEnter the Account Number : ");
        scanf("%d",&list[b].account_no);
        fflush(stdin);
        printf("Enter Name of the Account Holder : ");
        scanf("%s",&list[b].account_holder_name);
        printf("Enter Age of the Account Holder : ");
        scanf("%d",&list[b].age);
        printf("Enter Account Holder phno : ");
        scanf("%d",&list[b].account_holder_phno);
        
        list[b].balance = 0;
    } 
}

void display(struct customer list[80],int s)
{
    int i;

    printf("\n\nAccount no\t\tAccount Holder Name\t\tAccount Holder Age\t\tAccount holder phno\t\tAccount Balance\n");
    for(i=0;i<s;i++)
    {
        printf("\n%d\t\t\t%s\t\t\t\t%d\t\t\t\t%d\t\t\t\t%d\n\n",list[i].account_no,list[i].account_holder_name,list[i].age,list[i].account_holder_phno,list[i].balance);
    } 
}

int search(struct customer list[80],int s,int number)
{
    int i;

    for(i=0;i<s;i++)
    {
        if(list[i].account_no == number)
        {
            return i;
        } 
    }
    return - 1;
}

void deposit(struct customer list[],int s,int number,int amount)
{
    int i = search(list,s,number);
    if(i == - 1)
    {
        printf("The account number you entered is invalid !!");
    } 
    else
    {
        list[i].balance += amount;
    }
}

void withdraw(struct customer list[],int s,int number,int amount)
{
    int i = search(list,s,number);
    if(i == - 1)
    {
        printf("The account number you entered is invalid !!\n");
    } 
    else if(list[i].balance < amount)
    {
        printf("\n The Balance in Account is Insufficient to withdraw\n");
    }
    else
    {
        list[i].balance -= amount;
    }
}





