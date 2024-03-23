# Instruction
## algorithm
### ternary search
三分搜尋法
## data structure
### bfs
使Bfs實作較方便的資料結構，改良自queue

V1 with dp: t.first=index, t.second=val，會根據val值進行判斷，如果當前val>=最佳val則不會push進去，節省時間

V2 with mutiple argument: 將資料包成vector，只會比對資料有沒有出現過，出現過不會push進去，數字大小上限約1e9
### bit
[Sample](https://hackmd.io/kfG8cKWFTimdIkL8DmgCYw?view#bit)

Base 0，區間操作為[L,R]

### discretization 
[Sample](https://hackmd.io/kfG8cKWFTimdIkL8DmgCYw?view#discretization)

離散化，執行run後會使插入的資料排序並給一個key=[0,size)，可以O(1)查資料的key和查key對應的資料，add可以輸入int和vector<int>

如果想要由大到小排序可以這樣修改
```cpp=6
    void add(int tar){s.insert(-tar);}
    void add(vector<int>v){
        for(auto i:v)
            s.insert(-i);
    }
    void run(){
        cnt=0;
        for(auto i:s){
            mp[-i]=cnt++;
            rec.push_back(-i);
        }
    }
```
### dsu
[Sample](https://hackmd.io/kfG8cKWFTimdIkL8DmgCYw#dsu)

disjoint set unoin 並查集

有支援同時計算size的功能
### quad tree
四叉樹，類似2D的BIT，只是每次遞迴切成四等分，模擬產生一個(sz+1)*(sz+1)的array，範圍為[0,sz]，但當存取陣列內容時才會初始化

init: 設定sz，O(1) 

update: 單點修改，O lg(n)可以讓array[x][y]+=val

query: 區間查詢，O lg(n)查詢array[x][y]~array[a][b]圍成的四邊形內元素的和，有防呆，輸入左上右下或左下右上結果都一樣

通常會搭配離散化使用
### segement tree
使lazy tag的操作較容易修改，僅需修改op、range_op、push、pull，預設為ADD操作，區間操作為[L,R]，Base 0
### sqrt decomposition
### trie
可修改ch、node->nxt大小、query來達到想要的功能
## geometry
## graph
### dijkstra
## math
### isprime
有兩種時間複雜度，依需求使用
1. O(sqrt(n)) for each query
2. O(nlgn) for build, O(1) for each query
## misc
尚未整理的部分
## stl expansion
### priority_queue
priority_queue<vector<int>> ，可能存在問題
### string
split(string, token): 類似python的split，return一個vector

substr(string, l, r): 將切割方式從[l,l+r)改成[l,r]
### unordered_map
unordered_map<vector<int>,T>
## string
### hash
[Sample](https://hackmd.io/kfG8cKWFTimdIkL8DmgCYw?view#hash)

可以O(1)比對兩字串是否相等，採用double hashing
### KMP
### manacher
### SA