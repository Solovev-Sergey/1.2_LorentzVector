# 1.2 Перегрузка операторов для `LorentzVector`

В [предыдущем задании](https://github.com/pycpp2019/1.1_LorentzVector) вы уже реализовали класс `LorentzVector`.

Для класса `LorentzVector` перегрузите операторы
+ Сложения `operator+` и `operator+=`)
+ Вычитания (`operator-` и `operator-=`)
+ Унарного минуса (`operator-`)
+ Умножения (`operator*` и `operator*=`)
+ Вывода в поток `operator<(std::ostream& out, const LorentzVector& lv)`

## Указания

+ Создайте для этой задачи новый проект
+ Оператор вывода в поток не следует включать в класс `LorentzVector`. Если необходим доступ к приватным членам `LorentzVector`, можно объявить этот оператор с помощью ключевого слова `friend`.

## Примечания и уточнения

+ Возможны как `+---` так и `-+++` сигнатуры.
+ В `t` компоненте вектора должно лежать время, уже домноженное на скорость света. Это означает, что у вас в реализации скорость света нигде не должна фигурировать.
+ Конструктор по умолчанию `LorentzVector()` должен инициализировать компоненты вектора нулями.
+ Норма должна быть определена как для ![](https://latex.codecogs.com/gif.latex?%5Clarge%20t%20%5Cgeq%20%5Csqrt%7Bx%5E2%20&plus;%20y%5E2%20&plus;%20z%5E2%7D) так и для ![](https://latex.codecogs.com/gif.latex?%5Clarge%20t%20%3C%20%5Csqrt%7Bx%5E2%20&plus;%20y%5E2%20&plus;%20z%5E2%7D), при этом знак нормы не имеет значения.
+ При выводе с помощью `LorentzVector::operator<<()` требуется, чтобы компоненты вектора были разделены какими-либо символами кроме следующих: `01234567890.eE+-`, а в остальном формат может быть призвольным.

## Автоматическое тестирование

Тестирование решения запускается автоматически в сервисе [Travis](https://travis-ci.org/pycpp2019/1.2_LorentzVector/pull_requests) при появлении новых коммитов или пулл-реквестов в репозитории.

Но протестировать решение можно и локально на своём компьютере. Для этого, находясь в директории `1.2_LorentzVector`, нужно выполнить следующую команду:
```
make run-test
```

Или если вы используете MinGW в Windows:
```
mingw32-make run-test
```

Эта команда запустит процесс сборки, описанный в `Makefile`. Что такое мейкфайл можно прочитать например [тут](https://habr.com/ru/post/155201/).
