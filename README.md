# DWM-Project
ETL, Data preprocessing and Visualization using Tableau

![image](https://github.com/user-attachments/assets/47dd96e2-16a1-4df5-842c-f17dc32f3494)

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

