# Phân tích yêu cầu hệ thống quản lý xuất nhập khẩu hàng hóa

Nhóm 15
-	Nguyễn Quý Đức 20235682
-	Vũ Đức Hoàng Anh 20235658
-	Trần Đăng Sinh 20235821
-	Phan Khánh Vũ 20235880
-	Lương Quốc Khánh 20235754
-	Nguyễn Hữu Nhân 20235798


1. # **Biểu đồ use case**

   1. ## **Biểu đồ use case tổng quan**

```plantuml
@startuml
!include ./puml/usecase-overview.puml
@enduml
```

**Giải thích về các tác nhân**

- **Bộ phận bán hàng (Sales Department)**: lập và gửi danh sách yêu cầu nhập hàng (mã hàng, số lượng, đơn vị, ngày nhận mong muốn), theo dõi kết quả xử lý yêu cầu.
- **Bộ phận đặt hàng quốc tế (International Ordering Department)**: tiếp nhận yêu cầu từ Sales, tìm Site phù hợp, thu thập thông tin tồn kho, ra quyết định phân bổ và gửi đơn đặt hàng đến Site.
- **Site nhập khẩu (Overseas Import Site)**: cung cấp thông tin tồn kho, thông tin thời gian vận chuyển (tàu/hàng không), tiếp nhận và xử lý đơn đặt hàng.
- **Bộ phận quản lý kho (Warehouse Management Department)**: tiếp nhận hàng thực tế, kiểm hàng và đối soát với đơn đặt, cập nhật hệ thống kho nội bộ.
- **Quản trị hệ thống (System Administrator)**: quản lý tài khoản và phân quyền actor, quản trị dữ liệu dùng chung, giám sát vận hành và sao lưu/khôi phục dữ liệu.

**Giải thích về các use case tổng quan**

Các use case mức tổng quan trong hệ thống gồm:

- **Manage Import Requests**: quản lý yêu cầu nhập hàng từ khâu tạo, gửi, theo dõi trạng thái đến điều chỉnh/hủy yêu cầu.
- **Manage Site Information**: quản lý thông tin Site và dữ liệu phục vụ đặt hàng (danh mục mặt hàng kinh doanh, thời gian vận chuyển theo phương thức).
- **Collect Inventory Data**: gửi yêu cầu kiểm tra tồn kho tới các Site và ghi nhận phản hồi tồn kho theo từng mặt hàng.
- **Plan Import Allocation**: xác định phương án nhập hàng theo tiêu chí ưu tiên (tàu trước hàng không, tồn kho lớn hơn, số Site ít nhất) và kiểm tra khả năng đáp ứng ngày nhận mong muốn.
- **Place Overseas Orders**: tạo và gửi đơn đặt hàng chính thức tới các Site được chọn.
- **Receive and Reconcile Goods**: kiểm hàng thực nhận tại kho, đối soát với đơn đặt, ghi nhận sai lệch và cập nhật tồn kho.
- **Administer System**: quản trị người dùng, phân quyền, dữ liệu dùng chung, nhật ký vận hành và sao lưu/khôi phục dữ liệu.

  2. ## **Biểu đồ use case phân rã “Manage site”**

  3. ## **Biểu đồ use case phân rã “Manage user”**

![][image2]

2. # **Đặc tả Use case**

   1. ## **Use case “Register for course”**



2. ## **Use case “Close registration”**

..

3. # **Từ điển thuật ngữ**

Introduction to Glossary…

1. ## **Course**

…

2. ## **Credit**

…

4. # **Đặc tả phụ trợ**

   1. ## **Chức năng**

Cxxx

2. ## **Hiệu năng**

Xxxx

3. ## **Độ tin cậy**

…
