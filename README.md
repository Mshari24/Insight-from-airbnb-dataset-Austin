# Insight-from-airbnb-dataset-Austin

```
calendar.available.value_counts()
```

1-<img width="351" alt="Screenshot 2025-02-24 at 2 52 01 PM" src="https://github.com/user-attachments/assets/15fabe45-b38e-4480-ac43-abac027f0a9e" />

```
availability_percentage = calendar['available'].value_counts(normalize=True) * 100 availability_percentage
```

2-<img width="735" alt="Screenshot 2025-02-24 at 2 53 07 PM" src="https://github.com/user-attachments/assets/afda178d-98de-42f4-8984-c1d9c360315b" />

```
busiest_dates = calendar[calendar['available'] == 'f']['date'].value_counts()
print("Busiest Dates:")
print(busiest_dates.head())
```
3-<img width="649" alt="Screenshot 2025-02-24 at 2 53 40 PM" src="https://github.com/user-attachments/assets/7be1dba6-9ebe-4f49-a1c3-6cbfe02ce05b" />

```
import matplotlib.pyplot as plt
availability_percentage.plot(kind='bar', color=['green', 'red'])
plt.title('Availability Percentages')
plt.ylabel('Percentage')
plt.xlabel('Available (t/f)')
plt.show()
```
4-<img width="726" alt="Screenshot 2025-02-24 at 2 54 35 PM" src="https://github.com/user-attachments/assets/204bcc69-52ec-45bb-bf20-133b4acf52e0" />

```
busiest_dates.head(10).plot(kind='bar', color='orange')
plt.title('Top 10 Busiest Dates')
plt.ylabel('Number of Listings Unavailable')
plt.xlabel('Date')
plt.show()
```
5-<img width="776" alt="Screenshot 2025-02-24 at 2 55 54 PM" src="https://github.com/user-attachments/assets/c1996365-afcd-45e3-bf81-a14c2701c2e9" />
```
listings.columns
```
6-<img width="536" alt="Screenshot 2025-02-24 at 3 09 36 PM" src="https://github.com/user-attachments/assets/d4bac5ec-14e5-4145-bc1f-9fb45f47bdac" />

```
import matplotlib.pyplot as plt
price_by_room = listings.groupby('room_type')['price'].mean()
print(price_by_room)

# Plot price by room type
price_by_room.plot(kind='bar', color='cyan')
plt.title('Average Price by Room Type')
plt.ylabel('Average Price')
plt.xlabel('Room Type')

plt.show()
```
7-<img width="619" alt="Screenshot 2025-02-24 at 3 07 50 PM" src="https://github.com/user-attachments/assets/143e3222-cd94-4127-9668-050417a4322a" />


```
neighborhood_counts = listings['neighbourhood'].value_counts().head(10)
print("Top 10 Neighborhoods by Listings:")
print(neighborhood_counts)

# Plot neighborhoods with most listings
neighborhood_counts.plot(kind='bar', color='lightcoral')
plt.title('Top 10 Neighborhoods by Listings')
plt.ylabel('Number of Listings')
plt.xlabel('Neighborhood')
plt.xticks(rotation=90)
plt.show()

```
8-<img width="557" alt="Screenshot 2025-02-24 at 3 11 51 PM" src="https://github.com/user-attachments/assets/42c51a82-0492-41cb-a10d-71b84328e96e" />
```
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 6))
sns.scatterplot(data=listings, x='longitude', y='latitude', hue='price', palette='viridis', size='price', sizes=(10, 200))
plt.title('Geographical Distribution of Listings (Price Colored)')
plt.xlabel('Longitude')
plt.ylabel('Latitude')
plt.show()
```
9-<img width="828" alt="Screenshot 2025-02-24 at 3 13 45 PM" src="https://github.com/user-attachments/assets/358106a1-d764-476f-90d8-714cd4638046" />






