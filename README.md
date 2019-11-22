# Shoot-the-bullet
Проек повторяет игру Shoot-the-bullet (https://www.microsoft.com/en-us/p/brick-game-simulator/9nblggh4qfmw).
Реализован в 5 файлах: "Shoot-the-bullet.ino", "Field.cpp", "Field.h", "playerShip.cpp", "playerShip.h".
В "Shoot-the-bullet.ino" подключены небходимые библиотеки(Adafruit_PCD8544, Adafruit_GFX), файлы(Field.h, playerShip.h), перефирия(LCD5110, JoystickShield), созданы объекты классов и методы считывания(input) и вывода(output) информации.
  В "setup()" открыты нужные выходы и входы.
  В "loop()" реализована основная логика программы.
  В "input()" в зависимости от нажатой кнопки на JoystickShield и состояния игры производим соответсвующие дествия.
  В "output()" в зависимости от состояния игры выводим соотвествующие элименты на LCD5110.
В "Field.cpp" и "Field.h" реализованы методы и функции для описания поля, падающих рядов и летящих снарядов, а также их взаиможействия между собой. А также реализованы переходы между состояними игры.
В "playerShip.cpp" и "playerShip.h" реализованы методы и функции для описания модели игрока и управления ею.

# Геймплэй
Геймпэй предстовляет собой повторение оригинальной игры. Игроку нужно заполнять, посредством запуска снарядов, которые при столкновенни становятся частью соотвествующего ряда, падающие на него неполные ряды. Если заполнить ряд, то он уничтожится, а игрок получит очко. Если ряд дойдёт до уровня игрока, то игра закончится.

# Иструкция по эксплутации
При подключении питания к Arduino Uno, на эране отобразится меню игры в котром:
  Кнопоки A и C осуществляют перемещение курсора между пунктами меню вверх и вниз соотвественно.
  Кнопка B осуществляет выбор соотвествующего пункта меню.
Пункты меню:
  New Game - переход к новой игре.
  Continue - переход к игре, если есть приостоновленная игра.
  Difficulty - выбор сложности игры(от 1 до 3). Чем больше значнение, тем быстрее падают ряды.
  Size - выбор размера игрового поля(от 1 до 3). Значение соотвествуют размеру стороны одного блока в пикселях.
  Highcores - переход к таблице лучших результатов.

Во время игры отображается ировое поле и колличество очков. Кнопки отвечают:
  A и С - движение модели игрока вправо и влево на один пиксель соотвественно.
  D - выстрел блока.
  B - переход в меню с отстановкой текущей игры.
  
В случае поражения отображается сообщение о проигрыше, колличестово очков, накопленных игроком за последнию игру, и возможность выбора имя при помощи кнопок:
  B и D - передвижение курсора вправо и влево соотвественно, если курсор стоит на третей букве и нажать B, то случится переход в меню.
  A и C - изменение соотвествующей буквы в имени вверх и вних по алфавиту соотвественно.

В таблице с результами оттображаются лучшие 5 результатов. Кнопики отвечают:
  A, B, C - переход в меню.
  D - сброс таблицы результатов на изначальные. При первом запуске следует провести эту процедуру для корректного отображения результатов.
