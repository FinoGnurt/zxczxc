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
