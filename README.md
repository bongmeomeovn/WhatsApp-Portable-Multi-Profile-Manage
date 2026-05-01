# WhatsApp Portable — Multi-Profile Manager 💬

A lightweight, portable desktop application built with **Tauri v2** that allows you to manage multiple isolated WhatsApp Web profiles simultaneously, just like Google Chrome profiles.

![Profile Manager](https://img.shields.io/badge/Tauri-v2-24C8DB?style=flat-square&logo=tauri)
![Rust](https://img.shields.io/badge/Rust-Backend-f74c00?style=flat-square&logo=rust)
![Vanilla JS](https://img.shields.io/badge/Frontend-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript)

## ✨ Tính năng nổi bật (Features)

*   **🌐 Quản lý nhiều Profile (Multi-Accounts)**: Tạo không giới hạn số lượng profile WhatsApp. Mỗi profile hoạt động độc lập với một phiên đăng nhập (session) riêng biệt.
*   **💼 Hoàn toàn Portable (100% Portable)**: Mọi dữ liệu (Cookies, Local Storage, Session) được lưu trữ ngay trong thư mục `ProfileData/` nằm cùng cấp với file thực thi `.exe`. Bạn có thể copy toàn bộ thư mục app sang máy USB hoặc máy tính khác để dùng tiếp mà không mất dữ liệu đăng nhập.
*   **🎨 Giao diện Hiện đại (Glassmorphism UI)**: Quản lý profile với giao diện Dark Mode đẹp mắt, hỗ trợ đặt tên, chọn màu sắc nhận diện (Avatar) cho từng profile.
*   **⚡ Siêu nhẹ & Nhanh (High Performance)**: Viết bằng **Rust** và **Tauri v2**, sử dụng bộ nhớ cực thấp so với các ứng dụng bọc bằng Electron. Tối ưu WebView2 trên Windows.
*   **🔒 Cô lập dữ liệu (Data Isolation)**: Sử dụng Custom `data_directory` của WebView2 để đảm bảo các tài khoản không bị xung đột.

## 🚀 Hướng dẫn cài đặt & Chạy thử (Quick Start)

### Yêu cầu hệ thống
*   Hệ điều hành: Windows 10 / 11.
*   Môi trường Build: Node.js (v20+), Rust, và Visual Studio Build Tools (C++).

### Chạy ở chế độ Phát triển (Dev Mode)

1. Clone repository về máy.
2. Cài đặt các gói phụ thuộc NPM:
   ```bash
   npm install
   ```
3. Chạy ứng dụng:
   ```bash
   npm run tauri dev
   ```

### Đóng gói Ứng dụng (Build Production)

Để đóng gói thành file `.exe` độc lập để sử dụng hàng ngày:

```bash
npm run tauri build
```
File thực thi sau khi build sẽ nằm tại: `src-tauri/target/release/whatsapp-portable.exe`.

## 📂 Cấu trúc thư mục dữ liệu

Khi chạy app, nó sẽ tự động tạo thư mục dữ liệu bên cạnh file `.exe` như sau:

```text
/Thư-mục-chứa-app/
 ├── whatsapp-portable.exe
 ├── profiles.json          <-- Lưu thông tin cấu hình (tên, màu sắc) của các profile
 └── ProfileData/           <-- Chứa dữ liệu WebView (Trình duyệt)
      ├── profile_17000.../ <-- Dữ liệu duyệt web của Profile 1 (Cookies, Cache,...)
      ├── profile_17001.../ <-- Dữ liệu duyệt web của Profile 2
      └── ...
```

## 🛠️ Công nghệ sử dụng
*   **Tauri v2** - App framework.
*   **Rust** - Backend, Quản lý Window & Filesystem.
*   **Vanilla JS / HTML / CSS** - Frontend Profile Manager UI không sử dụng framework nặng nề.

## ⚠️ Lưu ý
* Đảm bảo máy tính Windows của bạn đã cài đặt [Microsoft Edge WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) (thường được cài sẵn trên Windows 10/11 hiện tại).
* Không xóa thư mục `ProfileData` nếu bạn không muốn đăng nhập lại các tài khoản WhatsApp.

