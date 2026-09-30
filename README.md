# Daily Python Practice with ChatGPT, Claude & Meta AI (WhatsApp) 30th September 2026
<b>Volcano Monitoring Report:<b><br>
<b>Mission:</b><br>

Write<br>
```python
def volcano_report(volcanoes):
```

<b>Step 1</b><br>
For every volcano calculate:<br>
<ul>
  <li><b>Average Ash</b></li>
  <li><b>Average Gas</b></li>
</ul>
<b>Step 2</b><br>
A Volcano is <b>"High Alert"</b> if:<br>
```Average Ash >= 60
AND
Average Gas >= 85 
```
<br>Otherwise <b>"Normal"</b><br>
<b>Step 3</b><br>
<b>Step 4</b><br>
<b>Step 5</b><br>

```python
volcanoes = {
    "Barren":    {"ash": [42, 38, 45, 40], 
                  "gas": [78, 82, 80, 85]},
    "Narcondam": {"ash": [15, 18, 20, 17], 
                  "gas": [45, 48, 46, 50]},
    "Merapi":    {"ash": [88, 92, 90, 95], 
                  "gas": [94, 96, 95, 97]},
    "Fuji":      {"ash": [28, 30, 26, 29], 
                  "gas": [52, 55, 50, 53]},
    "Etna":      {"ash": [60, 64, 62, 66], 
                  "gas": [84, 86, 83, 87]},
    "Krakatoa":  {"ash": [74, 78, 76, 80], 
                  "gas": [90, 92, 91, 93]}
}
def myfunction(volcanoes):
    report1 = {}
    statistics = {}
    total_average_ash = 0
    highest = None
    highest_volcano = 0
    lowest = None
    lowest_volcano = 0
    alert = []
    count = 0
    for volcano, data in volcanoes.items():
        average_ash = sum(data["ash"]) / len(data["ash"])
        average_gas = sum(data["gas"]) / len(data["gas"])
        if average_ash >= 60 and average_gas >= 85:
            if highest is None or average_ash > highest:
                highest = average_ash
                highest_volcano = volcano
            alert.append(volcano)
            if lowest is None or average_ash < lowest:
                lowest = average_ash
                lowest_volcano = volcano
            total_average_ash += average_ash
            count += 1
            report1[volcano] = {"Average Ash":average_ash,
                               "Average Gas":average_gas,
                               "Status":"High Alert"}
        else:
            report1[volcano] = {"Average Ash":average_ash,
                               "Average Gas":average_gas,
                               "Status":"Normal"}
    overall_ash = total_average_ash / count
    statistics = {"High Alert Volcanoes":alert,
                  "Overall Average Ash":overall_ash,
                  "High Ash Volnano":highest_volcano,
                  "Highest Average Ash":highest,
                  "Lowest Ash Volcano":lowest_volcano,
                  "Lowest ash Acerage":lowest}
    return report1,statistics
print(myfunction(volcanoes))
```
