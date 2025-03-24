---
marp: true
---

# 第九章：Python例外處理 - 龍與地下城冒險

## 學習目標
- 理解例外處理的概念與用途
- 學習使用try-except架構
- 掌握常見的例外類型
- 實作安全的遊戲功能

## 例外處理基礎

### 什麼是例外處理？
例外處理用於管理程式執行時可能發生的錯誤，讓程式能夠優雅地處理問題而不會崩潰。

### 基本語法結構
```python
try:
    # 可能發生錯誤的程式碼
    result = 10 / 0
except:
    # 處理錯誤的程式碼
    print("發生錯誤！")
```

### 指定例外類型
```python
try:
    file = open("save.txt", "r")
except FileNotFoundError:
    print("找不到檔案！")
except:
    print("發生其他錯誤！")
```

## 例外處理應用

### 檔案操作
```python
def load_game_data():
    try:
        file = open("save.txt", "r")
        data = file.read()
        file.close()
        return data
    except FileNotFoundError:
        print("找不到存檔！")
        return None
```

### 數值轉換
```python
def get_player_level():
    try:
        level = int(input("輸入等級："))
        return level
    except ValueError:
        print("請輸入有效的數字！")
        return 1
```

## 進階使用

### 使用raise拋出例外
```python
def use_item(item, character):
    if character["hp"] <= 0:
        raise ValueError("角色已經倒下！")
    # 使用道具的程式碼
```

### try-except-else-finally結構
```python
def save_game():
    file = None
    try:
        file = open("save.txt", "w")
        file.write("遊戲資料")
    except:
        print("儲存失敗！")
    finally:
        if file:
            file.close()
```

## 實作練習建議

1. **安全的檔案操作**
   - 存檔功能錯誤處理
   - 讀檔功能錯誤處理
   - 檔案關閉保證

2. **使用者輸入驗證**
   - 數值輸入檢查
   - 選項輸入驗證
   - 錯誤重試機制

3. **遊戲邏輯保護**
   - 角色狀態檢查
   - 戰鬥計算保護
   - 物品使用驗證

## 小結

在本章中，我們學習了：
1. 例外處理的基本概念
2. try-except的使用方法
3. 常見的例外類型
4. 如何實作安全的遊戲功能

## 課後挑戰

設計一個安全的遊戲系統，包含：
1. 完整的錯誤處理機制
2. 使用者輸入驗證
3. 檔案操作保護
4. 遊戲邏輯防護

在下一章中，我們將學習更多Python進階技巧，讓你的程式設計能力更上一層樓！
