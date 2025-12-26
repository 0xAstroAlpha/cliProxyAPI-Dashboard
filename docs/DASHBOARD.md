# 📊 CLIProxy Dashboard - Hướng Dẫn Sử Dụng

## Mục Lục
- [Truy Cập Dashboard](#truy-cập-dashboard)
- [Tổng Quan Giao Diện](#tổng-quan-giao-diện)
- [Các Tab Chức Năng](#các-tab-chức-năng)
- [Quản Lý Tài Khoản](#quản-lý-tài-khoản)
- [AI Playground](#ai-playground)
- [Cấu Hình](#cấu-hình)
- [Mobile/Responsive](#mobileresponsive)
- [FAQ](#faq)

---

![CLIProxy Dashboard Overview](Homepage.jpg)

## Truy Cập Dashboard

Sau khi khởi động CLIProxy server, truy cập Dashboard tại:

```
http://localhost:8317/static/management.html
```

> **Lưu ý:** Port mặc định là `8317`. Nếu bạn đổi port trong config, hãy thay đổi URL tương ứng.

### Xác Thực

Lần đầu truy cập, bạn sẽ được yêu cầu nhập **Management Key**. Key này được định nghĩa trong file `config.yaml` (nằm trong section `remote-management`):

```yaml
remote-management:
  secret-key: "your-secret-key"
```

---

## Tổng Quan Giao Diện

Dashboard sử dụng thiết kế **Vision UI** với các thành phần chính:

### 1. Sidebar (Thanh Bên Trái)
- **Navigation:** Chuyển đổi giữa các tab (Overview, Configuration, Logs, Activity, Playground)
- **Status Card:** Hiển thị trạng thái server và host:port
- **Buy Me a Coffee:** Nút ủng hộ tác giả

### 2. Header (Thanh Trên)
- **Online Status:** Chỉ báo kết nối real-time
- **Breadcrumb:** Vị trí hiện tại trong dashboard
- **Welcome Message:** Lời chào động theo giờ (☀️ Sáng / 🌤️ Chiều / 🌙 Tối)

### 3. Footer (Thanh Dưới)
- **Uptime:** Thời gian trang đã mở
- **Last Sync:** Thời điểm đồng bộ dữ liệu cuối
- **Version:** Phiên bản CLIProxy

---

## Các Tab Chức Năng

### 📊 Overview

Tab mặc định hiển thị tổng quan hệ thống:

| Thành Phần | Mô Tả |
|------------|-------|
| **Server Status** | Trạng thái kết nối, Host:Port, Debug Mode |
| **Usage Statistics** | Total Requests, Total Tokens với Sparkline charts |
| **Success/Failure** | Số lượng request thành công/thất bại |
| **Saved Cost** | Số tiền đã tiết kiệm (24h, 7d, Total) với emoji động |
| **Model Leaderboard** | Top 10 model được sử dụng nhiều nhất (🥇🥈🥉) |
| **Account Health** | Grid các tài khoản OAuth đã đăng nhập |

### ⚙️ Configuration

Cấu hình nhanh các settings:

- **Debug Mode:** Bật/tắt log debug
- **API Key Slots:** Quản lý API keys
- **Provider Settings:** Cấu hình từng provider

### 📜 Logs

Xem log server real-time:

- Auto-scroll khi có log mới
- Filter theo log level
- Clear logs

### 📈 Activity

Monitor chi tiết hoạt động:

| Tính Năng | Mô Tả |
|-----------|-------|
| **Usage Trends Chart** | Biểu đồ gradient hiển thị traffic theo giờ |
| **Activity Table** | Bảng chi tiết từng request với filter |
| **Status Pills** | Badge Success (xanh) / Failure (đỏ) |
| **Details Modal** | Xem chi tiết request/response |

**Filter Options:**
- Model filter
- Status filter (All/Success/Failure)

### 💬 Playground

Test trực tiếp các model:

1. **Chọn Model:** Dropdown hiển thị tất cả model khả dụng
2. **System Prompt:** Tùy chỉnh hành vi assistant
3. **Settings:**
   - Temperature (0-2)
   - Top P (0-1)
   - Max Tokens
   - Show Thinking (toggle)
4. **Chat Interface:**
   - Hỗ trợ ảnh (attach)
   - Shift+Enter xuống dòng
   - Enter gửi tin nhắn

---

## Quản Lý Tài Khoản

### Thêm Tài Khoản

1. Click nút **+ Add Account** hoặc FAB button (góc phải dưới)
2. Chọn provider (Gemini, Claude, OpenAI, Qwen, iFlow)
3. Sử dụng OAuth login hoặc paste API key

### Trạng Thái Tài Khoản

| Badge | Ý Nghĩa |
|-------|---------|
| 🟢 **Active** | Tài khoản hoạt động bình thường |
| 🟡 **Refreshing** | Đang refresh token |
| 🔴 **Error** | Có lỗi, cần kiểm tra |
| ⚫ **Disabled** | Tài khoản đã bị disable |

### OAuth Login

Với các provider hỗ trợ OAuth:
1. Click "Login with [Provider]"
2. Cửa sổ popup sẽ mở
3. Đăng nhập và authorize
4. Tài khoản tự động thêm vào danh sách

---

## AI Playground

### Sử Dụng Cơ Bản

```
1. Chọn model từ dropdown
2. (Optional) Nhập System Prompt
3. Nhập tin nhắn
4. Nhấn Enter hoặc click Send
```

### Gửi Kèm Ảnh

1. Click icon 📎 (paperclip)
2. Chọn ảnh từ máy
3. Ảnh preview sẽ hiển thị
4. Nhập prompt và gửi

### Xem Thinking Process

Với các model hỗ trợ reasoning (Claude, o1, etc.):
1. Bật toggle "Show Thinking"
2. Gửi tin nhắn
3. Click vào "💭 Thinking Process" để xem chi tiết suy luận

---

## Mobile/Responsive

Dashboard hỗ trợ đầy đủ trên mobile:

### Hamburger Menu
- Click icon ☰ (góc trái trên) để mở sidebar
- Click bất kỳ đâu ngoài sidebar hoặc nút X để đóng

### Responsive Features
- Table cuộn ngang trên màn hình nhỏ
- Cards stack theo chiều dọc
- FAB button luôn hiển thị

---

## FAQ

### Q: Dashboard không hiển thị dữ liệu?

**A:** Kiểm tra:
1. Server đã chạy chưa (`go run cmd/server/main.go`)
2. Management Key đúng chưa
3. Mở Console (F12) xem có lỗi không

### Q: Tài khoản báo lỗi?

**A:** 
1. Thử click Refresh
2. Kiểm tra token còn hạn không
3. Thử logout rồi login lại

### Q: Chart không hiển thị?

**A:** Đảm bảo có ít nhất 1 request đã được xử lý qua proxy.

### Q: Làm sao đổi port?

**A:** Sửa trong `config.yaml`:
```yaml
port: 8888
```

---

## Hỗ Trợ

- **Documentation:** [help.router-for.me](https://help.router-for.me/)
- **Repository:** [cliProxyAPI-Dashboard](https://github.com/0xAstroAlpha/cliProxyAPI-Dashboard)
- **Dashboard UI by:** [Brian Le](https://www.facebook.com/lehuyducanh/)

---

☕ **Nếu hữu ích, mời mình ly cà phê nhé!**

| Phương Thức | Địa Chỉ |
|-------------|---------|
| PayPal | `wikigamingmovies@gmail.com` |
| USDT (TRC20) | `TNGsaurWeFhaPPs1yxJ3AY15j1tDecX7ya` |
| USDT (BEP20) | `0x463695638788279F234386a77E0afA2Ee87b57F5` |
| Solana | `HkgpzujF8uTBuYEYGSFMnmGzBYmEFyajzTiZacRtXzTr` |
