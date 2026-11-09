import json

def generate_coc_army_clone():
    # Define the Clash of Clans army composition template
    army_config = {
        "army_name": "Standard Clone War Army",
        "housing_space_total": 280,
        "troops": [
            {"name": "Super Dragon", "count": 5, "housing_space": 40},
            {"name": "Balloon", "count": 8, "housing_space": 5},
            {"name": "Dragon Rider", "count": 3, "housing_space": 25}
        ],
        "spells": [
            {"name": "Clone Spell", "count": 3, "housing_space": 3},
            {"name": "Rage Spell", "count": 2, "housing_space": 2},
            {"name": "Freeze Spell", "count": 1, "housing_space": 1}
        ],
        "siege_machine": {
            "name": "Battle Blimp",
            "cc_troops": ["Super Archer", "Sneaky Goblin"]
        }
    }

    # Serialize to formatted JSON string
    json_output = json.dumps(army_config, indent=4)
    return json_output

if __name__ == "__main__":
    print(generate_coc_army_clone())
