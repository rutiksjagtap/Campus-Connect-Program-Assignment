# Campus-Connect-Program-Assignment
Q.Write a program to print all Perfect numbers between 1 to n
#include <stdio.h>
int main()
{
 int i, j, start, end, sum;
 /* Input lower and upper limit from user */
 printf("Enter lower limit: ");
 scanf("%d", &start);
 printf("Enter upper limit: ");
 scanf("%d", &end);
 printf("All Perfect numbers between %d to %d:\n", start, end);
 
 /* Iterate from start to end */
 for(i=start; i<=end; i++)
 {
 sum = 0;
 /* Check whether the current number i is Perfect number or not */
 for(j=1; j<i; j++)
 {
 if(i % j == 0)
 {
 sum += j;
 }
 }
 /* If the current number i is Perfect number */
 if(sum == i)
 {
 printf("%d, ", i);
 }
 }
 return 0;
}
o/p:-
Enter lower limit: 1
Enter upper limit: 50
All Perfect numbers between 1 to 50:
6, 28.
Q.Find total occurrences of each digits (0-9) using function.
#include <stdio.h>
/*function to get occurrence of a digit in a number*/
int findOccurrence(int num,int dig)
{
 int rem, cnt;
 
 cnt=0;
 while(num>0)
 {
 rem=num%10;
 if(rem==dig)
 cnt++;
 num/=10;
 } 
 return cnt;
}
 
int main()
{
 int num, digit, cnt;
 
 printf("Enter a number: ");
 scanf("%d",&num);
 printf("Enter digit to search: ");
 scanf("%d",&digit);
 
 cnt=findOccurrence(num,digit);
 
 printf("Total occurrence of digit is: %d in number: 
%d.",cnt,num);
 
 return 0;
}
o/p:-
Enter a number: 23111
Enter digit to search: 1
Total occurrence of digit is: 3 in number: 23111.
Q.Number to words
#include <stdio.h>
#include <math.h>
int main()
{
 int n, num = 0, digits;
 /* Input number from user */
 printf("Enter any number to print in words: ");
 scanf("%d", &n);
 
 /* Find total digits in n */
 digits = (int) log10(n);
 /* Store reverse of n in num */
 while(n != 0)
 {
 num = (num * 10) + (n % 10);
 n /= 10;
 }
 
 /* Find total trailing zeros */
 digits = digits - ((int) log10(num)); 
 /* 
 * Extract last digit of number and print corresponding number in 
words 
 * till num becomes 0
 */
 while(num != 0)
 {
 switch(num % 10)
 {
 case 0:
 printf("Zero ");
 break;
 case 1:
 printf("One ");
 break;
 case 2:
 printf("Two ");
 break;
 case 3:
 printf("Three ");
 break;
 case 4:
 printf("Four ");
 break;
 case 5:
 printf("Five ");
 break;
 case 6:
 printf("Six ");
 break;
 case 7:
 printf("Seven ");
 break;
 case 8:
 printf("Eight ");
 break;
 case 9:
 printf("Nine ");
 break;
 }
 
 num /= 10;
 }
 
 /* Print all trailing zeros */
 while(digits)
 {
 printf("Zero ");
 digits--;
 }
 
 return 0;
}
o/p:-
Enter any number to print in words: 362001
Three Six Two Zero Zero One
