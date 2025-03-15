# Power-BI---Tips-Tricks

 thhIn this repository, I'm going top share tips and tricks that I found useful while learning and exploring Power BI features.

 ### 1-- How to make a slicer transparent 

 ![image](https://github.com/user-attachments/assets/c0cc24e5-5e1d-4629-b172-ea07d45aeae6)

In order to make a slicer transparent, we can create a DAX measure called ```Transparent = "#00FFFFFF"```, and put on the fx function background color in the slicer setting.

![image](https://github.com/user-attachments/assets/2eaaedcb-45e1-436b-81c4-e12b53e71311)


### 2-- Put a Marker for the Highest & Lowest value in the Line Chart

Use this DAX Measure in order to Change the color of the Highest & Lowest points in the Line chart 


```
Highlight Colour =
VAR _highest =
    MAXX(
        ALLSELECTED('Calendar'[Month]),
        [Sales]
    )
VAR _lowest =
    MINX(
        ALLSELECTED('Calendar'[Month]),
        [Sales]
    )
VAR _highlight =
    SWITCH(
        TRUE(),
        _highest = [Sales], "Green",
        _lowest = [Sales], "Red",
        "Gray"
    )
RETURN
    _highlight

```
![image](https://github.com/user-attachments/assets/880e82dc-4446-4af4-9923-3787f16a7598)


















