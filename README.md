# Binary-To-Octal-Conversion-C-Program

Binary to Octal conversion in C
There are two approaches of converting an Binary Number into a Octal Number like

Converting Binary to Decimal and then Decimal to Octal
By grouping Binary Number into Groups of 3 digits/bits and then converting to Octal
We will cover both approaches in this post

binary to decimal in c
Method 1:-
We will first convert the Binary number into Decimal and then convert the Decimal number into Octal

Make sure that you have gone through these approaches below –

Binary to Decimal Conversion
Decimal to Octal Conversion
Method 1 Code
Run
#include<stdio.h>
#include<math.h>

// function to convert binary to octal
void convert(long long num)
{
    int octalDigit = 0, count = 1, i = 0, pos = 0;
    int octalArray[32] = {0};

    while(num != 0)
    {
        int digit = num % 10;
        
        octalDigit += digit * pow(2, i);
        i++;
        num /= 10;
        
        // placing current octalsum for 3 pair in array index position
        octalArray[pos] = octalDigit;
        
        // whenever we have read next 3 digits
        // setting values to default
        // increasing pos so next values can be placed at next array index
        if(count % 3 == 0)
        {
            octalDigit = 0;
            i = 0;
            pos++;
        }
        count++;
    }
        
    // printing octal array in reverse order
    for (int j = pos; j >= 0; j--)
        printf("%d",octalArray[j]);

}

//main program
int main()
{
    // long used rather than int to store large values
    long long binary;
    
    printf("Enter binary number: ");
    scanf("%lld", &binary);
    
    convert(binary);
    
    return 0;
}
Output :
Enter binary number: 1010
Decimal : 10
Octal : 12
While loop in C
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Permutations in which n people can occupy r seats in a classroom 

Octal to Binary conversion

Quadrants in which a given coordinate lies

Method 2:-
Method 2 uses the concept of grouping 3 successive digits/bits of the binary number and calculating octal digits against each grouping

We use an additional array to store the octal digits at each index.

We will need to print the array in reverse to get actual octal equivalent.

Method 2 Code
Run
#include<stdio.h>
#include<math.h>
// function to convert binary to octal
void convert(long long num)
{
    int octalDigit = 0, count = 1, i = 0, pos = 0;
    int octalArray[32] = {0};

    while(num != 0)
    {
        int digit = num % 10;
        
        octalDigit += digit * pow(2, i);
        i++;
        num /= 10;
        
        // placing current octalsum for 3 pair in array index position
        octalArray[pos] = octalDigit;
        
        // whenever we have read next 3 digits
        // setting values to default
        // increasing pos so next values can be placed at next array index
        if(count % 3 == 0)
        {
            octalDigit = 0;
            i = 0;
            pos++;
        }
        count++;
    }
        
    // printing octal array in reverse order
    for (int j = pos; j >= 0; j--)
        printf("%d",octalArray[j]);

}

//main program
int main()
{
    // long used rather than int to store large values
    long long binary;
    
    printf("Enter binary number: ");
    scanf("%lld", &binary);
    
    convert(binary);
    
    return 0;
}
Output :
Enter binary number: 010101
25
