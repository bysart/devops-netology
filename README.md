# DevOps-netology - учебный курс для DevOps инженеров

Это публичный репозиторий, созданный для обучения и отработки навыков.
Если вы DevOps специалист, то полезной информации для вас тут нет.

Здесь будут опубликованы некоторые ДЗ по курсу.
Github - простой и удобный способ доставки решения до преподавателя.

## Задание - 2.4 git инструменты

Git содержит достаточно большое количество команд. Выполнение некоторых приводит к одному и тому же результату.

Для отработки навыков, постараюсь получить результат разными командами.

Самое основное, что нужно помнить всегда - все что необходимо уже содержится в man.

> 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

Ответ:
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md

Использовал:
`git show aefea`;
`git log --pretty=format:"%H , %s" | grep ^aefea`

> 2. Какому тегу соответствует коммит 85024d3?

Ответ:
v0.12.23

Использовал:
`git show 85024d3`;
`git tag --points-at 85024d3` 

> 3. Сколько родителей у коммита b8d720? Напишите их хеши.

Ответ:
- Par1: 56cd7859e05c36c06b56d013b55a252d0bb7e158
- Par2: 9ea88f22fc6269854151c571162c5bcf958bee2b

Использовал:
`git show b8d720^`;
`git show b8d720^2`

> 4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

Ответ:
- b14b74c4939dcab573326f4e3ee2a62e23e12f89 [Website] vmc provider links
- 3f235065b9347a758efadc92295b540ee0a5e26e Update CHANGELOG.md
- 6ae64e247b332925b872447e9ce869657281c2bf registry: Fix panic when server is unreachable
- 5c619ca1baf2e21a155fcdb4c264cc9e24a2a353 website: Remove links to the getting started guide's old location
- 06275647e2b53d97d4f0a19a0fec11f6d69820b5 Update CHANGELOG.md
- d5f9411f5108260320064349b757f55c09bc4b80 command: Fix bug when using terraform login on Windows
- 4b6d06cc5dcb78af637bbb19c198faff37a066ed Update CHANGELOG.md
- dd01a35078f040ca984cdd349f18d0b67e486c35 Update CHANGELOG.md
- 225466bc3e5f35baa5d07197bbc079345b77525e Cleanup after v0.12.23 release

Использовал:
`git log v0.12.24...v0.12.23 --pretty=oneline`

> 5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).

Ответ:
8c928e83589d90a031f811fae52a81be7153e82f

Использовал:
`git log -S "func providerSource("`

> 6. Найдите все коммиты в которых была изменена функция globalPluginDirs.

Ответ:
- 78b12205587fe839f10d946ea3fdc06719decb05
- 52dbf94834cb970b510f2fba853a5b49ad9b1a46
- 41ab0aef7a0fe030e84018973a64135b11abcd70
- 66ebff90cdfaa6938f26f908c7ebad8d547fea17

Использовал:
`git grep -e "globalPluginDirs("` - поиск файла где функция создается;
`git log -L :globalPluginDirs:plugins.go` поиск коммитов, в которых вносятся изменения в функцию.

> 7. Кто автор функции synchronizedWriters?

Ответ:
Martin Atkins <mart@degeneration.co.uk>

Использовал:
`git log -S "synchronizedWriters("` - поиск коммита, где создается функция;
`git show 5ac311e2a91e381e2f52234668b49ba670aa0fe5` - просмот информации о коммите.

## Задание - объяснить наполнение файла  .gitignore

```
**/.terraform/* - игнорирование всего, что лежит в директории /.terraform/, которая может находится где угодно

*.tfstate - игнорирование файлов,которые заканчиваются на .tfstate
*.tfstate.* - игнорирование файлов,которые содержат .tfstate.

crash.log - игнорирование файла crash.log

*.tfvars - игнорирование файлов,которые заканчиваются на *.tfvars

override.tf
override.tf.json
- игнорирование override.tf, override.tf.json

*_override.tf
*_override.tf.json
- игнорирование файлов,которые заканчиваются на _override.tf, _override.tf.json

.terraformrc
terraform.rc
- игнорирование файлов .terraformrc, terraform.rc
```

## Задание - добавить первую строку в README.MD

Привет МИР!
