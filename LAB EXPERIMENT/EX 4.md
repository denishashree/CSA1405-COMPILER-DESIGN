#include <stdio.h>
#include <string.h>

int main()
{
    char s[5];

    printf("Enter any operator: ");
    scanf("%s", s);

    switch(s[0])
    {
        case '>':
            if(s[1] == '=')
                printf("Greater than or equal");
            else
                printf("Greater than");
            break;

        case '<':
            if(s[1] == '=')
                printf("Less than or equal");
            else
                printf("Less than");
            break;

        case '=':
            if(s[1] == '=')
                printf("Equal to");
            else
                printf("Assignment");
            break;

        case '!':
            if(s[1] == '=')
                printf("Not Equal");
            else
                printf("Bit Not");
            break;

        case '&':
            if(s[1] == '&')
                printf("Logical AND");
            else
                printf("Bitwise AND");
            break;

        case '|':
            if(s[1] == '|')
                printf("Logical OR");
            else
                printf("Bitwise OR");
            break;

        case '+':
            printf("Addition");
            break;

        case '-':
            printf("Substraction");
            break;

        case '*':
            printf("Multiplication");
            break;

        case '/':
            printf("Division");
            break;

        case '%':
            printf("Modulus");
            break;

        default:
            printf("Not a operator");
    }

    return 0;
}
<img width="1599" height="899" alt="WhatsApp Image 2026-10-06 at 10 20 52 AM" src="https://github.com/user-attachments/assets/066162fc-627e-4062-9629-c24adbd193fb" />

