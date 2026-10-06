#include <stdio.h>

int main()
{
    char str[100];
    int words = 0, lines = 0, characters = 0;
    int i;

    printf("Enter text (use ~ to end):\n");
    scanf("%[^~]", str);

    for(i = 0; str[i] != '\0'; i++)
    {
        if(str[i] == ' ' || str[i] == '\t')
        {
            words++;
        }
        else if(str[i] == '\n')
        {
            lines++;
        }
        else
        {
            characters++;
        }
    }

    if(characters > 0)
    {
        words++;
        lines++;
    }

    printf("Total number of words: %d\n", words);
    printf("Total number of lines: %d\n", lines);
    printf("Total number of characters: %d\n", characters);

    return 0;
}
<img width="1599" height="899" alt="WhatsApp Image 2026-10-06 at 10 24 55 AM" src="https://github.com/user-attachments/assets/5e2f2b07-39d1-4014-b19e-556300608abc" />
