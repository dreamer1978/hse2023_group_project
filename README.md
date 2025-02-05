# Групповой проект - DNA modification
[Вводная презентация](https://github.com/missaline/hse23_group_project/blob/main/data/Вводная.pdf)

[Финальная презентация](https://github.com/missaline/hse23_group_project/blob/main/data/Финальная.pdf) 

## Код для создания общей тепловой карты:
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Порядок занесения -log(e-value) (указан в документе с заданием): 
# "human", "mouse", "zebrafish", "drosophila", "c.elegans", "ciliate", "yeast", "methanocaldococcus", "thermococcus", "e.coli", "tuberculosis"

data = {"TET1" : [300, 300, 300, 231.6328751,	0,	0,	0, 0.01742306205,	1.472446383,	0,	1.131448369],
        "TDG" : [300, 300, 	150.105,	74.2314,	-0.919078,	0.0809219,	0.431798,	0.823909,	-0.39794,	19.5258,	-0.255273], 
        "METTL4" : [300, 300, 182.931445, 41.41697, 40.898410, 15.692828, 2.956512, 4.422849, 0.616186, -0.405465, 0.941609],
        "DNMT3B" : [300, 300, 300, 5.712198, 1.050610, 1.920819, 0.823909, 3.358526, -0.491362, 0.522879, 0.070581],
        "DNMT3A" : [300, 300, 300, 5.559, 2.045, 2.523, 3, 2.699, 0.137, 0.721, 0.079],
        "CENPC":	[300, 300, 8.135338, -1.458615, 4.074542,	-0.262364,	2.688248,	-1.360977,	-1.667707,	1.021651,	0.820981],
        "ALKBH4": [300, 300, 211.598812, 137.572890, 118.059199, 22.886089, -1.481605, -0.788457, 	0.634878, 	-1.722767 ,	2.375156]
}

organisms = ["human", "mouse", "zebrafish", "drosophila", "c.elegans", "ciliate", "yeast", "methanocaldococcus", "thermococcus", "e.coli", "tuberculosis"]
df = pd.DataFrame(data, index=organisms)

# Создание тепловой карты
plt.figure(figsize=(8, 6))
sns.heatmap(df, annot=True, cmap='coolwarm', fmt=".1e")
plt.title('Тепловая карта')
plt.xlabel('Название белка')
plt.ylabel('Организмы')
plt.show()
```
