# Yolo Mode - Chỉ dùng Claude Code

> Cho người lười, không muốn copy qua lại

```
┌─────────────────────────────────────────────────────────────┐
│                        USER                                  │
│              "Làm web cho tiệm nail đi"                      │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                      CLAUDE CODE                             │
│  • Hỏi clarify (như PM)                                      │
│  • Tự code luôn (như dev)                                    │
│  • Chạy server                                               │
│  • Fix khi user báo lỗi                                      │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    USER xem & feedback                       │
│  • Mở localhost:3000                                         │
│  • "Đổi màu hồng đi" / "Thêm form liên hệ"                  │
└─────────────────────────────────────────────────────────────┘
                              │
                         Loop ↺
```

---

## Setup (một lần)

### Bước 1: Cài Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### Bước 2: Tạo file cấu hình

Mở Terminal, chạy:

```bash
mkdir -p ~/.claude
cat > ~/.claude/CLAUDE.md << 'EOF'
# Non-Tech Mode

Khi user mô tả website họ muốn:

1. **Hỏi clarify trước** (3-5 câu max):
   - Màu sắc / phong cách?
   - Những section nào cần có?
   - Có form liên hệ không?
   - Có tham khảo website nào không?

2. **Sau khi hiểu rõ, tự làm luôn** - không hỏi thêm

3. **Output đơn giản**:
   - Không dùng thuật ngữ tech
   - Nói "nút bấm" không nói "button"
   - Nói "trang" không nói "page/route"

4. **Luôn chạy dev server** sau khi tạo xong

5. **Nhắc user mở browser** xem kết quả

## Khi user gửi ảnh/screenshot:
- Nhìn và hiểu vấn đề
- Tự fix luôn, không hỏi lại

## Khi user nói "xong" hoặc "ok":
- Hỏi có muốn đưa lên mạng không
- Nếu có thì hướng dẫn deploy Vercel

## Format output:

```
✅ Đã làm xong!

Mở trình duyệt vào: http://localhost:3000

Có gì muốn sửa thì nói mình nhé!
```
EOF
```

### Bước 3: Tạo thư mục làm việc

```bash
mkdir -p ~/my-websites
```

---

## Sử dụng hàng ngày

### Bắt đầu project mới:

```bash
cd ~/my-websites
mkdir ten-project && cd ten-project
claude
```

### Chat tự nhiên:

```
> Làm cho tui web tiệm nail đi

Claude: Để mình hỏi thêm chút:
- Màu sắc bạn thích? (hồng pastel, trắng sang, màu khác?)
- Cần những section nào? (bảng giá, gallery, đặt lịch?)
- Có logo/ảnh sẵn không?

> Hồng pastel, có bảng giá với gallery, chưa có logo

Claude: OK mình làm luôn nhé...
[tạo code, chạy server]

✅ Đã làm xong!
Mở trình duyệt vào: http://localhost:3000
Có gì muốn sửa thì nói mình nhé!

> Chữ hơi nhỏ, với đổi font đẹp hơn đi

Claude: [tự fix luôn]

✅ Đã sửa! Refresh trang xem thử.

> Ok đẹp rồi, đưa lên mạng đi

Claude: Mình sẽ đưa lên Vercel (free). Làm theo mấy bước này...
```

---

## So sánh 2 mode

| | Duo Mode | Yolo Mode |
|---|----------|-----------|
| **Số AI dùng** | 2 (ChatGPT + Claude Code) | 1 (Claude Code) |
| **Copy paste** | Nhiều | Không |
| **Gửi ảnh lỗi** | Qua ChatGPT | Kéo thả vào terminal* |
| **Chi phí** | $40/tháng | $20/tháng |
| **Độ tiện** | Mệt hơn | Nhanh hơn |

*Claude Code desktop app hỗ trợ kéo thả ảnh

---

## Khi nào dùng mode nào?

**Dùng Yolo Mode khi:**
- Muốn nhanh gọn, một chỗ
- Quen dùng terminal
- Tiết kiệm tiền ($20 vs $40)

**Dùng Duo Mode khi:**
- Thích UI chat đẹp của ChatGPT/Gemini
- Muốn gửi ảnh từ điện thoại dễ hơn
- Cần AI giải thích nhiều hơn

---

## Tips

1. **Nói tự nhiên** - Claude Code hiểu tiếng Việt tốt
2. **Mô tả cụ thể** - "màu hồng pastel" tốt hơn "màu đẹp"
3. **Feedback liên tục** - sửa từng thứ một, đừng gom lại
4. **Đừng ngại hỏi** - "cái này là gì?" Claude Code sẽ giải thích

---

## Troubleshooting

### "Không thấy localhost:3000"
```
Server chưa chạy đi
```
→ Claude Code sẽ tự chạy lại

### "Trang trắng không có gì"
```
Refresh thử, vẫn trắng thì báo mình
```
→ Claude Code sẽ check lỗi

### "Muốn dừng lại"
Gõ `/exit` hoặc bấm `Ctrl+C` 2 lần
