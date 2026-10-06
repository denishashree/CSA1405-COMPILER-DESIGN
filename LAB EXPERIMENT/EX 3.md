#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char ch, word[20];
    int i = 0;
    char keywords[][10] = {
        "int", "char", "float", "if", "else",
        "for", "while", "return", "main", "printf"
    };

    FILE *fp = fopen("flex_input.txt", "r");

    if (fp == NULL)
    {
        printf("File not found!");
        return 0;
    }

    while ((ch = fgetc(fp)) != EOF)
    {
        /* Ignore comments */
        if (ch == '/')
        {
            ch = fgetc(fp);
            if (ch == '/')
            {
                while ((ch = fgetc(fp)) != '\n' && ch != EOF);
                continue;
            }
            else
                ungetc(ch, fp);
        }

        /* Operators */
        if (strchr("+-*/%=", ch))
            printf("%c is operator\n", ch);

        /* Identify words */
        if (isalnum(ch))
        {
            word[i++] = ch;
        }
        else if ((isspace(ch) || strchr("();,{}\"", ch)) && i > 0)
        {
            int j, found = 0;
            word[i] = '\0';
            i = 0;

            for (j = 0; j < 10; j++)
            {
                if (strcmp(word, keywords[j]) == 0)
                {
                    found = 1;
                    break;
                }
            }

            if (found)
                printf("%s is keyword\n", word);
            else
                printf("%s is identifier\n", word);
        }
    }

    fclose(fp);
    return 0;
}
<img width="1600" height="1200" alt="WhatsApp Image 2026-10-06 at 10 17 46 AM" src="https://github.com/user-attachments/assets/3711c84c-e527-4705-aecd-02840733ec24" />
