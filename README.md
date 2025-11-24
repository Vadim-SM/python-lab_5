# python-lab_5

# словник: країна : (населення млн, площа тис.км2)
countries = {
    "Ukraine": (36.7, 603.7),
    "Poland": (38.2, 312.7),
    "Germany": (83.1, 357.4),
    "France": (67.5, 643.8),
    "Spain": (47.4, 505.9),
    "Italy": (59.6, 301.3),
    "Netherlands": (17.4, 41.5),
    "Belgium": (11.6, 30.7),
    "Czechia": (10.5, 78.8),
    "Portugal": (10.3, 92.1)
}

def print_dict(d):
    for key in d:
        print(key, d[key])

def add_country(d, name, population, area):
    d[name] = (population, area)

def delete_country(d, name):
    if name in d:
        del d[name]

def print_sorted(d):
    for key in sorted(d.keys()):
        print(key, d[key])

def max_density(d):
    max_name = ""
    max_val = 0
    for name, (pop, area) in d.items():
        density = (pop * 1_000_000) / (area * 1_000)
        if density > max_val:
            max_val = density
            max_name = name
    return max_name, max_val


print("Весь словник:")
print_dict(countries)

print("\nДодаємо Austria:")
add_country(countries, "Austria", 8.9, 83.9)
print_dict(countries)

print("\nВидаляємо Spain:")
delete_country(countries, "Spain")
print_dict(countries)

print("\nСортований словник:")
print_sorted(countries)

name, density = max_density(countries)
print("\nКраїна з найбільшою щільністю населення:")
print(name, "-", round(density, 2), "ос/км2")
