#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main()
{
    char str[100];
    int i, num;

    printf("Enter the string: ");
    scanf("%[^\n]", str);

    printf("\nIdentifiers: ");
    for(i = 0; i < strlen(str); i++)
    {
        if(isalpha(str[i]))
            printf("%c ", str[i]);
    }

    printf("\nConstants: ");
    for(i = 0; i < strlen(str); i++)
    {
        if(isdigit(str[i]))
        {
            num = 0;
            while(isdigit(str[i]))
            {
                num = num * 10 + (str[i] - '0');
                i++;
            }
            printf("%d ", num);
            i--;
        }
    }

    printf("\nOperators: ");
    for(i = 0; i < strlen(str); i++)
    {
        if(str[i] == '+' || str[i] == '-' ||
           str[i] == '*' || str[i] == '=')
        {
            printf("%c ", str[i]);
        }
    }

    return 0;
}
<img width="761" height="241" alt="image" src="https://github.com/user-attachments/assets/dfe81d54-2a68-47d4-afdc-f365783d1362" />
