# 🧰 PO Kit: Skills & Templates cho Giai đoạn Research & Discovery — TrekMate

## 1. Quy tắc bắt buộc cho AI (PO Skills & Guardrails)
- **Không nhảy cóc:** Tuyệt đối không viết tính năng kỹ thuật (Technical Specifications / User Stories) khi chưa làm rõ Nhu cầu người dùng du lịch tự túc (User Needs), Nỗi đau thực tế (Pain Points) và Khoảng trống thị trường (Market Gap).
- **Bài toán kinh doanh & ngân sách:** Mọi phân tích thị trường phải gắn liền với mô hình vận hành, cấu trúc chi phí (hạ tầng Cloud/API) và mô hình tạo doanh thu (Monetization).
- **Liên kết Vault (Second Brain):** Đầu mỗi file `.md` bắt buộc phải có khối trích dẫn `> **Liên kết ngữ cảnh:**` dẫn link tương đối (`./...` hoặc `../...`) tới các file liên quan trong kho tri thức Vault.
- **Trực quan hóa bắt buộc:** Bắt buộc sử dụng sơ đồ `Mermaid` (`quadrantChart`, `flowchart`, `journey`) để trực quan hóa luồng tư duy, ma trận cạnh tranh và hành trình trải nghiệm.
- **Ánh xạ Persona sang UI/UX Web:** Trong mỗi file Persona, bắt buộc có mục giải thích chuyên sâu: Từ độ tuổi, thói quen đi lại, thiết bị sử dụng (Desktop & Mobile Web) và Pain Points của nhóm du lịch, giao diện hệ thống cần bố trí màu sắc, bản đồ tương tác, bảng phân bổ ngân sách và touch target như thế nào.
- **Neo trên 3 Trụ cột Scope:** Toàn bộ giải pháp sản phẩm phải xoay quanh 3 phân hệ đã chốt trong đề tài:
  - Scope 1: Quản lý tài khoản & phân quyền (Xác thực OTP Email, Cập nhật Profile gu đi, Khóa tài khoản Admin).
  - Scope 2: Quản lý lịch trình & công việc (Lập lịch trình Gemini AI, Tối ưu tuyến đường Google Maps, Phân công Checklist công việc thời gian thực).
  - Scope 3: Quản lý ngân sách & chi phí (Hạn mức tự động 30-30-25-15, Bóc tách chi phí & Pie Chart cảnh báo >90%, Quyết toán VietQR tự động).

## 2. Cấu trúc Biểu mẫu chuẩn (Templates)
- **File `01-market-and-needs.md`:** 1. Nhu cầu người dùng du lịch tự túc $\rightarrow$ 2. Khoảng trống thị trường (Phân tích đối thủ + Mermaid `quadrantChart`) $\rightarrow$ 3. Mô hình kinh doanh & kiếm tiền (Monetization Model).
- **File `02-problem-statement.md`:** 1. Tuyên bố Vấn đề cốt lõi (Công thức 4 thành phần chuẩn, không chứa giải pháp) $\rightarrow$ 2. Hệ quả đối với người dùng & sản phẩm $\rightarrow$ 3. Sơ đồ Nguyên nhân - Hệ quả (Mermaid `flowchart`).
- **File `03-product-vision.md`:** Tuyên ngôn tầm nhìn theo khung Geoffrey Moore (For / Who / The Product / Is a / That / Unlike / Our Product) + 3 Product Goals + Hệ thống chỉ số SMART OKRs đo lường được trong 4 tuần Vibe Code MVP & 6 tháng.
- **File `04-product-canvas.md`:** Bảng tóm tắt Product Canvas + Mô hình kinh doanh Lean Canvas 9 ô + Sơ đồ Hành trình người dùng (`Mermaid journey`).
- **File `05-mvp-moscow.md`:** Phân loại tính năng theo Ma trận MoSCoW (Must Have, Should Have, Could Have, Won't Have) bám sát khung thời gian **4 tuần Vibe Code MVP (Sprint 1 đến Sprint 4, chu kỳ 1 tuần/sprint)** theo mô hình **Agile/Scrum**.
- **File `personas/*.md`:** 1. Demographics $\rightarrow$ 2. Goals & Motivations $\rightarrow$ 3. Habits $\rightarrow$ 4. Pain Points $\rightarrow$ 5. UI/UX Implications (Ánh xạ sang thiết kế Web Desktop & Mobile) $\rightarrow$ 6. User Journey (`Mermaid journey`).
