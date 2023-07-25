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
