### 软件使用

* ##### vscode右键菜单

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\*\shell\VSCode]
@="Open with Code"
"Icon"="D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe"

[HKEY_CLASSES_ROOT\*\shell\VSCode\command]
@="\"D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe\" \"%1\""

[HKEY_CLASSES_ROOT\Directory\shell\VSCode]
@="Open with Code"
"Icon"="D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe"

[HKEY_CLASSES_ROOT\Directory\shell\VSCode\command]
@="\"D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe\" \"%V\""

[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode]
@="Open with Code"
"Icon"="D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode\command]
@="\"D:\\Tools\\VSCode-win32-x64-1.30.2\\Code.exe\" \"%V\""

```



