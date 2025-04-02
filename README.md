# DWM-Project
ETL, Data preprocessing and Visualization using Tableau



## Preprocessing Steps
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

![image](https://github.com/user-attachments/assets/47dd96e2-16a1-4df5-842c-f17dc32f3494)
