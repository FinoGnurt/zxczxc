<link rel="stylesheet" href="../private/styles.css" />

<style>
  /* Cập nhật chung cho body */
body {
  font-family: "Arial", sans-serif; /* Thêm font đẹp hơn */
  font-size: 16px; /* Đặt cỡ chữ mặc định cho dễ đọc */
  line-height: 1.6; /* Tăng khoảng cách dòng để dễ nhìn */
  margin: 0;
  padding: 0;
  background-color: #121212; /* Nền tối */
  color: #e0e0e0; /* Màu chữ sáng để dễ đọc trên nền tối */
}

/* Căn giữa tiêu đề */
.title {
  text-align: center;
  font-size: 2.5em;
  margin-top: 20px;
  color: #4caf50; /* Màu xanh lá cho tiêu đề */
  text-transform: uppercase; /* Chữ in hoa */
}

/* Định dạng cho đoạn văn */
p {
  font-size: 1.2em; /* Cỡ chữ hơi lớn hơn cho đoạn văn */
  margin: 15px 0; /* Khoảng cách giữa các đoạn văn */
  padding: 0 10px; /* Thêm padding để tạo khoảng cách với viền */
  text-align: justify; /* Canh đều các đoạn văn */
  color: #b0b0b0; /* Màu chữ sáng nhẹ cho đoạn văn */
}

/* Định dạng cho h3 */
.text_h3 {
  font-size: 1.5em;
  font-weight: bold;
  margin-top: 30px; /* Khoảng cách trên cho rõ ràng */
  border-bottom: 2px solid #4caf50; /* Dòng dưới màu xanh lá */
  padding-bottom: 10px;
  color: #4caf50; /* Màu chữ xanh lá cho tiêu đề h3 */
}

/* Chỉnh sửa cho mã JavaScript */
pre {
  background-color: #2d2d2d; /* Nền tối cho mã */
  color: #f8f8f2; /* Chữ màu sáng */
  padding: 15px; /* Padding trong mã */
  border-radius: 5px; /* Góc bo tròn */
  overflow-x: auto; /* Cho phép cuộn ngang nếu mã dài */
  font-family: "Courier New", monospace; /* Font monospace cho mã */
  margin: 20px 0; /* Khoảng cách từ trên và dưới */
  line-height: 1.4; /* Tăng khoảng cách dòng cho dễ đọc */
}

/* Thêm hiệu ứng hover cho các thẻ h3 */
.text_h3:hover {
  color: #fff; /* Màu chữ trắng khi hover */
  background-color: #4caf50; /* Màu nền khi hover */
  transition: all 0.3s ease; /* Hiệu ứng chuyển đổi mượt mà */
}

</style>

<body>
<h1 class="title">Object.keys() Method in JavaScript</h1>
<p>Phương thức này trả về một mảng các tên thuộc tính riêng của đối tượng đã cho.</p>

<p>Ví dụ: </p>

```javascript
const person = {
  name: "John",
  age: 30,
  country: "USA",
};
const keys = Object.keys(person);
console.log(keys); // Output: ["name", "age", "country"]
```

<p>
Lưu ý:
 </br> + Chỉ trả về các khóa enumerable: Object.keys() chỉ trả về các thuộc tính có thể lặp qua được (enumerable). Nếu thuộc tính có enumerable: false, nó sẽ không xuất hiện trong kết quả.
 </br> + Không bao gồm các thuộc tính kế thừa từ prototype: Object.keys() chỉ trả về các thuộc tính của chính đối tượng (không bao gồm thuộc tính kế thừa từ prototype).
</p>

<p>
  So sánh với các phương thức khác:
    </br> + Object.getOwnPropertyNames(): Trả về một mảng chứa tất cả các thuộc tính (bao gồm các thuộc tính không enumerable) của đối tượng.
    </br> + for...in: Duyệt qua tất cả các thuộc tính của đối tượng và các thuộc tính kế thừa từ prototype.
</p>

<h3 class="text_h3">Ví dụ với thuộc tính không có enumerable</h3>

```javascript
const obj = {
  name: "Alice",
  age: 25,
  profession: "Engineer",
};
const keys2 = Object.keys(obj);
console.log(keys2); // Output: ["name", "age", "profession"]
```

<h3 class="text_h3">Ví dụ với thuộc tính không enumerable</h3>

```javascript
const obj2 = {};
Object.defineProperty(obj2, "hidden", {
  value: "This is hidden",
  enumerable: false,
}); // Thêm thuộc tính với key: hidden, value: "This is hidden" và enumerable: false
const keys3 = Object.keys(obj2);
const keys4 = Object.getOwnPropertyNames(obj2);
console.log(keys3); // [] vì 'hidden' không enumerable
console.log(keys3); // [ 'hidden' ] vì getOwnPropertyNames lấy tất cả key dù có enumerable là false hay true
```

</body>
