# Описание репозитория
Этот репозиторий содержит работу команды "Кванты" для хакатона, организованного ЦК МФТИ совместно с парнером Tinkoff. Здесь представлены материалы и код, разработанные в ходе решения поставленнй задачи.

## Тизер решения

В ходе работы:
1. Введена метрика прироста показателей сотрудников, позволяющая оценивать эффект от прохождения курсов.
2. Показано, что в прохождение курсов оказывает положительный эффект на персонал.
3. Разработана метрика, позволяющая оценивать эффект от использования произвольных рекомендательных систем.
4. Выявлено, что существуют наиболее полезные курсы, прохождение которых в среднем предпочтительнее других, и тем самым их можно рекомендовать всем сотрудникам.
5. Построена персонализированная ML-модель, которая предлагает сотрудникам набор курсов с учетом индивидуальных особенностей, рекомендации которой качественнее общего набора курсов для всех сотрудников.

Для всех сотрудников составлен ранжированный список рекомендованных курсов. В случае использования из него необходимо исключить ранее пройденные курсы на основании полной базы данных.

## Файлы в репозитории

Tinkoff_Kvant-EDA.ipynb: Jupyter Notebook, содержащий анализ данных, использованных в хакатоне. В нем вы найдете предварительную обработку данных, визуализации и первичные выводы, необходимые для понимания предоставленных данных.

Tinkoff_Final_solution.ipynb: Jupyter Notebook с построением рекомендательной системы и выдачей рекомендаций. 

Хакатон.pptx: презентация для защиты.

## Запуск скриптов

Для запуска блокнотов ipynb необходимо поместить [материалы задачи](https://disk.yandex.ru/d/UeFR_mBSR44TOg) в директорию `/data`

## А/Б тестирование

Приведенные в решении тесты указывают на то, что предложенная рекомендательная система принесет положительный эффект от внедрения. Однако, задним числом качественно протестировать систему невозможно, поскольку сотрудники не следовали нашим рекомендациям, а те курсы, которые они в действительности проходили, далеко не во всех случаях оказывались наверху предлагаемых нами списков. Таким образом, "эффективная" часть тестовой выборки получается довольно маленькой, представляя собой пересечение наших рекомендаций и реально проходившихся курсов.

Более качественно протестировать систему можно при ее реальном внедрении: в части случаев выдавать рекомендации случайным образом, в других ситуациях предлагать наиболее полезные курсы из фиксированного набора, и, наконец, в третьей группе испытаний выдавать персонализированные рекомендации нашей системы. При этом желательно, чтобы курсы были обязательными для прохождения, поскольку тестироваться будет главный компонент системы -- качество самих рекомендаций, а не их привлекальность для пользователей. Далее средние результаты прироста показателей в разных группах можно сравнить между собой. На выборке поряка нескольких тысяч прохождений курсов (позволяющей достичь хорошей погрешности среднего) можно будет сделать финальные выводы о пользе рекомендательной системы.