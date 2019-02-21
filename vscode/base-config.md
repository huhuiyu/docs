# vscode基础配置

- [返回](README.md)
  ***
- vscode基础配置  
  ![step001](images/vs012.png)  
  ![step002](images/vs013.png)  
  ![step003](images/vs014.png)  
  ![step004](images/vs015.png)  
  ![step005](images/vs016.png)  
  ![step006](images/vs017.png)  
  ![step007](images/vs018.png)  
  ![step008](images/vs019.png)  
  ![step009](images/vs020.png)  
  ![step010](images/vs021.png)  
  ![step011](images/vs022.png)  
  ![step012](images/vs023.png)  
  ![step013](images/vs024.png)  
  ***
- 配置代码

```json
  {  
    "workbench.iconTheme": "vscode-great-icons",
    "css.fileExtensions": ["css"],
    "html.format.wrapLineLength": 400,
    "editor.detectIndentation": false,
    "editor.tabSize": 2,
    "prettier.printWidth": 400,
    "prettier.singleQuote": true,
    "prettier.disableLanguages": ["vue", "html"],
    "beautify.language": {
      "js": {
        "type": ["json"],
        "filename": [".jshintrc", ".jsbeautifyrc"]
      },
      "css": ["scss"],
      "html": ["htm", "html"]
    },
    "search.followSymlinks": false,
    "window.zoomLevel": 0
  }
```

  ***

- [返回](README.md)