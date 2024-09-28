# Нейронная сеть для распознавания возраста и пола человека 
### Цели и задачи проекта
Целью и задачей данного проекта являлись разработка и обучение сверточной нейронной сети для точной идентификации личности на основе анализа полового и возрастного признаков на фотографиях. Сеть может применяться для составления статистических данных, которые могут быть использованы в различных областях, таких как маркетинг, социология, исследования рынка и другие. 

### Выбор инструментов реализации
- Для реализации поставленной цели была выбрана модель сверточной нейронной сети ResNet-18
- Для взаимодействия модели с пользователем использовался Telegram бот

### Небольшое ограничение
В связи с ФЗ № 152-ФЗ "О персональных данных", воздержались от обучения на картинках реальных людей и решили использовать персонажей из мультипликационного сериала “The Simpsons” (“Симпсоны”)

### Разработки нейронной сети
- Проходил долгий сбор кастомного датасета, так как найти картинки симпсонов с разметкой найти не удалось
- Для того, чтобы избежать переобучения модели применялись различные трансформации изображения такие как:
  - Переворот изображения
  - Поворот изображения на угол до 45 градусов в разные стороны
  - Изменение контрастности изображения до 30%
  - Изменение яркости изображения до 80%
  - Добавление случайного шума до 30% покрытия изображения
- Использовался Transfer Learning модели ResNet-18, т.е. обучали последние 3 слоя нейросети
- В качестве функции потерь была выбрана кросс энтропия 
- В качестве оптимизатора модели был выбран Adam с lerning rate = 1e-3
- Метрикой измерения качества была выбрана F1 мера из-за большого дисбаланса в некоторых классах. По итогам обучения лучшая модель выдала F1 = 0.82

### Архитектура сети
![alt text](https://github.com/OneSll/Age_gender_recognition/blob/main/pic/model_res.png)

### Разработка бота
- Зарегистрировали бота в Telegram
- Получили API токен

### Описание общей работы
1) Предварительно загружаем веса модели в бота
2) Запускаем бота (Он переходит в режим ожидания картинки)
3) Пользователь загружает в бота картинку
4) Модель предсказывает пол и возраста персонажа
5) Пользователю приходит ответ от бота с предсказанием модели

### Результаты работы 
- Работа модели
![alt text](https://github.com/OneSll/Age_gender_recognition/blob/main/pic/res.png)
- Работа бота в тг:
<p align="left">
  <img width="400" height="250" src="https://github.com/OneSll/Age_gender_recognition/blob/main/pic/res1.png">
</p>
<p align="left">
  <img width="400" height="250" src="https://github.com/OneSll/Age_gender_recognition/blob/main/pic/res2.png">
</p>

### Регистрация ПО
Так же имеется свидетельство о гос. регистрации ПО для ЭВМ
