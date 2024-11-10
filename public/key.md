<link rel="stylesheet" href="../private/styles.css" />

<body>
  <button id="theme-toggle">Switch to Dark Mode</button>
  <h1 class="title">Object.keys() Method in JavaScript</h1>
  <p>Phương thức này trả về một mảng các tên thuộc tính riêng của đối tượng đã cho.</p>
  <p>Ví dụ: </p>
  <pre>
  <code>
  const person = {
    name: "John",
    age: 30,
    country: "USA",
  };
  const keys = Object.keys(person);
  console.log(keys); // Output: ["name", "age", "country"]
  </code>
  </pre>
  <p>Lưu ý:</p>
  <p>...</p>
  <h3 class="text_h3">Ví dụ với thuộc tính không có enumerable</h3>
  <pre>
  <code>
  const obj = {
    name: "Alice",
    age: 25,
    profession: "Engineer",
  };
  const keys2 = Object.keys(obj);
  console.log(keys2); // Output: ["name", "age", "profession"]
  </code>
  </pre>
  <h3 class="text_h3">Ví dụ với thuộc tính không enumerable</h3>
  <pre>
  <code>
  const obj2 = {};
  Object.defineProperty(obj2, "hidden", {
    value: "This is hidden",
    enumerable: false,
  });
  const keys3 = Object.keys(obj2);
  const keys4 = Object.getOwnPropertyNames(obj2);
  console.log(keys3); // [] vì 'hidden' không enumerable
  console.log(keys4); // ['hidden'] vì getOwnPropertyNames lấy tất cả key dù có enumerable là false hay true
  </code>
  </pre>
</body>

<script>

// Lấy nút chuyển chế độ
const toggleButton = document.getElementById("theme-toggle");

// Kiểm tra xem người dùng đã chọn chế độ nào và áp dụng
const currentTheme = localStorage.getItem("theme") || "lightmode";
document.body.classList.add(currentTheme);

// Cập nhật trạng thái của nút và thay đổi chế độ
toggleButton.textContent = currentTheme === "lightmode" ? "Switch to Dark Mode" : "Switch to Light Mode";

// Lắng nghe sự kiện khi người dùng nhấn vào nút
toggleButton.addEventListener("click", () => {
  const newTheme = document.body.classList.contains("lightmode") ? "darkmode" : "lightmode";
  document.body.classList.replace(currentTheme, newTheme);
  localStorage.setItem("theme", newTheme); // Lưu lại lựa chọn của người dùng
  toggleButton.textContent = newTheme === "lightmode" ? "Switch to Dark Mode" : "Switch to Light Mode"; // Cập nhật lại nút
});
  </script>
