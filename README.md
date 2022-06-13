# hse22_project

### Ссылка на колаб: https://colab.research.google.com/drive/1HSva3Hay8-GavOMM0MfbKEmQbGjIJSrb?usp=sharing
## Общая информация:
### Таксон: Gammaproteobacteria
### Genus(es) of 5 selected species
*Mannheimia bovis* - Вид медленно растущих микобактерий, является возбудителем туберкулёза у крупного рогатого скота. Относится к комплексу M. tuberculosis complex - совокупности видов микобактерий, вызывающих туберкулёз у человека.

*Mannheimia granulomatis* - признан значимым патогеном у домашних и диких жвачных животных.

*Mannheimia haemolytica* - В зарубежной литературе инфекционное заболевание вызванное возбудителем Mannheimia haemolytica называется Mannheimiosis манхеймиоз. Является важным компонентом энзоотической пневмонии во всех новорожденных телят.

*Mannheimia ovis*  и *Mannheimia pernigra* 
# Описание выбранных геномов

|***Вид***|***Уровень сборки***|***размер(Mb)***|***GC%***|***скаффолды***|***Название(Colab)***|
|---|---|---|---|---|---|
|Mannheimia bovis| Chromosome|2,15516|39,8|1|GCF_014541205.1|
|Mannheimia granulomatis|Chromosome|2,27848|39,8|1|GCF_011455695.1|
|Mannheimia haemolytica|Chromosome|2,75708|41,1017|2|GCF_002285575.1|
|Mannheimia ovis| Chromosome|2,1437|39,1|1|GCF_009828705.1|
|Mannheimia pernigra|  Chromosome|2,26274|39,3358|3|GCF_013378015.1|


# Анализ аннотированных генов  

Название вида | Число генов |	Длина генома | Длина участков с экзонами |	Доля покрытия экзонами
---|---|---|---|---
bovis	| 2133	| 2155161	| 1926021	| 89.4
granulomatis| 2174	| 2278480	| 2031591	| 89.2
haemolytica | 2850	| 2757078	| 2446196	| 88.7
ovis	| 2148	| 2147704	| 1892290 | 88.3
pernigra	| 2268	| 2262740 | 1999599	| 88.4

Данные из Colab:

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/2022-06-13_13-54-25.png)

# Предсказание участков Z-DNA
В данном пункте было произведено предсказание участков Z-DNA с помощью программы zhunt. Далее были отобраны только те участки Z-DNA, у которых zh-score больше 500. По полученным данным были посчитаны некоторые показатели. Ниже представлены результаты для каждого генома.
 
|***Вид***|***Количество предсказанных Z-DNA***|***Количество участков с zh-score > 500***|***Общая длина участков***|
|---|---|---|---|
|Mannheimia bovis| 1229 | 12442 | 2155161 |
|Mannheimia granulomatis| 1343 | 13346 | 2278480 |
|Mannheimia haemolytica| 1540 | 15284 | 2753783 |
|Mannheimia ovis| 1064 | 10692 | 2143704 |
|Mannheimia pernigra| 1206 | 12442 | 2155161 |

Данные из Colab:

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/2022-06-13_13-55-06.png)

Файлы с предсказанием Z-DNA сохранены как текстовые файлы.
Гистограммы распределение ZH-Score для пяти геномов:  
  
  
![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z1.png)

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z2.png)

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z3.png)

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z4.png)

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/z5.png)
  
  
Как видно из гистограмм, ZH-Score распределен со смещением в сторону небольших значений с некоторыми всплесками (небольшим количеством очень больших значений), но по среднему ZH-Score наиболее подверженен образованию Z-DNA является *Mannheimia granulomatis*.  
  
 ### Затем, в гугл колабе создаем .bed файлы с ZH-Score
.bed файлы лежат в папке *bed and merge*

 ### Затем, в гугл колабе объединяем пересекающиеся участки Z-DNA с помощью утилиты bedtools merge
 
MERGED_\*.bed файлы лежат в папке *bed and merge*

# Ассоциация предсказанных участков с генами
С помощью ```bedtools slop``` создаем новые *_slop.bed файлы.

С помощью ```bedtools intersect``` создаем новые INTERSECTION_\*.bed файлы.
# Визуализация и анализ предсказаний и их ассоциации с генами
Визуализация генов и предсказанных участков Z-DNA с помощью GraphicFeature представлена в Колабе.
# Определение гомологов. Кластеризация
Информация по полученным гомологичным кластерам

Общее число кластеров: 2358

### Гистограмма кластеров по кол-ву разных геномов в кластере ###

![](https://github.com/shaggy99999/hse22_project/blob/main/pictures/sum.png)

# *Таблица с информацией по выбранным кластерам* #
Я выбирала такие кластеры, чтобы и в столбце # Speciуs и в столбце Genes было одно и тоже число 5, так как всего мы рассматриваем 5 геномов. Получается что я буду рассматривать кластеры, в которых находится по одному гену из генома, то есть всего 5 генов.
 
Номер кластера | Название вида | product_accession | имя | функция
---|---|---|---|---
9 | haemolytica | WP_005705959.1 | 30S ribosomal protein S11 | 30S рибосомальный белок S11 соединяет несколько разрозненных РНК-спиралей 16S рРНК и образует часть расщепления Shine-Dalgarno в рибосоме 70S
9 | ovis | WP_005705959.1 | 30S ribosomal protein S11 | 30S рибосомальный белок S11 соединяет несколько разрозненных РНК-спиралей 16S рРНК и образует часть расщепления Shine-Dalgarno в рибосоме 70S
9 | granulomatis | WP_005705959.1 | 30S ribosomal protein S11 | 30S рибосомальный белок S11 соединяет несколько разрозненных РНК-спиралей 16S рРНК и образует часть расщепления Shine-Dalgarno в рибосоме 70S
9 | pernigra | WP_005705959.1 | 30S ribosomal protein S11 | 30S рибосомальный белок S11 соединяет несколько разрозненных РНК-спиралей 16S рРНК и образует часть расщепления Shine-Dalgarno в рибосоме 70S
9 | bovis | WP_005705959.1 | 30S ribosomal protein S11 | 30S рибосомальный белок S11 соединяет несколько разрозненных РНК-спиралей 16S рРНК и образует часть расщепления Shine-Dalgarno в рибосоме 70S
601 | haemolytica | WP_006249544.1 | imidazole glycerol phosphate synthase subunit HisH| субъединица HisH обеспечивает деятельность амидотрансферазы глутамина которая производит аммиак необходимый к HisF для синтеза фосфата имидазол-глицерина и рибонуклеотида 5-аминоимидазол-4-карбоксамида
601 | ovis | WP_159629076.1 | imidazole glycerol phosphate synthase subunit HisH| субъединица HisH обеспечивает деятельность амидотрансферазы глутамина которая производит аммиак необходимый к HisF для синтеза фосфата имидазол-глицерина и рибонуклеотида 5-аминоимидазол-4-карбоксамида
601 | granulomatis | WP_165889356.1 | imidazole glycerol phosphate synthase subunit HisH| субъединица HisH обеспечивает деятельность амидотрансферазы глутамина которая производит аммиак необходимый к HisF для синтеза фосфата имидазол-глицерина и рибонуклеотида 5-аминоимидазол-4-карбоксамида
601 | pernigra | WP_176807515.1 | imidazole glycerol phosphate synthase subunit HisH| субъединица HisH обеспечивает деятельность амидотрансферазы глутамина которая производит аммиак необходимый к HisF для синтеза фосфата имидазол-глицерина и рибонуклеотида 5-аминоимидазол-4-карбоксамида
601 | bovis | WP_188156877.1| imidazole glycerol phosphate synthase subunit HisH| субъединица HisH обеспечивает деятельность амидотрансферазы глутамина которая производит аммиак необходимый к HisF для синтеза фосфата имидазол-глицерина и рибонуклеотида 5-аминоимидазол-4-карбоксамида
523 | haemolytica | WP_006250448.1	 | HTH-type transcriptional repressor FabR | функционально не охарактеризован
523 | ovis | WP_159628989.1 | HTH-type transcriptional repressor FabR | функционально не охарактеризован
523 | granulomatis | WP_165889426.1 | HTH-type transcriptional repressor FabR | функционально не охарактеризован
523 | pernigra | WP_176807632.1 | HTH-type transcriptional repressor FabR | функционально не охарактеризован
523 | bovis | WP_188157388.1 | HTH-type transcriptional repressor FabR | функционально не охарактеризован
1005 | haemolytica | WP_006248129.1 | glutamine-hydrolyzing GMP synthase | Включает активность GMP-синтазы (гидролиз глутамина). Участвует в биосинтетическом процессе GMP. Прогнозируется расположение в цитоплазме.
1005 | ovis | WP_159629730.1 | glutamine-hydrolyzing GMP synthase | Включает активность GMP-синтазы (гидролиз глутамина). Участвует в биосинтетическом процессе GMP. Прогнозируется расположение в цитоплазме.
1005 | granulomatis | WP_165888803.1 | glutamine-hydrolyzing GMP synthase | Включает активность GMP-синтазы (гидролиз глутамина). Участвует в биосинтетическом процессе GMP. Прогнозируется расположение в цитоплазме.
1005 | pernigra | WP_176808351.1 | glutamine-hydrolyzing GMP synthase | Включает активность GMP-синтазы (гидролиз глутамина). Участвует в биосинтетическом процессе GMP. Прогнозируется расположение в цитоплазме.
1005 | bovis | WP_188156165.1 | glutamine-hydrolyzing GMP synthase | Включает активность GMP-синтазы (гидролиз глутамина). Участвует в биосинтетическом процессе GMP. Прогнозируется расположение в цитоплазме.
311 | haemolytica | WP_006249362.1	 | 50S ribosomal protein L4 | функционально не охарактеризован
311 | ovis | WP_159628738.1	 | 50S ribosomal protein L4 | функционально не охарактеризован
311 | granulomatis | WP_027073853.1 | 50S ribosomal protein L4 | функционально не охарактеризован
311 | pernigra | WP_159628738.1	 | 50S ribosomal protein L4 | функционально не охарактеризован
311 | bovis | WP_188157226.1 | 50S ribosomal protein L4 | функционально не охарактеризован
491 | haemolytica | WP_006248507.1 | DNA polymerase III subunit delta' | катализирует ориентированное на ДНК расширение З'-конца цепи ДНК; субъединица дельта, кажется, взаимодействует с субъединицей гамма для переноса бета-субъединицы на ДНК
491 | ovis | WP_159628955.1 | DNA polymerase III subunit delta' | катализирует ориентированное на ДНК расширение З'-конца цепи ДНК; субъединица дельта, кажется, взаимодействует с субъединицей гамма для переноса бета-субъединицы на ДНК
491 | granulomatis | WP_165889928.1 | DNA polymerase III subunit delta' | катализирует ориентированное на ДНК расширение З'-конца цепи ДНК; субъединица дельта, кажется, взаимодействует с субъединицей гамма для переноса бета-субъединицы на ДНК
491 | pernigra | WP_176807658.1 | DNA polymerase III subunit delta' | катализирует ориентированное на ДНК расширение З'-конца цепи ДНК; субъединица дельта, кажется, взаимодействует с субъединицей гамма для переноса бета-субъединицы на ДНК
491 | bovis | WP_188157341.1 | DNA polymerase III subunit delta' | катализирует ориентированное на ДНК расширение З'-конца цепи ДНК; субъединица дельта, кажется, взаимодействует с субъединицей гамма для переноса бета-субъединицы на ДНК
3 | haemolytica | WP_006249240.1 | 50S ribosomal protein L20 | функционально не охарактеризован
3 | ovis | WP_005596075.1 | 50S ribosomal protein L20 | функционально не охарактеризован
3 | granulomatis | WP_165889142.1 | 50S ribosomal protein L20 | функционально не охарактеризован
3 | pernigra | WP_005596075.1 | 50S ribosomal protein L20 | функционально не охарактеризован
3 | bovis | WP_005596075.1 | 50S ribosomal protein L20 | функционально не охарактеризован
318 | haemolytica | WP_006248216.1 | metalloprotease TldD | функционально не охарактеризован
318 | ovis | WP_159628745.1 | metalloprotease TldD | функционально не охарактеризован
318 | granulomatis | WP_165889634.1 | metalloprotease TldD | функционально не охарактеризован
318 | pernigra | WP_176807748.1 | metalloprotease TldD | функционально не охарактеризован
318 | bovis | WP_188157220.1 | metalloprotease TldD | функционально не охарактеризован
1618 | haemolytica | WP_006250415.1 | - | -
1618 | ovis | WP_159631329.1 | LexA regulated protein | функционально не охарактеризован
1618 | granulomatis | WP_165889267.1 | LexA regulated protein | функционально не охарактеризован
1618 | pernigra | WP_176808951.1 | LexA regulated protein | функционально не охарактеризован
1618 | bovis | WP_025236558.1 | LexA regulated protein | функционально не охарактеризован
61 | haemolytica | WP_006250404.1 | flavodoxin-dependent (E)-4-hydroxy-3-methylbut-2-enyl-diphosphate synthase | функционально не охарактеризован
61 | ovis | WP_159628463.1 | flavodoxin-dependent (E)-4-hydroxy-3-methylbut-2-enyl-diphosphate synthase | функционально не охарактеризован
61 | granulomatis | WP_165889278.1 | flavodoxin-dependent (E)-4-hydroxy-3-methylbut-2-enyl-diphosphate synthase | функционально не охарактеризован
61 | pernigra | WP_176807322.1 | flavodoxin-dependent (E)-4-hydroxy-3-methylbut-2-enyl-diphosphate synthase | функционально не охарактеризован
61 | bovis | WP_188156784.1 | flavodoxin-dependent (E)-4-hydroxy-3-methylbut-2-enyl-diphosphate synthase | функционально не охарактеризован
	
# Множественное белковое выравнивание

Для каждого выбранного кластера было произведено множественное белоковое выравнивание на сайте https://www.ebi.ac.uk/Tools/msa/clustalo/ . В качестве алгоритма для выравнивания был выбран алгоритм ```ClustalW with character counts```. 

Номер кластера | Визуализация
---|---
0 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl1.1.png">
0 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl1.2.png">
0 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl1.3.png">
1 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl2.1.png">
1 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl2.2.png">
1 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl2.3.png">
2 |  -
3 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl4.1.png">
3 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl4.2.png">
3 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl4.3.png">
4 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl5.1.png">
4 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl5.2.png">
4 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl5.3.png">
5 |  -
6 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl7.1.png">
6 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl7.2.png">
6 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl7.3.png">
7 |  -
8 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl9.1.png">
8 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl9.2.png">
8 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl9.3.png">
9 |  <img width="359" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl10.1.png">
9 |  <img width="374" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl10.2.png">
9 |  <img width="380" alt="image" src="https://github.com/shaggy99999/hse22_project/blob/main/pictures/cl10.1.png">

На каждом рисунке выше отрисован ген из генома, попадающий в соотвествующий кластер. На каждом гене, отрисованы все z-dna с их zh-score. Такая визуализация помогает увидеть где именно находится участок z-dna относительно гена. Каждый ген подписан по следующему принципу: gene + LOCUS(из файла gbff), где LOCUS отвечает за то, к какому геному принадлежит ген. Из визуализации и координат можно заметить, что во многих случаях z-dna попадает на экзон интрон и промоутер, за исключением следующих случаев:
Номер кластера | Название вида | Куда попадает
---|---|---
1 | enriettii | промоутер и интрон
1 | panamensis | промоутер и интрон
3	| panamensis | промоутер и интрон
5	| enriettii | промоутер и интрон
5	| infantum JPCM5 | промоутер и интрон
5	| martiniquensis | промоутер и интрон
5	| panamensis | промоутер и интрон
6	| panamensis | промоутер и интрон
7	| donovani | интрон
7	| enriettii | интрон
7	| martiniquensis	| На данный ген не попали Z-DNA
7	| panamensis | промоутер и интрон
9	| panamensis | промоутер и интрон
