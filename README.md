# project-fatemehraja
project-fatemehraja created by GitHub Classroom
Fatemeh Rajaee-- 401105934
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(void)
{
    FILE *ft;
    char const *name = "abc.txt";
    int ch;
    ft = fopen(name, "r+");
    if (ft == NULL)
    {
        fprintf(stderr, "cannot open target file %s\n", name);
        exit(1);
    }
    while ((ch = fgetc(ft)) != EOF)
    {
        if (ch == 'i')
        {
            fseek(ft, -1, SEEK_CUR);
            fputc('a',ft);
            fseek(ft, 0, SEEK_CUR);
        }
    }
    fclose(ft);
    return 0;
}

int main()
{
    FILE *ft;
    char ch;
    ft=fopen("abc.txt","r+");
    if(ft==NULL)
    {
        printf("can not open target file\n");
        exit(1);
    }
    while(1)
    {
        ch=fgetc(ft);
        if(ch==EOF)
        {
            printf("done");
            break;
        }
        if(ch=='i')
        {
            fputc('a',ft);
        }
    }
    fclose(ft);
    return 0;
}

struct data
{
char name[30];
char gender[10];
int age;
};

int main(void)
{
struct data client;

FILE* fp;
char ch = 0;
do
{
    printf("Enter Name: ");
    scanf("%s", client.name);

    printf("Enter Gender: ");
    scanf("%s", client.gender);

    printf("Enter Age: ");
    scanf("%d", &client.age);

    fp = fopen("data.txt", "ab");
    fwrite(&client, sizeof(client), 1, fp);
    fclose(fp);
    printf("continue? \n");
    scanf(" %c", &ch);
} while (ch != 'n'); // continuously appends file till letter n is read;

char input[30]; // user input
printf("name?\n"); 
scanf("%s", input);

struct data Read; 
fp = fopen("data.txt", "rb");
int newAge;
while (fread(&client, sizeof(client), 1, fp))
{
    if (strcmp(client.name, input) == 0) // compare variable with user input
    {
        printf("%s", client.name);
        printf("       %s", client.gender);
        printf("      %d y/o", client.age);
        printf("\n");
        printf("enter new age"); 
        scanf("%d", &newAge);

        //fseek function
    }
}
return 0;
}
