# Tổng quan về Cấu Trúc Dữ Liệu<p>

Table of Contents<p>
- **1. CTDL Lưu trữ<p>**
    - 1.1. Mảng (array), danh sách liên kết (linked list)<p>
    - 1.2. Stack, Queue, Deque<p>
        - 1.2.1. Stack<p>
        - 1.2.2. Queue<p>
        - 1.2.3. Deque<p>
        - 1.3. Priority Queue - Heap<p>
        - 1.4. Cây Tìm Kiếm Nhị Phân<p>
        - 1.5. Bảng băm (Hash Tables)<p>
- **2. CTDL Truy vấn<p>**
    - 2.1. Mảng cộng dồn (Prefix Sum)<p>
        - 2.1.1. Mảng cộng dồn - Tìm tổng một đoạn liên tiếp<p>
        - 2.1.2. Mảng cộng dồn - Tăng giá trị các đoạn<p>
        - 2.1.3. Mảng cộng dồn trên bảng 2 chiều<p>
    - 2.2. Disjoint Sets<p>
    - 2.3. Sparse Table<p>
    - 2.4. Segment Tree<p>
    - 2.5. Fenwick<p>
    - 2.6. Heavy-light decomposition<p>
    - 2.7. Persistent Data Structures<p>
- **3. CTDL xâu<p>**
    - 3.1. Cây Tiền Tố (Trie)<p>
    - 3.2. Aho Corasick<p>
    - 3.3. Mảng Hậu Tố (Suffix Array)<p>
    - 3.4. Suffix Automaton<p>
    - 3.5. Palindrome Tree<p>
- **Các tài liệu tham khảo:<p>**



Mặc dù máy tính đã có thể xử lý hàng triệu phép tính mỗi giây, nhưng khi một bài toán trở phức tạp, cách tổ chức dữ liệu vẫn vô cùng quan trọng.

Để minh họa điểm này, hãy tham khảo ví dụ sau: bạn đi đến thư viện, thử tìm kiếm một quyển sách với chủ đề nào đó. Các cuốn sách được xếp theo lĩnh vực. Trong mỗi chủ đề, sách lại được xếp theo tên tác giả, nhờ vậy mà việc lấy và cất sách từ giá trở nên khá dễ dàng và đơn giản.

Bây giờ, hãy thử tưởng tượng thay vì tổ chức thành từng giá sách cụ thể, sách được chất thành từng đống ở khắp thư viện. Để tìm được quyển sách của mình, bạn sẽ phải mất hàng giờ, thậm chí rất nhiều ngày.

Tương tự, một phần mềm không thể vận hành hiệu quả khi dữ liệu không được lưu trữ một cách phù hợp với ứng dụng.

Trong bài viết này, chúng ta sẽ cùng nhau điểm qua các loại cấu trúc dữ liệu từ cơ bản đến nâng cao. Để tìm hiểu chi tiết về một cấu trúc dữ liệu, các bạn có thể đọc ở link tương ứng. Trong bài viết này, mình tạm chia các CTDL được chia thành các loại sau:

CTDL lưu trữ: thường có các thao tác như thêm 1 phần tử, xóa 1 phần tử. Có thể có thêm các thao tác như tìm kiếm 1 phần tử.
CTDL truy vấn: thường dùng cho các bài toán mà bạn phải duy trì một tập hợp các số và thực hiện 1 số truy vấn trên đó.
CTDL xâu: dùng cho các bài tập Xử lý xâu.

# 1. CTDL Lưu trữ
## 1.1. Mảng (array), danh sách liên kết (linked list)
Mảng và danh sách liên kết là 2 cấu trúc dữ liệu nền tảng cho tất cả các loại cấu trúc dữ liệu khác. Mảng và danh sách liên kết đều được dùng khi bạn muốn lưu nhiều dữ liệu (thường có cùng kiểu dữ liệu). Bảng dưới đây so sánh các thao tác về mảng và danh sách liên kết:
|        **Đặc điểm**       | **Mảng**                                   | **Danh sách liên kết**               |
|-----------------------|-----------------------------------------|----------------------------------|
| **Bộ nhớ**               | Cố định (cần biết trước số phần tử)     | Có thể tăng giảm tùy ý          |
| **Thêm/Xóa 1 phần tử**    | O(N)  | O(1)                             |
| **Tìm kiếm 1 phần tử**    | O(N)                                    | O(N)                             |
| **Truy cập phần tử**      | O(1)                                    | O(N)                             |
| **Khác**                  | - Ít bộ nhớ hơn                      |             |

Bạn có thể đọc thêm về mảng và danh sách liên kết ở đây

## 1.2. Stack, Queue, Deque
### 1.2.1. Stack
Stack là CTDL cho phép thực hiện các thao tác:

- Thêm 1 phần tử vào cuối CTDL<p>
- Xóa 1 phần tử khỏi cuối CTDL

Cả 2 thao tác trên đều có độ phức tạp O(1). Chú ý ta chỉ có thể xóa phần tử ở cuối CTDL, nói cách khác là phần tử mà mới được thêm vào gần nhất. Vì vậy, Stack còn được gọi là FIFO (First In First Out).<p>
Stack có cài đặt đơn giản và được sử dụng trong nhiều thuật toán như DFS, tìm chu trình Euler, tìm khớp của đồ thị.<p>
Trong C++ STL, có sẵn kiểu dữ liệu `stack`.<p>

### 1.2.2. Queue
Queue là CTDL cho phép thực hiện các thao tác:
- Thêm 1 phần tử vào cuối CTDL
- Xóa 1 phần tử khỏi đầu CTDL.

Cả 2 thao tác đều có độ phức tạp O(1). Chú ý ta chỉ có thể xóa phần tử ở đầu CTDL, nói cách khác là phần tử mà đã được thêm vào lâu nhất. Vì vậy, Stack còn được gọi là LIFO (Last In First Out).<p>
Queue có cài đặt đơn giản và được sử dụng trong BFS.

Trong C++ STL, có sẵn kiểu dữ liệu `queue`.

### 1.2.3. Deque
Deque (Double Ended Queue), là CTDL tổng quát hơn của Stack và Queue. Nó cho phép:
- Thêm 1 phần tử vào đầu hoặc cuối CTDL.
- Xóa 1 phần tử khỏi đầu hoặc cuối CTDL.

Cả 2 thao tác đều có độ phức tạp O(1).

Deque được sử dụng trong một số thuật toán như:
- BFS 01
- Tìm Min/Max trên đoạn tịnh tiến.

Trong C++ STL, có sẵn kiểu dữ liệu `deque`.

## 1.3. Priority Queue - Heap
Heap là một cấu trúc dữ liệu cho phép thực hiện các thao tác:
- Thêm một phần tử, với độ phức tạp O(logN)
- Xóa một phần tử, với độ phức tạp O(logN)
- Tìm max của các phần tử, với độ phức tạp O(1)

Bạn có thể đọc thêm về Heap ở đây

Fibonacci Heap là một dạng heap có độ phức tạp bé hơn. Trong C++, CTDL priority_queue được cài đặt bằng Fibonacci Heap.

## 1.4. Cây Tìm Kiếm Nhị Phân
Cây Tìm Kiếm Nhị Phân (BST Binary Search Tree) là một cây nhị phân có tính chất: Với mỗi giá trị trên đỉnh đang xét, giá trị của mọi đỉnh trên cây con trái luôn nhỏ hơn đỉnh đang xét và giá trị của mọi đỉnh trên cây con phải luôn lớn hơn đỉnh đang xét.

<img src="https://scontent.fhan17-1.fna.fbcdn.net/v/t39.30808-6/412643113_1595936764488627_4574686401041546529_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=524774&_nc_eui2=AeGa-YxFWuQMLiMVDE1CJdP34VWZZjz4tM7hVZlmPPi0ziDkM4TYta_NEYYer2nUge69RQDVMc00IBDjKaVbaZsn&_nc_ohc=_m3Ss94EQFQAX_X5Sk_&_nc_ht=scontent.fhan17-1.fna&oh=00_AfBwWPg5N1-2Rm4E0MP4kc5ADR17BBCKGSDsFY3DsAhjlw&oe=6587374F">

Cây tìm kiếm nhị phân cho phép thực hiện các thao tác:
- Thêm 1 phần tử.
- Xóa 1 phần tử.
- Kiểm tra 1 phần tử có tồn tại hay không.
- Tìm phần tử đầu tiên lớn hơn hoặc bằng 1 giá trị x cho trước.

Trong trường hợp dữ liệu ngẫu nhiên, các thao tác trên có độ phức tạp trung bình là O(logN)
. Tuy nhiên trong trường hợp xấu nhất, cây tìm kiếm nhị phân bị suy biến (thành 1 _"đường thẳng"_), thì độ phức tạp mỗi thao tác là O(N)
.

Để khắc phục điều này, có rất nhiều CTDL cải tiến từ cây tìm kiếm nhị phân, thường được gọi là các cây nhị phân cân bằng. Khi đó, các thao tác trên có thể được thực hiện với độ phức tạp O(logN)
. Ví dụ:

- Cây Đỏ Đen (Red-Black Tree) là một dạng cây tìm kiếm nhị phân (BST) mà sau mỗi truy vấn được thực hiện, cây tự cân bằng theo đúng tính chất của nó với độ phức tạp O(log(N))
. CTDL set trong C++ được cài đặt bằng cây đỏ đen.
<img src="https://scontent.fhan17-1.fna.fbcdn.net/v/t39.30808-6/412437370_1595937417821895_4285596929297032193_n.jpg?_nc_cat=108&ccb=1-7&_nc_sid=524774&_nc_eui2=AeEd_HCTgf5lBBiEe-S_hKcTnu6r8jz4cLue7qvyPPhwuwgiiDzfxWatIddT0xJZpz-cn9J_wT_OU36qolqge_fq&_nc_ohc=l58GgrZciOEAX_hm_kr&_nc_ht=scontent.fhan17-1.fna&oh=00_AfA_lR3tkvUFFH-oidhgHk0OG6HrCx4xvmpmZVwrptNh4g&oe=65867BE2">

- Splay tree, Skip list, Treap thường được dùng trong các kỳ thi bởi cài đặt đơn giản.

## 1.5. Bảng băm (Hash Tables)
Bảng băm là một CTDL thường được sử dụng như một từ điển: mỗi phần tử trong bảng băm là một cặp (khóa, giá trị). Nếu so sánh với mảng, khóa được xem như chỉ số của mảng, còn giá trị giống như giá trị mà ta lưu tại chỉ số tương ứng. Bảng băm không như các loại từ điển thông thường - ta có thể tìm được giá trị thông qua khóa của nó.

Bảng băm hoạt động dựa trên hàm Hash: Hash là quá trình khởi tạo một giá trị khóa (thường là 32 bit hoặc 64 bit) từ một phần dữ liệu. Nó có thể là n
 bit đầu tiên của dữ liệu, n
 bit cuối cùng, giá trị mod cho một số nguyên tố nào đó. Dựa theo giá trị hash, dữ liệu được chia vào các bucket:
 
<img src="https://scontent.fhan17-1.fna.fbcdn.net/v/t39.30808-6/412648907_1595938007821836_2639875278394353950_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=524774&_nc_eui2=AeEHM-MOWqEEkaguhAumrk1fY24UT2M1QyZjbhRPYzVDJmi72Hx_ybKLpb6yL0kr5sn8pNzz3I_pV8aPB8kGmnrl&_nc_ohc=bZnm39fPUn4AX-PBLF-&_nc_ht=scontent.fhan17-1.fna&oh=00_AfB1LnNyg0BnvsetkGDaSSFRvcPLWdoWQwDPhKrUs0QMPQ&oe=6586B25A">
Trong trường hợp hàm Hash hoạt động tốt, mỗi bucket có rất ít phần tử, độ phức tạp của các thao tác trên Hash table như sau:
- Tìm 1 khóa: O(1)
- Thêm / xóa 1 khóa: O(1)

Bạn có thể đọc thêm về Hash table ở đây

# 2. CTDL Truy vấn
## 2.1. Mảng cộng dồn (Prefix Sum)
Mảng cộng dồn là một cách áp dụng khéo léo mảng. Có 2 dạng bài cơ bản có thể giải được bằng cách áp dụng Prefix Sum.

### 2.1.1. Mảng cộng dồn - Tìm tổng một đoạn liên tiếp

Ví dụ
- Cho một mảng a1,a2,a3,…,aN
- Cần trả lời nhiều truy vấn, mỗi truy vấn cho 2 số L và R, yêu cầu in ra tổng aL+aL+1+…+aR.

Cách làm
- Tạo một mảng S, với Si=a1+a2+…+ai. Mảng S được gọi là mảng cộng dồn.
- Với mỗi truy vấn, in ra: SR–SL−1.

### 2.1.2. Mảng cộng dồn - Tăng giá trị các đoạn
Ví dụ
- Cho mảng a1,a2,…,aN
- Cần thực hiện nhiều truy vấn, mỗi truy vấn cho 3 số L, R, V. Yêu cầu: với mỗi i(L≤i≤R), cộng V vào ai.
- Tính mảng a sau khi thực hiện tất cả các truy vấn.

Cách làm
- Tạo một mảng P: p1,p2,…,pN
- Khởi tạo pi=0.
- Với mỗi truy vấn, tăng pL lên V và trừ pR+1 đi V.
- Cuối cùng, với mỗi i (từ 1), pi+=pi–1. Ta có ai=ai+pi.

### 2.1.3. Mảng cộng dồn trên bảng 2 chiều
Trên bảng 2 chiều A(i,j)
, ta đặt f(i,j)
 là tổng các ô trong hình chữ nhật có 2 đỉnh đối diện là (1,1)
 và (i,j)
.

Khi đó, ta có: f(i,j)=f(i−1,j)+f(i,j−1)−f(i−1,j−1)+A(i,j)
.

Giải thích công thức trên:

<img src="https://scontent.fhan17-1.fna.fbcdn.net/v/t39.30808-6/412841820_1595945811154389_5734863089954893734_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=524774&_nc_eui2=AeEbiegQLELhpPh--WrNOcrF0YGuyZ3i1S_Rga7JneLVL-tV2W6D2CK3nKE2xdJvGBsneg9Tdb5d1ZLDsdtN1_7A&_nc_ohc=zk0WXD8_k5cAX9X3KXh&_nc_ht=scontent.fhan17-1.fna&oh=00_AfC3qPMejDMUr1en6wsOY8Eyr0frgEKXO5G664JuPCCbZg&oe=65873DAC">

đỏ = xanh da trời + vàng - tím + xanh lá<p>
f(i,j)=f(i−1,j)+f(i,j−1)−f(i−1,j−1)+A(i,j)

## 2.2. Disjoint Sets
Disjoint Sets là cấu trúc dữ liệu được sử dụng trong thuật toán Kruskal và thuật toán Prim - 2 thuật toán tìm cây khung nhỏ nhất của đồ thị. Như tên gọi của nó, Disjoint Set được dùng để quản lý các tập hợp không giao nhau.

Bài toán

Cho đồ thị có N
 đỉnh. Ta cần thực hiện 2 loại truy vấn:

- Nối 2 đỉnh i và j
- Kiểm tra 2 đỉnh i và j
 có thuộc cùng thành phần liên thông hay không.

Disjoint set cho phép ta thực hiện 2 thao tác trên với độ phức tạp O(logN).

Bạn có thể đọc thêm về Disjoint Set ở [bài viết này.](https://vnoi.info/wiki/algo/data-structures/disjoint-set)

## 2.3. Sparse Table
Sparse Table là cấu trúc dữ liệu được sử dụng trong [bài toán LCA & RMQ.](https://vnoi.info/wiki/translate/topcoder/Range-Minimum-Query-and-Lowest-Common-Ancestor)

Với cả 2 bài toán, Sparse Table cho phép:

- Khởi tạo với độ phức tạp: O(N∗logN).
- Trả lời truy vấn với độ phức tạp O(1)

## 2.4. Segment Tree
Segment Tree, còn được gọi là Interval Tree trong nhiều tài liệu tiếng Việt, là cấu trúc dữ liệu cho phép thực hiện các truy vấn trên một dãy số. Segment Tree rất linh động và có thể áp dụng với nhiều loại truy vấn khác nhau, nên nó xuất hiện rất nhiều trong các kỳ thi.

Với dãy số độ dài N, Segment Tree cho phép thực hiện các thao tác với độ phức tạp O(logN).

Bạn có thể đọc thêm về Segment Tree [ở đây.](https://vnoi.info/wiki/algo/data-structures/segment-tree-extend)

Segment Tree cũng có một mở rộng với nhiều ứng dụng quan trọng là [Segment Tree trên tập đoạn thẳng.](https://vnoi.info/wiki/algo/data-structures/interval-tree-tap-doan-thang)

## 2.5. Fenwick
Cũng giống như Segment Tree, Fenwick tree (còn được gọi là Binary Indexed Tree) là cấu trúc dữ liệu cho phép thực hiện các truy vấn trên một dãy số:

- Ưu điểm:
    - Độ phức tạp mỗi thao tác cũng là O(logN).
    - Hằng số tự nhiên thấp hơn Segment Tree, nên chạy nhanh hơn.
    - Dùng ít bộ nhớ hơn.
    - Dễ cài đặt hơn Segment Tree
- Nhược điểm:
    - Không tổng quát bằng Segment Tree. Tất cả những bài giải được bằng Fenwick tree đều có thể giải được bằng Segment Tree. Nhưng chiều ngược lại không đúng.

Bạn có thể đọc thêm về Fenwick Tree [ở đây.](https://vnoi.info/wiki/algo/data-structures/fenwick)

## 2.6. Heavy-light decomposition
Heavy Light Decomposition là một thuật toán được áp dụng nhiều trong những bài cần xử lý các truy vấn trên cây. Heavy-light decomposition là kĩ thuật phân tách một cây thành nhiều chuỗi đỉnh (chain) rời nhau. Sau đó, chúng ta có thể áp dụng các cấu trúc dữ liệu như Interval Tree hay Binary-Indexed Tree lên những chuỗi này để có thể cập nhật dữ liệu hoặc trả lời các truy vấn trên một đường đi giữa 2 đỉnh trong cây.

Bạn có thể đọc thêm ở: [Thuật toán phân tách cây.](https://vnoi.info/wiki/algo/data-structures/heavy-light-decomposition)

## 2.7. Persistent Data Structures
Persistent Data Structures là những cấu trúc dữ liệu được dùng khi chúng ta cần có toàn bộ lịch sử của các thay đổi trên 1 cấu trúc dữ liệu.

Bạn có thể đọc thêm ở: [Persistent Data Structures](https://vnoi.info/wiki/algo/data-structures/persistent-data-structures)

# 3. CTDL xâu
## 3.1. Cây Tiền Tố (Trie)
Trie là một cấu trúc dữ liệu dùng để quản lý một tập hợp các xâu. Trie cho phép:

- Thêm một xâu vào tập hợp, với độ phức tạp O(L) với L là độ dài xâu cần thêm.
- Xóa một xâu khỏi tập hợp, với độ phức tạp O(L).
- Kiểm tra một xâu có tồn tại trong tập hợp hay không, với độ phức tạp O(L).
- Ngoài ra trên thực tế, trie cũng rất tiết kiệm bộ nhớ khi áp dụng để lưu các từ có nghĩa, vì vậy nó là một CTDL có ứng dụng rất lớn.

Bạn có thể đọc thêm [bài viết về trie.](https://vnoi.info/wiki/algo/data-structures/trie)

## 3.2. Aho Corasick
Bài viết sẽ được cập nhật sau

## 3.3. Mảng Hậu Tố (Suffix Array)
Suffix Array là một CTDL giúp sắp xếp các hậu tố của một xâu theo thứ tự từ điển. CTDL này thường được sử dụng trong các bài toán xử lý xâu.

Bạn có thể đọc thêm về Suffix Array [ở đây.](https://vnoi.info/wiki/algo/data-structures/suffix-array)

## 3.4. Suffix Automaton
Bài viết sẽ được cập nhật sau.

## 3.5. Palindrome Tree
Palindrome tree (còn được gọi là Eertree), là một CTDL mới được phổ biến vào năm 2014 nhờ bài thuyết trình của [Mikhail Rubinchik.](http://codeforces.com/profile/MikhailRubinchik)

Như tên gọi của nó, Palindrome tree là một CTDL giúp giải quyết các bài toán về Palindrome. Bạn có thể đọc thêm [ở đây](https://vnoi.info/wiki/translate/codeforces/palindrome-tree)

# Các tài liệu tham khảo:
- [Codeforces](http://codeforces.com/blog/entry/15729)
- [Topcoder](https://www.topcoder.com/community/data-science/data-science-tutorials/data-structures/)
