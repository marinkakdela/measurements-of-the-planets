# measurements-of-the-planets
import matplotlib.pyplot as plt
import numpy as np

# Data for the planets
planets = [
    {"name": "Mercury", "distance_from_sun": 57.9, "diameter": 4879, "orbital_period": 88},
    {"name": "Venus", "distance_from_sun": 108.2, "diameter": 12104, "orbital_period": 225},
    {"name": "Earth", "distance_from_sun": 149.6, "diameter": 12742, "orbital_period": 365.25},
    {"name": "Mars", "distance_from_sun": 227.9, "diameter": 6779, "orbital_period": 687},
    {"name": "Jupiter", "distance_from_sun": 778.3, "diameter": 139820, "orbital_period": 4331},
    {"name": "Saturn", "distance_from_sun": 1427, "diameter": 116460, "orbital_period": 10747},
    {"name": "Uranus", "distance_from_sun": 2871, "diameter": 50724, "orbital_period": 30589},
    {"name": "Neptune", "distance_from_sun": 4495, "diameter": 49244, "orbital_period": 59800}
]

# Function to plot the solar system
def plot_solar_system(planets):
    fig, ax = plt.subplots()
    ax.set_aspect('equal')
    ax.set_xlim(-5000, 5000)
    ax.set_ylim(-5000, 5000)

    # Plotting the orbits and planets
    for planet in planets:
        orbit = plt.Circle((0, 0), planet["distance_from_sun"], color='gray', fill=False)
        ax.add_artist(orbit)
        ax.plot(planet["distance_from_sun"], 0, 'o', label=planet["name"])
        ax.text(planet["distance_from_sun"], 0, f' {planet["name"]}', verticalalignment='center')

    plt.title('Solar System')
    plt.xlabel('Distance from Sun (million km)')
    plt.ylabel('Distance from Sun (million km)')
    plt.legend(loc='upper right')
    plt.grid(True)
    plt.show()

# Display planetary data
for planet in planets:
    print(f"Planet: {planet['name']}")
    print(f"  Distance from Sun: {planet['distance_from_sun']} million km")
    print(f"  Diameter: {planet['diameter']} km")
    print(f"  Orbital Period: {planet['orbital_period']} days")
    print()

# Plot the solar system
plot_solar_system(planets)
456
