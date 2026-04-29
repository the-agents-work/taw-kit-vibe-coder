# Hướng dẫn tạo Supabase (cho ChatGPT gửi user)

> ChatGPT sẽ gửi từng phần của hướng dẫn này khi user cần database

---

## Khi nào cần Supabase?

- Form đăng ký/liên hệ **cần lưu lại** thông tin
- Trang có **đăng nhập** user
- **Danh sách** sản phẩm/bài viết có thể thêm/sửa/xóa
- Bất kỳ data nào cần **lưu trữ online**

---

## Hướng dẫn từng bước (ChatGPT copy gửi user)

### Phần 1: Tạo tài khoản

```
📱 TẠO TÀI KHOẢN SUPABASE (Miễn phí)

Bước 1: Mở trình duyệt, vào: supabase.com

Bước 2: Bấm nút "Start your project" (màu xanh lá)

Bước 3: Đăng nhập bằng GitHub hoặc Google
         (Dùng Google cho nhanh nếu chưa có GitHub)

Bước 4: Bấm "New Project"

Bước 5: Điền thông tin:
         • Name: đặt tên gì cũng được (vd: my-website)
         • Database Password: đặt mật khẩu (GHI LẠI vào đâu đó!)
         • Region: chọn Singapore (gần Việt Nam nhất)

Bước 6: Bấm "Create new project"

Bước 7: Đợi 1-2 phút để Supabase tạo xong

Xong bước này báo mình nhé!
```

### Phần 2: Lấy API Keys

```
🔑 LẤY 2 CÁI KEY (Quan trọng!)

Bước 1: Trong Supabase dashboard, nhìn sidebar bên trái

Bước 2: Bấm vào biểu tượng ⚙️ "Project Settings" (gần cuối)

Bước 3: Bấm "API" trong menu

Bước 4: Bạn sẽ thấy 2 thứ cần copy:

         📍 Project URL: (dạng https://xxxxx.supabase.co)
         
         📍 anon public key: (dãy chữ dài bắt đầu bằng "eyJ...")

Bước 5: Copy từng cái và gửi cho mình theo format:

         URL: [paste vào đây]
         KEY: [paste vào đây]

⚠️ Đây là key PUBLIC, an toàn để share. 
   KHÔNG share "service_role key" (cái bên dưới) nhé!
```

### Phần 3: Xác nhận

```
✅ KIỂM TRA

Bạn đã gửi mình 2 thứ:
• URL: https://xxxxx.supabase.co ✓
• KEY: eyJhbGc... (dài ~200 ký tự) ✓

Hoàn hảo! Giờ mình sẽ tạo lệnh cho Claude Code.
```

---

## Template lệnh có Supabase

Khi đã có keys, ChatGPT tạo lệnh dạng:

```
📋 COPY LỆNH NÀY VÀO CLAUDE CODE:

/taw Tạo form đăng ký nhận tin với Supabase

SUPABASE_URL=https://xxxxx.supabase.co
SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

Cần:
- Form có: Họ tên, Email, Số điện thoại
- Khi submit: lưu vào Supabase table "subscribers"
- Hiện thông báo "Đăng ký thành công!"
```

---

## Xem data trong Supabase

Hướng dẫn user xem data đã lưu:

```
📊 XEM DATA ĐÃ LƯU

Bước 1: Vào supabase.com, đăng nhập

Bước 2: Chọn project của bạn

Bước 3: Bấm "Table Editor" ở sidebar trái

Bước 4: Chọn table (vd: "subscribers")

Bước 5: Bạn sẽ thấy data dạng bảng như Excel!

Có thể:
• Xem tất cả data
• Thêm row mới bằng tay
• Sửa/xóa row
• Export ra CSV
```

---

## Troubleshooting

### "Không thấy data sau khi submit form"

```
Có thể do:
1. Form chưa kết nối đúng - chụp màn hình Console (F12) gửi mình
2. Table chưa được tạo - vào Table Editor kiểm tra
3. Key sai - kiểm tra lại trong Project Settings > API
```

### "Lỗi permission denied"

```
Cần bật Row Level Security. Gửi mình lỗi cụ thể để tạo lệnh fix.
```

---

## Notes cho ChatGPT

1. **Chỉ hướng dẫn Supabase khi thực sự cần** - đừng suggest nếu user chỉ làm static landing page

2. **Giải thích đơn giản** - Supabase = "database online, như bảng Excel trên mạng"

3. **Chỉ lấy anon key** - KHÔNG bao giờ hỏi service_role key

4. **Nhắc user lưu password** - họ sẽ cần nếu muốn access database trực tiếp

5. **Table Editor là bạn** - khuyến khích user dùng UI thay vì SQL
