**Какими регулярными выражениями я создавала файлы для импортирования в ELAN?**

Сначала ставим галочку на "Не выводить имена участников", убираем галочку с "сс.мс"

Чтобы убрать первые три столбца из экспортированного из ELAN файла используем такое регулярное выражение: `.*\t` на ничего. Получившийся текст из файла вставляем в Mystem

Убрала из экспортированного файла последний столбец: `(#|[а-яА-ЯЁё-]|/)` на ничего

Заменила `words@knc2006f` на `lemma@knc2006f`. В другом таком же файле: `words@knc2006f` на `morph@knc2006f`

В выдаче Mystem `.*{(.*?)=.*}` на `\1`, далее `.*{(.*?)}` на `\1` - текстовый файл с леммами. Во втором таком же файле: `.*{(.*?)=(.*)}` на `\2`, далее `.*{(.*?)}` на `\1` - текстовый файл с частями речи

Импортировала текстовый файл c `lemma@knc2006f` и таймкодами в Excel (как текст с разделителями), инструкцию нашла в справке Microsoft. Потом импортировала таким же образом файл с леммами, скопировала столбец, вставила в таблицу со слоем и таймкодами.

То же самое сделала с текстовыми файлами с частями речи. Получилось две таблицы Exel: одна с лемамми, названием слоя и таймкодами, другая - с частями речи, названием слоя и таймкодами. Сохранила их как текстовые файлы с разделителем-табуляцией. Потом открыла их в Notepad и преобразовала в кодировку UTF-8 (потому что иначе ELAN выдавал кракозябры).

Импортировала файлы в ELAN как текст с разделителями. (Указала первую строку с данными - 1, разделитель - табуляция, а также для столбоцов поставила "свойства": слой, время начала, время окончания, аннотация). Ура, получилось!
