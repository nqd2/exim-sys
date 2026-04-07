# AGENTS.md

## Mục tiêu repository
- Đây là repo tài liệu phân tích yêu cầu cho bài tập môn ITSS về hệ thống đặt hàng nhập khẩu.
- Trọng tâm hiện tại là các file trong `docs/` (SRS, phân tích actor/use case, PlantUML).

## Phạm vi chỉnh sửa
- Được phép chỉnh sửa: `docs/**`, `.vscode/settings.json`, `.gitignore`, `AGENTS.md`.
- Không chỉnh sửa nội dung trong `docs/do-not-edit/**` trừ khi có yêu cầu rõ ràng từ người dùng.
- Không tự ý đổi tên file đang được giảng viên/nhóm tham chiếu.

## Quy ước nội dung
- Ngôn ngữ chính: tiếng Việt.
- Tên use case nên nhất quán theo tiếng Anh ngắn gọn (ví dụ: `ManageImportRequests`).
- Nội dung phải bám sát đề bài trong `docs/Project BTL - HeThongDatHangNhapKhau 20252.docx.md`.
- Tránh đưa thêm tính năng ngoài phạm vi bài toán nếu chưa có yêu cầu.

## Quy ước PlantUML
- Tất cả sơ đồ `.puml` đặt trong `docs/puml/`.
- Dùng style chung qua:
  - `!include ./astah_style.puml` (khi file sơ đồ cùng thư mục `docs/puml`)
- Với tài liệu markdown trong `docs/`, nhúng sơ đồ bằng:
  - `!include ./puml/<ten-file>.puml`
- Giữ style Astah-like, đường nối thẳng/góc vuông theo `astah_style.puml`.
- Biểu đồ phân rã use case (nhóm ITSS): `usecase_manage_import_requests.puml`, `usecase_manage_site_information.puml`, `usecase_collect_inventory_data.puml`, `usecase_plan_import_allocation.puml`, `usecase_place_overseas_orders.puml`, `usecase_receive_and_reconcile_goods.puml`, `usecase_manage_system.puml`.

## Render Markdown + PlantUML (VSCode)
- Dùng extension `Markdown Preview Enhanced`.
- Cấu hình jar tại `.vscode/settings.json`:
  - `markdown-preview-enhanced.plantumlJarPath` trỏ tới `.jar/plantuml.jar` (phải là đường dẫn tuyệt đối).
- Nếu render lỗi local jar, có thể dùng server:
  - `markdown-preview-enhanced.plantumlServer: "https://kroki.io/plantuml/svg/"`

## Checklist trước khi kết thúc chỉnh sửa
- Kiểm tra liên kết include PlantUML đúng path tương đối.
- Đảm bảo các mục actor/use case đồng bộ giữa `docs/Analysis.md` và `docs/RequirementAnalysis-VN.docx.md`.
- Không để placeholder kiểu `...`, `xxx`, `TODO` ở phần đã yêu cầu hoàn thiện.


## Naming convention
- Tên file markdown: `<ten-use-case>.md` (ví dụ: `ManageImportRequests.md`).
- Tên file PlantUML: `<ten-diagram>.puml` (ví dụ: `usecase_overview.puml`).
- Đặt tên trong biểu đồ và trường dữ liệu: tiếng Anh, ưu tiên chuẩn dạng identifier dễ đọc.
    - Tên actor: `PascalCase` (ví dụ: `SalesDepartment`, `SystemAdministrator`).
    - Tên use case: `PascalCase` theo cụm động từ (ví dụ: `ManageImportRequests`, `PlanImportAllocation`).
    - Tên class (nếu có trong diagram phân tích): `PascalCase` (ví dụ: `ImportRequest`, `Site`, `InventoryRecord`).
    - Tên method/operation (nếu có trong diagram phân tích): `camelCase` (ví dụ: `calculateAllocation()`, `reconcileGoods()`).
    - Tên biến (nếu có): `camelCase` (ví dụ: `requestedQty`, `inStockQty`).
    - Tên diagram (tên file): `snake_case` (ví dụ: `usecase_overview.puml`, `sequence_manage_site.puml`).


## Cách biểu diễn đặc tả use case 
### json:
```{
  "useCase": {
    "Mã UseCase": ${useCaseId},
    "Tên UseCase": "${useCaseName}",
    "Tác nhân": [
      ${actor1}, ${actor2}, ...
    ],
    "Tiên điều kiện": "${preconditions}",
    "Luồng sự kiện chính": [
      {
        "STT": "1",
        "Thực hiện bởi": "${actorPerformingAction1}",
        "Hành động": "${action1}"
      },
      {
        "STT": "2",
        "Thực hiện bởi": "${actorPerformingAction2}",
        "Hành động": "${action2}"
      },
      {
        "STT": "3",
        "Thực hiện bởi": "${actorPerformingAction3}",
        "Hành động": "${action3}"
      },
      {
        "STT": "4",
        "Thực hiện bởi": "${actorPerformingAction4}",
        "Hành động": "${action4}"
      },
      {
        "STT": "5",
        "Thực hiện bởi": "${actorPerformingAction5}",
        "Hành động": "${action5}"
      }
    ],
    "luongSuKienThayThe": [
      {
        "STT": "5a",
        "Thực hiện bởi": "${actorPerformingAction5a}",
        "Hành động": "${action5a}"
      }
    ],
    "hauDieuKien": "${alternativePreconditions}",
    "Dữ liệu đầu vào": [
      {
        "STT": "1",
        "Trường dữ liệu": "${inputData1}",
        "Mô tả": "${inputData1Description}",
        "Bắt buộc": boolean,
        "Điều kiện hợp lệ": "${inputData1ValidCondition}",
        "Ví dụ": "${inputData1Example}"
      },
      {
        "STT": "2",
        "Trường dữ liệu": "${inputData2}",
        "Mô tả": "${inputData2Description}",
        "Bắt buộc": boolean,
        "Điều kiện hợp lệ": "${inputData2ValidCondition}",
        "Ví dụ": "${inputData2Example}"
      },
      {
        "STT": "3",
        "Trường dữ liệu": "${inputData3}",
        "Mô tả": "${inputData3Description}",
        "Bắt buộc": boolean,
        "Điều kiện hợp lệ": "${inputData3ValidCondition}",
        "Ví dụ": "${inputData3Example}"
      }
    ]
  }
}
```
### HTML bảng lồng nhau:

<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width: 100%;">
  <colgroup>
    <col style="width: 16%;">
    <col style="width: 34%;">
    <col style="width: 16%;">
    <col style="width: 34%;">
  </colgroup>
  <tr>
    <th colspan="4">Đặc tả Use Case</th>
  </tr>
  <tr>
    <td><strong>Mã UseCase</strong></td>
    <td>${useCaseId}</td>
    <td><strong>Tên UseCase</strong></td>
    <td>${useCaseName}</td>
  </tr>
  <tr>
    <td><strong>Tác nhân</strong></td>
    <td colspan="3">${actor1}, ${actor2}, ...</td>
  </tr>
  <tr>
    <td><strong>Tiền điều kiện</strong></td>
    <td colspan="3">${preconditions}</td>
  </tr>
  <tr>
    <td><strong>Luồng sự kiện chính</strong></td>
    <td colspan="3">
      <table border="1" cellpadding="4" cellspacing="0" style="border-collapse: collapse; width: 100%;">
        <tr>
          <th>STT</th>
          <th>Thực hiện bởi</th>
          <th>Hành động</th>
        </tr>
        <tr>
          <td>1</td>
          <td>${actorPerformingAction1}</td>
          <td>${action1}</td>
        </tr>
        <tr>
          <td>2</td>
          <td>${actorPerformingAction2}</td>
          <td>${action2}</td>
        </tr>
        <tr>
          <td>3</td>
          <td>${actorPerformingAction3}</td>
          <td>${action3}</td>
        </tr>
        <tr>
          <td>4</td>
          <td>${actorPerformingAction4}</td>
          <td>${action4}</td>
        </tr>
        <tr>
          <td>5</td>
          <td>${actorPerformingAction5}</td>
          <td>${action5}</td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td><strong>Luồng sự kiện thay thế</strong></td>
    <td colspan="3">
      <table border="1" cellpadding="4" cellspacing="0" style="border-collapse: collapse; width: 100%;">
        <tr>
          <th>STT</th>
          <th>Thực hiện bởi</th>
          <th>Hành động</th>
        </tr>
        <tr>
          <td>5a</td>
          <td>${actorPerformingAction5a}</td>
          <td>${action5a}</td>
        </tr>
      </table>
    </td>
  </tr>
  <tr>
    <td><strong>Hậu điều kiện</strong></td>
    <td colspan="3">${alternativePreconditions}</td>
  </tr>
  <tr>
    <td><strong>Dữ liệu đầu vào</strong></td>
    <td colspan="3">
      <table border="1" cellpadding="4" cellspacing="0" style="border-collapse: collapse; width: 100%;">
        <tr>
          <th>STT</th>
          <th>Trường dữ liệu</th>
          <th>Mô tả</th>
          <th>Bắt buộc</th>
          <th>Điều kiện hợp lệ</th>
          <th>Ví dụ</th>
        </tr>
        <tr>
          <td>1</td>
          <td>${inputData1}</td>
          <td>${inputData1Description}</td>
          <td>${inputData1Required}</td>
          <td>${inputData1ValidCondition}</td>
          <td>${inputData1Example}</td>
        </tr>
        <tr>
          <td>2</td>
          <td>${inputData2}</td>
          <td>${inputData2Description}</td>
          <td>${inputData2Required}</td>
          <td>${inputData2ValidCondition}</td>
          <td>${inputData2Example}</td>
        </tr>
        <tr>
          <td>3</td>
          <td>${inputData3}</td>
          <td>${inputData3Description}</td>
          <td>${inputData3Required}</td>
          <td>${inputData3ValidCondition}</td>
          <td>${inputData3Example}</td>
        </tr>
      </table>
    </td>
  </tr>
</table>



## Screen Transition Diagram:
