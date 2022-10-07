# Patika.dev Binary-Search-Tree-Projesi

[Patika.dev - Binary Search Tree Proje Ödevi Linki](https://app.patika.dev/courses/veri-yapilari-ve-algoritmalar/binary-search-tree-proje)

# Binary Search Tree Projesi

Proje 3


[7, 5, 1, 8, 3, 6, 0, 9, 4, 2] dizisinin Binary-Search-Tree aşamalarını yazınız.

## Aşamalar :

temel mantık :  Listenin en başındaki sayı root olarak seçilir. Root'dan büyük sayılar sağına, root'dan küçük sayılar doluna yazılır.

```python 

class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data
# Insert Node
   def insert(self, data):
      if self.data:
         if data < self.data:
            if self.left is None:
               self.left = Node(data)
            else:
               self.left.insert(data)
         elif data > self.data:
            if self.right is None:
               self.right = Node(data)
            else:
               self.right.insert(data)
      else:
         self.data = data


   def inorderTraversal(self, root):
      res = []
      if root:
         res = self.inorderTraversal(root.left)
         res.append(root.data)
         res = res + self.inorderTraversal(root.right)
      return res

    
clusters  = [7, 5, 1, 8, 3, 6, 0, 9, 4, 2]

tree = Node(clusters[0])
for i in clusters[1:]:
    tree.insert(i)
    temp = tree.inorderTraversal(tree)
    print(*temp, sep=' - ')

```

```cmd
5 - 7
1 - 5 - 7
1 - 5 - 7 - 8
1 - 3 - 5 - 7 - 8
1 - 3 - 5 - 6 - 7 - 8
0 - 1 - 3 - 5 - 6 - 7 - 8
0 - 1 - 3 - 5 - 6 - 7 - 8 - 9
0 - 1 - 3 - 4 - 5 - 6 - 7 - 8 - 9
0 - 1 - 2 - 3 - 4 - 5 - 6 - 7 - 8 - 9
```
