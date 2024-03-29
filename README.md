# mipt_hackathon_2023_BBB
Этот код используется для построения рекомендательной системы. Код разделен на две части:

### **Часть 1**

- Установить библиотеку implicit с помощью pip.
- Загрузить обучающий набор данных из файла parquet.
- Преобразовать обучающий набор данных в таблицу различных действий пользователя.
- Проанализировать каждый шаблон действий пользователя и выдать возможное следующее действие пользователя для каждого взаимодействия.
- Подогнать модель Байесовского персонализированного ранжирования (BPR) к матрице пользователь-элемент.
- Предсказать потенциальные действия для каждого пользователя на основе обученной модели BPR.
- Создать датафрейм, содержащий потенциальные действия для каждого пользователя.

### **Часть 2**

- Отметить наиболее важные действия для каждого пользователя.
- Создать новую разреженную матрицу и подгоните ее под алгоритм Alternating Least Squares (ALS).
- Предсказать 5 лучших рекомендуемых вакансий для каждого пользователя на основе обученной модели ALS.
- Рассчитать метрику precision@5 для оценки эффективности модели.
- Обучить модель ALS с различными гиперпараметрами и сохранить результаты в датафрейме.

В коде используются следующие библиотеки:

- Pandas: для работы с данными.
- Numpy: для численных вычислений.
- Tqdm: для индикатора прогресса во время итерации по набору данных.
- Scipy: для операций с разреженными матрицами.
- Implicit: для построения рекомендательных систем с использованием матричной факторизации.

Код считывает данные для обучения и тестирования из файлов parquet. Затем он преобразует данные в матрицу "пользователь-элемент" и обучает на ней BPR-модель. Модель BPR используется для прогнозирования потенциальных действий для каждого пользователя. Затем отмечаются наиболее важные действия для каждого пользователя и создается новая разреженная матрица. Алгоритм ALS обучается на этой новой матрице и используется для предсказания 5 лучших рекомендуемых элементов для каждого пользователя. Для оценки эффективности модели ALS используется метрика precision@5. Наконец, модель ALS обучается с различными гиперпараметрами, и результаты сохраняются в датафрейме.
