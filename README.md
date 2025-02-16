# NVIDIA-Stock-Data-Analysis

Acest proiect analizează datele istorice privind prețurile acțiunilor NVIDIA, dividendele și split-urile, folosind SQL Server, Excel și Tableau pentru a extrage informații esențiale despre tendințele pieței și performanța acțiunilor.

# Structura proiectului
## Baza de date și importul datelor:

### Fișiere CSV utilizate:
```
nvda_stock_price.csv
nvda_stock_dividend.csv
nvda_stock_split.csv
```
Am utilizat SQL Server pentru a crea și popula tabelele necesare.

## Analiza SQL:

### Curățarea și procesarea datelor folosind SQL:
```
Eliminarea valorilor nule și duplicate.
Crearea de coloane noi pentru calcule suplimentare (de exemplu, creșterea procentuală a prețului).
Întrebări utilizate:
Tendința prețurilor pe lună.
Dividende plătite anual.
Split-urile de acțiuni și efectul asupra prețurilor.
```
### Analiza în Excel:
```
Datele au fost exportate din SQL în Excel pentru vizualizări suplimentare.
Tabele pivot pentru analiza:
Evoluției prețurilor acțiunilor.
Performanței dividendele și sezonalității.
Dashboard-uri în Tableau:
```

Dashboard 1: Evoluția prețurilor NVIDIA în timp.\
Dashboard 2: Efectul split-urilor asupra prețurilor.\
Dashboard 3: Tendința dividendelor și performanța generală.\

# Cum să rulezi proiectul
## Importul fișierelor CSV în SQL Server:
```
Conectează-te la baza de date din SQL Server Management Studio (SSMS).
Creează tabelele folosind comenzile CREATE TABLE.
Folosește Tasks → Import Data pentru a importa fișierele CSV în tabele.
```
## Curățarea și analiza datelor:

Rulează scripturile SQL furnizate în fișierul sql_queries.sql pentru analiza datelor.

### Exportarea datelor în Excel:
```
Folosește opțiunea Export Data din SSMS pentru a transfera datele în Excel.
Creează tabele pivot și grafice pentru vizualizarea rezultatelor.
```
Vizualizarea în Tableau:
```
Importă fișierul Excel sau conectează-te direct la baza de date SQL Server din Tableau.
Creează dashboard-uri interactive pentru vizualizarea tendințelor.
Tehnologii utilizate
SQL Server: Pentru stocarea, curățarea și analiza datelor.
Microsoft Excel: Vizualizarea și analiza datelor cu tabele pivot și grafice.
Tableau: Dashboard-uri interactive pentru explorarea datelor.
```
# Întrebări SQL importante
## Total dividende plătite pe an:
```
sql
Copy
Edit
SELECT YEAR(date) AS year, SUM(dividend) AS total_dividend
FROM nvda_stock_dividend
GROUP BY YEAR(date)
ORDER BY year;
```
## Evoluția prețurilor pe lună:
```
sql
Copy
Edit
SELECT FORMAT(price_date, 'yyyy-MM') AS month, AVG(close_price) AS avg_close_price
FROM nvda_stock_price
GROUP BY FORMAT(price_date, 'yyyy-MM')
ORDER BY month;
```
# Concluzii
După analiza datelor istorice privind prețurile, dividendele și split-urile acțiunilor NVIDIA, am obținut următoarele concluzii importante:

### Tendință generală de creștere:
Prețul acțiunilor NVIDIA a prezentat o creștere constantă în timp, în special în perioadele de inovație tehnologică sau expansiune a pieței. Aceasta sugerează o performanță puternică pe termen lung și încrederea investitorilor în companie.

### Impactul split-urilor de acțiuni:
Deși split-urile de acțiuni nu afectează valoarea fundamentală a companiei, ele au stimulat volumele de tranzacționare și au sporit accesibilitatea acțiunilor pentru investitorii retail. După fiecare split, prețul a arătat o tendință pozitivă de revenire și creștere.

### Dividendele:
Dividendele distribuite au fost consistente, ceea ce arată că NVIDIA menține o strategie de recompensare a investitorilor, în ciuda faptului că este o companie axată pe creștere. Acest lucru indică o poziție financiară solidă.

### Sezonalitatea:
Am identificat o anumită sezonalitate în prețurile acțiunilor și dividende, cu creșteri semnificative în perioadele de lansare de produse noi sau anunțuri financiare importante.

