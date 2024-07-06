## Algorithm 演算法
### 演算法的定義
一個有限的、明確規定的步驟集合，這些步驟按照一定的順序執行，最終達到預期的結果。簡單來說，演算法就是解決某一類問題的方法或過程。
### 需要滿足的條件
1. 有限性（Finiteness）：
	演算法必須在有限步驟內結束。換句話說，它不能是無限循環的，必須保證在有限的時間內產生結果。
2. 明確性（Definiteness）：
	演算法的每一步驟必須是明確和無歧義的。每一步操作都應該清晰、精確，讓執行者（無論是人還是機器）可以毫無疑問地進行操作。
3. 輸入（Input）：
	演算法應該有零個或多個輸入。這些輸入是演算法處理的初始數據，從外部提供給演算法。
4. 輸出（Output）：
	演算法應該有一個或多個輸出。這些輸出是演算法完成計算或處理後產生的結果。
5. 可行性（Feasibility）：
	演算法的每一步操作都應該是基本的，理論上可以在有限的時間內完成。換句話說，每一步操作都應該是實際可行的。
## Recursion 遞迴

### 遞迴的定義
遞迴是一個過程，其中函數調用自身以解決更小的子問題。每個遞迴過程必須有一個基礎情況（基準情況），以便在某些條件下終止遞迴調用，防止無限遞迴。
### 三種類型
1. 直接遞歸（Direct Recursion）：
	當一個函數直接調用自身時，稱之為直接遞歸。這是最常見的遞歸形式。
``` python
# 計算階乘
def factorial(n): 
	if n == 0: 
		return 1 
	else: 
		return n * factorial(n - 1)
```
2. 間接遞歸（Indirect Recursion）：
	當一個函數通過調用其他函數間接調用自身時，稱之為間接遞歸。即函數A調用函數B，函數B再調用函數A。
``` python
# 函數A調用函數B，函數B再調用函數A
def functionA(n): 
	if n > 0: 
		print("Function A", n) 
		functionB(n - 1) 
def functionB(n): 
	if n > 0: 
		print("Function B", n) 
		functionA(n - 1)
```
3. 尾遞歸（Tail Recursion）：
	當一個函數在遞歸調用之後不再進行任何操作，這種形式的遞歸稱為尾遞歸。尾遞歸的特點是遞歸調用是函數中的最後一步操作。
	這種遞歸可以被優化為迭代，減少調用堆棧的深度，從而提高性能。
``` python
# 尾遞歸版本的計算階乘
def tail_recursive_factorial(n, accumulator=1): 
	if n == 0: 
		return accumulator 
	else: 
		return tail_recursive_factorial(n - 1, n * accumulator)
```