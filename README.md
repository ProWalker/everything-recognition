## Обнаружение объетов на видео
Скрипт для обнаружения объектов на видео. Обнаруженные обекты выделяются рамкой.

### Как пользоваться 
Python3 должен быть уже установлен. Затем используйте pip (или pip3, есть конфликт с Python2) для установки зависимостей:

    pip install -r requirements.txt

Скрипт использует библиотеку OpenCV. Если в процессе установки возникли проблемы, прочитайте FAQ в [репозитории пакета](https://pypi.org/project/opencv-python/3.4.3.18/),
или же попробуйте установить библиотеку [вручную.](https://docs.opencv.org/4.x/da/df6/tutorial_py_table_of_contents_setup.html)  
Для работы скрипта необходима камера.  
Скрипт использует набор обученных моделей для определения объектов на видео.  
Модели распологаются в папке haarcascades в виде xml-файлов. Список моделей довольно большой.  
По умолчанию используются модели поиска лица и глаз.  
Модели указываются в файле config.py словарём CASCADES. Формат такой:  
    
    "{Название модели}": {
        "path": "{путь к файлу модели}",
        "color": (255, 0, 0),
        "draw": bool,
    }

Ключ "draw" указывает применять модель или нет.  
Найденные объекты выделяются рамкой, за цвет рамки отвечает параметр CASCADES['модель']['color'].  
Для формата BGR указывается кортеж, например (255, 0, 0) для синего цвета. 
Для оттенков серого просто укажите скалярное значение.    

### Пример запуска скрипта

    python3 run.py

Если запуск прошёл успешно, вы увидите изображение с камеры, на котором будут определяться указанные объекты.  

### Завершение скрипта
Для завершения скрипта нажмите клавишу q.  
