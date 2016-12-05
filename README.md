# MainWindow Class

Esta clase representa la ventana principal de una aplicación, en el constructor 
inicializa la ventana con una barra de menú y una barra de estado.

## Constructor

Cuenta con el mismo constructor que la clase Window, pero recibe adicionalmente 
los campos `MenuTemplate` y `StatusbarText`

## Métodos

- [x] setChild
- [x] getChilds
- [ ] setMenuTemplate
- [ ] getMenuTemplate

## Ejemplo

```lua
-- Importar clases necesarias
local MainWindow = require 'forms.mainwindowclass'

app.MainWindow = MainWindow:new { 

  Name = 'windMain', Title = 'LNomina v0.0.1',
  Width = 800, Height = 600,
  Flags = WIN_DEFAULT_STYLE,

  MenuTemplate = 'forms/mainwindow_menutemplate.lua',
}

app.MainWindow:centre()

app.MainWindow.onClose : setHandler ( function ( ... )
    io.stdout:write '[lide.app] exit\n' io.stdout:flush () io.stdout:close ()
    os.exit()
end)

return app.MainWindow
```