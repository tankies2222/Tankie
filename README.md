# Tankie
# K-Drama Rating App

kdramas = {}

while True:
    print("\n=== K-Drama Rating App ===")
    print("1. Rate a K-Drama")
    print("2. View Ratings")
    print("3. Exit")

    choice = input("Choose an option (1-3): ")

    if choice == "1":
        drama = input("Enter K-Drama name: ")

        try:
            rating = float(input("Enter rating (1-10): "))

            if 1 <= rating <= 10:
                if drama not in kdramas:
                    kdramas[drama] = []

                kdramas[drama].append(rating)
                print(f"Rating added for {drama}!")
            else:
                print("Rating must be between 1 and 10.")

        except ValueError:
            print("Please enter a valid number.")

    elif choice == "2":
        if not kdramas:
            print("No ratings yet.")
        else:
            print("\nK-Drama Ratings:")
            for drama, ratings in kdramas.items():
                average = sum(ratings) / len(ratings)
                print(f"{drama}: {average:.1f}/10 ({len(ratings)} ratings)")

    elif choice == "3":
        print("Goodbye!")
        break

    else:
        print("Invalid option. Please choose 1, 2, or 3.")
