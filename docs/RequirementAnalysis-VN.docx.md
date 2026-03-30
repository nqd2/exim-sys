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
!include ./puml/usecase_overview.puml
@enduml
```

**Giải thích về các tác nhân**

- **Bộ phận bán hàng (`SalesDepartment`)**: lập và gửi danh sách yêu cầu nhập hàng (mã hàng, số lượng, đơn vị, ngày nhận mong muốn), theo dõi kết quả xử lý yêu cầu.
- **Bộ phận đặt hàng quốc tế (`InternationalOrderingDepartment`)**: tiếp nhận yêu cầu từ Sales, tìm Site phù hợp, thu thập thông tin tồn kho, ra quyết định phân bổ và gửi đơn đặt hàng đến Site.
- **Site nhập khẩu (`OverseasImportSite`)**: cung cấp thông tin tồn kho, thông tin thời gian vận chuyển (tàu/hàng không), tiếp nhận và xử lý đơn đặt hàng.
- **Bộ phận quản lý kho (`WarehouseManagementDepartment`)**: tiếp nhận hàng thực tế, kiểm hàng và đối soát với đơn đặt, cập nhật hệ thống kho nội bộ.
- **Quản trị hệ thống (`SystemAdministrator`)**: quản lý tài khoản và phân quyền actor, quản trị dữ liệu dùng chung, giám sát vận hành và sao lưu/khôi phục dữ liệu.

**Giải thích về các use case tổng quan**

Các use case mức tổng quan trong hệ thống gồm:

- **ManageImportRequests**: quản lý yêu cầu nhập hàng từ khâu tạo, gửi, theo dõi trạng thái đến điều chỉnh/hủy yêu cầu.
- **ManageSiteInformation**: quản lý thông tin Site và dữ liệu phục vụ đặt hàng (danh mục mặt hàng kinh doanh, thời gian vận chuyển theo phương thức).
- **CollectInventoryData**: gửi yêu cầu kiểm tra tồn kho tới các Site và ghi nhận phản hồi tồn kho theo từng mặt hàng.
- **PlanImportAllocation**: xác định phương án nhập hàng theo tiêu chí ưu tiên (tàu trước hàng không, tồn kho lớn hơn, số Site ít nhất) và kiểm tra khả năng đáp ứng ngày nhận mong muốn.
- **PlaceOverseasOrders**: tạo và gửi đơn đặt hàng chính thức tới các Site được chọn.
- **ReceiveAndReconcileGoods**: kiểm hàng thực nhận tại kho, đối soát với đơn đặt, ghi nhận sai lệch và cập nhật tồn kho.
- **ManageSystem**: quản trị người dùng, phân quyền, dữ liệu dùng chung, nhật ký vận hành và sao lưu/khôi phục dữ liệu.

  2. ## **Biểu đồ use case phân rã "ManageImportRequests"**

```plantuml
@startuml
!include ./puml/usecase_manage_import_requests.puml
@enduml
```

  3. ## **Biểu đồ use case phân rã "ManageSiteInformation"**

```plantuml
@startuml
!include ./puml/usecase_manage_site_information.puml
@enduml
```

  4. ## **Biểu đồ use case phân rã "CollectInventoryData"**

```plantuml
@startuml
!include ./puml/usecase_collect_inventory_data.puml
@enduml
```
  
  5. ## **Biểu đồ use case phân rã "PlanImportAllocation"**

```plantuml
@startuml
!include ./puml/usecase_plan_import_allocation.puml
@enduml
```
  
  6. ## **Biểu đồ use case phân rã "PlaceOverseasOrders"**

```plantuml
@startuml
!include ./puml/usecase_place_overseas_orders.puml
@enduml
```
  
  7. ## **Biểu đồ use case phân rã "ReceiveAndReconcileGoods"**

```plantuml
@startuml
!include ./puml/usecase_receive_and_reconcile_goods.puml
@enduml
```
  
  8. ## **Biểu đồ use case phân rã "ManageSystem"**

```plantuml
@startuml
!include ./puml/usecase_manage_system.puml
@enduml
```


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
