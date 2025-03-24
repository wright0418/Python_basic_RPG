---
marp: true
---

# 第八章：Python模組系統與import用法 - 龍與地下城冒險

## 學習目標
- 理解模組的概念與用途
- 學習如何導入模組
- 掌握模組的組織方式
- 實作模組化遊戲系統

## 模組基礎

### 什麼是模組？
模組是一個包含Python定義和陳述式的檔案，可以在其他Python程式中重複使用。

### 基本import用法
```python
import game_character
import game_items
```

### 使用模組功能
```python
warrior = game_character.create_warrior("勇者")
sword = game_items.create_weapon("鐵劍", 10)
```

## 模組開發

### 建立模組
```python
# game_character.py
def create_warrior(name):
    warrior = {
        "name": name,
        "hp": 100
    }
    return warrior
```

### 模組化設計
- 將相關功能歸類到同一個模組
- 每個模組專注於特定功能
- 模組之間保持獨立性

## 實作練習建議

1. **角色模組**
   - 角色創建功能
   - 屬性管理功能
   - 技能系統

2. **物品模組**
   - 物品創建
   - 物品使用
   - 裝備管理

3. **戰鬥模組**
   - 戰鬥計算
   - 技能效果
   - 傷害處理

## 小結

在本章中，我們學習了：
1. 模組的基本概念
2. 如何導入和使用模組
3. 模組化程式設計的原則
4. 如何組織遊戲程式碼

## 課後挑戰

設計一個模組化的遊戲系統，包含：
1. 角色管理模組
2. 物品系統模組
3. 戰鬥系統模組
4. 遊戲紀錄模組

在下一章中，我們將學習Python例外處理，讓你的程式能夠更好地處理錯誤情況！
