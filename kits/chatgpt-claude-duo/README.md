# ChatGPT + Claude Code Duo Kit

> Workflow cho người không biết code tạo website

```
┌─────────────────────────────────────────────────────────────┐
│                        USER (Non-tech)                       │
│                    "Tôi muốn web bán hàng"                  │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                     CHATGPT (PM/Chủ thầu)                   │
│  • Hỏi clarify: màu gì? bán gì? có form không?              │
│  • Ra lệnh: /taw Tạo landing page bán giày...               │
└─────────────────────────────────────────────────────────────┘
                              │
                    Copy lệnh ▼
┌─────────────────────────────────────────────────────────────┐
│                  CLAUDE CODE (Thợ thi công)                  │
│  • Tạo code Next.js + Tailwind                              │
│  • Chạy dev server                                          │
│  • Output: "Xong! Mở localhost:3000 xem"                    │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                      USER xem kết quả                        │
│  • Mở browser → localhost:3000                              │
│  • Test các nút, form                                       │
│  • Chụp screenshot nếu cần fix                              │
└─────────────────────────────────────────────────────────────┘
                              │
              Screenshot/feedback ▼
┌─────────────────────────────────────────────────────────────┐
│                        CHATGPT                               │
│  • Nhìn screenshot → hiểu vấn đề                            │
│  • Ra lệnh fix: /taw Fix nút Gửi không hoạt động            │
└─────────────────────────────────────────────────────────────┘
                              │
                         Loop ↺
```

---

## Files trong kit này

| File | Mục đích |
|------|----------|
| `chatgpt-pm.md` | Prompt paste vào ChatGPT |
| `claude-code-setup.md` | Hướng dẫn setup Claude Code |
| `README.md` | File này |

---

## Quick Start

### 1. Setup Claude Code (một lần)

Xem `claude-code-setup.md`

### 2. Setup ChatGPT (mỗi session)

Copy toàn bộ nội dung `chatgpt-pm.md` → paste vào ChatGPT

### 3. Bắt đầu làm

1. Chat với ChatGPT: "Tôi muốn làm web cho tiệm nail"
2. ChatGPT hỏi thêm, rồi đưa ra lệnh
3. Copy lệnh vào Claude Code
4. Mở browser xem kết quả
5. Chụp màn hình gửi ChatGPT nếu cần fix
6. Lặp lại đến khi hài lòng

---

## Yêu cầu

- **ChatGPT Plus** ($20/tháng) - cần GPT-4o để đọc ảnh
- **Claude Pro** ($20/tháng) - để dùng Claude Code
- **Node.js** - [Download tại đây](https://nodejs.org)
- **Máy tính** - Mac, Windows, hoặc Linux

---

## FAQ

**Q: Tại sao cần cả 2 AI?**

A: ChatGPT giỏi nói chuyện, hiểu ý, nhìn ảnh. Claude Code giỏi code thật, tạo file, chạy server. Kết hợp = best of both.

**Q: Tốn bao nhiêu tiền/tháng?**

A: ~$40/tháng (ChatGPT Plus + Claude Pro). Rẻ hơn thuê dev rất nhiều.

**Q: Có thể dùng ChatGPT free không?**

A: Được nhưng không đọc được ảnh. Phải mô tả lỗi bằng text.

**Q: Website làm xong có thể đưa lên mạng không?**

A: Có! Dùng lệnh `/taw deploy` - Claude Code sẽ hướng dẫn từng bước.

---

## Roadmap

- [ ] Video hướng dẫn tiếng Việt
- [ ] Template cho các loại web phổ biến
- [ ] Hỗ trợ Supabase cho form/database
- [ ] One-click deploy lên Vercel
