<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 1: Python Coding Exercises

_Authors: Joseph Nelson (DC) _

---

The following code challenges are drawn from common exercises used in technical interviews.

Please note that there may be several ways to approach each challenge. If you get stuck, try mapping out your approach in pseudocode first. Finally, while solutions to problems like these may be found online, remember that if you copy/paste code that you can't explain, you'll be missing out on the point of the project. The only way to truly learn a new skill is through practice, trial, and error - we can only help you improve by understanding where you are having trouble.

### Challenge 1: Largest Palindrome
A palindromic number reads the same both ways. For example, 1234321 is a palindrome. The largest palindrome made from the product of two two-digit numbers is 9009 = 91 × 99. Find the largest palindrome made from the product of two three-digit numbers. Afterward, write a brief explanation walking through your code's logic in markdown.


```python
#declare variable to hold the palindrome numbers 
palin_val  = 0 

#loop function for the first 3-digits
for num1 in range (100, 999):        
    
    #loop function for the second 3-digits 
    for num2 in range (100, 999):          
        
        #multiply the first 3-digits and the second 3-digits 
        prod_num = num1 * num2                   
        if str(prod_num) == str(prod_num)[::-1]: 
            
            #if the product of the two numbers is bigger than value stores in palin_val, store the value. 
            if prod_num > palin_val:
                palin_val = prod_num
                
print("largest palindrome: {}".format(palin_val))
```

    largest palindrome: 906609
    

#### Explanation: 

First, we declare the a variable called `palin_val` to hold the palindrome numbers and initialize the value to 0. Then, we find the largest palindrome based on the multiplication of two 3-digit number. We check each of the the 3-digit number ranging from least 3-digit number `(100)` to the most 3-digit number `(999)` using loop function for the first 3-digit and iterate inside the first iteration for the second 3-digit number. 

The 3-digit numbers from both iterations then will be multiplied and the result is stored inside `prod_num`. To check whether the result is palindrome or otherwise, we check the `prod_num` value from backward and compare with the result. If the backward form and the result is similar, we proceed to compare whether the result is bigger than the value stores inside `palin_val` variable  


### Challenge 2: Summation of Primes
The sum of the primes below 10 is 2 + 3 + 5 + 7 = 17. Find the sum of all the primes below 2,000. Afterward, write a brief explanation walking through your code's logic in markdown.


```python
#variable to hold sum of primes
total_prime = 0

#find the prime num ranging 1 t0 2000 (below 2000)
for primeNum in range(1, 2000):
    
    #starts iterating with 2 because prime number starts from 2. 
    if primeNum > 1:
        for num in range(2, primeNum):
            
            #stop operation if the number is a divisible number 
            if(int(primeNum % num) == 0):
                break
        else:
            
            #sum the value of total_prime and the prime number value 
            total_prime += primeNum
            
print("Sum of prime numbers below 2000 is {}".format(total_prime))
```

    Sum of prime numbers below 2000 is 277050
    

#### Explanation 

First, we declare a variable to hold the sum of the prime number and initialize its value to 0. Then we find the prime number below 2000 by using loop function. The operation starts iterating from 2 to the 2000 and find the modulo of prime number and the number below 2000. If the remainder of the result is zero, the operation stops. To find the sum of prime numbers below 2000, sum the value inside `total_prime` variable and the prime number

### Challenge 3: Multiples of 3 and 5
If we list all of the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6, and 9. The sum of these multiples is 23. Find the sum of all the multiples of 3 and 5 below 1,000. Afterward, write a brief explanation walking through your code's logic in markdown.


```python
#initialise the sum of the multiples 3 and 5 
sumNum = 0

#find the number ranging from 1 to 1000
for num in range (1, 1000):
    
    #check whether the number is either modulos to 3 and 5, if yes, then add the number with sumNum value
    if (num % 3 == 0 or num % 5 == 0):
        sumNum = sumNum + num
    else:
        sumNum = sumNum + 0 

print("Sum of Multiples of 3 and 5: ", sumNum)
```

    Sum of Multiples of 3 and 5:  233168
    

### Challenge 4: String Compressor
Implement a method to perform basic string compression using the counts of repeated characters. (This is called run-length encoding.) For example, the string "aabcccccaaa" would become a2b1c5a3. If the “compressed” string would not become smaller than the original string, your method should return the original string. You can assume the string has only uppercase and lowercase letters (a–z). Specify whether your solution is case sensitive or case insensitive and what you would need to change to make it the other. Afterward, write a brief explanation walking through your code's logic in markdown.


```python
sentence = "aaaaabbbbcccdd"
```


```python
def string_compress(sentence):
    index = 0
    compressed_sentence = ""
    string_len  = len(sentence)
    
    while index != string_len:
        count = 1
        while (index < string_len - 1) and (sentence[index] == sentence[index + 1]):
            count = count + 1
            index = index + 1
        if count == 1:
            compressed_sentence += str(sentence[index])
        else:
            compressed_sentence += str(sentence[index]) + str(count)
        
        index = index + 1
        
    return compressed_sentence
```


```python
print("Compressed String: ", string_compress(sentence))
```

    Compressed String:  a5b4c3d2
    

### *BONUS* Challenge: FizzBuzz
Write a program that prints all of the numbers from 1 to 100. For multiples of 3, instead of the number, print "Fizz;" for multiples of 5, print "Buzz." For numbers that are multiples of both 3 and 5, print "FizzBuzz." Afterward, write a brief explanation walking through your code's logic in markdown.


```python
for num in range (1, 100):
    
    if num % 15 == 0:
        print('FizzBuzz')
    elif num % 3 == 0:
        print("Fizz")
    elif num % 5 == 0: 
        print("Buzz")
    else:
        print(num)
```


```python

```
