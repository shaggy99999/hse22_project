# hse22_project

### Ссылка на колаб: https://colab.research.google.com/drive/1k6Z5mgrFmKFgd3yLSHpeDSLaV7xlPS8f?usp=sharing
## Общая информация:
### Таксон: Gammaproteobacteria
### Genus(es) of 5 selected species
*Mannheimia bovis* - Вид медленно растущих микобактерий, является возбудителем туберкулёза у крупного рогатого скота. Относится к комплексу M. tuberculosis complex - совокупности видов микобактерий, вызывающих туберкулёз у человека.

*Mannheimia granulomatis* - признан значимым патогеном у домашних и диких жвачных животных.

*Mannheimia haemolytica* - В зарубежной литературе инфекционное заболевание вызванное возбудителем Mannheimia haemolytica называется Mannheimiosis манхеймиоз. Является важным компонентом энзоотической пневмонии во всех новорожденных телят.

*Mannheimia ovis*  и *Mannheimia pernigra* 
# Описание выбранных геномов

|***Species***|***Level***|***Size(Mb)***|***GC%***|***Scaffolds***|***Assembly***|
|---|---|---|---|---|
|Mannheimia bovis| Chromosome|2,15516|39,8|1|GCF_014541205.1|
|Mannheimia granulomatis|Chromosome|2,27848|39,8|1|GCF_011455695.1|
|Mannheimia haemolytica|Chromosome|2,75708|41,1017|2|GCF_002285575.1|
|Mannheimia ovis| Chromosome|2,1437|39,1|1|GCF_009828705.1|
|Mannheimia pernigra|  Chromosome|2,26274|39,3358|3|GCF_013378015.1|  

# Анализ аннотированных генов  

|***Species***|***Length***|***Annotated genes***|***Annotated genes %***|
|---|---|---|---|
|Mannheimia bovis| 2133 | 1959328 | 0.9091330067684038 |
|Mannheimia granulomatis| 2174 | 2064210 | 0.9059592359818827 |
|Mannheimia haemolytica| 2852 | 2480421 | 0.899655722471399 |
|Mannheimia ovis| 2148 | 1925222 | 0.8980820113224587 |
|Mannheimia pernigra| 2268 | 2033377 | 0.898634840945049 |

# Предсказание участков Z-DNA
Количество предсказанных zhunt участков, их суммарная длина и средняя длина предсказанного участка Z-DNA:  
|***Species***|***Amount***|***Overal length***|***Mean length***| ***Mean ZH-Score*** |
|---|---|---|---|---|
|Mannheimia bovis| 1229 | 12442 | 10.12 | 1243.05 |
|Mannheimia granulomatis| 1343 | 13346 | 9.94 | 1599.85 |
|Mannheimia haemolytica| 1541 | 15296 | 9.93 | 1237.97 |
|Mannheimia ovis| 1064 | 10692 | 10.05 | 1128.98 |
|Mannheimia pernigra| 1251 | 12558 | 10.04 | 1185.28 |

Файлы с предсказанием Z-DNA сохранены как текстовые файлы.
Гистограммы распределение ZH-Score для пяти геномов:  
  
  
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z1.png)
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z2.png)
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z3.png)
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z4.png)
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z5.png)
  
  
Как видно из гистограмм, ZH-Score распределен со смещением в сторону небольших значений с некоторыми всплесками (небольшим количеством очень больших значений), но по среднему ZH-Score наиболее подверженен образованию Z-DNA является Saccharomyces eubayanus геном.  
  
 ### Затем, в гугл колабе создаем .bed файлы с ZH-Score
.bed файлы 

 ### Затем, в гугл колабе объединяем пересекающиеся участки Z-DNA с помощью утилиты bedtools merge
 
MERGED_\*.bed файлы  

# Ассоциация предсказанных участков с генами
С помощью ```bedtools slop``` создаем новые *_slop.bed файлы.

С помощью ```bedtools intersect``` создаем новые INTERSECTION_\*.bed файлы.
# Визуализация и анализ предсказаний и их ассоциации с генами
# Определение гомологов. Кластеризация
