---
marp: true
---

# 第六章：Python類別(Class)概念 - 龍與地下城冒險

## 學習目標
- 理解類別的基本概念
- 學習定義和使用類別
- 掌握物件導向程式設計基礎
- 實作遊戲角色系統

## 類別基礎

### 什麼是類別？
類別是一種程式設計的模板，可以想像成角色的設計圖，定義了角色應該具有的屬性和能力。

### 基本類別定義
```python
class Character:
    def __init__(self, name):
        self.name = name
        self.hp = 100
        self.mp = 50
```

### 建立物件
```python
# 創建一個角色
player = Character("勇者")
print(f"角色名稱：{player.name}")
```

## 類別的組成部分

### 建構子 (__init__)
```python
def __init__(self, name):
    self.name = name    # 設定角色名稱
    self.hp = 100      # 設定初始生命值
    self.mp = 50       # 設定初始魔力值
```

### 方法
```python
def show_status(self):
    print(f"=== {self.name} 的狀態 ===")
    print(f"生命值：{self.hp}")
    print(f"魔力值：{self.mp}")
```

## 繼承

### 基本繼承概念
```python
class Warrior(Character):
    def __init__(self, name):
        Character.__init__(self, name)
        self.hp = 150  # 戰士有更多生命值
```

### 特殊方法
```python
def attack(self):
    print(f"{self.name} 使用物理攻擊！")
```

## 實作範例：角色系統

### 基本角色類別
```python
class Character:
    def __init__(self, name):
        self.name = name
        self.hp = 100
        self.mp = 50
        self.inventory = []
        
    def show_status(self):
        print(f"=== {self.name} 的狀態 ===")
        print(f"生命值：{self.hp}")
        print(f"魔力值：{self.mp}")
```

### 職業類別
```python
class Warrior(Character):
    def attack(self):
        print(f"{self.name} 揮動劍刃！")

class Mage(Character):
    def cast_spell(self):
        print(f"{self.name} 施放魔法！")
```

## 物件的使用

### 建立和使用物件
```python
# 創建角色
warrior = Warrior("戰士小明")
mage = Mage("法師小華")

# 使用方法
warrior.show_status()
warrior.attack()

mage.show_status()
mage.cast_spell()
```

## 實作練習建議

1. **角色類別系統**
   - 設計基礎角色類別
   - 實作不同職業類別
   - 添加技能和屬性

2. **道具類別系統**
   - 設計道具基礎類別
   - 實作不同類型道具
   - 實現道具效果

3. **戰鬥系統**
   - 實作戰鬥邏輯
   - 角色互動
   - 技能使用

## 小結

在本章中，我們學習了：
1. 類別的基本概念和定義方法
2. 如何建立和使用物件
3. 類別的繼承概念
4. 如何設計遊戲角色系統

## 課後挑戰

設計一個完整的角色系統，包含：
1. 多個職業類別（戰士、法師、盜賊等）
2. 技能系統
3. 等級成長系統
4. 裝備系統

在下一章中，我們將學習檔案處理的技巧，讓你能夠儲存遊戲進度！
