Config prettierrc + eslint

Создайте файл  .prettierrc в корне проекта и добавьте туда правила из файла репозитория, вы можете посмотреть значения этих правил и добавить свои, изучив документацию https://prettier.io/docs/en/options.html

нажмите ctrl shift p и зайдите в >Preferences: Open User Setting (JSON)
там в качестве дефолтного форматера впишите prettier  
`"editor.defaultFormatter": "esbenp.prettier-vscode" `

C помощью Ctrl +  , зайдите в настройки
В поиске наберите `auto save` в пункте Files: Auto Save выберите  onFocusChange - это необходимо для сохранения файла при потере фокуса файла

наберите `format on` и поставьте галочку в чексбоксе Editor: Format On Save - так при сохранении файла будут применяться правила из конфига Prettierrc

а также наберите `Prettier` в пункте prettier: Require Config  поставьте галочку, эта настройка будет требовать файл Prettierrc для каждого проекта

Теперь связываем Prettierrc + eslint, выполняем команду в терминале:
```
npm install --save-dev eslint-config-prettier eslint-plugin-prettier prettier
```
Если у вас нет файла .eslintrc.cjs , то выполните команду 
```
npx eslint --init
```
в .eslintrc.cjs в extends добавляем `'plugin:prettier/recommended',` в rules добавьте `'prettier/prettier': ['warn']`,  после чего может проверить подсветку синтаксиса, если вдруг не заработало нажмите ctrl shift p и наберите `>Developer: Reload Window` или перезапустите студию

Также можете добавить в  setting.json правило 
```
"editor.codeActionsOnSave": { "source.fixAll.eslint":true, }, 
```
оно будет фиксить ошибки правил eslint правил без использования ``husky``
