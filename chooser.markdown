---
layout: default
title: Picker
permalink: /picker/
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recipe Picker</title>
    <style>
        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h2, h3 {
            color: #2c3e50;
        }
        label {
            font-weight: bold;
        }
        select, button {
            margin: 10px 0;
            padding: 10px;
            width: 100%;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            background-color: #3498db;
            color: #fff;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background-color: #2980b9;
        }
        #result {
            margin-top: 20px;
            padding: 10px;
            background-color: #e8f6f3;
            border: 1px solid #d1e7e0;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Answer the Questions</h2>
        <form id="recipeForm">
            <label for="mealType">What kind of meal are you in the mood for?</label>
            <select id="mealType" required>
                <option value="">-- Choose --</option>
                <option value="breakfast">Breakfast</option>
                <option value="lunch">Lunch</option>
                <option value="dinner">Dinner</option>
            </select>

            <label for="time">How much time do you have?</label>
            <select id="time" required>
                <option value="">-- Choose --</option>
                <option value="quick">Less than 30 minutes</option>
                <option value="moderate">30-60 minutes</option>
                <option value="long">More than an hour</option>
            </select>

            <label for="diet">Do you follow any dietary preferences?</label>
            <select id="diet" required>
                <option value="">-- Choose --</option>
                <option value="vegetarian">Vegetarian</option>
                <option value="vegan">Vegan</option>
                <option value="none">No preference</option>
            </select>

            <button type="button" onclick="recommendRecipe()">Get My Recipe!</button>
        </form>

        <div id="result" style="display: none;">
            <h3>Your Recommended Recipe:</h3>
            <p id="recipeOutput"></p>
        </div>
    </div>

    <script>
        function recommendRecipe() {
            const mealType = document.getElementById("mealType").value;
            const time = document.getElementById("time").value;
            const diet = document.getElementById("diet").value;

            let recipe = "Sorry, I couldn't find a recipe for you!";

            if (mealType === "breakfast" && time === "quick" && diet === "vegetarian") {
                recipe = "Avocado and Tomato Salad - Quick, fresh, and perfect for breakfast!";
            } else if (mealType === "lunch" && time === "moderate" && diet === "vegetarian") {
                recipe = "Chickpea and Spinach Curry - A hearty vegetarian lunch.";
            } else if (mealType === "dinner" && time === "long" && diet === "none") {
                recipe = "Classic Margherita Pizza - Take your time and enjoy homemade pizza!";
            } else if (mealType === "lunch" && time === "quick" && diet === "vegan") {
                recipe = "Vegetarian Stir-Fried Noodles - Quick, healthy, and completely vegan!";
            } else {
                recipe = "Welcome to Jekyll! Try exploring more recipes!";
            }

            document.getElementById("result").style.display = "block";
            document.getElementById("recipeOutput").innerText = recipe;
        }
    </script>
</body>
</html>
