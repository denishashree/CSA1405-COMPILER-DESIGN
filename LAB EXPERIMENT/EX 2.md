#include <stdio.h>
#include <string.h>

int main()
{
    char com[100];

    printf("Enter comment: ");
    fgets(com, sizeof(com), stdin);

    if (com[0] == '/')
    {
        if (com[1] == '/')
        {
            printf("It is a comment");
        }
        else if (com[1] == '*')
        {
            if (strstr(com + 2, "*/") != NULL)
                printf("It is a comment");
            else
                printf("It is not a comment");
        }
        else
        {
            printf("It is not a comment");
        }
    }
    else
    {
        printf("It is not a comment");
    }

    return 0;
}
<img width="725" height="293" alt="image" src="https://github.com/user-attachments/assets/3ad04e5e-7be1-4b47-80bf-79daf812d16e" />
