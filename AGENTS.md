# AGENTS.md

## Mục tiêu repository
- Đây là repo tài liệu phân tích yêu cầu cho bài tập môn ITSS về hệ thống đặt hàng nhập khẩu.
- Trọng tâm hiện tại là các file trong `docs/` (SRS, phân tích actor/use case, PlantUML).

## Phạm vi chỉnh sửa
- Được phép chỉnh sửa: `docs/**`, `.vscode/settings.json`, `AGENTS.md`.
- Không chỉnh sửa nội dung trong `docs/do-not-edit/**` trừ khi có yêu cầu rõ ràng từ người dùng.
- Không tự ý đổi tên file đang được giảng viên/nhóm tham chiếu.

## Quy ước nội dung
- Ngôn ngữ chính: tiếng Việt.
- Tên use case nên nhất quán theo tiếng Anh ngắn gọn (ví dụ: `Manage Import Requests`).
- Nội dung phải bám sát đề bài trong `docs/Project BTL - HeThongDatHangNhapKhau 20252.docx.md`.
- Tránh đưa thêm tính năng ngoài phạm vi bài toán nếu chưa có yêu cầu.

## Quy ước PlantUML
- Tất cả sơ đồ `.puml` đặt trong `docs/puml/`.
- Dùng style chung qua:
  - `!include ./astah-style.puml` (khi file sơ đồ cùng thư mục `docs/puml`)
- Với tài liệu markdown trong `docs/`, nhúng sơ đồ bằng:
  - `!include ./puml/<ten-file>.puml`
- Giữ style Astah-like, đường nối thẳng/góc vuông theo `astah-style.puml`.

## Render Markdown + PlantUML (VSCode)
- Dùng extension `Markdown Preview Enhanced`.
- Cấu hình jar tại `.vscode/settings.json`:
  - `markdown-preview-enhanced.plantumlJarPath` trỏ tới `.jar/plantuml.jar`.
- Nếu render lỗi local jar, có thể dùng server:
  - `markdown-preview-enhanced.plantumlServer: "https://kroki.io/plantuml/svg/"`

## Checklist trước khi kết thúc chỉnh sửa
- Kiểm tra liên kết include PlantUML đúng path tương đối.
- Đảm bảo các mục actor/use case đồng bộ giữa `docs/Analysis.md` và `docs/RequirementAnalysis-VN.docx.md`.
- Không để placeholder kiểu `...`, `xxx`, `TODO` ở phần đã yêu cầu hoàn thiện.


## Naming convention
- Tên file markdown: `<ten-use-case>.md` (ví dụ: `ManageImportRequests.md`).
- Tên file PlantUML: `<ten-diagram>.puml` (ví dụ: `usecase-overview.puml`).
- Đặt tên trong biểu đồ và trường dữ liệu: tiếng Anh, ưu tiên chuẩn dạng identifier dễ đọc.
    - Tên actor: `PascalCase` (ví dụ: `SalesDepartment`, `SystemAdministrator`).
    - Tên use case: `PascalCase` theo cụm động từ (ví dụ: `ManageImportRequests`, `PlanImportAllocation`).
    - Tên class (nếu có trong diagram phân tích): `PascalCase` (ví dụ: `ImportRequest`, `Site`, `InventoryRecord`).
    - Tên method/operation (nếu có trong diagram phân tích): `camelCase` (ví dụ: `calculateAllocation()`, `reconcileGoods()`).
    - Tên biến (nếu có): `camelCase` (ví dụ: `requestedQty`, `inStockQty`).
    - Tên diagram (tên file): `snake_case` (ví dụ: `usecase_overview.puml`, `sequence_manage_site.puml`).