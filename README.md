# 112-2-CS1010301 Group1-Plumber

 ## Member
  B11230017-吳秉彥(組長)
  
## Quick Start
  - 使用到的外部庫有: IrrKlang.
  - 照理來說應該可以在Linux/Windows系統運行，但我沒有實際測試過，所以只保證在Windows"可能可以運行"。
  Windows的話應該只要無腦的用CMakeLists建置就可以了，但如果是其他作業系統的話，可能需要進入CmakeLists.txt更改Irrklang的安裝方式，又或者其實根本就不能運行，笑死。

## Control

![image](https://github.com/112-NTUST-CS1010301/group1/assets/99705287/7642af62-cb93-4cdb-953e-d81b2f1aa522)
- <kbd>a</kbd> 向左
- <kbd>d</kbd> 向右
- <kbd>SPACE</kbd> 選擇模式

![image](https://github.com/112-NTUST-CS1010301/group1/assets/99705287/eab1f3d2-828f-4b3f-b850-9c8743634853)
- 自訂的board檔案必須以txt格式上傳，並且必須與你的當前執行檔同個資料夾才能成功抓取。
- 本程式不會驗證board檔案的完整性，所以請務必先確定符合格式還有盤面確定可以通關。
### 格式範例
```
4 5
#P# #P# ### #P# #P#
PP# PPP PPP PPP PP#
### #P# ### #P# ###

#P# #P# #P# #P# #P#
PPP PPP PP# PPP PPP
#P# #P# ### ### ###

### ### ### ### ###
PPP PPP PPP PPP PPP
### ### ### ### ###

### ### ### #P# ###
PPP PPP PPP PP# PPP
### ### ### ### ###
```

![image](https://github.com/112-NTUST-CS1010301/group1/assets/99705287/fc078fc4-f950-4c45-86e1-433649217dc6)
- <kbd>a</kbd> 向左
- <kbd>d</kbd> 向右
- <kbd>s</kbd> 向下
- <kbd>w</kbd> 向上
- <kbd>e</kbd> 讓當前水管順時針轉
- <kbd>q</kbd> 讓當前水管逆時針轉

## Contribution
 吳秉彥-你想的到的全部工作
