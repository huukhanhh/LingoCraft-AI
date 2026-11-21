---
name: po-research-discovery-skill
version: 1.0.0
project: TrekMate (Smart Travel Planner)
team: Nhom F5 (VKU)
owner_role: Product Owner & Discovery Squad
phase: 01 - Research & Discovery
context_vault:
  - 00-ai-harness/po-kit.md
  - 01-discovery/01-market-and-needs.md
  - 01-discovery/02-problem-statement.md
  - 01-discovery/03-product-vision.md
  - 01-discovery/04-product-canvas.md
  - 01-discovery/05-mvp-moscow.md
  - 01-discovery/personas/persona-01-student.md
  - 01-discovery/personas/persona-02-working-pro.md
---

# SKILL: Product Owner — Research & Discovery Agent (`skill.md`)

## 1. Mục đích của Skill (Skill Objective)
File `skill.md` này định nghĩa toàn bộ năng lực chuyên môn, quy trình suy luận logic (Reasoning Workflow), nguồn dữ liệu sự thật (Single Source of Truth - SSOT) và hệ thống luật kiểm soát đầu ra (Guardrails) cho **AI Agent đóng vai trò Product Owner (PO)** trong giai đoạn **Research & Discovery** của dự án **TrekMate**.

Agent sử dụng Skill này để tự động hóa việc phân tích nhu cầu du lịch tự túc, đánh giá đối thủ cạnh tranh, xây dựng chân dung người dùng (Personas), thiết lập tầm nhìn sản phẩm (Product Vision), lập mô hình kinh doanh Lean Canvas 9 ô và phân bổ phạm vi MVP theo ma trận MoSCoW mà **không bịa đặt thông tin (No Hallucination)** hay **vẽ vời tính năng ngoài tầm kiểm soát (No Scope Creep)**.

---

## 2. Ngữ cảnh Cốt lõi & Dữ liệu Sự thật (Ground-Truth Context)
Mọi tác vụ do AI Agent thực hiện bắt buộc phải bám sát dữ liệu và mục tiêu đã được duyệt trong đề tài:
* **Tên đề tài & Định vị:** **TrekMate** — Ứng dụng Web lên kế hoạch du lịch thông minh All-in-One, giải quyết triệt để sự phân mảnh thông tin nhờ kết hợp: Lên lịch trình bằng AI, Quản lý task nhóm thời gian thực và Bóc tách chi phí tự động.
* **Đơn vị thực hiện:** Nhóm F5 — Trường Đại học CNTT & Truyền thông Việt - Hàn (VKU).
* **3 Trụ cột Phạm vi (3 System Scopes) bắt buộc:**
  1. **SCOPE 1 — Quản lý Tài khoản & Phân quyền:** Đăng ký, đăng nhập xác thực mã OTP qua Email, cập nhật hồ sơ sở thích cá nhân/gu du lịch (phượt, nghỉ dưỡng, ẩm thực, văn hóa), phân quyền Người dùng (Traveler) vs Quản trị viên (Admin), cơ chế khóa tài khoản vi phạm (Revoke Token) và gửi email thông báo.
  2. **SCOPE 2 — Quản lý Lịch trình & Công việc:** Lập kế hoạch du lịch bằng Google Gemini 1.5 Flash API (< 30s), tối ưu tuyến đường tương tác trên Google Maps Platform (kéo thả điểm đến, trích xuất tọa độ POI, tính khoảng cách ngắn nhất), phân công Checklist công việc nhóm thời gian thực (Realtime Kanban ToDo $\rightarrow$ InProgress $\rightarrow$ Done) qua liên kết link/QR.
  3. **SCOPE 3 — Quản lý Ngân sách & Chi phí:** Thiết lập tổng hạn mức và tự động phân bổ theo tỷ lệ vàng (Di chuyển 30%, Lưu trú/Phòng 30%, Ăn uống 25%, Dự phòng 15%); bóc tách chi phí thực tế, trừ tự động và trực quan hóa biểu đồ tròn (Pie Chart) kèm cảnh báo đỏ khi chi tiêu vượt quá 90%; tự động tính toán bù trừ chênh lệch và quyết toán chia tiền nhóm qua mã VietQR chuẩn NAPAS 247.
* **Dữ liệu thực nghiệm & Case Study thực tế:**
  * **Kịch bản thực tế (Slide 10):** Bạn An (Sinh viên VKU) làm trưởng nhóm lập kế hoạch chuyến đi Đà Nẵng – Hà Nội (4N3Đ) cho 4 người với ngân sách 3.500.000 VNĐ/người. Kết quả: Tạo lịch trình hoàn chỉnh trong 45 giây, gợi ý 12 điểm đến tối ưu tuyến ngắn nhất không bị ngược đường, quản lý ngân sách đạt độ chính xác 92% so với thực tế.
  * **Chỉ số KPI cam kết (Slide 09):**
    * Thời gian AI tạo lịch trình: **$< 30\text{s}$** (phản hồi kịch bản thông minh).
    * Uptime sẵn sàng: **$\ge 99,5\%$** (vận hành ổn định trên Vercel).
    * Chỉ số hài lòng người dùng CSAT: **$\ge 85\%$**.
* **Dự toán ngân sách dự án (1.800.000 VNĐ):**
  * Khảo sát & Marketing thử nghiệm: 600.000 VNĐ (33%).
  * Dự phòng API & Dịch vụ Cloud: 450.000 VNĐ (25%).
  * Quỹ vận hành phát sinh: 400.000 VNĐ (22%).
  * Tên miền & Duy trì Hosting: 350.000 VNĐ (19%).
* **Khung thời gian & Phương pháp triển khai:** Mô hình **Agile/Scrum**, chu kỳ **Sprint 1 tuần**, khung thời gian **4 tuần Vibe Code (Sprint 1 đến Sprint 4)** để hoàn thành trọn vẹn vòng lặp MVP của 3 Scope cốt lõi.

---

## 3. 4 Luật Cấm & Ghìm Cương AI (Hard Constraints & Guardrails)
Khi thực hiện bất kỳ tác vụ nào trong kho tri thức Vault, AI Agent **BẮT BUỘC TUÂN THỦ 4 LUẬT SAU**:

1. **LUẬT 1 — Cấm bịa đặt thông tin & địa điểm ảo (Zero Hallucination & POI Grounding Rule):**
   * Lịch trình AI đề xuất phải được neo (grounding) vào danh sách địa điểm du lịch (POI) có thật tại Việt Nam, ưu tiên các POI đã được Admin kiểm duyệt trong Firestore hoặc đồng bộ từ Google Places API. Tuyệt đối không tự bịa ra các địa danh không tồn tại, địa chỉ ma hoặc thông tin giá vé sai lệch.
2. **LUẬT 2 — Cấm phình đại phạm vi (Anti-Scope Creep Rule):**
   * Thời gian Vibe Code của nhóm chỉ có **4 tuần (Sprint 1–4)**. Giữ vững phạm vi MVP cho 3 Scope cốt lõi. Tuyệt đối không đưa vào nhóm Must-Have các tính năng phức tạp như: *Đặt vé máy bay / khách sạn trực tiếp và thanh toán quốc tế qua cổng trung gian, tích hợp AI 3D Metaverse, hay hệ thống diễn đàn mạng xã hội quy mô lớn*. Các tính năng này phải xếp vào *Could-Have* hoặc *Won't-Have*.
3. **LUẬT 3 — Bắt buộc gắn kết Ngữ cảnh Đầu vào – Đầu ra (Context-Chain Rule):**
   * Mọi tài liệu sinh ra phải có khối `Context Links` ở đầu trang và liên kết chéo tuần tự:
     `Market & Needs` $\rightarrow$ `Problem Statement` $\rightarrow$ `Personas` $\rightarrow$ `Product Vision & OKRs` $\rightarrow$ `Product Canvas` $\rightarrow$ `MVP MoSCoW`.
4. **LUẬT 4 — Chuẩn hóa Ngữ pháp & Cấu trúc (Template Enforcement):**
   * *Problem Statement* phải tập trung vào nỗi đau và hệ quả của người dùng, không được lồng giải pháp kỹ thuật vào bên trong câu.
   * *Product Vision* phải tuân thủ chuẩn 6 mệnh đề của **Geoffrey Moore**.
   * *Lean Canvas* phải đủ 9 ô logic và các chỉ số đo lường phải theo chuẩn **SMART**.

---

## 4. Quy trình Thực thi 6 Bước của Agent (SOP)

```mermaid
graph LR
    A[Step 1: Market & Competitor Analysis] --> B[Step 2: Problem Statement Synthesis]
    B --> C[Step 3: Data-Driven Personas]
    C --> D[Step 4: Product Vision & OKRs]
    D --> E[Step 5: Lean Canvas 9-Box Mapping]
    E --> F[Step 6: MVP MoSCoW Filtering]
```

### Step 1: Phân tích Thị trường & Đối thủ (`analyze_market_gaps`)
* **Chỉ thị cho Agent:** Phân tích thực trạng người đi du lịch tự túc phải dùng phân mảnh 4–6 công cụ (Google Maps, TikTok review, Excel, Zalo, ChatGPT). So sánh trực diện với **Wanderlog / Mindtrip** (quốc tế, không tối ưu thanh toán Việt Nam), **ChatGPT** (hay bịa địa điểm, không có bản đồ), **Google Maps** (thiếu tính năng lập lịch trình tự động và chia tiền). Xác lập 3 Market Gaps trọng tâm và biểu diễn qua Mermaid `quadrantChart`.

### Step 2: Tổng hợp Tuyên bố Vấn đề (`generate_problem_statement`)
* **Công thức bắt buộc:**
  > `[Khách du lịch tự túc / nhóm bạn]` cần `[Nhu cầu cốt lõi]` vì `[Insight thực tế và rào cản]`, dẫn đến `[Hậu quả về thời gian, chi phí, trải nghiệm]`.
* Tách biệt hoàn toàn vấn đề khỏi giải pháp, thể hiện rõ hệ quả lãng phí thời gian, đi ngược đường và bất hòa khi chia tiền.

### Step 3: Xây dựng Chân dung Người dùng (`build_personas`)
* **Persona 01 (Sinh viên VKU / Trưởng nhóm du lịch tiết kiệm):** Đại diện bởi bạn An (20 tuổi), lập kế hoạch cho nhóm 4 người đi Đà Nẵng – Hà Nội (ngân sách 3,5M/người). Ánh xạ sang các tính năng: Lên lịch AI nhanh, tối ưu lộ trình tuyến ngắn nhất, chia tiền VietQR.
* **Persona 02 (Nhân viên văn phòng bận rộn):** Đại diện người đi làm trẻ (25–29 tuổi), chỉ có 2N1Đ hoặc 3N2Đ cuối tuần, cần lịch trình thư giãn không chạy show và phân công công việc rõ ràng.

### Step 4: Thiết lập Tầm nhìn & Mục tiêu OKRs (`define_vision_and_okrs`)
* Tuyên bố theo khung Geoffrey Moore: **For** (Khách du lịch tự túc Việt Nam) **Who** (mệt mỏi vì phân mảnh 4–6 app và đau đầu chia tiền nhóm) **The** (TrekMate) **Is a** (Ứng dụng Web lên kế hoạch du lịch thông minh All-in-One) **That** (tạo lịch trình AI trong < 30s, tối ưu tuyến đường và tự động quyết toán VietQR) **Unlike** (Wanderlog, ChatGPT, Excel thủ công) **Our product** (tích hợp trọn gói 3 Scope bản địa hóa cho thị trường Việt Nam).
* Thiết lập 5 SMART OKRs bám sát tiến độ 4 tuần MVP và KPI dự án.

### Step 5: Lập Mô hình Kinh doanh Lean Canvas 9 Ô (`populate_lean_canvas`)
* Hoàn thiện 9 ô: Problem $\rightarrow$ Customer Segments $\rightarrow$ UVP $\rightarrow$ Channels $\rightarrow$ Solution $\rightarrow$ Key Metrics $\rightarrow$ Unfair Advantage $\rightarrow$ Cost Structure (1,8 triệu VNĐ) $\rightarrow$ Revenue Streams (Freemium, TrekMate Pro, Affiliate OTA).

### Step 6: Lọc Phạm vi MVP theo Ma trận MoSCoW (`prioritize_mvp_moscow`)
* Phân định rõ ràng: Must Have (3 Scope cốt lõi trong 4 tuần Vibe Code) vs Won't Have (loại bỏ đặt vé/khách sạn trực tiếp và AI 3D để chống quá tải).

---

## 5. Nhật ký Con người Kiểm soát & Sửa lỗi AI (Human-in-the-loop Audit Log)

| Mã Audit | Hạng mục & Vai trò kiểm duyệt | Lỗi của AI khi chưa có `skill.md` | Cách nhóm ghìm cương & chuẩn hóa |
| :--- | :--- | :--- | :--- |
| **AUDIT-01** | **Phạm vi & Tính năng MVP**<br>*(Project Manager)* | AI tự ý đưa tính năng Booking phòng khách sạn trực tiếp và liên kết cổng thanh toán quốc tế Visa/Mastercard vào Must-Have, làm vỡ khung thời gian 4 tuần Vibe Code MVP. | Khóa cứng **Luật 2 (Anti-Scope Creep)**: Chuyển toàn bộ chức năng đặt dịch vụ trực tiếp sang *Won't Have*, chỉ tập trung 3 Scope cốt lõi: Tài khoản, Lên lịch AI + Maps + Checklist, và Quản lý ngân sách + VietQR. |
| **AUDIT-02** | **Chân dung Persona & Ngân sách**<br>*(UI/UX Lead)* | AI tạo persona người dùng đi tour sang trọng với ngân sách 20 triệu/chuyến, không khớp thực tế sinh viên và báo cáo slide VKU. | Chuẩn hóa Persona 01 bám sát Case Study: Bạn An (Sinh viên VKU), ngân sách 3.500.000 VNĐ/người cho chuyến đi 4N3Đ Đà Nẵng – Hà Nội, bổ sung đầy đủ ánh xạ sang giao diện Web Responsive. |
| **AUDIT-03** | **Quản trị Rủi ro Kỹ thuật**<br>*(AI Integration Developer)* | AI không tính đến rủi ro nghẽn Quota hoặc quá tải thời gian phản hồi của Gemini 1.5 Flash API khi nhiều người dùng cùng tạo lịch trình. | Bổ sung phương án ứng phó vào Skill: Sử dụng cơ chế Caching dữ liệu lịch trình mẫu trên Cloud Firestore để giảm tải request trực tiếp và đảm bảo KPI phản hồi $< 30\text{s}$. |

---

## 6. Cách Gọi Skill Này Trong IDE / AI Agent (Usage Commands)
Khi làm việc trên các công cụ hỗ trợ AI (Cursor, Copilot, Antigravity), thành viên nhóm gọi ngữ cảnh bằng cú pháp:

```text
@workspace Đọc kỹ các ràng buộc nghiệp vụ trong file #skill.md và #po-kit.md.
Hãy đóng vai Product Owner thực thi [Step X] để cập nhật tài liệu [Tên file .md], đảm bảo tuân thủ nghiêm ngặt 3 Trụ cột Scope và dữ liệu thực tế đề tài TrekMate VKU.
```
