def show_all(countries):
    print("\nДані про держави:")
    for country, data in countries.items():
        population, area = data
        density = population / area
        print(f"{country}: населення = {population} млн, площа = {area} тис. км², щільність = {density:.2f}")

def max_density_country(countries):
    max_density = 0
    max_country = ""

    for country, data in countries.items():
        population, area = data
        density = population / area

        if density > max_density:
            max_density = density
            max_country = country

    print(f"\nДержава з максимальною щільністю населення: {max_country}")
    print(f"Щільність населення: {max_density:.2f} млн/тис.км²")


countries = {
    "Україна": (41, 603),
    "Польща": (38, 312),
    "Німеччина": (83, 357),
    "Франція": (65, 643),
    "Італія": (60, 301),
    "Іспанія": (47, 505),
    "Японія": (125, 378),
    "Китай": (1440, 9597),
    "Індія": (1400, 3287),
    "Велика Британія": (67, 244)
}

show_all(countries)
max_density_country(countries)
