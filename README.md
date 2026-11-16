# Python Analysis: Sales Performance and Profitability

## Project Overview

This project uses Python to analyze online and offline sales. It examines which categories and markets contribute the most revenue and gross profit, how sales change over time, and whether time to shipment is associated with profit per order.

## Objectives

- Compare revenue, gross profit, gross margin, and units sold across categories, markets, and sales channels.
- Identify the categories that contributed most to year-over-year revenue changes.
- Compare revenue by weekday and check whether category sales peak in the same month across years.
- Compare time to shipment across categories and markets.

## Dataset

The [source dataset](https://drive.google.com/file/d/1tBFXaUCvcJZUOsWa-Dn-G0eYO96N87br/view?usp=sharing) covers January 1, 2010 through July 23, 2017 and contains three tables:

- `events.csv` — order and shipment dates, product and country codes, sales channel, quantity, unit price, and unit cost.
- `products.csv` — product identifiers and category names.
- `countries.csv` — country names, codes, regions, and subregions.

The source does not specify a currency, so monetary figures use the original dataset units.

## Tools & Technologies

- Python and Google Colab
- pandas and NumPy for data preparation and analysis
- Matplotlib and seaborn for charts and heatmaps

## Analysis Process

1. Standardized dates and categorical fields, checked for duplicate order IDs, and removed two orders with missing quantities.
2. Joined the three tables using product and country codes. Retained 82 orders with missing country codes in company totals and excluded them from geographic rankings.
3. Calculated revenue, cost, gross profit, gross margin, and average order value.
4. Compared categories, countries, regions, and sales channels. Used a scatter plot and Pearson correlation to examine time to shipment and gross profit per order.
5. Compared weekdays and used the seven complete years from 2010 to 2016 to examine annual trends and recurring monthly peaks.

## Key Findings

- The 1,328 orders generated 1.70 billion in revenue and 501.43 million in gross profit, with a gross margin of 29.46%.
- Office Supplies led revenue (402.21 million), Cosmetics led gross profit (92.72 million), and Clothes had the highest gross margin (67.20%).
- Europe accounted for 88.5% of total revenue. Offline stores generated 51.22% of revenue, while online sales had a slightly higher gross margin (29.86% versus 29.08%).
- Revenue fell by 35.9% from 2012 to 2013. Cosmetics accounted for about 41% of the decline.
- Monday generated the most revenue (275.47 million). Friday had the highest average order value (1.50 million) and gross profit (79.23 million).
- Across all 12 categories, no single month ranked first in units sold more than twice in seven years. Time to shipment had almost no linear association with gross profit per order (Pearson’s r = 0.0603).

## Project Files

- [Analysis notebook](./Python_for_DA_Module_Task%289%29.ipynb) — data cleaning, calculations, visualizations, findings, and recommendations. To run it in Colab, save the dataset archive as `MyDrive/Jupyter/dataset.zip` or update the archive path in the notebook.

## Conclusions

Office Supplies is a priority for reviewing purchase costs and pricing: it generated the most revenue, but its gross margin was 19.39%, below the company average of 29.46%. Clothes accounted for only 3.8% of revenue despite its high margin, making it a candidate for a small assortment expansion test. Improving country-code capture would also allow 103.15 million in revenue to be attributed to specific markets.

---

# Python-аналіз: результати продажів і прибутковість

## Опис проєкту

У проєкті за допомогою Python проаналізовано онлайн- та офлайн-продажі компанії. Досліджено, які категорії й ринки формують найбільший дохід і валовий прибуток, як змінюються продажі з часом і чи пов’язаний час до відправки з прибутком замовлення.

## Мета проєкту

- Порівняти дохід, валовий прибуток, валову маржу та кількість проданих одиниць за категоріями, ринками й каналами продажу.
- Визначити, які категорії найбільше вплинули на зміну річного доходу.
- Порівняти дохід за днями тижня та перевірити, чи повторюються пікові місяці продажів у кожній категорії.
- Порівняти час до відправки за категоріями та ринками.

## Набір даних

[Вихідний набір даних](https://drive.google.com/file/d/1tBFXaUCvcJZUOsWa-Dn-G0eYO96N87br/view?usp=sharing) охоплює період із 1 січня 2010 року до 23 липня 2017 року та містить три таблиці:

- `events.csv` — дати замовлення й відправки, коди товару та країни, канал продажу, кількість, ціна й собівартість одиниці.
- `products.csv` — ідентифікатори товарів і назви категорій.
- `countries.csv` — назви та коди країн, регіони й субрегіони.

Валюту в джерелі не зазначено, тому грошові показники наведено в умовних одиницях.

## Інструменти та технології

- Python і Google Colab
- pandas і NumPy для підготовки й аналізу даних
- Matplotlib і seaborn для побудови графіків і теплових карт

## Процес аналізу

1. Приведено дати й категоріальні поля до єдиного формату, перевірено унікальність номерів замовлень і видалено два записи без кількості проданих одиниць.
2. Об’єднано три таблиці за кодами товарів і країн. У загальних показниках враховано 82 замовлення без коду країни, а географічні рейтинги побудовано за замовленнями з відомою країною.
3. Розраховано дохід, собівартість, валовий прибуток, валову маржу та середній чек.
4. Порівняно категорії, країни, регіони й канали продажу. Зв’язок між часом до відправки та валовим прибутком замовлення досліджено за допомогою діаграми розсіювання та кореляції Пірсона.
5. Порівняно продажі за днями тижня. Для аналізу річної динаміки й повторюваності місячних піків використано сім повних років — із 2010 до 2016 року.

## Основні результати

- За 1 328 замовленнями дохід становив 1,70 млрд, валовий прибуток — 501,43 млн, а валова маржа — 29,46%.
- Office Supplies забезпечила найбільший дохід (402,21 млн), Cosmetics — найбільший валовий прибуток (92,72 млн), а Clothes мала найвищу валову маржу (67,20%).
- На Європу припало 88,5% загального доходу. Офлайн-магазини забезпечили 51,22% доходу, а онлайн-продажі мали дещо вищу валову маржу (29,86% проти 29,08%).
- З 2012 до 2013 року дохід знизився на 35,9%. На Cosmetics припало близько 41% цього скорочення.
- Понеділок лідирував за доходом (275,47 млн), а п’ятниця — за середнім чеком (1,50 млн) і валовим прибутком (79,23 млн).
- У жодній із 12 категорій той самий місяць не був піковим за кількістю проданих одиниць більше ніж двічі за сім років. Лінійний зв’язок між часом до відправки та валовим прибутком замовлення майже відсутній (r Пірсона = 0,0603).

## Файли проєкту

- [Ноутбук з аналізом](./Python_for_DA_Module_Task%289%29.ipynb) — очищення даних, розрахунки, графіки, висновки та рекомендації. Для запуску в Colab збережи архів даних як `MyDrive/Jupyter/dataset.zip` або зміни шлях до архіву в ноутбуці.

## Висновки

Варто переглянути закупівельні ціни та націнки в Office Supplies. За найбільшого доходу серед категорій її валова маржа становила 19,39% проти 29,46% загалом. На Clothes припало лише 3,8% доходу за найвищої маржі, тому доцільно перевірити попит на ширший асортимент цієї категорії. Повніше заповнення кодів країн також допоможе визначити, на які ринки припадають 103,15 млн доходу від замовлень із невідомою країною.
