# Lazarus "Hint from comment" ПО ДРУГОМУ #

**Идея**: 
для методов и функций искать "комментарий-описание" в разделе **implementation** в любом случае.

**Решение**:
не красивое. `ink_codehelp.pas`

Установка
---------
1. положить файл 
`ink_codehelp.pas` в директорию `...lazarus/ide/`
2. отредактировать файл 
`...lazarus/ide/CodeHelp.pas` обозначив метод `TCodeHelpManager.GetPasDocCommentsAsHTML` как `virtual`
3. отредактировать файл 
`...lazarus/ide/IDEHelpManager.pas` добавив в раздел `uses` модуль `ink_codehelp` и в конструкторе `TIDEHelpManager.Create` заменить строку `CodeHelpBoss:=TCodeHelpManager.Create(Self);` на ` CodeHelpBoss:=TinkCodeHelpManager.Create(Self);` 
