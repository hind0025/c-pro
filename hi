#include <stdio.h>
#include <string.h>

#define MAX_CONTACTS 100

struct Contact 
{
    char name[50];
    char phone_number[11];
    char email[50];
};

struct Contact contacts[MAX_CONTACTS];
int num_contacts = 0;

void add_contact() 
{
    if (num_contacts >= MAX_CONTACTS) 
    {
        printf("Error: maximum number of contacts reached\n");
        return;
    }

    struct Contact new_contact;
    printf("Enter name: ");
    scanf("%s", new_contact.name);

    printf("Enter phone number: ");
    scanf("%s", new_contact.phone_number);

    printf("Enter Email: ");
    scanf("%s", new_contact.email);

    contacts[num_contacts] = new_contact;
    num_contacts++;

    printf("Contact added successfully\n");
}

void list_contacts() 
{
    if (num_contacts == 0) 
    {
        printf("No contacts found\n");
        return;
    }

    printf("ALL CONTACTS:\n");
    for (int i = 0; i < num_contacts; i++) 
    {
       printf("%s - %s - %s\n", contacts[i].name, contacts[i].phone_number,contacts[i].email);
       
    }
}

void search_contacts() 
{
    if (num_contacts == 0) 
    {
        printf("No contacts found\n");
        return;
    }

    char search_term[50];
    printf("Enter NAME/NUMBER : ");
    scanf("%s", search_term);

    int num_matches = 0;
    for (int i = 0; i < num_contacts; i++) 
    {
        if (strstr(contacts[i].name, search_term) != NULL || strstr(contacts[i].phone_number, search_term) != NULL) 
        {
            printf("%s - %s\n", contacts[i].name, contacts[i].phone_number);
            num_matches++;
        }
    }

    if (num_matches == 0) 
    {
        printf("No matches found\n");
    }
}

int main() 
{
    int choice;
    do {
        printf("CONTACT MANAGEMENT SYSTEM \n");
        printf("-------------------------\n");
        printf("1. Add Contact\n");
        printf("2. List Contacts\n");
        printf("3. Search Contacts\n");
        printf("4. Quit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
            case 1:
                add_contact();
                break;
            case 2:
                list_contacts();
                break;
            case 3:
                search_contacts();
                break;
            case 4:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice, please try again\n");
        }

        printf("\n");
    } 
    while (choice != 4);

    return 0;

}
