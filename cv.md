* Ivan Zhurikho
* Telegram: @I_ASID_I Discord: Dexenys#7888
* The main aim is to study javascript. I am careful and punctual.
* Had some experience with C#, Unity and Python.
* Here comes the code example:

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Field : MonoBehaviour
{
    [Header("Field Properties")]
    public float CellSize;
    public float Spacing;
    public int FieldSize;
    [Space(10)]
    [SerializeField]
    private Cell cellPref;
    [SerializeField]
    private RectTransform rt;

    private Cell[,] field;
    private void Start()
    {
        GenerateField();
    }
    private void CreateField()
    {
        field = new Cell[FieldSize, FieldSize];
        float fieldwidth = FieldSize * (CellSize + Spacing) + Spacing;
        rt.sizeDelta = new Vector2(fieldwidth, fieldwidth);
        float startX = -(fieldwidth / 2) + (CellSize / 2) + Spacing;
        float startY = (fieldwidth / 2) - (CellSize / 2) - Spacing;

        for(int x = 0; x < FieldSize; x++)
        {
            for(int y = 0; y < FieldSize; y++)
            {
                var cell = Instantiate(cellPref, transform, false);
                var position = new Vector2(startX + (x * (CellSize + Spacing)), startY - (y * (CellSize - Spacing)));
                field[x, y] = cell;
                cell.SetValue(x, y, 0);
            }
        }
    }
    private  void GenerateField()
    {
        if (field == null)
            CreateField();
        for (int x = 0; x < FieldSize; x++)
            for (int y = 0; y < FieldSize; y++)
                field[x, y].SetValue(x, y, 0);
    }
} 
```
* C# - beginning by GeekBrains, studying at the 8th grate at the moment
* B1 English
