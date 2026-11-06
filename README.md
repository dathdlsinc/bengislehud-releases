# BengIsleHUD

HUD tiếng Việt cho **The Isle (Evrima)** trên Windows: bảng chỉ số khủng long, bản đồ nhỏ theo thời gian thực, nhật ký cắn / bị cắn, bảng Prime của server và vị trí nhóm.

HUD **chỉ đọc gói tin mạng** của game (qua Npcap). Không gửi gì vào game, không chỉnh sửa game, không đọc bộ nhớ game.

> Repo này chỉ chứa **bộ cài** và dữ liệu tự cập nhật, không có mã nguồn.

## Tải về

**[Tải bản mới nhất (BengIsleHUD-Setup)](https://github.com/dathdlsinc/bengislehud-releases/releases/latest)**: vào trang Release, mục *Assets*, tải file `BengIsleHUD-Setup-x.y.z.exe`.

Các file `.blockmap` và `latest.yml` dùng cho tự cập nhật, không cần tải.

## Cài (1 lần, khoảng 3 phút)

1. **Cài BengIsleHUD**: chạy `BengIsleHUD-Setup-x.y.z.exe`.
   - Nếu Windows hiện *"Windows protected your PC"*: bấm **More info > Run anyway** (app chưa ký số).
   - App tự cài, có biểu tượng BengIsleHUD ở Desktop và Start Menu. Không cần Python, không cần Wireshark.
2. **Cài Npcap** (driver đọc gói tin):
   - Mở BengIsleHUD, nếu máy chưa có Npcap thì bấm **F9 > Cài Npcap**: app tải bộ cài chính thức từ npcap.com, bấm *Next / I Agree / Install*.
   - Hoặc tự tải ở <https://npcap.com> và cài mặc định. Máy đã có Wireshark thường đã có Npcap.
   - **Không** tick *"Restrict Npcap driver's access to Administrators only"*. Lỡ tick thì cài lại Npcap.

Cài đặt, server đã lưu và đăng nhập nằm ở `%APPDATA%\isle-hud`: cập nhật hay cài lại đều giữ nguyên.

## Cập nhật

- App tự kiểm tra bản mới khi mở và 2 giờ một lần. Có bản mới thì hiện **2 dòng nhỏ ở trên cùng màn hình**, không che game.
- Bấm **F9 > Phiên bản** để xem bản mới có gì, bấm **"Cập nhật lên x.y.z"** khi muốn: app tự tải, tự cài và mở lại.
- Không cập nhật cũng không sao, app vẫn chạy bình thường.

## Chạy mỗi lần chơi

1. Mở BengIsleHUD (nên mở **trước** khi vào server để HUD nhận được tên loài của các con quanh bạn).
2. Mở The Isle, vào server. Sau vài giây HUD tự nhận server và con khủng long của bạn.
3. **Lần đầu vào một server**, bấm **F9**:
   - Mục *Server đang chơi*: nhập tên server và trang web của server (ví dụ `sdvn.org`), bấm **Lưu**.
   - Bấm **F7** để đăng nhập Steam vào trang server. Xong sẽ thấy *"Đã đăng nhập"*.
   - Lần sau vào lại server này, app tự nhận.
4. Bấm F9 lần nữa để đóng cài đặt.

## Phím tắt

| Phím | Việc |
|---|---|
| **F9** | Cài đặt, kéo thả vị trí các bảng, bật / tắt từng bảng, cập nhật |
| **F8** | Hiện / ẩn bảng Prime: tab *Prime Quest* và *Pack dino (garage)* |
| **F7** | Đăng nhập Steam vào trang web server |
| **F6** | Đặt điểm hẹn từ toạ độ đã chép (bấm lần nữa để xoá) |
| **F4** | Bản đồ lớn: kéo để xem, +/- để phóng to, chuột phải để đánh dấu điểm, Esc để đóng |

## Tính năng

- **Bảng khủng long**: tên loài, % Growth (75 % = lớn tối đa, trên 75 % là Prime), Máu, Thể lực, Thức ăn, Nước; *Chảy máu* chỉ hiện khi đang mất máu.
- **Bản đồ nhỏ**: bản đồ Gateway có vùng, tên khu vực; vị trí và hướng của bạn, cả khi bay.
- **Nhật ký cắn / bị cắn**: luôn hiện 5 dòng gần nhất trên màn hình, dòng mới ở trên.
  - Bạn cắn: `Tên bạn > Ceratosaurus: damage/máu còn lại`
  - Bị cắn: `Không rõ > Tên bạn: damage/máu còn lại`
- **Điểm hẹn**: chép toạ độ bạn gửi (nút copy vị trí trong game), bấm F6: bản đồ có đường chỉ tới và khoảng cách.
- **Vị trí nhóm thời gian thực**: cả nhóm cùng cài HUD, **F9 > tick "Chia sẻ vị trí với nhóm"**, nhập **cùng một mã nhóm** (ít nhất 4 ký tự, đừng dùng mã dễ đoán) và điền *Tên nhân vật*. Mọi người thấy nhau trên bản đồ nhỏ và bản đồ lớn ở mọi khoảng cách, cập nhật mỗi giây, tối đa 30 người. Chỉ gửi vị trí con của chính mình, máy chủ không lưu gì.
- **Bảng Prime (F8)**: trang Prime Quest và Pack dino của web server, mỗi server nhớ riêng.
- Chuột bấm xuyên qua HUD, không vướng khi chơi. Chạy được khi bật hay tắt Cloudflare WARP.

## Chưa có / lưu ý

- Tên kẻ cắn mình (đang hiện *"Không rõ"*).
- Cú cắn làm mình chết chưa hiện tin.
- Con đã ở gần bạn trước khi bật HUD có thể chưa có tên loài.
- Tên AI (động vật) bị cắn chưa có; máu AI đọc được với Boar và Deer.

## Khi có lỗi

Tắt HUD, mở **PowerShell**, chạy lệnh dưới để chép file log ra Desktop:

```powershell
Copy-Item -Force "$env:APPDATA\isle-hud\logs\isle-hud.log" ([Environment]::GetFolderPath("Desktop"))
```

Gửi file `isle-hud.log` cho Beng, kèm mô tả: đang chơi loài gì, làm gì thì lỗi.
