<!-- doc.py -->
Определение размера константного массива
========================================
Специальный макрос чтобы показать переменную для отладки
``` cpp
#define SHOW(x) cout << #x << " = " << (x) << endl;
```

Определение размера константного массива
Делим размер массива в байтах на размер его первого элемента,
получаем количество элементов в массиве
``` cpp
#define SIZE(array) (sizeof(array) / sizeof(array[0]))
```

В функцию для вывода массива придётся передать его размер явно
``` cpp
void showArray(int mas[], int size) {
  for(int i = 0; i < size; i++)
    cout << "mas[" << i << "] = " << mas[i] << endl;
}
```

Создаём константный массив
``` cpp
  int mas[] = {1, 2, 3};
```

В той же области видимости мы можем определить его размер с помощью макроса SIZE
``` cpp
  for(int i = 0; i < SIZE(mas); i++)
    cout << "mas[" << i << "] = " << mas[i] << endl;
```

А в функцию размер массива придётся передать в виде параметра:
``` cpp
  showArray(mas, SIZE(mas));
```

[main.cpp](main.cpp)

