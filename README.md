# EPM-Assignment-Fardin-Wafi-
"""
EPM Assignment for crystal structure
Group-7 (Batch--57)
ID:241-141-001
   241-141-010
"""

import math

structure = input("write crystal structure (BCC or FCC): ").strip().upper()

if structure not in ["BCC", "FCC"]:
    print("Error: Only allow 'BCC' or 'FCC'.")
    exit()

#Data input
density = float(input("write the density (kg/m³):"))
atomic_mass = float(input("write the atomic mass (kg/mol):"))
Na_number = float(input("write Na number (atoms/mol):"))


if structure == "BCC":
    n = 2
elif structure == "FCC":
    n = 4


a = ((n * atomic_mass) / (density * Na_number)) ** (1 / 3)


if structure == "BCC":
    R = (math.sqrt(3) * a) / 4
elif structure == "FCC":
    R = (math.sqrt(2) * a) / 4

atomic_concentration = n / (a ** 3) / 1e6

print(f"Lattice parameter (a): {a:.6e} m")
print(f"Atomic radius (R): {R:.6e} m")
print(f"Atomic concentration: {atomic_concentration:.6e} atoms/cm³")
