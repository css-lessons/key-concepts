## Свойство display

#### display: block

Блочные элементы отображаются на странице в виде прямоугольника, занимают всю ширину доступную ширину. Высота блочного элемента определяется его содержимым или может быть явно задана.

![alt text](/images/display-block.png "display: block")

[http://codepen.io/dra1n/pen/gpmVmP](http://codepen.io/dra1n/pen/gpmVmP)

В потоке по умолчанию блочный элемент занимает всю доступную ширину, даже если явно заданная ширина меньше ширины родителя.

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

При display: none элемент полностью удаляется из потока при visibility:
hidden элемент остается в потоке, то есть занимает отведенное для него
место, но не отображается.

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
  плавающими элементами. Проблема – несмотря на то, что контейнер снова влияет на
поток, его собственная высота равна нулю [[http://codepen.io/dra1n/pen/jPmZaQ](http://codepen.io/dra1n/pen/jPmZaQ)]

![alt text](/images/float-left-5.png "float: left")

* Использование свойства clear для элемента, находящегося на одном
  уровне с плавающими элементами (ручная очистка float). Проблема – требуется дополнительный элемент. [[http://codepen.io/dra1n/pen/QbvQPo](http://codepen.io/dra1n/pen/QbvQPo)]

* Задание overflow контейнеру [[http://codepen.io/dra1n/pen/EjmEPN](http://codepen.io/dra1n/pen/EjmEPN)]

* clearfix [[http://codepen.io/dra1n/pen/mJmxdL](http://codepen.io/dra1n/pen/mJmxdL)]

![alt text](/images/float-left-6.png "float: left")

## position: absolute (fixed)

#### absolute

position: absolute не оставляет места в потоке для элемента. Вообще.
Вместо этого позиционирует элемент в указанном месте относительно его
ближайшего позиционированного родителя (имеющего position relative, fixed или absolute).
Абсолютно позиционированные элементы могут иметь марджины, которые не
накладываются ни на какие другие марджины.

![alt text](/images/position-absolute.png "position: absolute")

[http://codepen.io/dra1n/pen/NqjYXK](http://codepen.io/dra1n/pen/NqjYXK)
