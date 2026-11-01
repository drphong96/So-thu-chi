# Bật đồng bộ điện thoại và laptop (Firebase, miễn phí)

Sau khi làm xong, mọi khoản thu chi ghi trên máy nào cũng hiện trên máy kia sau vài giây. Sổ được lưu thêm trên tài khoản Google của bạn nên mất máy vẫn còn dữ liệu. Trang vẫn ghi được khi mất mạng và tự gộp lại khi có mạng.

Gói Spark của Firebase miễn phí, không cần thẻ thanh toán. Mức miễn phí rộng hơn nhiều so với một sổ chi tiêu cá nhân.

## Bước 1. Tạo dự án
1. Vào https://console.firebase.google.com, đăng nhập bằng tài khoản Google.
2. Bấm "Create a project", đặt tên (ví dụ `so-thu-chi`), tắt Google Analytics, bấm Create.

## Bước 2. Bật đăng nhập Google
1. Menu trái: Build > Authentication > Get started.
2. Tab Sign-in method > Google > Enable, chọn email hỗ trợ, bấm Save.

## Bước 3. Tạo cơ sở dữ liệu
1. Menu trái: Build > Firestore Database > Create database.
2. Chọn vị trí `asia-southeast1` (Singapore), chọn Production mode, bấm Create.
3. Tab Rules, thay toàn bộ nội dung bằng đoạn dưới rồi bấm Publish. Đoạn này chỉ cho chính bạn đọc và ghi sổ của bạn:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```

## Bước 4. Lấy cấu hình
1. Biểu tượng bánh răng cạnh "Project Overview" > Project settings.
2. Kéo xuống "Your apps" > bấm biểu tượng `</>` (Web), đặt tên bất kỳ, bấm Register app.
3. Sao chép khối `firebaseConfig` hiện ra.

## Bước 5. Dán cấu hình và đăng lại
1. Mở file `firebase-config.js`, thay `null` bằng khối cấu hình (xem ví dụ trong file).
2. Tải lại các file lên GitHub Pages hoặc Cloudflare Pages như trong HUONG-DAN-DANG-WEB.md.

## Bước 6. Cho phép tên miền trang của bạn
1. Firebase: Authentication > Settings > Authorized domains > Add domain.
2. Thêm tên miền trang của bạn, ví dụ `tenban.github.io` hoặc `so-thu-chi.pages.dev` (chỉ phần tên miền, không có https://).

## Bước 7. Đăng nhập
1. Mở trang, vào mục Sao lưu, bấm "Đăng nhập Google" ở thẻ "Đồng bộ nhiều thiết bị".
2. Làm tương tự trên thiết bị còn lại bằng cùng tài khoản Google. Dữ liệu hai bên được gộp, không ghi đè.

## Lưu ý
- Nếu iPhone cài trang ra màn hình chính mà cửa sổ đăng nhập không mở, hãy đăng nhập một lần trong Safari rồi mở lại từ màn hình chính.
- Trang vẫn có nút "Tải file sao lưu". Nên giữ thêm một bản sao lưu mỗi tháng.
- Xóa một khoản ở máy này sẽ xóa ở máy kia. Dùng nút Hoàn tác ngay sau khi ghi nếu lỡ tay.
