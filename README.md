# High Level Plans

## Step 1: Define the Purpose and Use Cases of the Chatbot
Before diving into the technical details, it's crucial to define what you want the chatbot to do. Here are some possible use cases:

- Answer questions about specific products (ingredients, nutritional information, pricing).

- Recommend dips or soups based on customer preferences (dietary restrictions, meal pairings).

- Provide suggestions for meal planning or event catering.

- Making dip suggestions based on wine, food or beverage compliment.

- For each dip it should suggest different dipping options like carrots sticks or types of crackers

## Step 2: Build the Dataset
To build the correct dataset of questions and answers, you’ll need a well-structured approach.

Let's start with a file of basic questions we can iterate on.
- /question/questions.csv


### 2.1. Collect Product Information
- **Product details:** Gather all the available information about each product. This includes the product name, ingredients, nutritional facts, potential allergens, and serving suggestions.

- **Categorize products:** Group products into categories like vegan, gluten-free, low-carb, etc.

- **Meal pairings:** Include suggested pairings for dips with certain meals (e.g., bread, chips) or soups with meals (e.g., sandwiches).


### 2.2. Generate Frequently Asked Questions (FAQ)
 - **Customer interactions:**  If your friend has any existing customer support records, use that data to find common questions customers ask.

- **Product questions:** Create a list of questions customers might ask about products. Example: “What ingredients are in this dip?” or “Is this soup gluten-free?”


- **Recommendation queries:** Build questions for recommendations. Example: “What dips go well with tacos?” or “What are good vegan options?”

- **Nutritional queries:** Create questions about nutritional value. Example: “How many calories are in this soup?” or “Is this dip low-fat?”

Use a local LLM to say iterate over questions.csv and products.csv to generate synthetic questions / answer pairs.

Use LLM to score and review Q/A pairs.

### 2.3. Data Formatting for Training
Question-answer pairs: Format the questions and answers into pairs. Each entry should have a clear structure, like:

``` json
{
  "question": "What ingredients are in the spicy bean dip?",
  "answer": "The spicy bean dip contains black beans, red chili peppers, garlic, and lime."
}
```

Store question and answer pairs in ./data-prep for each reviewing by product before consolidating into parquet file.

## Step 3. Aproaches
Can use either fine-tuning or rag for this.

## Step 4: Evaluation and Improvement
- **Testing:** Need a testing strategy
- **User Feedback:** User feedback, monitor and evaluate performance.
- **Retraining:** Periodically update data and re fine-tune the model when things change.