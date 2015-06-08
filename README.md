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
