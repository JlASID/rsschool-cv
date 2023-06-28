# Ivan Zhurikho
## Contacts:
Discord: dexenys

Telegram: I_ASID_I

## About me: willing to learn how to create a site
## Skills: C# (.Net Framework), C++, Python, Unity3D
## Code example:
```
static string OperationsWithStrings(string operable1, string operable2, char operation)
        {
            operable1 = Reverse(operable1);
            operable2 = Reverse(operable2);
            int i1 = 0, i2 = 0;
            string sum = "";
            int value;
            int previousValue = '0';
            while(i1 < operable1.Length || i2 < operable2.Length)
            {
                if (i1 < operable1.Length && i2 < operable2.Length) value = operable1[i1] + ((operable2[i2] - '0' + previousValue - '0') * (operation == '+' ? 1 : -1));
                else if (i1 < operable1.Length) value = operable1[i1] + ((previousValue - '0') * (operation == '+' ? 1 : -1));
                else value = ((operable2[i2] - '0' + previousValue) * (operation == '+' ? 1 : -1));
                if (value > '9')
                {
                    value = value - 10;
                    previousValue = '1';
                    sum = Convert.ToChar(value) + sum;
                }
                else if (value < 0)
                {
                    if (i1 == operable1.Length - 1 || i2 == operable2.Length - 1 && sum.IndexOf('-') == -1) sum = (previousValue < 0? "-1" : "") + sum;
                }
                else if (value < '0')
                {
                    value += 10;
                    previousValue = '1';
                    sum = Convert.ToChar(value) + sum;
                }
                else
                {
                    previousValue = '0';
                    sum = Convert.ToChar(value) + sum;
                }
                i1++;
                i2++;
                if (!(i1 < operable1.Length || i2 < operable2.Length) && previousValue == '1') sum = "1" + sum;
            }
            return sum;
        }
        static string Reverse(string s)
        {
            string revS = "";
            foreach (char c in s)
                revS = c + revS;
            return revS;
        }
```
## Experience: 0
## Education: completed compulsory education, C# level 1 GeekBrains
## B2 English level
