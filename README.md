# Lesanth-N.py-training-placement

1.Create a list of first 10 natural numbers. And write a program to find the lists of odd numbers and even numbers separately. And, to find the square of its odd and even lists
    numbers = list(range(1, 11))

odd_numbers = [num for num in numbers if num % 2 != 0]
even_numbers = [num for num in numbers if num % 2 == 0]

squares_odd = [num ** 2 for num in odd_numbers]
squares_even = [num ** 2 for num in even_numbers]

print("Odd Numbers:", odd_numbers)
print("Even Numbers:", even_numbers)
print("Squares of Odd Numbers:", squares_odd)
print("Squares of Even Numbers:", squares_even)

OUTPUT:
Odd Numbers: [1, 3, 5, 7, 9]
Even Numbers: [2, 4, 6, 8, 10]
Squares of Odd Numbers: [1, 9, 25, 49, 81]
Squares of Even Numbers: [4, 16, 36, 64, 100]

2.Write a program to find the largest and smallest number in the list without using the in-built function.

def find_max_min(numbers):
    if not numbers:
        return None, None

    max_num = numbers[0]
    min_num = numbers[0]

    for num in numbers:
        if num > max_num:
            max_num = num
        elif num < min_num:
            min_num = num

    return max_num, min_num

numbers_list = [10, 5, 20, 3, 15]
largest, smallest = find_max_min(numbers_list)
print(f"Largest number: {largest}")
print(f"Smallest number: {smallest}")

OUTPUT:
Largest number: 20
Smallest number: 3

3.Write a program to find the second largest and second smallest number in the list without using the in-built function.

def find_second_largest_smallest(input_list):
    first_max = second_max = float('-inf')
    first_min = second_min = float('inf')

    for num in input_list:
        if num > first_max:
            second_max = first_max
            first_max = num
        elif num > second_max and num != first_max:
            second_max = num

        if num < first_min:
            second_min = first_min
            first_min = num
        elif num < second_min and num != first_min:
            second_min = num

    return second_max, second_min

numbers = [5, 2, 8, 1, 9, 4]
second_largest, second_smallest = find_second_largest_smallest(numbers)
print("Second Largest Number:", second_largest)
print("Second Smallest Number:", second_smallest)

OUTPUT:
Second Largest Number: 8
Second Smallest Number: 2

4.Write a program to sort elements stored in the list as Ascending order and Descending order without using the in-built function (sort ()).
Eg: [5,3,7,9,8,4,2] Output: [2,3,4,5,7,8,9] – Ascending Order, [9,8,7,5,4,3,2] – Descending Order

def custom_sort_ascending(input_list):
    for i in range(len(input_list)):
        for j in range(i + 1, len(input_list)):
            if input_list[i] > input_list[j]:
                input_list[i], input_list[j] = input_list[j], input_list[i]
    return input_list

def custom_sort_descending(input_list):
    for i in range(len(input_list)):
        for j in range(i + 1, len(input_list)):
            if input_list[i] < input_list[j]:
                input_list[i], input_list[j] = input_list[j], input_list[i]
    return input_list

input_list = [5, 3, 7, 9, 8, 4, 2]
ascending_order = custom_sort_ascending(input_list.copy())
descending_order = custom_sort_descending(input_list.copy())

print("Ascending Order:", ascending_order)
print("Descending Order:", descending_order)


OUTPUT:
Ascending Order: [2, 3, 4, 5, 7, 8, 9]
Descending Order: [9, 8, 7, 5, 4, 3, 2]

5.Find the index position of the specific number stored in the list. Eg: a= [45,67,83,24,55,87,77,34] What is the position of 55? Output: 4

a = [45, 67, 83, 24, 55, 87, 77, 34]
index_position = a.index(55)
print("The position of 55 in the list is:", index_position)

OUTPUT:
The most frequent element in the list is: 4

7. Below are the two lists. Write a Python program to convert them into a dictionary in a way that item from list1 is the key and item from list2 is the value by using update method ().
keys = ['Ten', 'Twenty', 'Thirty']
values = [10, 20, 30]
Output:
{'Ten': 10, 'Twenty': 20, 'Thirty': 30}

keys = ['Ten', 'Twenty', 'Thirty']
values = [10, 20, 30]

result_dict = {}
for key, value in zip(keys, values):
    result_dict.update({key: value})

print(result_dict)

OUTPUT:
{'Ten': 10, 'Twenty': 20, 'Thirty': 30}

8. Create a list of 10 members as a Voter_list. Assume that there are 3 Candidates (A, B & C) are going to contest in the election process. Write a program that voters will cast their votes and predict the Winner and Runner of the election process and to find the members who voted for the Winner and Runner.

print("candidates: virat kholi dhoni")
print("1 for virat as well as enter 2 and 3 for kholi and dhoni then 4 for nota")
voters=["luffy","zoro","nami","sanji","usopp","chopper","robin","franky","brook","zimbei"]

v=0
k=0
d=0
n=0
for i in voters:
    vote=int(input(f"voters-{i}: "))
    if vote==1:
        v+=1
    elif vote==2:
        k+=1
    elif vote==3:
        d+=1
    else:
        n+=1

print(f"virat count={v}",f"kholi count: {k}",f"dhoni count: {d}",f"nota count: {n}",sep="\n")

if(v > k or d or n):
    print("Winner virat")
elif(k > v or d or n):
    print("winner kholi")
elif(d > n or k or v):
    print("winner dhoni")
elif(n > v or k or d):
    print("nota")

OUTPUT:
candidates: virat kholi dhoni
1 for virat as well as enter 2 and 3 for kholi and dhoni then 4 for nota
voters-luffy: 1
voters-zoro: 2
voters-nami: 3
voters-sanji: 1
voters-usopp: 2
voters-chopper: 3
voters-robin: 1
voters-franky: 2
voters-brook: 3
voters-zimbei: 1
virat count=4
kholi count: 3
dhoni count: 3
nota count: 0
Winner virat

9. Write a program to calculate the following functions:
	1. India (Rupee) to US (Dollar) conversion
	2. Celsius to Fahrenheit
	3. BMI Calculation
	4. Simple Interest Calculation

def inr_to_usd(inr_amount):
    return inr_amount/83.160

def celsius_to_fahrenheit(celsius_temp):
    return (celsius_temp * 9/5)+32

def calculate_bmi(weight_kg, height_m):
    return weight_kg / (height_m ** 2)

def calculate_simple_interest(principal, rate, time):
    return (principal * rate * time)/100

print("INR to USD:", inr_to_usd(1000))
print("Celsius to Fahrenheit:", celsius_to_fahrenheit(25))
print("BMI Calculation:", calculate_bmi(70, 1.75))
print("Simple Interest Calculation:", calculate_simple_interest(1000, 5, 2))

OUTPUT:
INR to USD: 12.025012025012025
Celsius to Fahrenheit: 77.0
BMI Calculation: 22.857142857142858
Simple Interest Calculation: 100

10.Write a program to get 0s and 1s in the list: Eg: Input list= [0,1,0,1,1,0,1,0,1,0] Output:
[0,0,0,0,0,1,1,1,1,1]

input_list = [0, 1, 0, 1, 1, 0, 1, 0, 1, 0]
output_list = sorted(input_list)
print(output_list)

OUTPUT:
[0, 0, 0, 0, 0, 1, 1, 1, 1, 1]
