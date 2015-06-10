## Свойство display

#### display: block

Блочные элементы отображаются на странице в виде прямоугольника, занимают всю доступную ширину. Высота блочного элемента определяется его содержимым или может быть явно задана.

![alt text](/images/display-block.png "display: block")

[http://codepen.io/dra1n/pen/gpmVmP](http://codepen.io/dra1n/pen/gpmVmP)

В потоке по умолчанию блочный элемент занимает всё доступное пространство по горизонтали, даже если явно заданная ширина меньше ширины родителя.

![alt text](/images/display-block-2.png "display: block")

[http://codepen.io/dra1n/pen/XbMvxO](http://codepen.io/dra1n/pen/XbMvxO)

#### display: inline

inline или строчные элементы отображаются на странице в ряд друг за другом


![alt text](/images/display-inline.png "display: inline")

[http://codepen.io/dra1n/pen/qdmWKR](http://codepen.io/dra1n/pen/qdmWKR)


Разница между блочными и строчными элементами:

* Строчные элементы могут содержать только данные или другие строчные элементы, то есть блочные элементы в них вкладывать нельзя

* Блочные элементы начинаются с новой строки, а строчные следуют друг за
  другом

* Высота и ширина строчных элементов определяется их содержимым и не
  может быть задана явно

![alt text](/images/display-inline-2.png "display: inline")

[http://codepen.io/dra1n/pen/QbvLeX](http://codepen.io/dra1n/pen/QbvLeX)

#### display: inline-block

Такие элементы перенимают свойства блочных и строчных элементов. От
блочных – возможность задавать ширину и отступы, от строчных –
обтекание справа.

![alt text](/images/display-inline-block.png "display: inline-block")
![alt text](/images/display-inline-block-2.png "display: inline-block")

[http://codepen.io/dra1n/pen/OVmJdJ](http://codepen.io/dra1n/pen/OVmJdJ)

## display: none vs visibility: hidden

При display: none элемент полностью удаляется из потока. При visibility: hidden элемент остается в потоке, то есть занимает отведенное для него место, но не отображается.

![alt text](/images/visibility-vs-display.png "visibility vs display")

[http://codepen.io/dra1n/pen/mJmyzE](http://codepen.io/dra1n/pen/mJmyzE)

![alt text](/images/visibility-vs-display-2.png "visibility vs display")

[http://codepen.io/dra1n/pen/qdmEKe](http://codepen.io/dra1n/pen/qdmEKe)


## position: relative

При заданном position: relative положение элемента устанавливается относительно его исходного места. Добавление свойств left, top, right и bottom изменяет позицию элемента и сдвигает его в ту или иную сторону от первоначального расположения. При этом в потоке для него выделяется место, которое занимал элемент до сдвига.

![alt text](/images/position-relative.png "position: relative")

[http://codepen.io/dra1n/pen/xGdPzp](http://codepen.io/dra1n/pen/xGdPzp)

## floats

Свойство float указывает элементу что он должен быть изъят из
нормального потока и прижат к левой или правой стороне своего
контейнера. При этом текст и строчные элементы должны его обтекать.

![alt text](/images/float-right.png "float: right")

[http://codepen.io/dra1n/pen/JdNMXm](http://codepen.io/dra1n/pen/JdNMXm)

#### Позиционирование float элементов

float элемент сдвигается влево или вправо до тех пор пока он не
прижмется к краю родителя или другого float элемента.

![alt text](/images/float-left-2.png "float: left")

[http://codepen.io/dra1n/pen/OVmzOX](http://codepen.io/dra1n/pen/OVmzOX)

#### Очистка float

Очистка float нужна если:

* Плавающие элементы имеют высоту большую, чем неплавающий контент

![alt text](/images/float-right-3.png "float: right")

[http://codepen.io/dra1n/pen/gpWvmx](http://codepen.io/dra1n/pen/gpWvmx)

* Все вложенные элементы являются плавающими элементами. Здесь же хорошо
  видно как float элементы удаляются из нормального потока и создают
свой поток.

![alt text](/images/float-left-4.png "float: left")

[http://codepen.io/dra1n/pen/wadydm](http://codepen.io/dra1n/pen/wadydm)

Стандартная ситуация:

![alt text](/images/float-left-7.png "float: left")

[http://codepen.io/dra1n/pen/xGdWbg](http://codepen.io/dra1n/pen/xGdWbg)

Способы очистки:

* Использование свойства clear для элемента, следующего за контейнером с
  плавающими элементами. Проблема: несмотря на то, что контейнер снова влияет на
поток, его собственная высота равна нулю [[http://codepen.io/dra1n/pen/jPmZaQ](http://codepen.io/dra1n/pen/jPmZaQ)]

![alt text](/images/float-left-5.png "float: left")

* Использование свойства clear для элемента, находящегося на одном
  уровне с плавающими элементами (ручная очистка float). Проблема: требуется дополнительный элемент. [[http://codepen.io/dra1n/pen/QbvQPo](http://codepen.io/dra1n/pen/QbvQPo)]

* Задание overflow контейнеру [[http://codepen.io/dra1n/pen/EjmEPN](http://codepen.io/dra1n/pen/EjmEPN)]

* clearfix [[http://codepen.io/dra1n/pen/mJmxdL](http://codepen.io/dra1n/pen/mJmxdL)]

![alt text](/images/float-left-6.png "float: left")

## position: absolute / fixed

#### absolute

position: absolute не оставляет места в потоке для элемента. Вообще.
Вместо этого позиционирует элемент в указанном месте относительно его
ближайшего позиционированного родителя (имеющего position: relative, fixed или absolute).
Абсолютно позиционированные элементы могут иметь марджины, которые не
накладываются ни на какие другие марджины.

![alt text](/images/position-absolute.png "position: absolute")

[http://codepen.io/dra1n/pen/NqjYXK](http://codepen.io/dra1n/pen/NqjYXK)

#### fixed

position: fixed не оставляет места в потоке для элемента. Вместо этого
позизионирует элемент в указанном месте относительно окна. При скролле
такой элемент остается на месте. При печати такой элемент выводится на
каждой странице.

![alt text](/images/position-fixed.png "position: fixed")

[http://codepen.io/dra1n/pen/EjmEzQ](http://codepen.io/dra1n/pen/EjmEzQ)

## Таблицы

#### Ширина таблицы

Ширина таблицы, если она явно не указана, устанавливается браузером автоматически исходя из содержимого ячеек.

![alt text](/images/table-1.png "table")

[http://codepen.io/dra1n/pen/GJmPQp](http://codepen.io/dra1n/pen/GJmPQp)

#### Ширина ячеек

Ширина ячейки, так же как и ширина всей таблицы, если явно не указана, устанавливается автоматически исходя из содержимого. При определении ширины ячейки содержимое первично, то есть если оно не вмещается в явно указанную ширину, то ширина ячейки будет увеличена. Самая широкая ячейка в столбце определяет ширину столбца (то есть ширину всех ячеек в столбце)

![alt text](/images/table-2.png "table")

[http://codepen.io/dra1n/pen/jPmXKG](http://codepen.io/dra1n/pen/jPmXKG)

#### Что хорошего в таблицах?

* Легко делать колонки одинаковой высоты
* Можно центрировать данные по вертикали

![alt text](/images/table-3.png "table")

[http://codepen.io/dra1n/pen/doWwwb](http://codepen.io/dra1n/pen/doWwwb)

#### Что плохого в таблицах?

* Иногда с их помощью пытаются делать разметку макета (хотя они
  предназначены только для отображения структурированных данных)
* Ячейке нельзя задать позиционирование (а иногда очень хочется)

#### display: table

С помощью свойства display разным элементам можно задать такое же
поведение как и у таблицы, строки или ячейки [[http://codepen.io/dra1n/pen/QbvPgp](http://codepen.io/dra1n/pen/QbvPgp)]

## Трансформации

По аналогии с position: relative в потоке для элемента выделяется место,
которое он бы занимал не имея никаких трансформаций. То есть
трансформации не влияют на поток.

![alt text](/images/transform.png "transforms")

[http://codepen.io/dra1n/pen/ZGKPvO](http://codepen.io/dra1n/pen/ZGKPvO)

## Bonus (z-index)

#### Наложение элементов без указания z-index ([Stacking without z-index](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Understanding_z_index/Stacking_without_z-index))

Когда элементы не имеют z-index они накладываются в таком порядке (снизу
вверх):

* Бекграунд и границы корневого элемента
* Вложенные элементы в нормальном потоке в порядке появления в HTML коде
* Вложенные позиционированные элементы в порядке появления в HTML коде

![alt text](/images/zindex2.png "z-index")

[http://codepen.io/dra1n/pen/bdRdYv](http://codepen.io/dra1n/pen/bdRdYv)

#### Контекст вложенности ([Stacking context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Understanding_z_index/The_stacking_context))

![alt text](/images/zindex1.png "z-index")

[http://codepen.io/dra1n/pen/XbgbKG](http://codepen.io/dra1n/pen/XbgbKG)

## Bonus (layout)

![alt text](/images/layout.png "layout")

[http://codepen.io/dra1n/pen/XbgbKG](http://codepen.io/dra1n/pen/yNXNEw)

