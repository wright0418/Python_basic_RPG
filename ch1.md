---
marp: true
---

# 第一章：Python 基礎入門 - 龍與地下城冒險(RPG)

## 學習目標
- 了解 Python 的基本介紹與特點
- 掌握基本的輸出功能：`print()` 函數
- 學習獲取用戶輸入：`input()` 函數
- 掌握字串格式化：f-string 的使用方法

## Python 簡介

Python 是一種高階、通用型的程式語言，以其簡潔易讀的語法而聞名。它被廣泛應用於網頁開發、數據分析、人工智能、科學計算和自動化等領域。在我們的教學中，我們將通過龍與地下城的角色扮演冒險故事來學習 Python。

### Python 的優勢：

1. **易學易用**：語法簡潔明了，接近自然語言
2. **豐富的生態系統**：擁有大量的第三方庫
3. **跨平台**：可在 Windows、Mac OS、Linux 等系統上運行
4. **廣泛的應用領域**：從網頁開發到人工智能，應用範圍極廣

## Python 基礎輸出：`print()` 函數

`print()` 函數是 Python 中最基本的輸出函數，用於在控制台顯示文字或變數的值。

### 基本用法

```python
print("你眼前出現了一位神秘的法師...")
print("法師說：「歡迎來到Python的奇幻世界，勇敢的冒險者！」")
```

這段代碼會在控制台顯示：
```
你眼前出現了一位神秘的法師...
法師說：「歡迎來到Python的奇幻世界，勇敢的冒險者！」
```

### 多行字串輸出

使用三個引號 `"""` 或 `'''` 可以創建多行字符串：

```python
print("""
法師拿出一本古老的魔法書，上面寫著：
「Python是一種強大而靈活的程式語言，
 它簡單易學，卻能創造無窮的可能性。」
""")
```

輸出效果：
```
法師拿出一本古老的魔法書，上面寫著：
「Python是一種強大而靈活的程式語言，
 它簡單易學，卻能創造無窮的可能性。」
```

## Python 輸入：`input()` 函數

`input()` 函數用於從使用者獲取輸入。函數會暫停程式的執行，等待使用者輸入文字並按下 Enter 鍵。

### 基本用法

```python
player_name = input("請輸入你的名字：")
print("法師點頭說道：「啊，" + player_name + "，一個注定成為傳奇的名字！」")
```

這段代碼會：
1. 顯示提示訊息 "請輸入你的名字："
2. 等待使用者輸入
3. 將輸入的文字存入 `player_name` 變數
4. 使用這個變數來顯示一個訊息

### 獲取並使用多個輸入

```python
character_race = input("選擇你的種族 (人類/精靈/矮人/半獸人)：")
character_class = input("選擇你的職業 (戰士/法師/盜賊/牧師)：")

print("\n角色創建完成！")
print("名稱：" + player_name)
print("種族：" + character_race)
print("職業：" + character_class)
```

在這個例子中，我們獲取了使用者對種族和職業的選擇，並將這些信息顯示出來。

### 字串連接

在上面的例子中，我們使用了 `+` 操作符來連接字串：

```python
print("名稱：" + player_name)
```

這是連接字串的一種方式，但當需要連接多個變數和字串時，可能會變得不那麼方便。這就是為什麼我們需要學習 f-string。

## 字串格式化：f-string

f-string（格式化字串字面值）是 Python 3.6 引入的一種字串格式化方法，它提供了一種簡潔而強大的方式來將變數嵌入字串中。

### 基本用法

在字串前加上字母 `f`，然後在字串中使用花括號 `{}` 來插入變數：

```python
print(f"法師說：「偉大的{character_race} {character_class}啊，歡迎你，{player_name}！」")
```

這比使用 `+` 連接字串更加直觀和簡潔。

### 顯示數值和變數

```python
strength = 10
intelligence = 10
dexterity = 10
charisma = 10

print(f"力量: {strength}")
print(f"智力: {intelligence}")
print(f"敏捷: {dexterity}")
print(f"魅力: {charisma}")
```

### 進階格式化：數值格式

f-string 允許我們控制數值的顯示格式：

```python
health = 100
mana = 50
print(f"生命值: {health}/100 ({health}%)")
print(f"魔力值: {mana}/100 ({mana}%)")
```

### 進階格式化：文本對齊

f-string 提供了強大的文本對齊功能：

```python
print(f"{'屬性':<10}{'數值':>5}")
print(f"{'-'*15}")
print(f"{'力量':<10}{strength:>5}")
print(f"{'智力':<10}{intelligence:>5}")
```

格式說明：
- `:<10` 表示靠左對齊，總寬度為10個字符
- `:>5` 表示靠右對齊，總寬度為5個字符
- `{'-'*15}` 使用字符重複運算符創建分隔線

輸出效果：
```
屬性          數值
---------------
力量             10
智力             10
```

### 在 f-string 中進行計算

f-string 還允許在花括號 `{}` 內進行簡單計算：

```python
level = 1
exp_needed = level * 100
print(f"當前等級: {level}")
print(f"升級所需經驗: {exp_needed}")
```

## 實作練習

1. 創建一個更完整的角色創建系統，讓使用者輸入更多的角色資訊（如年齡、背景故事等）
2. 使用 f-string 創建一個格式化的角色屬性卡，包含更多統計數據
3. 實現一個簡單的冒險開頭，根據使用者的輸入給出不同的回應

## 小結

在這一章中，我們學習了：
- Python 的基本輸出函數 `print()`
- 獲取使用者輸入的 `input()` 函數
- 使用 f-string 進行字串格式化

這些是 Python 程式設計的基礎，也是創建互動程式的關鍵。在下一章中，我們將學習條件判斷與控制流程，這將使我們的程式能夠根據不同情況做出不同的反應，為我們的龍與地下城冒險增添更多可能性。

## 課後挑戰

創建一個龍與地下城角色生成器，實現以下功能：
1. 讓使用者輸入角色的名稱、種族、職業和背景故事
2. 根據選擇的種族和職業，自動調整角色的屬性值
3. 使用 f-string 創建一個美觀的角色資料卡，包含所有角色信息和屬性
4. 為角色生成一段個性化的介紹文字，融合使用者提供的所有資訊