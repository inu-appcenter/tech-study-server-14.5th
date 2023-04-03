# Tree

## Concept

트리는 <b>노드로 이루어진 자료구조</b>이다

    1. 트리는 하나의 루트 노드를 가진다
    2. 루트 노드는 0개 이상의 자식 노드를 가진다
    3. 그 자식 노드 또한 0개 이상의 자식 노드를 가진다 (반복)

트리는 노드(node)들과 이를 연결하는 간선(edge)들로 구성된다

- 트리에는 사이클(cycle)이 존재할 수 없다
  - (= 사이클이 없는 하나의 연결 그래프라고도 볼 수 있다)
- 각 노드는 어떤 자료형으로도 표현이 가능하다

## Terms

![Tree-Terms](week3/img/tree-terms.png)

- 루트 노드(root node): 부모가 없는 노드, 트리는 하나의 루트 노드만을 가진다.
- 단말 노드(leaf node): 자식이 없는 노드, ‘말단 노드’ 또는 ‘잎 노드’라고도 부른다.
- 내부(internal) 노드: 단말 노드가 아닌 노드
- 간선(edge): 노드를 연결하는 선 (link, branch 라고도 부름)
- 형제(sibling): 같은 부모를 가지는 노드
- 노드의 크기(size): 자신을 포함한 모든 자손 노드의 개수
- 노드의 깊이(depth): 루트에서 어떤 노드에 도달하기 위해 거쳐야 하는 간선의 수
- 노드의 레벨(level): 트리의 특정 깊이를 가지는 노드의 집합
- 노드의 차수(degree): 하위 트리 개수 / 간선 수 (degree) = 각 노드가 지닌 가지의 수
- 트리의 차수(degree of tree): 트리의 최대 차수
- 트리의 높이(height): 루트 노드에서 가장 깊숙히 있는 노드의 깊이

## Types

- 트리 (Tree)
- 이진 트리 (Binary Tree) - 자식 노드가 최대 2개
  - 이진 트리 탐색
    - 전위 (preorder) VLR
    ```C
    void inorder(TreeNode node) {
        if (node != null) {
            visit(node);
            preorder(node.left);
            preorder(node.right);
        }
    }
    ```
    - 중위 (inorder) LVR
    ```C
    void inorder(TreeNode node) {
        if (node != null) {
            inorder(node.left);
            visit(node);
            inorder(node.right);
        }
    }
    ```
    - 후위 (postorder) LRV
    ```C
    void postorder(TreeNode node) {
        if (node != null) {
            postorder(node.left);
            postorder(node.right);
            visit(node);
        }
    }
    ```
- 이진 탐색 트리 (Binary Search Tree (BST)) - 모든 왼쪽 자식 <= n <= 모든 오른쪽 자식 (모든 노드 n에서 반드시 참이어야 함)

---

- 균형 트리 - O(logN) 시간에 insert와 find를 할 수 있을 정도로 균형이 잡힌 트리 (ex. AVL 트리)

---

![tree-types-ex](week3/tree-types.example.png)

- 전 이진 트리 (Full)
  - 모든 노드가 0개 or 2개의 자식 노드를 갖는 트리
- 완전 이진 트리 (Complete)
  - 트리의 모든 높이에서 노드가 꽉 찬 이진 트리 (마지막 레벨 제외 모두 채워진 상태)
  - 마지막 레벨은 (1 ~ level - 1)개의 노드를 가진다
  - 마지막 레벨은 채워진 형태가 왼쪽에서 오른쪽으로 채워져 있어야 한다
- 포화 이진 트리 (Perfect)
  - 전 이진 트리 && 완전 이진 트리
    - 모든 노드가 0개이면서 노드가 꽉 찰 수 없음 -> 모든 노드가 2개로 노드가 꽉찬 이진 트리를 의미

## Implementation

- 인접 행렬
- 인접 리스트
- 그 외 원하는 방법 (python 딕셔너리 - 인접 리스트 응용)

### references

[tree-blog-link](https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html)
