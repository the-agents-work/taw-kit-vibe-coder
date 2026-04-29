# Claude Code Setup Guide

> Hướng dẫn setup Claude Code cho workflow ChatGPT + Claude Code

---

## Bước 1: Cài Claude Code

Mở Terminal và chạy:

```bash
npm install -g @anthropic-ai/claude-code
```

## Bước 2: Đăng nhập

```bash
claude
```

Làm theo hướng dẫn đăng nhập tài khoản Anthropic.

## Bước 3: Tạo thư mục làm việc

```bash
mkdir ~/my-websites
cd ~/my-websites
```

## Bước 4: Thêm cấu hình cho workflow

Tạo file `~/.claude/CLAUDE.md` với nội dung:

```markdown
# Non-Tech Workflow Mode

Khi nhận lệnh từ user (thường bắt đầu bằng `/taw`):

1. **Thực hiện task** - code, tạo file, chạy server
2. **Output đơn giản** - không dùng thuật ngữ tech
3. **Luôn chạy dev server** sau khi tạo/sửa code
4. **Nhắc user mở browser** xem kết quả

## Format output sau mỗi task:

```
✅ XONG!

Đã làm:
- [Mô tả ngắn việc 1]
- [Mô tả ngắn việc 2]

👉 Mở trình duyệt vào: http://localhost:3000

Nếu OK thì báo "xong" hoặc chụp màn hình gửi ChatGPT để tiếp tục.
Nếu có lỗi thì chụp màn hình gửi ChatGPT để fix.
```

## Quy tắc:

- Không hỏi clarify - ChatGPT đã clarify rồi
- Không suggest thêm feature - làm đúng yêu cầu
- Lỗi thì tự fix, không hỏi user
- Giữ output ngắn gọn
```

---

## Sử dụng hàng ngày

### Bắt đầu session mới:

```bash
cd ~/my-websites
claude
```

### Khi nhận lệnh từ ChatGPT:

1. Copy lệnh từ ChatGPT
2. Paste vào Claude Code
3. Đợi chạy xong
4. Mở browser xem kết quả
5. Chụp screenshot gửi lại ChatGPT (nếu cần fix)

### Các lệnh hay dùng:

| Việc cần làm | Gõ trong Claude Code |
|--------------|---------------------|
| Xem web | Mở browser → `localhost:3000` |
| Dừng server | `Ctrl + C` trong terminal |
| Thoát Claude | Gõ `/exit` hoặc `Ctrl + C` 2 lần |

---

## Troubleshooting

### "Port 3000 đang được dùng"
```bash
# Trong Claude Code, gõ:
Tắt process đang chạy ở port 3000 và chạy lại server
```

### "Không thấy thay đổi"
- Refresh browser (Ctrl + R hoặc Cmd + R)
- Hoặc hard refresh (Ctrl + Shift + R)

### "Lỗi đỏ trong terminal"
- Chụp màn hình lỗi
- Gửi cho ChatGPT để phân tích

---

## Tips

1. **Mỗi project một thư mục** - `cd ~/my-websites/cafe-saigon`
2. **Đừng đóng terminal** - để server chạy liên tục
3. **Chụp full màn hình** - để ChatGPT thấy đủ context
4. **Kiên nhẫn** - đợi Claude Code chạy xong mới test
