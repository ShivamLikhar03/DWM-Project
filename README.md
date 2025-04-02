# DWM-Project
ETL, Data preprocessing and Visualization using Tableau



## Preprocessing Steps

### **Total Reported Crimes (Calculated Field)**

**Calculated Field Name:** `Total Reported Crimes`

**Description:**
This field calculates the total number of reported crimes by counting all report numbers.

**Formula:**
```sql
COUNT([Report Number])
```


### **Resolved Cases (Calculated Field)**

**Calculated Field Name:** `Resolved Cases`

**Description:**
This field calculates the number of resolved cases by counting cases where the status is "Resolved."

**Formula:**
```sql
SUM(IF [Case Status] = "Resolved" THEN 1 ELSE 0 END)
```

### **Resolution Rate (Calculated Field)**

**Calculated Field Name:** `Resolution Rate`

**Description:**
This field calculates the resolution rate of cases based on resolved and total cases.

**Formula:**
```sql
[ResolvedCases] / [TotalCases] * 100
```


### **Age Classification (Calculated Field)**
**Calculated Field Name:** `Age Description`

**Description:**
This field categorizes victims based on their age into four groups: Infant, Teenager, Adult, and Old.

**Formula:**
```sql
IF [Victim Age] >= 0 AND [Victim Age] <= 5 THEN "Infant"
ELSEIF [Victim Age] >= 6 AND [Victim Age] <= 18 THEN "Teenager"
ELSEIF [Victim Age] >= 19 AND [Victim Age] <= 59 THEN "Adult"
ELSEIF [Victim Age] >= 60 THEN "Old"
ELSE "Unknown"
END
```


### **Age Group Classification (Calculated Field)**

**Calculated Field Name:** `Age Group`

**Description:**
This field categorizes victims into decade-based age groups.

**Formula:**
```sql
IF [Victim Age] >= 1 AND [Victim Age] <= 10 THEN "1 - 10"
ELSEIF [Victim Age] >= 11 AND [Victim Age] <= 20 THEN "11 - 20"
ELSEIF [Victim Age] >= 21 AND [Victim Age] <= 30 THEN "21 - 30"
ELSEIF [Victim Age] >= 31 AND [Victim Age] <= 40 THEN "31 - 40"
ELSEIF [Victim Age] >= 41 AND [Victim Age] <= 50 THEN "41 - 50"
ELSEIF [Victim Age] >= 51 AND [Victim Age] <= 60 THEN "51 - 60"
ELSEIF [Victim Age] >= 61 AND [Victim Age] <= 70 THEN "61 - 70"
ELSEIF [Victim Age] >= 71 AND [Victim Age] <= 80 THEN "71 - 80"
ELSEIF [Victim Age] >= 81 AND [Victim Age] <= 90 THEN "81 - 90"
ELSEIF [Victim Age] >= 91 AND [Victim Age] <= 100 THEN "91 - 100"
ELSE "Unknown"
END
```

### **Police Deployment Classification (Calculated Field)**

**Calculated Field Name:** `Police Deployment`

**Description:**
This field categorizes the number of police deployed into specific ranges.

**Formula:**
```sql
IF [Police Deployed] >= 1 AND [Police Deployed] <= 5 THEN "1 - 5"
ELSEIF [Police Deployed] >= 6 AND [Police Deployed] <= 10 THEN "6 - 10"
ELSEIF [Police Deployed] >= 11 AND [Police Deployed] <= 15 THEN "11 - 15"
ELSEIF [Police Deployed] >= 16 AND [Police Deployed] <= 20 THEN "16 - 20"
ELSEIF [Police Deployed] >= 21 AND [Police Deployed] <= 25 THEN "21 - 25"
ELSE "Unknown"
END
```

### **City Tier Classification (Calculated Field)**

**Calculated Field Name:** `City Tier`

**Description:**
This field categorizes cities into Tier 1, Tier 2, and Tier 3 based on their development level and population size.

**Formula:**
```sql
CASE [City]
    WHEN "Ahmedabad" THEN "Tier 1"
    WHEN "Bangalore" THEN "Tier 1"
    WHEN "Chennai" THEN "Tier 1"
    WHEN "Delhi" THEN "Tier 1"
    WHEN "Hyderabad" THEN "Tier 1"
    WHEN "Kolkata" THEN "Tier 1"
    WHEN "Mumbai" THEN "Tier 1"
    WHEN "Pune" THEN "Tier 1"

    WHEN "Agra" THEN "Tier 2"
    WHEN "Bhopal" THEN "Tier 2"
    WHEN "Faridabad" THEN "Tier 2"
    WHEN "Ghaziabad" THEN "Tier 2"
    WHEN "Indore" THEN "Tier 2"
    WHEN "Jaipur" THEN "Tier 2"
    WHEN "Kanpur" THEN "Tier 2"
    WHEN "Lucknow" THEN "Tier 2"
    WHEN "Ludhiana" THEN "Tier 2"
    WHEN "Meerut" THEN "Tier 2"
    WHEN "Nagpur" THEN "Tier 2"
    WHEN "Nashik" THEN "Tier 2"
    WHEN "Patna" THEN "Tier 2"
    WHEN "Rajkot" THEN "Tier 2"
    WHEN "Surat" THEN "Tier 2"
    WHEN "Thane" THEN "Tier 2"
    WHEN "Varanasi" THEN "Tier 2"
    WHEN "Visakhapatnam" THEN "Tier 2"

    WHEN "Kalyan" THEN "Tier 3"
    WHEN "Srinagar" THEN "Tier 3"
    WHEN "Vasai" THEN "Tier 3"
END
```

### **City Zone Classification (Calculated Field)**

**Calculated Field Name:** `Zone of City`

**Description:**
This field categorizes cities into different zones (North, South, East, West).

**Formula:**
```sql
CASE [City]
    WHEN "Agra" THEN "North"
    WHEN "Delhi" THEN "North"
    WHEN "Faridabad" THEN "North"
    WHEN "Ghaziabad" THEN "North"
    WHEN "Jaipur" THEN "North"
    WHEN "Kanpur" THEN "North"
    WHEN "Lucknow" THEN "North"
    WHEN "Ludhiana" THEN "North"
    WHEN "Meerut" THEN "North"
    WHEN "Srinagar" THEN "North"
    WHEN "Varanasi" THEN "North"

    WHEN "Bangalore" THEN "South"
    WHEN "Chennai" THEN "South"
    WHEN "Hyderabad" THEN "South"
    WHEN "Visakhapatnam" THEN "South"

    WHEN "Kolkata" THEN "East"
    WHEN "Patna" THEN "East"

    WHEN "Ahmedabad" THEN "West"
    WHEN "Bhopal" THEN "West"
    WHEN "Indore" THEN "West"
    WHEN "Kalyan" THEN "West"
    WHEN "Mumbai" THEN "West"
    WHEN "Nagpur" THEN "West"
    WHEN "Nashik" THEN "West"
    WHEN "Pune" THEN "West"
    WHEN "Rajkot" THEN "West"
    WHEN "Surat" THEN "West"
    WHEN "Thane" THEN "West"
    WHEN "Vasai" THEN "West"
END
```
![image](https://github.com/user-attachments/assets/47dd96e2-16a1-4df5-842c-f17dc32f3494)
