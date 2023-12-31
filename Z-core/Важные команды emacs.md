202312251331
Tags: #

---
# Важные команды [[Emacs]]
Все ``командные сокращения (keystrokes)'' в Emacs (те, которые `M-x что-нибудь` или `C-что-нибудь`) в действительности являются указателями на функции, которые являются частью Emacs. Вы можете вызвать любую из этих функций набрав `M-x имя-функции` и нажав `Enter`. Вы также можете использовать клавиатурное сокращение для этой функции (если оно имеется).

Например функция Emacs, которая сохраняет буфер на диск называется `save-buffer`. По умолчанию она также присвоена комбинации клавиш `C-x C-s`. Так что вы можете использовать либо эту комбинацию клавиш, либо вы можете набрать `M-x save-buffer` и достигнете тех же самых результатов.

|Сочетание клавиш |  Функция      |      Описание|
|---------------------|-----------------|---------------|
|C-x C-s | save-buffer     |   Сохранить буфер на диске |
|C-x u   |    undo         |      Отменить последнюю операцию|
|C-c C-f |    find-file    |      открыть файл на диске
|C-s    |     isearch-forward  |   Поиск строки вперед
|C-r    |     isearch-backward |  Поиск строки назад |
||   replace-string  |   Поиск и замена строки
||   replace-regexp  |    Поиск и замена с использованием регулярного выражения
|C-h t    |   help-with-tutorial | Использовать интерактивный учебник
|C-h f    |    describe-function |  Показать справку по функции
|C-h v    |  describe-variable |  Показать справку по переменной
|C-h x    |   describe-key     |  Показать данные, о том, что делает последовательность клавиш
|C-h a    |   apropos          |  Поиск в справке по строке/регулярному выражению
|C-h F    |   view-emacs-FAQ   |  Показать Emacs FAQ
|C-h i    |   info             |  Документация по Emacs (Info)
|C-x r m  |   bookmark-set     |  Установить закладку. Полезно при поисках
|C-x r b  |   bookmark-jump    |  Перейти к закладке

There are many C-x commands.  Here is a list of the ones you have learned:

	C-x C-f		Find file
	C-x C-s		Save buffer to file
	C-x s		Save some buffers to their files
	C-x C-b		List buffers
	C-x b		Switch buffer
	C-x C-c		Quit Emacs
	C-x 1		Delete all but one window
	C-x u		Und
	C-x k  Kill buffer
---
### Zero-links

- [[00 Emacs]]

---
### Links

-