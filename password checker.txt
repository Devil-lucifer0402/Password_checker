def chk_passwd_strenght(passwd):

    length = len(passwd) >= 8
    contain_upper = any(char.isupper() for char in passwd)
    contain_lower = any(char.islower() for char in passwd)
    contain_digit = any(char.isdigit() for char in passwd)
    contain_spl_char = any(char in '`~!@#$%^&*()_<>?:"{}|//' for char in passwd)

    if length and contain_upper and contain_lower and contain_digit and contain_spl_char:
        return "Strong password"
    elif length and (contain_upper or contain_lower) and contain_digit:
        return "Moderate Password"
    else:
        return "Weak Password"

passwd = input("Enter a password: ")
strength = chk_passwd_strenght(passwd)
print("")
print("Paasword Strength",strength)