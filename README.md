# Kiến trúc của Java Reflection API

Các lớp được dùng trong reflection nằm trong hai package là java.lang và java.lang.reflect. Package java.lang.reflect bao gồm ba lớp chính mà bạn cần biết là Constructor, Field và Method:

- Class<T>: lớp này đại diện cho các lớp, interface và chứa các phương thức dùng để lấy các đối tượng kiểu Constructor, Field, Method,…
- AccessibleObject: các kiểm tra về phạm vi truy xuất (public, private, protected) của field, method, constructor sẽ được bỏ qua. Nhờ đó bạn có thể dùng reflection để thay đổi, thực thi các thành phần này mà không cần quan tâm đến phạm vi truy xuất của nó.
- Constructor: chứa các thông tin về một constructor của lớp.
- Field: chứa các thông tin về một field của lớp, interface.
- Method: chứa các thông tin về một phương thức của lớp, interface.

![image](https://github.com/user-attachments/assets/45e00020-33de-4fdb-92b3-9b4f90d6eb4f)

## Lớp (Classes)
Khi sử dụng Java Reflection để duyệt qua một class thì việc đầu tiên thường phải làm đó là có được một đối tượng kiểu Class, từ các đối tượng kiểu Class chúng ta có thể lấy được các thông tin về:

- Class Name
- Class Modifies (public, private, synchronized etc.)
- Package Info
- Superclass
- Implemented Interfaces
- Constructors
- Methods
- Fields
- Annotations

# Tạo đối tượng Class<>
- Đối tượng kiểu Class được tạo ra bằng cách sử dụng phương thức static Class.forName(). Cách này thường được sử dụng khi chỉ biên được tên lớp lúc thực thi (runtime)
- Trong trường hợp không tìm thấy lớp tương ứng, phương thức trên sẽ ném ra ngoại lệ ClassNotFoundException. Điều này có thể bất tiện vì bạn phải sử dụng try catch hoặc ném ngoại lệ này khỏi phương thức.
- Khi bạn biết chính xác tên Lớp tại thời điểm biên dịch (combine), có thể sử dụng TenLop.class để tạo đối tượng kiểu Class. Cách này đảm bảo rằng lớp được sử dụng luôn luôn tồn tại và không có ngoại lệ nào xảy ra. Đối với các kiểu dữ liệu nguyên thủy như void, int, boolean, char,… bạn có thể dùng field TYPE để lấy được đối tượng Class tương ứng.
