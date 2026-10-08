#include <stdio.h>
#include <ctype.h>

int main()
{
    char a[20];
    int flag = 1, i = 1;

    printf("Enter an identifier: ");
    fgets(a, sizeof(a), stdin);

    if(isalpha(a[0]))
    {
        while(a[i] != '\0' && a[i] != '\n')
        {
            if(!isdigit(a[i]) && !isalpha(a[i]))
            {
                flag = 0;
                break;
            }
            i++;
        }
    }
    else
    {
        flag = 0;
    }

    if(flag == 1)
        printf("Valid identifier\n");
    else
        printf("Not a valid identifier\n");

    return 0;
}
<img width="959" height="506" alt="image" src="https://github.com/user-attachments/assets/0e9770f0-b69b-44d5-94c1-2ca4981ea76a" />
