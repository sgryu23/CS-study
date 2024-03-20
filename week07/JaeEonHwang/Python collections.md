# namedtuple
* immutable
* 이름을 통해 데이터로 접근 가능
* 메모리 활용 최적화
```python
from collections import namedtuple

point = namedtuple('point', ['x', 'y'])
p = point(11, y=22)

p[0] + p[1] # 33
p # point(x=11, y=22)
p.x # 11
p[x] # error
i, j = p
i, j # (11, 12)
i # 11

d = {'x': 100, 'y': 200}
p = point(**d)
p.x # 100

p.index(100) # 0
p.count(100) # 1
p.index('x') # error
p.count('x') # 0
```
# deque
* 양방향 큐
* 데이터 회전 가능
* maxlen을 통해 최대 항목 수 설정 가능
```python
from collections import deque

# maxlen을 3으로 설정한 deque 생성
my_deque = deque(maxlen=3)

# 요소 추가
my_deque.append(1)
my_deque.append(2)
my_deque.append(3)

print(my_deque)  # 출력: deque([1, 2, 3], maxlen=3)

# maxlen을 초과하는 요소 추가
my_deque.append(4)

print(my_deque)  # 출력: deque([2, 3, 4], maxlen=3)

my_deque.rotate # deque([4, 2, 3], maxlen=3)
```
# ChainMap
* 복수의 딕셔너리/리스트를 구분한 상태에서 합침
```python
from collections import ChainMap

dict1 = {'one': 1, 'two': 2, 'three': 3}
dict2 = {'four': 4}

chain = ChainMap(dict1, dict2)

print(chain) # ChainMap({'one': 1, 'two': 2, 'three': 3}, {'four': 4})

'one' in chain # True
'five' in chain # False

len(chain) # 4

chain.values() # ValuesView(ChainMap({'one': 1, 'two': 2, 'three': 3}, {'four': 4}))
chain.keys() # KeysView(ChainMap({'one': 1, 'two': 2, 'three': 3}, {'four': 4}))
chain.items() # ItemsView(ChainMap({'one': 1, 'two': 2, 'three': 3}, {'four': 4}))

chain[0] # error
chain['dict1'] # error

chain.maps # [{'one': 1, 'two': 2, 'three': 3}, {'four': 4}]
chain.maps[0] # {'one': 1, 'two': 2, 'three': 3}
```
# Counter
```python
from collections import Counter

a = [1, 1, 1, 2, 3, 4, 5, 5, 5, 6, 7, 8, 8, 8, 8]
c = Counter(a)
c # Counter({1: 3, 2: 1, 3: 1, 4: 1, 5: 3, 6: 1, 7: 1, 8: 4})
for i in c:
    print(i, end=', ') # 1, 2, 3, 4, 5, 6, 7, 8,
for i in c.elements():
    print(i, end=', ') # 1, 1, 1, 2, 3, 4, 5, 5, 5, 6, 7, 8, 8, 8, 8,
 
c.keys() # dict_keys([1, 2, 3, 4, 5, 6, 7, 8])
c.values() # dict_values([3, 1, 1, 1, 3, 1, 1, 4])
c.items() # dict_items([(1, 3), (2, 1), (3, 1), (4, 1), (5, 3), (6, 1), (7, 1), (8, 4)])

for i, j in c.items():
    print(i, j end=', ') # 1 3, 2 1, 3 1, 4 1, 5 3, 6 1, 7 1, 8 4,

c.most_common() # [(1, 3), (2, 1), (3, 1), (4, 1), (5, 3), (6, 1), (7, 1), (8, 4)] 

s = 'hello, world'
sc = Counter(s)
sc # Counter({' ': 1, ',': 1, 'd': 1, 'e': 1, 'h': 1, 'l': 3, 'o': 2, 'r': 1, 'w': 1})
sc.update('hello')
sc # Counter({' ': 1, ',': 1, 'd': 1, 'e': 2, 'h': 2, 'l': 5, 'o': 3, 'r': 1, 'w': 1})
sc.subtract('hello') 
sc # Counter({' ': 1, ',': 1, 'd': 1, 'e': 1, 'h': 1, 'l': 3, 'o': 2, 'r': 1, 'w': 1})
sc.subtract('hello') 
sc # Counter({' ': 1, ',': 1, 'd': 1, 'e': 0, 'h': 0, 'l': 1, 'o': 1, 'r': 1, 'w': 1})
sc.subtract('hello') 
sc # Counter({' ': 1, ',': 1, 'd': 1, 'e': -1, 'h': -1, 'l': -1, 'o': 0, 'r': 1, 'w': 1})

d = {'one': 100, 'two': 200, 'three': 300}
s = Counter(d)
s # Counter({'one': 100, 'three': 300, 'two': 200})
```
# OrderedDict
* 순서가 있는 dict 자료형
* LRU 알고리즘 구현 가능
* 3.7 버전부터는 딕셔너리 순서 유지
```python
from collections import OrderedDict

dict1 = {'one': 1, 'two': 2, 'three': 3}
d = OrderedDict(dict1)
d # OrderedDict([('one', 1), ('two', 2), ('three', 3)])

d.move_to_end('one')
d # OrderedDict([('two', 2), ('three', 3), ('one', 1)])

d.move_to_end('two')
d # OrderedDict([('three', 3), ('one', 1), ('two', 2)])

d.move_to_end('two', False)
d # OrderedDict([('two', 2), ('three', 3), ('one', 1)])

d.popitem() # ('one', 1)
d.popitme(False) # ('two', 2)
```
# defaultdict
* 키로 어떤 값이 들어올지 모를 경우 사용
```python
from collections import defaultdict

d = defaultdict(list)
d['one'] = '1'
d['two'] = '2'
d['three']
d # defaultdict(str, {'one': '1', 'three': [], 'two': '2'})

d = defaultdict(int)
for i in range(5):
    d[i] += 1
d # defalutdict(int, {0: 1, 1: 1, 2: 1, 3: 1, 4: 1})
```