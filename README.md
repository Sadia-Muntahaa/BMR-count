# BMR-count
Basal Metabolic Rate (BMR) represents the number of calories your body needs to perform basic life-sustaining functions such as breathing, circulation, and cell production. It serves as the foundation for determining your total calorie requirements.
weight = float(input('Enter your weight in kg: '))
height = float(input('Enter your height in cm: '))
age = float(input('Enter your age in years: '))
gender = input('Enter your gender (1 for male, 2 for female): ')
bmr = 0  # Initialize BMR
if gender == "1":
    bmr = 66.47 + (13.75 * weight) + (5.003 * height) - (6.755 * age)
    print(f"Your BMR (Male): {bmr:.2f} calories/day")
elif gender == "2":
    bmr = 655.1 + (9.563 * weight) + (1.85 * height) - (4.676 * age)
    print(f"Your BMR (Female): {bmr:.2f} calories/day")
else:
    print('Enter a correct gender option (1 or 2).')
    exit()
print("\nEnter your activity level:")
activity_level = input(
    "1. Sedentary (Little or no exercise, desk job) \n"
    "2. Lightly active (Light exercise/sports 1–3 days per week) \n"
    "3. Moderately active (Moderate exercise/sports 3–5 days per week) \n"
    "4. Very active (Hard exercise/sports 6–7 days per week) \n"
    "5. Super active (Very hard exercise/physical job or intense training twice a day) \n"
    "Enter your choice: "
)

activity_factors = {
    "1": 1.2,
    "2": 1.375,
    "3": 1.55,
    "4": 1.725,
    "5": 1.9
}
if activity_level in activity_factors:
    total = bmr * activity_factors[activity_level]
    print(f"Your Total Daily Energy Needed: {total:.2f} calories/day")
else:
    print('Enter a correct activity level (1 to 5).')
