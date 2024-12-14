# Insertion-and-Shell-sort
To implement insertion and shell sort
# Function for Insertion sort

def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while ((j >= 0) and (key < arr[j])):
            arr[j + 1] = arr[j]
            j = j - 1
        arr[j + 1] = key
    print("\n Sorted List of students by using Insertion sort")
    print(arr, end=" , ")


# <*******************************************************************>

# Function for Shell sort

def shell_sort(arr, n):
    interval = n // 2
    while interval > 0:
        for i in range(interval, n):
            temp = arr[i]
            j = i
            while ((j >= interval) and (arr[j - interval] > temp)):
                arr[j] = arr[j - interval]
                j = j - interval
            arr[j] = temp
        interval = interval // 2
    print("\n Sorted List of students by using Shell sort")
    print(arr, end=" , ")


# <******************************************************************>

n = int(input("Enter how many students' percentages you want to store: "))
array = []
print("Enter marks for", n, "students (Press ENTER after every student's marks): ")

for i in range(n):
    p = int(input("Percentage of student {}: ".format(i + 1)))
    array.append(p)
print("The percentages of", n, "students are: ")
print(array)

flag = 1
while flag == 1:
    print("\n---------------MENU---------------\n")
    print("1. Insertion Sort of the marks")
    print("2. Shell Sort of the marks")
    print("3. Exit")
    ch = int(input("\nEnter your choice (from 1 to 3): "))

    if ch == 1:
        insertion_sort(array)
    elif ch == 2:
        shell_sort(array, n)
    elif ch == 3:
        flag = 0
        print("Thanks for using this program!")
    else:
        print("!!Wrong Choice!! ")
        a = input("\n\nDo you want to continue (yes/no): ").lower()
        if a != "yes":
            flag = 0
            print("Thanks for using this program!")
