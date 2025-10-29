* Welcome to the Fast Food Nutrition Dataset, which provides a comprehensive breakdown of the nutritional content of various fast food products from popular fast food chains.

* Fast food is known for its convenience and affordability, but it is also infamous for its high-calorie, high-fat, and high-sugar content.

* This dataset aims to shed light on the nutritional value of these fast food products, helping consumers make more informed decisions about their food choices.

* With information on calories, fat, carbohydrates, protein, and other key nutrients, this dataset provides a valuable resource for nutritionists, researchers, and health-conscious individuals. 

* By analyzing this dataset, we can gain a better understanding of the nutritional impact of fast food consumption and work towards creating healthier food options in the fast food industry.
## OBJECTIVE AND ANSWERS
1. Number of menu items per restaurant
```plt.figure(figsize=(8,6))
sns.countplot(x='restaurant', data=df, palette='coolwarm', edgecolor='black')
plt.title('Number of Menu Items per Restaurant')
plt.xlabel('Restaurant')
plt.tight_layout()
plt.ylabel('Count')
plt.show()
```
2. Show to plot bar plot of Distribution of calories across fastfood 
```sns.histplot(df['calories'], bins=5, kde=True, color='lime', edgecolor='black')
plt.title("Distribution of Calories Across Fast Food Items")
plt.xlabel("Calories")
plt.ylabel("Frequency")
plt.show()
```
3. Compare nutrients in Mcdonalds Menu
```sns.pairplot(df[['calories', 'total_fat', 'protein', 'sodium']], diag_kind='hist')
plt.suptitle("Pairplot: Comparing Nutrients in McDonald's Menu", y=1.02)
plt.show()
```
4. show the barplot of top 10 items which have high protein content 
c = df.sort_values('protein', ascending=False).head(10)
sns.barplot(x='item', y='protein', data=c, palette='inferno')
```
plt.title("Top 10 Items by Protein Content")
plt.xlabel("Item")
plt.ylabel("Protein (g)")
plt.xticks(rotation=90)
plt.show()
```
5. show the correlation of 1st 100 items in Mcdonalds
```df= df.corr(numeric_only=True)
plt.figure(figsize=(8,6))
sns.heatmap(df, annot=True, cmap='coolwarm', fmt=".2f")
plt.title(" First 100 McDonald's Items")
plt.show()
```