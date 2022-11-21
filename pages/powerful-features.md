# Powerful Features for Patscenario? ⚡
This page covers some of Evidence's more powerful features: Loops and Logic.

# Loops

```category_sales
select
Country,
Currency,
sum(Filing_Fee) as Filing_Fee
from Mappe2_Tabelle1
group by 1
order by 2 desc
```

Die Daten kommen per SQL direkt hier rein und werden durch - ja was wohl - Svelte ausgeliefert.

## Patent Filing Fees per Countries

{#each category_sales as category_row}
- {category_row.Country}: {category_row.Filing_Fee} {category_row.Currency}


{/each}



# Und noch ein paar Daten zur Demonstration
```orders_per_day
Select
Country,
year_1,
year_2,
year_3,
year_4,
year_5,
year_6,
sum(Filing_Fee) as Filing_Fee
from Mappe2_Tabelle1
group by 1
order by 2 desc
```

<DataTable
    data={orders_per_day}
    rows=50 
/>


```claim_fee
Select
Country,
Claim_Fee

from Mappe2_Tabelle1
WHERE Claim_Fee IS NOT NULL;

order by 2 desc
```

<BarChart
    data={claim_fee} 
    x=Country
    y=Claim_Fee
/>


