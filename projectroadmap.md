import json

def add_recipe():
 name = input("Enter recipe name: ")
    ingredients = input("Enter recipe ingredients (separated by commas): ")
    directions = input("Enter recipe directions: ")
    
with open("recipes.json", "r") as f:
        data = json.load(f)
        data[name] = {"ingredients": ingredients.split(", "), "directions": directions}
    
 with open("recipes.json", "w") as f:
        json.dump(data, f)
