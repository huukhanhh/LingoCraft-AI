> **Liên kết ngữ cảnh:** [UI/UX Skill](../00-ai-harness/ui-ux-skill.md) | [Personas](../01-discovery/personas/persona-01-trip-planner.md) | [Component Library](./component-library.md) | [Screens](./prototype-screens.md) | [Backlog](../03-requirements/product-backlog.md)

# Design Tokens — SmartTrip Web

## 1. Hướng thiết kế

Giao diện du lịch sáng sủa, tin cậy, gọn gàng; ưu tiên khả năng đọc lịch trình và nhận biết rõ thông tin nào là ước tính. Bố cục responsive cho web desktop, tablet và mobile. Các giá trị là đề xuất ban đầu, cần kiểm tra tương phản và thử nghiệm prototype.

## 2. Màu sắc

| Token | Light | Dark | Mục đích |
|---|---|---|---|
| `color.brand.primary` | `#176B5B` | `#64C7A7` | Hành động chính, trạng thái chọn |
| `color.brand.hover` | `#105447` | `#8AD8BE` | Hover/focus của hành động chính |
| `color.brand.soft` | `#E8F4F0` | `#173C35` | Nền nhấn nhẹ |
| `color.accent` | `#E6A23C` | `#F2BE69` | Điểm nhấn, không dùng làm chữ nhỏ trên nền trắng |
| `color.success` | `#18794E` | `#62C58B` | Hoàn tất |
| `color.warning` | `#9A6700` | `#F1C75B` | Cảnh báo cần chú ý |
| `color.error` | `#B42318` | `#F97066` | Lỗi/không hợp lệ |
| `color.text.primary` | `#17211F` | `#F1F5F4` | Nội dung chính |
| `color.text.secondary` | `#52615D` | `#B6C2BE` | Mô tả, thông tin phụ |
| `color.surface` | `#FFFFFF` | `#17211F` | Thẻ và biểu mẫu |
| `color.background` | `#F5F8F7` | `#101715` | Nền trang |
| `color.border` | `#D7E1DD` | `#34433E` | Viền và phân cách |

Không dùng màu làm tín hiệu duy nhất. Trạng thái phải kèm nhãn/icon; văn bản thường hướng tới tương phản WCAG AA.

## 3. Typography

Ưu tiên font sans-serif phổ biến có hỗ trợ tiếng Việt; nội dung lịch trình dùng line-height thoáng.

| Token | Kích thước / độ đậm | Dùng cho |
|---|---|---|
| `type.display` | 36 / 700 | Hero, tiêu đề landing |
| `type.title` | 28 / 700 | Tiêu đề trang |
| `type.heading` | 20 / 600 | Khối và ngày trong lịch |
| `type.body` | 16 / 400 | Nội dung |
| `type.bodyStrong` | 16 / 600 | Nhãn và hoạt động |
| `type.caption` | 14 / 400 | Trạng thái, nguồn, chú thích |

## 4. Spacing, radius, breakpoint

| Token | Giá trị |
|---|---:|
| `space.1` / `.2` / `.3` / `.4` / `.6` / `.8` | 4 / 8 / 12 / 16 / 24 / 32 px |
| `radius.control` | 10 px |
| `radius.card` | 16 px |
| `radius.panel` | 20 px |
| `size.control.minHeight` | 44 px |
| `layout.contentMax` | 1200 px |
| `breakpoint.tablet` | 768 px |
| `breakpoint.desktop` | 1024 px |

## 5. Chuyển động và trạng thái

- Dùng chuyển động ngắn, không thiết yếu cho việc hiểu nội dung; tôn trọng `prefers-reduced-motion`.
- Giữ nguyên dữ liệu form khi tạo lịch trình thất bại.
- Trạng thái loading, empty, error, success luôn có ngữ nghĩa và nội dung văn bản.
- Nhãn “Ước tính”, “Gợi ý AI” hoặc tên/giờ cập nhật nguồn phải xuất hiện cạnh thông tin liên quan.
