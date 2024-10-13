# Kiến trúc của Java Reflection API

Các lớp được dùng trong reflection nằm trong hai package là java.lang và java.lang.reflect. Package java.lang.reflect bao gồm ba lớp chính mà bạn cần biết là Constructor, Field và Method:

Class<T>: lớp này đại diện cho các lớp, interface và chứa các phương thức dùng để lấy các đối tượng kiểu Constructor, Field, Method,…
AccessibleObject: các kiểm tra về phạm vi truy xuất (public, private, protected) của field, method, constructor sẽ được bỏ qua. Nhờ đó bạn có thể dùng reflection để thay đổi, thực thi các thành phần này mà không cần quan tâm đến phạm vi truy xuất của nó.
Constructor: chứa các thông tin về một constructor của lớp.
Field: chứa các thông tin về một field của lớp, interface.
Method: chứa các thông tin về một phương thức của lớp, interface.

![image](https://github.com/user-attachments/assets/45e00020-33de-4fdb-92b3-9b4f90d6eb4f)
