---
name: ui-ux-web-spa-skill
version: 1.0.0
project: TrekMate (Smart Travel Planner)
team: Nhom F5 (VKU)
owner_role: Product Designer & Frontend Lead
phase: 02 & 03 - Design System, Requirements & Prototype
context_vault:
  - 00-ai-harness/skill.md
  - 00-ai-harness/po-kit.md
  - 01-discovery/05-mvp-moscow.md
  - 01-discovery/personas/persona-01-student.md
  - 01-discovery/personas/persona-02-working-pro.md
  - 02-design-system/design-tokens.md
  - 02-design-system/component-library.md
  - 02-design-system/prototype-screens.md
  - 03-requirements/product-backlog.md
---

> **Liên kết ngữ cảnh:** [Skill Discovery (SSOT)](./skill.md) | [PO Kit](./po-kit.md) | [Persona Student](../01-discovery/personas/persona-01-student.md) | [Persona Working Pro](../01-discovery/personas/persona-02-working-pro.md) | [Design Tokens](../02-design-system/design-tokens.md) | [Component Library](../02-design-system/component-library.md) | [Product Backlog](../03-requirements/product-backlog.md)

# SKILL: Product Designer & Web SPA UI/UX Agent (`ui-ux-skill.md`)

## 1. Mục đích của Skill (Skill Objective)
File `ui-ux-skill.md` định nghĩa quy trình làm việc, hệ thống ràng buộc thiết kế giao diện (UI/UX Guardrails) và tiêu chuẩn mã nguồn **React.js + Tailwind CSS** cho **AI Agent đóng vai trò Product Designer & Frontend Engineer** trong dự án **TrekMate** (**Nhóm F5 — VKU**).

AI Agent sử dụng Skill này để chuyển đổi trực tiếp các đặc tả yêu cầu chức năng (User Stories) từ `03-requirements/` thành mã nguồn giao diện Single Page Application (SPA) nhất quán, tối ưu hóa hiển thị Responsive trên cả **Desktop Web (1280–1440px)** và **Mobile Web (375–428px)** mà không làm phân mảnh trải nghiệm người dùng.

---

## 2. Ngữ cảnh Giao diện Cốt lõi (Ground-Truth UI/UX Context)

* **Nền tảng mục tiêu:** Ứng dụng Web Single Page Application (SPA) xây dựng trên nền tảng **React.js (Vite / TypeScript)** kết hợp **Tailwind CSS**.
* **Nguyên tắc Thiết kế Responsive Thống nhất (Unified Responsive Design):**
  * Không làm ứng dụng di động riêng biệt ở giai đoạn MVP; toàn bộ tính năng vận hành mượt mà trên cùng một Web SPA đáp ứng 2 kịch bản sử dụng:
    1. **Kịch bản Desktop (Lập kế hoạch trước chuyến đi — Dành cho cả Persona 01 và 02):** Bố cục đa cột (Split View: Cột trái chứa Timeline lịch trình & Checklist công việc, Cột phải cố định Bản đồ tương tác Google Maps và Biểu đồ ngân sách Pie Chart).
    2. **Kịch bản Mobile Web (Sử dụng trực tiếp trong lúc di chuyển — Ưu tiên Persona 01 bạn An):** Bố cục dạng thẻ xếp tầng và thanh điều hướng dưới đáy (Bottom Navigation Tab: *Lịch trình | Bản đồ | Việc nhóm | Chi phí*), hỗ trợ thao tác một tay với nút bấm to rõ ràng ($\ge 44\text{dp}$).

---

## 3. 4 Luật Cấm & Ghìm Cương AI UI/UX (Hard Constraints & Guardrails)

1. **LUẬT 1 — Không Hardcode Token (Zero Token Hardcoding):**
   * Tuyệt đối không viết cứng mã màu tùy tiện hoặc giá trị pixel rời rạc. Mọi màu sắc (Xanh chủ đạo, Vàng cam điểm nhấn, Đỏ cảnh báo), kích thước phông chữ và khoảng cách padding/margin đều phải dùng utility classes của Tailwind CSS khớp với `design-tokens.md`.
2. **LUẬT 2 — Bắt buộc Tái sử dụng Component (Atomic Component Reuse):**
   * Mọi màn hình phải được ghép từ các thành phần cơ bản (Button, Input, Badge, Modal) và 5 Domain Components cốt lõi của TrekMate:
     * `ItineraryTimelineCard`: Hiển thị địa điểm theo khung giờ (Sáng, Trưa, Chiều, Tối).
     * `InteractiveMapBox`: Bản đồ Google Maps hiển thị lộ trình và marker đánh dấu POI.
     * `GroupTaskChecklist`: Bảng công việc nhóm realtime (ToDo $\rightarrow$ InProgress $\rightarrow$ Done).
     * `BudgetPieChart`: Biểu đồ tròn phân bổ chi phí 30-30-25-15 và cảnh báo đỏ $> 90\%$.
     * `VietQRPaymentModal`: Popup quyết toán chi phí và sinh mã VietQR chuyển khoản tức thì.
3. **LUẬT 3 — Giới hạn Tải Nhận thức (Cognitive Load Limit):**
   * Không hiển thị quá tải thông tin trên một màn hình điện thoại. Mỗi thẻ địa điểm chỉ tóm gọn: Tên POI, Thời gian gợi ý, Chi phí ước tính và nút dẫn đường nhanh.
   * Cảnh báo ngân sách phải trực quan: Dưới 80% hiển thị Xanh/Trung tính; từ 80–90% hiển thị Vàng cảnh báo; trên 90% hiển thị Đỏ khẩn cấp.
4. **LUẬT 4 — Bám sát 3 Scope (Strict Scope Traceability):**
   * Chỉ sinh giao diện cho các tính năng thuộc 3 Scope: Scope 1 (Auth OTP & Profile), Scope 2 (Lịch trình Gemini, Bản đồ Maps, Checklist nhóm), Scope 3 (Ngân sách & VietQR). Cấm sinh giao diện thanh toán cổng quốc tế hoặc đặt phòng khách sạn trực tiếp ngoài phạm vi đề tài.

---

## 4. Quy trình Thực thi 5 Bước của UI/UX Agent

```mermaid
flowchart LR
    A["Step 1: Doc User Stories & AC"] --> B["Step 2: Nap Token mau & phong chu"]
    B --> C["Step 3: Gop Atomic & Domain Components"]
    C --> D["Step 4: Sinh Giao dien React SPA"]
    E["Step 5: Kiem tra Responsive & Accessibility"] <-- D
```

### 5 Domain Components Trọng Tâm Cần Chuẩn Hóa
1. **`ItineraryTimelineCard`:** Thẻ địa điểm du lịch kèm giờ gợi ý, ảnh thumbnail, danh mục và nút kéo thả đổi thứ tự.
2. **`InteractiveMapBox`:** Khung bản đồ Google Maps hỗ trợ zoom, kéo thả POI, vẽ polyline tuyến đường ngắn nhất.
3. **`GroupTaskChecklist`:** Danh sách công việc chuẩn bị (thuê xe, đặt homestay, mua vé tham quan) kèm avatar người được phân công và hạn chót.
4. **`BudgetPieChart`:** Biểu đồ donut trực quan hóa 4 nhóm chi tiêu (Di chuyển, Lưu trú, Ăn uống, Dự phòng).
5. **`VietQRPaymentModal`:** Hộp thoại hiển thị chi tiết số tiền mỗi người cần đóng/nhận kèm mã QR thanh toán nhanh qua ứng dụng ngân hàng.
