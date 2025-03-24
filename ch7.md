---
marp: true
---

# 第七章：Python檔案處理技巧 - 龍與地下城冒險

## 學習目標
- 理解檔案處理的基本概念
- 學習讀寫文字檔案
- 掌握檔案處理的錯誤處理
- 實作遊戲存檔系統

## 檔案處理基礎

### 檔案開啟模式
```python
# 寫入模式（覆蓋）
file = open("save.txt", "w")

# 讀取模式
file = open("save.txt", "r")

# 追加模式
file = open("save.txt", "a")
```

### 基本檔案寫入
```python
def save_game_data():
    file = open("save.txt", "w")
    file.write("角色名稱：勇者\n")
    file.write("等級：1\n")
    file.close()
```

### 基本檔案讀取
```python
def load_game_data():
    try:
        file = open("save.txt", "r")
        data = file.readlines()
        file.close()
        for line in data:
            print(line.strip())
    except:
        print("找不到存檔！")
```

## 檔案處理應用

### 遊戲存檔
```python
def save_character(name, level, hp, mp):
    file = open("character.txt", "w")
    file.write(f"名稱：{name}\n")
    file.write(f"等級：{level}\n")
    file.write(f"生命：{hp}\n")
    file.write(f"魔力：{mp}\n")
    file.close()
```

### 背包系統
```python
def save_inventory(items):
    file = open("inventory.txt", "w")
    for item in items:
        file.write(f"{item}\n")
    file.close()
```

## 進階應用

### 存檔檢查
```python
def check_save_file():
    try:
        file = open("save.txt", "r")
        file.close()
        return True
    except:
        return False
```

### 追加記錄
```python
def add_game_log(message):
    file = open("game_log.txt", "a")
    file.write(f"{message}\n")
    file.close()
```

## 實作練習建議

1. **角色存檔系統**
   - 儲存角色資料
   - 讀取角色資料
   - 更新角色資訊

2. **背包管理系統**
   - 儲存物品清單
   - 新增/移除物品
   - 讀取背包內容

3. **遊戲記錄系統**
   - 記錄遊戲事件
   - 保存戰鬥記錄
   - 查看歷史記錄

## 小結

在本章中，我們學習了：
1. 檔案的基本讀寫操作
2. 不同的檔案開啟模式
3. 檔案處理的錯誤處理
4. 如何實作遊戲存檔功能

## 課後挑戰

設計一個完整的遊戲存檔系統，包含：
1. 角色資料的儲存與讀取
2. 背包系統的存檔功能
3. 遊戲進度的保存
4. 多個存檔欄位

在下一章中，我們將學習Python的模組(Module)系統與import用法，
讓你能夠更有效地組織程式碼，並使用豐富的Python套件庫！
