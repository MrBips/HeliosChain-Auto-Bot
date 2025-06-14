![image](https://github.com/user-attachments/assets/f5c891be-e0f0-4b11-b87c-c531d9aa211e)
# Helios Testnet Auto Bot

## Giới thiệu

**Helios Testnet Auto Bot** là một công cụ tự động hóa các hoạt động trên mạng thử nghiệm Helios Chain, bao gồm:
- Tự động bridge token HLS sang các chain testnet khác.
- Tự động stake HLS vào các validator.
- Đăng ký tài khoản Helios, onboarding, claim faucet, claim reward, v.v.
- Giao diện terminal trực quan, dễ sử dụng.

Bot hỗ trợ nhiều tài khoản (qua file pk.txt), có thể cấu hình số lần lặp, số lượng HLS cho mỗi hoạt động, và sử dụng Tor để đổi IP cho mỗi tài khoản.

## Tính năng chính

- **Tự động Bridge**: Chuyển HLS sang các chain testnet khác với số lượng và số lần lặp ngẫu nhiên trong khoảng cấu hình.
- **Tự động Stake**: Stake HLS vào các validator với số lượng và số lần lặp ngẫu nhiên trong khoảng cấu hình.
- **Đăng ký tài khoản Helios**: Đăng ký hàng loạt tài khoản mới bằng private key và invite code.
- **Claim Faucet**: Tự động claim token faucet cho tất cả tài khoản.
- **Giao diện TUI**: Hiển thị thông tin ví, log giao dịch, menu thao tác, cấu hình trực tiếp trên terminal.
- **Hỗ trợ Tor**: Đổi IP qua Tor cho mỗi tài khoản khi đăng ký/claim faucet.

## Hướng dẫn cài đặt

1. **Cài đặt Node.js**  
   Tải và cài đặt Node.js tại [nodejs.org](https://nodejs.org/).

2. **Cài đặt dependencies**  
   Mở terminal tại thư mục dự án và chạy:
   ```bash
   npm install
   ```

3. **Chuẩn bị dữ liệu**
   - Tạo file `pk.txt`: Mỗi dòng là một private key (64 ký tự hex, có thể có/không có tiền tố 0x).
   - Tạo file `register.txt`: Private key cho các tài khoản cần đăng ký mới.
   - Tạo file `code.txt`: Mỗi dòng là một invite code hợp lệ.
   - File `config.json` sẽ tự động sinh ra khi bạn cấu hình trong app.

4. **Cài đặt Tor (nếu muốn dùng Tor)**
   - Cài Tor Browser hoặc Tor service.
   - Đảm bảo Tor SOCKS proxy chạy ở `127.0.0.1:9050` và control port ở `127.0.0.1:9051`.
   - Đặt mật khẩu control port Tor (hoặc sửa biến `TOR_CONTROL_PASSWORD` trong code).

## Hướng dẫn sử dụng

- **Chạy bot**  
  - Windows: Nhấp đúp `Run.bat` hoặc chạy:
    ```bash
    node index.js
    ```
- **Giao diện menu**  
  - Dùng phím mũi tên để di chuyển, Enter để chọn.
  - Các chức năng chính:
    - Start Auto Daily Activity: Tự động bridge & stake cho tất cả tài khoản.
    - Set Manual Config: Cấu hình số lần lặp, số lượng HLS cho bridge/stake.
    - Register an account: Đăng ký tài khoản mới từ `register.txt` và `code.txt`.
    - Faucet Tokens: Claim faucet cho tất cả tài khoản trong `pk.txt`.
    - Clear Logs: Xóa log giao dịch.
    - Refresh: Làm mới dữ liệu ví.
    - Exit: Thoát chương trình.

- **Cấu hình**  
  - Có thể chỉnh số lần lặp, min/max HLS cho bridge/stake ngay trong menu.

## File cấu trúc

- `index.js`: Toàn bộ logic chính của bot.
- `pk.txt`: Danh sách private key để chạy auto bridge/stake.
- `register.txt`: Danh sách private key để đăng ký tài khoản mới.
- `code.txt`: Danh sách invite code để đăng ký tài khoản.
- `config.json`: File cấu hình (tự sinh).
- `Run.bat`: Script chạy nhanh trên Windows.
- `package.json`: Thông tin package và dependencies.

## Lưu ý bảo mật

- **Không chia sẻ file pk.txt, register.txt, code.txt cho bất kỳ ai.**
- Chỉ sử dụng private key testnet, không dùng ví thật/mainnet.

## License

Vui lòng cập nhật thông tin giấy phép nếu cần. 
