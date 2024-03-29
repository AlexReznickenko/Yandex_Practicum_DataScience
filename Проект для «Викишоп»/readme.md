# Определение токсичных комментариев

## Статус проекта: завершён

## Описание проекта

Интернет-магазин «Викишоп» запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.

Обучите модель классифицировать комментарии на позитивные и негативные. В вашем распоряжении набор данных с разметкой о токсичности правок.

Постройте модель со значением метрики качества F1 не меньше 0.75.

Инструкция по выполнению проекта

- Загрузите и подготовьте данные.
- Обучите разные модели.
- Сделайте выводы.

## Навыки и инструменты

- **pandas**
- sklearn.model_selection **train_test_split**
- sklearn.utils **shuffle**
- sklearn.metrics **f1_score**
- sklearn.pipeline **Pipeline**
- tqdm.notebook **tqdm**
- **nltk**
- nltk.corpus **stopwords** 
- nltk.stem **WordNetLemmatizer**
- **re** 
- nltk.corpus **wordnet**
- sklearn.feature_extraction.text **TfidfVectorizer**
- sklearn.feature_extraction.text **CountVectorizer**
- sklearn.feature_extraction.text **TfidfTransformer**
- sklearn.model_selection **GridSearchCV**
- sklearn.linear_model **LogisticRegression**
- sklearn.tree **DecisionTreeClassifier**
- sklearn.ensemble **RandomForestClassifier**

## Цель исследования

Определение токсичности комментариев.


## Описание данных

Столбец text в нём содержит текст комментария, а toxic — целевой признак.

## Вывод по итогам исследования

Мы научились лемматизировать текстовые данные, а также преобразовывать их в вектора.

В ходе работы возникли технические проблемы: ядро питона "умирало", когда было загружено слишком много данных в оперативную память. Проблему удалось решить используя команду del.

Было испробовано три модели - случайный лес, дерево решений и логистическая регрессия. Логистическая регрессия показала себя лучше всего на кросс-валидации. На тестовых данных результат ещё лучше: F1-метрика достигла 76,9%, что соответсвует требованиям.

До этого были попытки избавиться от дисбаланса методом downupsampling, но это только ухудшило результаты.
