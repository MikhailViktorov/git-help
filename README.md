Основные команды
Всего несколько команд нужно для базового варианта использования Git для ведения истории изменений.

git add
Команда git add добавляет содержимое рабочего каталога в индекс (staging area) для последующего коммита. По умолчанию git commit использует лишь этот индекс, так что вы можете использовать git add для сборки слепка вашего следующего коммита.

Это одна из ключевых команд Git, мы упоминали о ней десятки раз на страницах книги. Ниже перечислены наиболее интересные варианты использования этой команды.

Знакомство с этой командой происходит в разделе Отслеживание новых файлов главы 2.

О том как использовать git add для разрешения конфликтов слияния написано в разделе Основные конфликты слияния главы 3.

В разделе Интерактивное индексирование главы 7 показано как использовать git add для добавления в индекс лишь отдельных частей изменённого файла.

В разделе Деревья показано как эта команда работает на низком уровне, чтобы вы понимали, что происходит за кулисами.

git status
Команда git status показывает состояния файлов в рабочем каталоге и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.

Мы познакомили вас с этой командой в разделе Определение состояния файлов главы 2, разобрали стандартный и упрощённый формат вывода. И хотя мы использовали git status повсеместно в этой книге, практически все варианты использования покрыты в указанной главе.

git diff
Команда git diff используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей копией и индексом (собственно git diff), разница между индексом и последним коммитом (git diff --staged), или между любыми двумя коммитами (git diff master branchB).

Мы познакомили вас с основами этой команды в разделе Просмотр индексированных и неиндексированных изменений главы 2, где показали как посмотреть какие изменения уже добавлены в индекс, а какие — ещё нет.

О том как использовать эту команду для проверки на проблемы с пробелами с помощью аргумента --check можно почитать в разделе Правила создания коммитов главы 5.

Мы показали вам как эффективно сравнивать ветки используя синтаксис git diff A…​B в разделе Определение применяемых изменений главы 5.

В разделе Продвинутое слияние главы 7 показано использование опции -w для скрытия различий в пробельных символах, а также рассказано как сравнивать конфликтующие изменения с опциями --theirs, --ours и --base.

Использование этой команды с опцией --submodule для сравнения изменений в подмодулях показано в разделе Начало работы с подмодулями главы 7.

git difftool
Команда git difftool просто запускает внешнюю утилиту сравнения для показа различий в двух деревьях, на случай если вы хотите использовать что-либо отличное от встроенного просмотрщика git diff.

Мы лишь вкратце упомянули о ней в разделе Просмотр индексированных и неиндексированных изменений главы 2.

git commit
Команда git commit берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.

Вы познакомились с основами модели коммитов в разделе Коммит изменений главы 2. Там же мы продемонстрировали использование опций -a для добавления всех изменений в индекс без использования git add, что может быть удобным в повседневном использовании, и -m для передачи сообщения коммита без запуска полноценного редактора.

В разделе Операции отмены главы 2 мы рассказали об опции --amend, используемой для изменения последнего совершённого коммита.

В разделе О ветвлении в двух словах главы 3 мы более подробно познакомились с тем, что делает команда git commit и почему она делает это именно так.

Мы показали вам как подписывать ваши коммиты, используя опцию -S в разделе Подпись коммитов главы 7.

И наконец мы заглянули внутрь команды git commit в разделе Объекты коммитов главы 10 и узнали что она делает за кулисами.

git reset
Команда git reset, как можно догадаться из названия, используется в основном для отмены изменений. Она изменяет указатель HEAD и, опционально, состояние индекса. Также эта команда может изменить файлы в рабочем каталоге при использовании параметра --hard, что может привести к потере наработок при неправильном использовании, так что убедитесь в серьёзности своих намерений прежде чем использовать его.

Мы рассказали об основах использования git reset в разделе Отмена индексации файла главы 2, где эта команда использовалась для удаления файла из индекса, добавленного туда с помощью git add.

В разделе Раскрытие тайн reset, полностью посвящённой этой команде, мы разобрались в деталях её использования.

Мы использовали git reset --hard чтобы отменить слияние в разделе Прерывание слияния главы 7, там же было продемонстрировано использование команды git merge --abort для этих целей, которая работает как обёртка над git reset.

git rm
Команда git rm используется в Git для удаления файлов из индекса и рабочей копии. Она похожа на git add с тем лишь исключением, что она удаляет, а не добавляет файлы для следующего коммита.

Мы немного разобрались с этой командой в разделе Удаление файлов главы 2, показали как удалять файлы из рабочего каталога и индекса и только из индекса, используя флаг --cached.

Ещё один вариант использования git rm приведён в разделе Удаление объектов главы 10, где мы вкратце объяснили как использовать опцию --ignore-unmatch при выполнении git filter-branch, которая подавляет ошибки удаления несуществующих файлов. Это может быть полезно для автоматически выполняемых скриптов.

git mv
Команда git mv — это всего лишь удобный способ переместить файл, а затем выполнить git add для нового файла и git rm для старого.

Мы лишь вкратце упомянули эту команду в разделе Перемещение файлов главы 2.

git clean
Команда git clean используется для удаления мусора из рабочего каталога. Это могут быть результаты сборки проекта или файлы конфликтов слияний.

Синхронизация локального и удалённого репозиториев
git remote add origin https://github.com/YandexPracticum/first-project.git (от англ. remote, «удалённый» + add, «добавить») — привяжи локальный репозиторий к удалённому с URL https://github.com/YandexPracticum/first-project.git;
git remote -v (от англ. verbose, «подробный») — проверь, что репозитории действительно связались;
git push -u origin main (от англ. push, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.
💡 Ваша ветка может называться master, а не main. Подправьте команду, если это необходимо.
git push (от англ. push, «толкать») — загрузи коммиты в удалённый репозиторий после того, как он был привязан с помощью флага -u.
Копирование чужих репозиториев
Клонирование
git clone git@github.com:TheGreatOwner/the-great-project.git (от англ. clone, «клон», «копия») — склонируй репозиторий с URL the-great-project.git из аккаунта TheGreatOwner на мой локальный компьютер.
«Форк»
«Форк» — операция, которая не связана с Git напрямую и выполняется через графический интерфейс GitHub (кнопка Fork в правом верхнем углу страницы репозитория). «Форк» создаёт независимую копию репозитория со всеми файлами, коммитами и ветками в аккаунте GitHub. Такая копия будет полностью независима. Внесённые изменения не будут синхронизированы с исходным репозиторием.
💡 Комбинацию «форк» + clone часто используют для внесения изменений в публичные репозитории. В этом случае «форк» становится подготовительным этапом перед клонированием чужого репозитория на локальный компьютер.
Если репозиторий приватный или это репозиторий вашей компании, при работе с ним достаточно clone.
SSH-ключи
Протокол SSH обеспечивает безопасный обмен данными в сети. С его помощью можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.
SSH-ключ состоит из двух частей — публичной и приватной. Приватный ключ хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных. Публичный ключ доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.
Файл с расширением .pub содержит публичный ключ, им можно делиться с веб-сайтами или коллегами. Файл без расширения .pub — приватный.
Прежде чем генерировать новую пару ключей, следует убедиться, что они отсутствуют на вашем компьютере. Проверить это можно командой ls -la .ssh/ в домашней директории. Если ключи отсутствуют, создать их можно командой ssh-keygen в директории ~/.ssh. После генерации ключ нужно привязать к GitHub.