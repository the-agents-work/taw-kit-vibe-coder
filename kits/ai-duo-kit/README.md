# AI Duo Kit

> Workflow cho người không biết code tạo website

## Chọn mode phù hợp

| Mode | Mô tả | Chi phí |
|------|-------|---------|
| **[Yolo Mode](yolo-mode.md)** | Chỉ dùng Claude Code, không copy paste | $20/tháng |
| **[Duo Mode](#duo-mode)** | ChatGPT/Gemini + Claude Code | $40/tháng |

---

## Duo Mode

```
┌─────────────────────────────────────────────────────────────┐
│                        USER (Non-tech)                       │
│                    "Tôi muốn web bán hàng"                   │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│              AI PM (ChatGPT / Gemini / Claude)               │
│  • Hỏi clarify: màu gì? bán gì? có form không?               │
│  • Ra task: "Tạo landing page bán giày với..."               │
└─────────────────────────────────────────────────────────────┘
                              │
                    Copy task ▼
┌─────────────────────────────────────────────────────────────┐
│                  CLAUDE CODE (Thợ thi công)                  │
│  • Tạo code Next.js + Tailwind                               │
│  • Chạy dev server                                           │
│  • Output: "Xong! Mở localhost:3000 xem"                     │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                      USER xem kết quả                        │
│  • Mở browser → localhost:3000                               │
│  • Test các nút, form                                        │
│  • Chụp screenshot nếu cần fix                               │
└─────────────────────────────────────────────────────────────┘
                              │
              Screenshot/feedback ▼
┌─────────────────────────────────────────────────────────────┐
│                          AI PM                               │
│  • Nhìn screenshot → hiểu vấn đề                             │
│  • Ra task fix: "Fix nút Gửi không hoạt động..."             │
└─────────────────────────────────────────────────────────────┘
                              │
                         Loop ↺
```

---

## Tại sao dùng 2 AI?

| AI | Giỏi cái gì |
|----|-------------|
| **ChatGPT/Gemini** | Nói chuyện, hỏi clarify, nhìn ảnh, planning |
| **Claude Code** | Viết code thật, tạo file, chạy server, deploy |

Kết hợp = non-tech user chỉ cần mô tả, không cần biết code!

---

## Files trong kit

| File | Mục đích |
|------|----------|
| `yolo-mode.md` | **Mode 1 AI** - chỉ Claude Code, không copy paste |
| `pm-prompt.md` | Prompt cho AI PM (ChatGPT/Gemini) |
| `claude-code-setup.md` | Hướng dẫn setup Claude Code |
| `supabase-guide.md` | Hướng dẫn database (khi cần) |

---

## Quick Start

### 1. Setup Claude Code (một lần)

Xem `claude-code-setup.md` - cài đặt khoảng 5 phút

### 2. Setup AI PM (mỗi session)

Copy nội dung `pm-prompt.md` → paste vào ChatGPT hoặc Gemini

### 3. Bắt đầu làm

1. Chat với AI PM: "Tôi muốn làm web cho tiệm nail"
2. AI PM hỏi thêm, rồi đưa ra task
3. Copy task vào Claude Code
4. Mở browser xem kết quả
5. Chụp màn hình gửi AI PM nếu cần fix
6. Lặp lại đến khi hài lòng

---

## Chi phí

| Option | Chi phí/tháng | Ghi chú |
|--------|---------------|---------|
| ChatGPT Free + Claude Pro | $20 | ChatGPT free không đọc ảnh |
| ChatGPT Plus + Claude Pro | $40 | Recommended |
| Gemini + Claude Pro | $20-40 | Gemini có free tier tốt |

Vẫn rẻ hơn thuê dev ($500-2000+/project)

---

## FAQ

**Q: Dùng Gemini thay ChatGPT được không?**

A: Được! Prompt trong `pm-prompt.md` hoạt động với cả hai.

**Q: Tại sao không dùng Claude cho cả 2 việc?**

A: Claude Code chạy trong terminal, không có UI chat đẹp để gửi ảnh. ChatGPT/Gemini có app mobile, dễ chụp màn hình gửi.

**Q: Website làm xong có thể đưa lên mạng không?**

A: Có! Bảo AI PM "muốn đưa web lên mạng" → nó sẽ ra task deploy.

**Q: Cần biết tiếng Anh không?**

A: Không! Mọi thứ hoạt động với tiếng Việt.

---

## Ví dụ thực tế

**User:** "Tôi muốn làm web portfolio cho mình, mình là photographer"

**AI PM:** "Tuyệt! Để mình hỏi thêm:
- Bạn có bao nhiêu ảnh muốn show?
- Màu sắc bạn thích? (tối/sáng/màu sắc)
- Có thông tin liên hệ không?"

**User:** "Khoảng 20 ảnh, thích tone tối minimalist, có form liên hệ"

**AI PM:** 
```
✅ Hiểu rồi!

📋 COPY VÀO CLAUDE CODE:

Tạo portfolio website cho photographer với:
- Hero section fullscreen với ảnh nổi bật
- Gallery grid hiển thị 20 ảnh (dùng placeholder trước)
- About section ngắn gọn
- Form liên hệ

Phong cách: dark theme, minimalist, typography sans-serif

---
Sau khi xong, mở localhost:3000 xem nhé!
```

---

## Yêu cầu hệ thống

- **Node.js** - [Download tại đây](https://nodejs.org)
- **Máy tính** - Mac, Windows, hoặc Linux
- **Trình duyệt** - Chrome, Firefox, Safari, Edge

---

## Roadmap

- [ ] Video hướng dẫn tiếng Việt
- [ ] Template cho các loại web phổ biến
- [ ] Hỗ trợ mobile app với Expo
