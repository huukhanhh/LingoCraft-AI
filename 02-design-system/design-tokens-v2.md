> **Liên kết ngữ cảnh:** [Skill UI/UX (React Native)](../00-ai-harness/ui-ux-skill.md) | [Persona Student](../01-discovery/personas/persona-01-student.md) | [Persona Working Pro](../01-discovery/personas/persona-02-working-pro.md) | [Component Library v2](./component-library-v2.md) | [Prototype Screens v2](./prototype-screens-v2.md) | [Product Backlog](../03-requirements/product-backlog.md) | Bản gốc: [design-tokens.md](./design-tokens.md)

# 🎨 Hệ thống Design Tokens v2 (`LingoCraft AI`) — sinh theo Skill Kit khác

Bản v2 giữ nguyên **nguyên lý Persona → Token** của bản gốc nhưng được viết lại theo quy trình của các **AI skill kit thiết kế** khác (mục 1), thay vì chỉ dựa vào `ui-ux-skill.md` nội bộ.

---

## 1. Các Skill Kit tham chiếu & cách áp dụng

| Skill Kit | Nguồn | Ý tưởng cốt lõi | Áp dụng vào v2 |
| :--- | :--- | :--- | :--- |
| **UI UX Pro Max** | `nextlevelbuilder/ui-ux-pro-max-skill` | Bộ máy lập luận sinh design system theo cấu trúc **Pattern + Style + Colors + Typography + Effects**, có luật theo ngành, kiểm tra **anti-pattern** và checklist trước khi giao. Chạy như skill cho Claude Code, Cursor, Windsurf… | Mục 2 (**Design System Brief**) và mục 8 (**Pre-delivery Checklist**) |
| **Google Stitch `DESIGN.md`** + `stitch-skills` | `google-labs-code/stitch-skills` | Mô tả nhận diện thị giác bằng **token có tên + văn xuôi Markdown** để AI agent đọc và sinh giao diện nhất quán. Định dạng được open-source từ 04/2026. | Mục 4 (**Visual Description**) để dán thẳng cho agent |
| **taste-skill** (Stitch Design Taste) | `Leonxlnx/taste-skill` | Chống giao diện "generic AI": typography nghiêm ngặt, màu được hiệu chỉnh, micro-motion có chủ đích, chú ý hiệu năng, có danh sách anti-pattern rõ ràng. | Font riêng cho tiếng Việt, motion tokens, danh sách anti-pattern |

> ⚠️ **Lưu ý trung thực:** Môi trường sinh tài liệu này không chạy được CLI `uipro` hay Stitch. Bản v2 là kết quả **áp dụng phương pháp và định dạng** của các kit trên, không phải output chạy thật. Để đối chiếu, chạy thử `npm i -g uipro-cli && uipro init --ai claude` trong repo, nhập brief ở mục 2 rồi so với bảng token bên dưới.

---

## 2. Design System Brief (định dạng UI UX Pro Max)

| Hạng mục | Quyết định cho `LingoCraft AI` | Lý do (Persona) |
| :--- | :--- | :--- |
| **Pattern** | *Daily micro-habit loop*: Home (tiến độ + tiếp tục 5p) → **1 câu / 1 màn hình** → phản hồi tức thì → thưởng XP/Streak | P01 nhanh chán (69,4%), P02 chỉ có 10–15 phút |
| **Style** | **Soft Bento**: thẻ bo lớn, nền phẳng, viền mảnh + bóng rất nhẹ. Tránh glassmorphism và gradient nặng | P02 đọc ngoài trời / trên xe, cần tương phản cao |
| **Colors** | **Teal** (bình tĩnh, tin cậy) làm chủ đạo; **Violet** riêng cho AI Tutor; **Cam / Vàng / San hô** cho gamification; đỏ dịu cho báo sai | Thay Indigo gốc để AI Tutor (violet) tách biệt hẳn khỏi màu thương hiệu |
| **Typography** | **Be Vietnam Pro** (font thiết kế cho tiếng Việt), `lineHeight ≈ 1.4–1.5` để dấu thanh không bị chạm dòng | Nội dung chính là tiếng Việt + tiếng Anh |
| **Effects** | Press scale `0.98`, sheet trượt lên `200ms`, mic pulse khi thu âm. **Tắt hết khi hệ thống bật Reduce Motion** | P01 sợ nói sai: phản hồi nhẹ nhàng, không chói |
| **Anti-patterns** | Xem mục 7 | — |

---

## 3. Bảng Color Tokens (Light & Dark)

Tỷ lệ tương phản ghi là **ước tính gần đúng** so với nền đi kèm; hãy kiểm tra lại bằng công cụ contrast trước khi release.

| Nhóm | Token | Light | Dark | Dùng cho | Tương phản (ước tính, Light) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Brand** | `primary` | `#0F766E` | `#2DD4BF` | CTA chính, thanh tiến độ | ≈ 5,5 : 1 trên `surface` |
| **Brand** | `primaryPressed` | `#115E59` | `#14B8A6` | Trạng thái nhấn | — |
| **Brand** | `primarySurface` | `#F0FDFA` | `#042F2E` | Nền đáp án / thẻ đang chọn | — |
| **AI Tutor** | `aiPrimary` | `#6D28D9` | `#A78BFA` | Nút "Giải thích lỗi sai bằng AI", mic | ≈ 7 : 1 |
| **AI Tutor** | `aiAccent` | `#0891B2` | `#22D3EE` | Viền khung giải thích, huy hiệu AI | Chỉ dùng cho viền / icon |
| **AI Tutor** | `aiSurface` | `#F5F3FF` | `#2E1065` | Nền hộp giải thích tiếng Việt | — |
| **Gamification** | `streak` | `#C2410C` | `#FB923C` | Ngọn lửa Streak (51,9% động lực) | ≈ 5,2 : 1 |
| **Gamification** | `xpGold` | `#A16207` | `#FACC15` | Điểm XP (37,0% động lực) | ≈ 4,9 : 1 |
| **Gamification** | `heartCoral` | `#E11D48` | `#FB7185` | Tim (Hearts) | ≈ 4,7 : 1 |
| **Semantic** | `success` / `successSurface` | `#15803D` / `#F0FDF4` | `#4ADE80` / `#052E16` | Đúng, phát âm đạt (≥ 70%) | ≈ 4,9 : 1 |
| **Semantic** | `error` / `errorSurface` | `#B91C1C` / `#FEF2F2` | `#F87171` / `#450A0A` | Báo sai dịu, từ phát âm sai | ≈ 5,9 : 1 |
| **Semantic** | `warning` / `warningSurface` | `#B45309` / `#FFFBEB` | `#FBBF24` / `#451A03` | Chế độ "Tạm ẩn Nghe/Nói 15p" | ≈ 4,7 : 1 |
| **Neutral** | `background` | `#FAFAF9` | `#0C0A09` | Nền màn hình | — |
| **Neutral** | `surface` | `#FFFFFF` | `#1C1917` | Card, Sheet, Input | — |
| **Neutral** | `border` | `#E7E5E4` | `#44403C` | Viền, đường phân cách | — |
| **Neutral** | `textPrimary` | `#1C1917` | `#FAFAF9` | Văn bản chính | ≈ 16 : 1 |
| **Neutral** | `textSecondary` | `#57534E` | `#A8A29E` | Nhãn phụ, gợi ý | ≈ 7 : 1 |
| **On-color** | `textOnPrimary` | `#FFFFFF` | `#042F2E` | Chữ trên nút `primary` | Dark mode cần chữ **tối** vì nền teal sáng |
| **On-color** | `textOnAi` | `#FFFFFF` | `#2E1065` | Chữ trên nút AI | như trên |
| **On-color** | `textOnError` | `#FFFFFF` | `#450A0A` | Chữ trên nút `danger` | như trên |

---

## 4. Visual Description (dán cho agent, tinh thần `DESIGN.md`)

```markdown
# LingoCraft AI — Visual Description

## Atmosphere
Bình tĩnh, khích lệ, không phán xét. Nền ấm trung tính (stone), một màu thương hiệu teal,
AI Tutor luôn là violet để người học nhận ra "đây là lời giải thích của AI".

## Color roles
- primary (teal): hành động chính duy nhất trên mỗi màn hình.
- aiPrimary (violet): mọi thứ do AI tạo ra (giải thích, chấm phát âm).
- streak / xpGold / heartCoral: chỉ dùng cho chỉ số gamification, không dùng làm màu nút.
- error là đỏ dịu trên nền errorSurface; không bao giờ dùng đỏ đặc cho nút "Tiếp tục".

## Typography
Be Vietnam Pro. Câu hỏi 22/32 đậm; lời giải thích AI 15/23, tối đa 4 dòng; nút 16/22.

## Shape & depth
Bento card bo 20, viền 1px + bóng rất nhẹ. Sheet phản hồi bo 20 hai góc trên.

## Motion
Nhấn nút: scale 0.98 trong 120ms. Sheet: trượt lên 200ms. Mic: vòng pulse 1.2s khi đang thu.
Reduce Motion bật → bỏ pulse và trượt, chỉ đổi màu / hiện tức thì.

## Touch & layout
Mọi vùng chạm ≥ 48dp. Lề màn hình 16. Lưới 8pt. Một CTA chính ở footer, đặt vừa tầm ngón cái.
```

---

## 5. Typography, Spacing, Motion & Elevation

### 5.1 Typography Scale (Be Vietnam Pro)

| Token | `fontSize` | `lineHeight` | Font weight (family) | Áp dụng |
| :--- | :---: | :---: | :--- | :--- |
| `headingLg` | 24 | 34 | Bold | Tiêu đề màn hình, hoàn thành bài |
| `questionTitle` | 22 | 32 | Bold | Câu hỏi / câu thoại luyện nói |
| `headingMd` | 18 | 26 | SemiBold | Tiêu đề thẻ, sheet |
| `body` | 16 | 24 | Regular | Đáp án, input |
| `aiBody` | 15 | 23 | Regular | Giải thích AI tiếng Việt (≤ 4 dòng) |
| `buttonLabel` | 16 | 22 | SemiBold | Nhãn nút |
| `caption` | 14 | 20 | Medium | Chỉ số Streak, XP, Hearts |
| `micro` | 12 | 18 | Medium | Chỉ dùng cho `2/6`; **không** dùng cho nội dung cần đọc |

### 5.2 Spacing, Radius, Layout, Motion

| Nhóm | Token | Giá trị |
| :--- | :--- | :--- |
| **Spacing** | `xs` / `sm` / `md` / `lg` / `xl` | `4` / `8` / `16` / `24` / `32` |
| **Radius** | `sm` / `md` / `lg` / `xl` / `full` | `8` / `12` / `20` / `28` / `9999` |
| **Layout** | `minTouchTarget` / `screenPadding` | `48` / `16` |
| **Motion** | `fast` / `base` / `slow` / `pressScale` | `120ms` / `200ms` / `320ms` / `0.98` |
| **Elevation** | `card` / `sheet` | bóng nhẹ (`opacity 0.06`) / bóng sheet (`opacity 0.12`) |

---

## 6. Mã nguồn Theme (React Native TypeScript)

### 6.1 `src/theme/tokens.ts`

```typescript
// src/theme/tokens.ts — Single Source of Truth (v2)
// Font: cài @expo-google-fonts/be-vietnam-pro rồi load 4 weight bên dưới trước khi render.

export const lightColors = {
  primary: '#0F766E',
  primaryPressed: '#115E59',
  primarySurface: '#F0FDFA',
  aiPrimary: '#6D28D9',
  aiAccent: '#0891B2',
  aiSurface: '#F5F3FF',
  streak: '#C2410C',
  xpGold: '#A16207',
  heartCoral: '#E11D48',
  success: '#15803D',
  successSurface: '#F0FDF4',
  error: '#B91C1C',
  errorSurface: '#FEF2F2',
  warning: '#B45309',
  warningSurface: '#FFFBEB',
  background: '#FAFAF9',
  surface: '#FFFFFF',
  border: '#E7E5E4',
  textPrimary: '#1C1917',
  textSecondary: '#57534E',
  textOnPrimary: '#FFFFFF',
  textOnAi: '#FFFFFF',
  textOnError: '#FFFFFF',
};

// Không dùng `as const` ở trên để darkColors gán được giá trị khác mà vẫn type-safe.
export type ColorTokens = typeof lightColors;

export const darkColors: ColorTokens = {
  primary: '#2DD4BF',
  primaryPressed: '#14B8A6',
  primarySurface: '#042F2E',
  aiPrimary: '#A78BFA',
  aiAccent: '#22D3EE',
  aiSurface: '#2E1065',
  streak: '#FB923C',
  xpGold: '#FACC15',
  heartCoral: '#FB7185',
  success: '#4ADE80',
  successSurface: '#052E16',
  error: '#F87171',
  errorSurface: '#450A0A',
  warning: '#FBBF24',
  warningSurface: '#451A03',
  background: '#0C0A09',
  surface: '#1C1917',
  border: '#44403C',
  textPrimary: '#FAFAF9',
  textSecondary: '#A8A29E',
  textOnPrimary: '#042F2E',
  textOnAi: '#2E1065',
  textOnError: '#450A0A',
};

export const fontFamily = {
  regular: 'BeVietnamPro_400Regular',
  medium: 'BeVietnamPro_500Medium',
  semibold: 'BeVietnamPro_600SemiBold',
  bold: 'BeVietnamPro_700Bold',
} as const;

// Với font tùy chỉnh, chọn weight bằng fontFamily (không dùng fontWeight) để Android hiển thị đúng.
export const typography = {
  headingLg: { fontFamily: fontFamily.bold, fontSize: 24, lineHeight: 34 },
  questionTitle: { fontFamily: fontFamily.bold, fontSize: 22, lineHeight: 32 },
  headingMd: { fontFamily: fontFamily.semibold, fontSize: 18, lineHeight: 26 },
  body: { fontFamily: fontFamily.regular, fontSize: 16, lineHeight: 24 },
  aiBody: { fontFamily: fontFamily.regular, fontSize: 15, lineHeight: 23 },
  buttonLabel: { fontFamily: fontFamily.semibold, fontSize: 16, lineHeight: 22 },
  caption: { fontFamily: fontFamily.medium, fontSize: 14, lineHeight: 20 },
  micro: { fontFamily: fontFamily.medium, fontSize: 12, lineHeight: 18 },
};

export const spacing = { xs: 4, sm: 8, md: 16, lg: 24, xl: 32 } as const;
export const radius = { sm: 8, md: 12, lg: 20, xl: 28, full: 9999 } as const;
export const layout = { minTouchTarget: 48, screenPadding: 16 } as const;
export const motion = { fast: 120, base: 200, slow: 320, pressScale: 0.98 } as const;

export const elevation = {
  card: {
    shadowColor: '#1C1917',
    shadowOpacity: 0.06,
    shadowRadius: 12,
    shadowOffset: { width: 0, height: 4 },
    elevation: 2,
  },
  sheet: {
    shadowColor: '#1C1917',
    shadowOpacity: 0.12,
    shadowRadius: 20,
    shadowOffset: { width: 0, height: -6 },
    elevation: 8,
  },
} as const;

export type ThemeMode = 'light' | 'dark';

export const createTheme = (mode: ThemeMode = 'light') => ({
  mode,
  colors: mode === 'dark' ? darkColors : lightColors,
  typography,
  spacing,
  radius,
  layout,
  motion,
  elevation,
});

export type AppTheme = ReturnType<typeof createTheme>;
```

### 6.2 `src/theme/ThemeProvider.tsx` — Dark Mode chạy thật theo hệ thống

```tsx
// src/theme/ThemeProvider.tsx
import React, { createContext, useContext, useMemo } from 'react';
import { useColorScheme } from 'react-native';
import { AppTheme, createTheme, ThemeMode } from './tokens';

const ThemeContext = createContext<AppTheme>(createTheme('light'));

export const ThemeProvider: React.FC<{ forcedMode?: ThemeMode; children: React.ReactNode }> = ({
  forcedMode,
  children,
}) => {
  const scheme = useColorScheme();
  const mode: ThemeMode = forcedMode ?? (scheme === 'dark' ? 'dark' : 'light');
  const theme = useMemo(() => createTheme(mode), [mode]);
  return <ThemeContext.Provider value={theme}>{children}</ThemeContext.Provider>;
};

export const useTheme = (): AppTheme => useContext(ThemeContext);
```

---

## 7. Anti-patterns bị cấm (rút từ UI UX Pro Max & taste-skill)

| # | Anti-pattern | Thay bằng |
| :-: | :--- | :--- |
| 1 | Dùng **emoji làm icon** (🔥 ❤️ 🔊 🎙️) — hiển thị khác nhau giữa iOS/Android, không đổi màu theo theme | Bộ icon vector (`lucide-react-native`) qua `AppIcon` |
| 2 | **Chỉ dùng màu** để báo đúng/sai | Màu + icon + chữ (✓ / ✕ và nhãn tiếng Việt) |
| 3 | Vùng chạm nhỏ hơn 48dp (chip tắt Nghe/Nói ở bản gốc) | `minHeight: 48` cho mọi phần tử bấm được |
| 4 | Cắt cụt lời giải thích AI bằng `numberOfLines` | Giới hạn độ dài nội dung (≤ 240 ký tự), không cắt giữa câu |
| 5 | Nút "Tiếp tục" **đỏ đặc** sau khi sai (tạo cảm giác bị phạt) | Nút `primary`; chỉ khung phản hồi mang màu lỗi dịu |
| 6 | Animation lặp vô hạn không thể tắt | Tôn trọng Reduce Motion |
| 7 | Chữ chính dưới 14px hoặc nền xám nhạt chữ xám nhạt | Dùng bảng Typography và cặp màu ở mục 3 |
| 8 | Hardcode màu / số liệu spacing trong màn hình | Chỉ dùng `useTheme()` |

---

## 8. Pre-delivery Checklist (chạy trước khi bàn giao màn hình)

- [ ] Không còn mã màu hex hay số `padding/margin` cố định trong file màn hình (chỉ token).
- [ ] Mọi phần tử bấm được có `minHeight ≥ 48`, có `accessibilityRole` và `accessibilityLabel`.
- [ ] Thông tin đúng/sai luôn có **icon + chữ**, không chỉ màu.
- [ ] Đã xem cả **Light và Dark**; chữ trên nút dùng token `textOn*`.
- [ ] Tăng cỡ chữ hệ thống lên 130% vẫn không vỡ bố cục.
- [ ] Bật Reduce Motion: không còn pulse / trượt.
- [ ] Mỗi màn hình chỉ có **1 CTA chính**; mỗi màn hình bài học chỉ có **1 câu hỏi**.
- [ ] Có đủ trạng thái: `loading`, `error` (kèm nút thử lại), `empty`, `offline` cho phần gọi AI.
- [ ] Lời giải thích AI ≤ 4 dòng, cỡ `15px`, bằng tiếng Việt.

---

## 9. Khác biệt so với `design-tokens.md` (v1)

| Hạng mục | v1 | v2 |
| :--- | :--- | :--- |
| Màu thương hiệu | Indigo `#4F46E5` | Teal `#0F766E`; AI giữ violet nên tách biệt rõ hơn |
| Nền | Slate lạnh | Stone ấm (`#FAFAF9`), dịu mắt hơn |
| Icon | Emoji | Icon vector qua `AppIcon` |
| Font | Mặc định hệ thống | Be Vietnam Pro, `lineHeight` ~1,45 |
| Dark Mode | Khai báo nhưng `tokens = createTheme('light')` cố định nên **không bao giờ bật** | `ThemeProvider` + `useTheme()` theo hệ thống |
| Kiểu dữ liệu | `darkColors: typeof lightColors` với `as const` → TypeScript báo lỗi vì khác literal | Bỏ `as const`, dùng `ColorTokens` |
| Chữ trên nút | Luôn `#FFFFFF` | `textOnPrimary/Ai/Error` đổi theo mode (đảm bảo tương phản ở Dark) |
| Màu Streak/XP/Hearts | Cam/vàng sáng, tương phản thấp trên nền trắng | Đậm hơn ở Light để đủ ≈ 4,5 : 1 |
| Motion & Elevation | Không có | Có `motion` và `elevation` tokens |
| Kiểm soát chất lượng | Không | Anti-patterns + Pre-delivery Checklist |
