# Facade-detection

## Задача

Вам необходимо решить модельный бизнес кейс от некоторого заказчика - строительной компании, которая занимается возведением  многоквартирных домов.

Заказчику необходимо подсчитать сколько в уже построенном районе находится окон в жилых зданиях, а также количество этажей в здании и количество колонн (вертикальных рядов окон)

Также заказчик хотел бы выделять на фото фасад "главного" здания, если на изображении несколько зданий)

Вам необходимо:

    Сделать обзор всевозможных решений решений по применению ИИ в строительстве, проектировании и эксплуатации и продажи квартир, показать вашу экспертизу и подготовку

    Провести описание подходов, которые вы планируете использовать для решения задачи

    Собрать датасет на котором изображены многоквартирные жилые дома, либо использовать синтетические данные

    Провести необходимую для вас разметку датасета (сегментация фасада, окна)

    САМЫЙ ВАЖНЫЙ ПУНКТ - обучить собственный алгоритм (pytorch, tensorflow) сегментации фасада главного здания, а также алгоритм определения числа окон, числа этажей и числа колонн на выбор, можно решить несколько). То есть сегментация + одна из задач по подсчёту.

    Составить презентацию и ноутбук с результатами, выложить на гитхаб
    
## CycleGAN
Этот набор данных был получен из официального каталога Pix2Pix Datasets Калифорнийского университета в Беркли. 

https://www.kaggle.com/datasets/balraj98/facades-dataset?resource=download
https://arxiv.org/abs/1611.07004

## CMP_Facade
Мы представляем базу данных изображений фасадов, собранную в Центре машинного восприятия и включающую 606 ректифицированных изображений фасадов из различных источников, 

которые были аннотированы вручную. Фасады представлены из разных городов мира и различных архитектурных стилей.

В отчете указаны происхождение, формат и обработка данных, принципы аннотирования для 12 классов.

* facade 
* molding
* cornice
* pillar
* window
* door
* sill
* blind
* balcony
* shop
* deco
* background
  
https://cmp.felk.cvut.cz/~tylecr1/facade/

## TRIMS
Состоит из 60 нерельефных изображений фасадов, которые отличаются большей нерегулярностью и лишь слабо следуют архитектурным принципам.

[http://ps-old.is.tue.mpg.de/project/Facade_Segmentation](http://www.ipb.uni-bonn.de/projects/etrims_db/)

## TMBuD
Timisoara Building Dataset - TMBuD - состоит из 1363 изображений с разрешением 768x1024 пикселей. Мы считаем, что такое разрешение является хорошим балансом между ресурсами обработки, необходимыми для манипулирования изображением, и реальным разрешением фотографий, сделанных с помощью смартфонов. Кроме того, это реальное разрешение видео для съемки на смартфон - основной сенсор для систем обнаружения зданий.

TMBuD создан из изображений зданий в Тимишоаре. Каждое здание представлено в нескольких ракурсах, поэтому этот набор данных можно использовать и для оценки алгоритма обнаружения зданий. В наборе данных содержатся изображения, являющиеся истинными, для выделения характерных краев, для семантической сегментации и GPS-координаты зданий.

Общее количество изображений следующее: 1363 изображения, 160 изображений, подтверждающих истинность краев, 300 изображений, подтверждающих истинность меток.
CLASSES :
BACKGROUND = 0 = ( 0, 0, 0)
BUILDING = 1 = ( 125, 125, 0)
DOOR = 2 = ( 0, 125, 125)
WINDOW = 3 = ( 0, 255, 255)
SKY = 4 = ( 255, 0, 0)
VEGETATION = 5 = ( 0, 255, 0)
GROUND = 6 = ( 125, 125, 125)
NOISE = 7 = ( 0, 0, 255)

https://github.com/CipiOrhei/TMBuD/tree/main


### Инструмент для создания аннотаций изображений

http://www.ipb.uni-bonn.de/html/software/annotation_tool/index.html


###  Источники

@inproceedings{isola2017image,
  title={Image-to-image translation with conditional adversarial networks},
  author={Isola, Phillip and Zhu, Jun-Yan and Zhou, Tinghui and Efros, Alexei A},
  booktitle={Proceedings of the IEEE conference on computer vision and pattern recognition},
  pages={1125--1134},
  year={2017}
}

@INPROCEEDINGS{Tylecek13,
  author = {Radim Tyle{\v c}ek and Radim {\v S}{\' a}ra},
  title = {Spatial Pattern Templates for Recognition of Objects with Regular Structure},
  booktitle = {Proc. GCPR},
  year = {2013},
  address = {Saarbrucken, Germany},
}

@techreport{ korc-forstner-tr09-etrims,
             author = "Kor{\v c}, F. and F{\" o}rstner, W.",
             title = "{eTRIMS} {I}mage {D}atabase for Interpreting Images of Man-Made Scenes",
             number = "TR-IGG-P-2009-01",
             month = "April",
             year = "2009",
             institute = "Dept. of Photogrammetry, University of Bonn",
             url = "http://www.ipb.uni-bonn.de/projects/etrims_db/" }

@inproceedings{orhei2021tmbud,
title={TMBuD: a dataset for urban scene building detection},
author={Orhei, Ciprian and Vert, Silviu and Mocofan, Muguras and Vasiu, Radu},
booktitle={International Conference on Information and Software Technologies},
pages={251--262},
year={2021},
organization={Springer}
}

@phdthesis{orhei2022urban,
  author  = {Ciprian-Constantin Orhei},
  title   = {Urban landmark detection using Computer Vision},
  school  = {The Polytechnic University of Timisoara},
  year    = {2022},
  month   = {06},
  publisher = "Politehnica Publishing House, Timisoara"
  isbn = {978-606-35-0513-3}
}
