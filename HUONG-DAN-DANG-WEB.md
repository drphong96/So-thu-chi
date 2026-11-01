# Đưa Sổ Thu Chi lên web (miễn phí)

Thư mục này là một web tĩnh, không cần máy chủ. Cách dễ nhất là GitHub Pages. Muốn đồng bộ điện thoại và laptop, làm tiếp HUONG-DAN-DONG-BO.md.

## Cách 1: GitHub Pages (khuyên dùng)
1. Tạo tài khoản GitHub (miễn phí), bấm New repository, đặt tên `so-thu-chi`, chọn Private hoặc Public.
2. Bấm "uploading an existing file", kéo thả 7 file (không cần file .md) trong thư mục này vào, bấm Commit.
3. Vào Settings > Pages > Source: Deploy from a branch > Branch: main, thư mục / (root) > Save.
4. Sau 1 đến 2 phút có địa chỉ dạng `https://<tên-bạn>.github.io/so-thu-chi/`.
   Lưu ý: Pages cho repo Private cần gói trả phí, nên chọn Public. Mã nguồn công khai nhưng dữ liệu của bạn không nằm trong đó, vì dữ liệu chỉ ở trình duyệt.

## Cách 2: Cloudflare Pages
1. Tạo tài khoản Cloudflare (miễn phí), vào Workers & Pages > Create > Pages > Upload assets.
2. Kéo cả thư mục này vào, đặt tên dự án, bấm Deploy. Địa chỉ dạng `https://so-thu-chi.pages.dev`.

## Cài lên điện thoại và laptop
- Điện thoại Android (Chrome): mở địa chỉ, bấm menu ⋮ > Cài đặt ứng dụng.
- iPhone (Safari): bấm nút Chia sẻ > Thêm vào Màn hình chính.
- Laptop (Chrome, Edge): bấm biểu tượng cài đặt ở cuối thanh địa chỉ.
Khi chạy trên https, micro hoạt động ổn định hơn và ứng dụng mở được cả khi mất mạng.

## Giữ dữ liệu an toàn
- Mặc định dữ liệu lưu trong trình duyệt của từng thiết bị. Bật đồng bộ theo HUONG-DAN-DONG-BO.md để dùng chung một sổ.
- Mỗi tuần vào mục Sao lưu, bấm "Tải file sao lưu" và cất file vào Google Drive hoặc email cho chính mình.
- Chuyển máy: tải file ở máy cũ, vào Sao lưu > "Nạp từ file" ở máy mới.
- Đừng xóa "dữ liệu trang web" của trình duyệt khi chưa sao lưu.
