# dialogs

============

Подключение:

Требуется: jquery-1.11.1, jquery.mousewheel

Файлы плагина: dialogs.js, dialogs.css

==============


Использование:

<div class="ilex-dialog" id="dialogID"></div>


Открытие диалога: ILex_OpenDialog(dialog, options);

dialog - JQuery селектор или объект. Обязательное.

options - набор параметров.


Закрытие диалога: ILex_OpenDialog(dialog);

dialog - JQuery селектор или объект. Обязательное.

Открытие сообщения об ошибке: ILex_OpenErrorDialog(content, options);

content - HTML контент.

options - набор параметров.


Открытие информационного сообщения: ILex_OpenMessageDialog(content, options);

content - HTML контент.

options - набор параметров.


==========

Параметры:

width: integer. Ширина диалога.

disableScroll: boolean. Отключение прокрути страницы. По умолчанию true.

showClose: boolean. Показывать кнопку закрытия. По умолчанию true.

showOverlay: boolean. Показывать оверлей. По умолчанию true.

    Если false, то доступны следующие параметры:
    
    closeOnOuterClick: boolean. Закрывать диалог по клику вне него. По умолчанию false.
    
    toggle: boolean. Закрывать диалог при попытке открыть его снова. По умолчанию false.
    
position: string. Способ позиционирования: absolute/fixed. По умолчанию fixed.

    Если absolute, то disableScroll = false и доступны параметры:
    
    pos: object. Набор параметров позиционирования:
    
        target: JQ object/string. DOM элемент, относительно которого позиционируется диалог. По умолчанию body.
        
        alignX: string. Горизонтальное выравнивание. Доступны значения:
        
            left - левая граница диалога выравнивается по левой границе объекта;
            
            outerLeft - правая граница диалога выравнивается по левой границе объекта;
            
            right - правая граница диалога выравнивается по правой границе объекта;
            
            outerRight - левая граница диалога выравнивается по правой границе объекта;
            
            center - диалог выравнивается по центру объекта (по умолчанию).
            
        alignY: string. Вертивальное выравнивание. Доступны значения:
        
            top - верхняя граница диалога выравнивается по верхней границе объекта;
            
            outerTop - нижняя граница диалога выравнивается по верхней границе объекта;
            
            bottom - нижняя граница диалога выравнивается по нижней границе объекта;
            
            outerBottom - верхняя граница диалога выравнивается по нижней границе объекта;
            
            center - диалог выравнивается по центру объекта (по умолчанию).
            
        offsetX: integer. Сдвиг по оси X. По умолчанию 0.
        
        offsetY: integer. Сдвиг по оси Y. По умолчанию 0.
        
        
        
События:onBeforeShow - событие перед открытием диалога.

onAfterShow - событие после открытия диалога.

onClose - событие после закрытия диалога.



Inline параметры:

data-dialog-title - Заголовок.

data-dialog-options - Все опции в виде JSON-Объекта.



==================

История изменений:

2.0

Futures:

Теперь системные функции не болтаются в глобальной области видимости

Плагин jquery.mousewheel поставляется в комплекте.

Добавлена горизонтальная прокрутка на тач-устройствах в случае, когда даилог не помещается на экране по ширине.

Добавлена возможность показывать диалог с абсолютным позиционированием, а не только с фиксированным;

    - так же можно указать привязку в объекту и горизонтальное и вертикальнео выравниение, относительно него. Так же доступен сдвиг относительно конечных координат.
    
Картинка кнопки закрытия теперь векторная.

Теперь диалоги по умолчанию считают ширину с учетом внутренних отступов и рамок, как на уровне js, так и на css.

Fix:

Исправлены баги с выключением/включением прокрутки при множестве диалогов, с различными параметрами.

Добавлена проверка на количество тач-прикосновений, во избежании блокировки попытки масштабирования.

Исправлено сохранение параметров для каждого диалога.

Changes:

Параметры диалога теперь можно задавать в атрибуте data-dialog-options.

Заголовок в атрибутах теперь задается data-dialog-title, ранее было dialog-title.

Класс кнопки закрытия .close => .dialog-close.

Класс загаловка .title => .dialog-title.


Класс контейнера в диалогах ошибки/успеха .content => .dialog-content.



2.0.1

Fix:

Исправлена ситуация, что в некоторых браузерах не отключалась прокрутка с помощью disableScroll.



2.0.2

Fix:

Исправлена ошибка, возникающая при попытке открыть несуществующий диалог.


2.0.3

Fix:

Исправлена ошибка, при которой нельзя было отключить заголовок


2.0.4

Changes:

Добавлена опция showOverlay (по умолчанию true)


2.0.5b

Fix: 

Исправлена работа атрибута data-dialog-title



2.0.6

Fix:

Добавлены проверки на наличие опций у диалогов при открытии и закрытии.

Исправлена ошибка с позиционированием, возникающая при повторном открытии диалога, но уже другого размера.



2.1.0

Futures:

Добавлена опция closeOnOuterClick (по умолчанию false, работает только при showOverlay = false). При клике вне диалога он будет закрыт.

Добавлена опция toggle (по умолчанию false, работает только при showOverlay = false). При повторном вызове диалога он будет закрыт.

Fix:

Исправлена ошибка с отключение заголовка.

Исправлена ошибка с отключение кнопки закрытия.

Changes:

Теперь событие onBeforeShow вызывает до проверки активности диалога.
