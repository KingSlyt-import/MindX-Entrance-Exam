# Web Technical Test By Nguyen Duc Quan
## Kiến thức về HTML
Thẻ <input> thường được sử dụng bên trong thẻ <form>, nó chỉ có thể lấy dữ liệu từ một dòng input của người dùng
Thẻ <textarea> dùng để lấy dữ liệu phức tạp hơn, thường là nhiều dòng chữ hoặc số từ phía người dùng

## Kiến thức về CSS
### 1) Liệt kê  5 CSS pseudo class/element
- 5 CSS pseudo class: ...:link, ...:visited, ...:hover, ...:active, ...:first-child
- 5 CSS pseudo element: ...::first-line, ...::first-letter, ...::before, ...::after, ...::marker

### 2) Sự khác nhau của hệ màu RGBA so với RGB
- Giá trị màu RGBA là phần mở rộng của RGB với kênh A - Alpha (độ mờ) 


## Kiến thức về JavaScript
### 1) Có 4 cách viết vòng lặp for:
- For loop thường: 
```
    for (let index = 0; index < array.length; index++) {
        const element = array[index];
        
    }
```
- Foreach: 
```
    array.forEach(element => {
        
    });
```
- For in: 
```
    for (const key in object) {
    
    }
```
- For of: 
```
    for (const iterator of object) {
    
    }
```

### 2) 
```
    function f (){
            let b = 9
            return ++b < 10 ? b : 'Yah'
        }
        let a = f()
        console.log(a)
```
- Đoạn code trên sẽ trả về kết quả là Yah. Vì toán tử ++ đã tăng giá trị của b lên 10, do đó trong câu lệnh if ngắn gọn trên thì 10 < 10 (sai) => return Yah

### 3)
- Những cách để làm đoạn code trên ngắn gọn là::
+ return thẳng giá trị kết quả về thay vì để vào biến
+ Chặn những trường hợp ngoại lệ (Chữ hoặc số không hợp lệ, số < 0,...) ở đầu function để tránh việc chạy hết if mới trả kết quả "?"
+ Kết hợp với cách viết if ngắn gọn (cú pháp if ? ... : ...) cho từng cặp số (1 vs 2, 3 vs 4,...)
+ Cho tất cả các ký tự Roman vào một array, sau đó trả kết quả về bằng array[decimal_number-1]

### 4)
- Regular expression có thể match được email: (String)@(String).(2-3 chars) => [a-z0-9]+@[a-z]+\.[a-z]{2,3}

### 5)
- Kết quả trả về sẽ theo thứ tự như sau:
### sequentialStart()
+ Đầu tiên hàm sequentialStart() sẽ được gọi, in ra "==SEQUENTIAL START=="
+ Sau đó hàm resolveAfter2Seconds() sẽ được gọi, do tính chất async await nên khi hàm này thực hiện xong hết 2s hàm tiếp theo mới được gọi để thực hiện
+ Tiếp theo, hàm resolveAfter1Second() được gọi, chạy hết 1s và kết thúc
### setTimeout(concurrentStart, 4000)
+ Đầu tiên, sau 4s thì hàm concurrentStart() sẽ được gọi, in ra "==CONCURRENT START with await=="
+ Sau đó, do tính chất asynchronous của JavaScript, 2 hàm resolveAfter2Seconds() và resolveAfter1Seconds() sẽ được chạy đồng thời
+ Cuối cùng, do câu lệnh await thì hàm chạy 2s sẽ phải xong thì hàm chạy 1s mới in ra được kết quả
### setTimeout(concurrentPromise, 7000)
+ Đầu tiên, sau 7s thì hàm concurrentPromise() sẽ được gọi, in ra "==CONCURRENT START with Promise.all=="
+ Việc sử dụng Promise.all sẽ cho chạy đồng thời hai promise
+ Và khi và chỉ khi cả hai promise đều hoàn thành, log ra console messages[0] và messages[1]
### setTimeout(parallel, 10000)
+ Đầu tiên, sau 10s thì hàm parallel() sẽ được gọi, in ra "==PARALLEL with await Promise.all=="
+ Khá tương tự với ví dụ trên, tuy sử dụng async await nhưng việc kết hợp với Promise.all nên cả hai promise đều được chạy đồng thời

