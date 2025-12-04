## pharmacy_sales Sample Input:
product_id	units_sold	total_sales	cogs	manufacturer	drug
    9	       37410	293452.54	208876.01	Eli Lilly	Zyprexa
    34	       94698	600997.19	521182.16	AstraZeneca	Surmontil
    61	       77023	500101.61	419174.97	Biogen	    Varicose Relief
    136	       144814	1084258	    1006447.73	Biogen	    Burkhart

-- which sold between 100,000 units and 105,000 units,AND were manufactured by either Biogen, AbbVie, or Eli Lilly
SELECT manufacturer,drug,units_sold
FROM pharmacy_sales
WHERE manufacturer IN ('Biogen', 'AbbVie', 'Eli Lilly')
  AND units_sold BETWEEN 100000 AND 105000;