Настройка вотчера

Идём в Preferences -> Tools ->File Watchers и добавляем новый. Тут вся мякотка.

Scope — Project Files. Мы ж не хотим проверять файлы не из нашего проекта.

Program — это полный путь до флейка. Если используете виртуальное окружение, он лежит в нём в bin. Можете просто сделать which flake8 в консоли. У меня это /Users/ilebedev/.virtualenvs/project_name/bin/flake8.

Arguments — это $FileDir$/$FileName$. Просто скопируйте, это полный путь до файла по-пайчармовски.

Working directory — это путь до корня проекта: место, где лежит setup.cfg с настройками флейка. У меня это /Users/ilebedev/projects/project_name/core/.

Show console — Never. К чёрту консоль, у нас всё будет в редакторе.

Output filters — $FILE_PATH$:$LINE$:$COLUMN$: $MESSAGE$. Это мы рассказываем Пайчарму про формат вывода флейка.

Теперь Пайчарм умеет запускать флейк когда мы редактируем файл, но не умеет выводить результаты.
Настройка инспекции
Идём в Preferences -> Editor->Inspections. Там в списке проверок ищем File watcher problems, ставим ему Severity: Error, чтобы ошибки подчёркивались раздражающей красной волнистой линией.