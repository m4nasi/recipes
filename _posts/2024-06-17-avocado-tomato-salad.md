---
layout: post
title: "Avocado and Tomato Salad"
date: 2024-06-17 16:00:00 +0000
categories: recipes vegetarian salads
---

This refreshing **Avocado and Tomato Salad** is packed with flavour and nutrients. A light and healthy option for any meal.

## Ingredients:
- 2 ripe avocados, diced
- 2 large tomatoes, chopped
- 1/2 red onion, thinly sliced
- 1 tbsp olive oil
- 1 tbsp lemon juice
- Salt and pepper to taste
- Fresh basil leaves for garnish

## Instructions:
1. In a large bowl, combine avocados, tomatoes, and red onion.
2. Drizzle with olive oil and lemon juice.
3. Season with salt and pepper to taste.
4. Toss gently to mix, garnish with fresh basil, and serve immediately.

Perfect as a side dish or a light lunch!

<button id="export-btn">Export Ingredients</button>

<script>
    document.getElementById('export-btn').addEventListener('click', function() {
  const ingredients = [];
  const ingredientItems = document.querySelectorAll('#ingredient-list li');
  
  ingredientItems.forEach(function(item) {
    ingredients.push(item.textContent);
  });

  // Export the ingredients as a CSV, JSON, or Text file
  exportIngredientsAsCSV(ingredients);  // Or use exportIngredientsAsJSON or exportIngredientsAsText
});

// Export as CSV
function exportIngredientsAsCSV(ingredients) {
  let csvContent = "data:text/csv;charset=utf-8,Ingredient\n";  // CSV header
  ingredients.forEach(function(ingredient) {
    csvContent += ingredient + "\n";
  });

  const encodedUri = encodeURI(csvContent);
  const link = document.createElement('a');
  link.setAttribute('href', encodedUri);
  link.setAttribute('download', 'ingredients.csv');
  link.click();
}
</script>