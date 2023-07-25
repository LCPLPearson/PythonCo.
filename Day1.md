# Examples
## Format
### "example1{}".format(example2)
### f"example1 {var3} example2 {var2}"
## Split
### ".split()"
### ipaddress = "192.168.6.99".split(".")
## Join
### ".".join(ipaddress)

# CONDITIONS
    #!/usr/bin/env python3

    a = int(input("Enter a number: "))


    if a % 5 == 0 and a % 3 == 0:
    print("fizzbuzz")

    elif a % 5 == 0:
    print("buzz")

    elif a % 3 == 0:
    print("fizz")

    else:
    print(a)
# WHILE LOOP
    
    while True:

    age = int(input("How old are you: "))

    if age > 50:
        print("You get SCD!")

       elif age == 33:
            print("You win!")
            break

        elif age < 50 and age > 21:
            print("You pay the full price..")

        else:
            print("Young Adult Rate!")
# For loop

    numlist = list(range(0,101))

    for number in numlist:
    print(number *5)
    ~     

# Example

    !/usr/bin/env python3
    def guess_number(a):
    while True:
        b = int(input("enter a number: "))
        if b > a:
            print("too high")

        elif b < a:
            print("too low")

        elif a == b:
            print("win")
            break


    guess_number(23)
