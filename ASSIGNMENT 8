#include<stdio.h>
struct student
{
 int rollno;
 char name[15];
 char div[3];
 char address[30];
}stud;
// INSERT RECORD
void insert()
{
 FILE *fp;
 fp = fopen("Record", "a");
 printf("Enter roll no:");
 scanf("%d", &stud.rollno);
 printf("Enter name:");
 scanf("%s", stud.name);
 printf("Enter div:");
 scanf("%s", stud.div);
 printf("Enter address:");
 scanf("%s", stud.address);
 fwrite(&stud, sizeof(stud), 1, fp);
 fclose(fp);
}
//DISPLAY RECORDS
void disp()
{
 FILE *fp1;
 fp1 = fopen("Record", "r");
 printf("\nRollNo\tName\tDiv\t\tAddress\n\n");
 while (fread(&stud, sizeof(stud), 1, fp1))
 printf("%d\t%s\t%s\t%s\n", stud.rollno, stud.name, stud.div,stud.address);
 fclose(fp1);
}

//DELETE A RECORD
void deletefile()
{
 FILE *fpo;
 FILE *fpt;
 int r, s;
 printf("Enter the Roll no you want to delete :");
 scanf("%d", &r);
 if (r == 0 || r == 21 || r == 22 || r == 23 || r==24 || r == 25 || r == 26 || r == 27 || r==28 || r == 29 || r==30)
  printf("Roll no %d is not available in the file\n", r);
 else
 {
  fpo = fopen("Record", "r");
  fpt = fopen("TempFile", "w");
  while (fread(&stud, sizeof(stud), 1, fpo))
  {
   s = stud.rollno;
   if (s != r)
    fwrite(&stud, sizeof(stud), 1, fpt);
  }
  fclose(fpo);
  fclose(fpt);
  fpo = fopen("Record", "w");
  fpt = fopen("TempFile", "r");
  while (fread(&stud, sizeof(stud), 1, fpt))
   fwrite(&stud, sizeof(stud), 1, fpo);
  printf("\nRECORD DELETED\n");
  fclose(fpo);
  fclose(fpt);
 }

}
//UPDATE THE RECORD
void update()
{
 int avl;
 FILE *fpt;
 FILE *fpo;
 int s, r, ch;
 printf("Enter roll number to update:");
 scanf("%d", &r);
 avl = r;
 if (avl == 0)
 {
  printf("Roll number %d is not Available in the file", r);
 }
 else
 {
  fpo = fopen("Record", "r");
  fpt = fopen("TempFile", "w");
  while (fread(&stud, sizeof(stud), 1, fpo))
  {
   s = stud.rollno;
   if (s != r)
    fwrite(&stud, sizeof(stud), 1, fpt);
   else
   {
    printf("\n1.Update Name of Roll Number %d", r);
    printf("\n2.Update div of Roll Number %d", r);
    printf("\n3.Update address of Roll Number %d", r);
    printf("\n4.Done");
    printf("\nEnter your choice:");
    scanf("%d", &ch);
    switch (ch)
    {
    case 1:
     printf("Enter Name:");
     scanf("%s", stud.name);
     break;

    case 2:
     printf("Enter div: ");
     scanf("%s", stud.div);
     break;

    case 3:
     printf("Enter address: ");
     scanf("%s", stud.address);
     break;
    }
    fwrite(&stud, sizeof(stud), 1, fpt);
   }
  }
  fclose(fpo);
  fclose(fpt);
  fpo = fopen("Record", "w");
  fpt = fopen("TempFile", "r");
  while (fread(&stud, sizeof(stud), 1, fpt))
  {
   fwrite(&stud, sizeof(stud), 1, fpo);
  }
  fclose(fpo);
  fclose(fpt);
  printf("RECORD UPDATED");
 }
}

int main()
{
 int c, emp;
 do
 {
  printf("\nMENU:-\n");
  printf("1.INSERT\n2.DISPLAY\n3.DELETE\n4.UPDATE\n5.EXIT");
  printf("\nEnter your choice:");
  scanf("%d", &c);

  switch (c)
  {
  case 1:
   insert();
   break;
  case 2:
    disp();
   break;
  case 3:
   deletefile();
   break;
  case 4:
   update();
   break;

  }
 } while (c!= 5);
 if(c==5)
 printf("Thank you!");
}
