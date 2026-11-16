# Changelog — Gom Gom Rotate (web prototype)

Ghi mỗi thay đổi người chơi thấy được, mới nhất ở trên. Định dạng: ngày → nhóm (Gameplay / UI / Deco / Tools / Docs) → mô tả ngắn.

## 2026-11-16

### UI (onboarding)
- Flow mới: màn 1 -> nhận mèo -> mèo cam nói -> màn 2 -> nhận quà -> **vào thẳng Deco** mở quà -> "Yay!" -> **vào thẳng màn 3**.
  Trước đó thắng màn 2 về Home (phải tự vào Deco) và mở quà xong đứng ở Deco. Hộp quà màn 3 (xu) cũng vào thẳng Deco.
- Bấm Continue sau màn 2 / 3 không còn thoáng hiện Home hub trước khi sang Deco (bỏ bước ghé Home + hộp quà bay vào tab).
- File HTML gửi người chơi build bằng `npm run build:html -- --no-dev` (không có nút dev).

### Deco
- Dấu "!" (thùng mèo, hộp quà, mèo cam) hiện đúng màu vàng trên điện thoại. Lỗi: shader toon `pow()` số âm sau bước pastel (màu vàng đậm có kênh
  xanh dương âm), GPU Android ra NaN nên dấu thành xanh lá. Xanh lá giờ chỉ còn ở cọc khu kế tiếp khi đủ điều kiện mở.
- Xoay camera Deco bằng hai ngón về lại chiều cũ (`DRAG.DECO_ROTATE_REVERSED` mặc định tắt, bật lại được qua Remote Config).

### Gameplay
- Bonus Time (xả lượt sau khi thắng) về lại nhịp nhanh cũ: lượt chỉ gom mèo có sẵn không còn phải chờ bằng lượt có mèo mọc.
  Cờ `TIMING.BONUS_EVEN_PACE` (tuning.mjs) đổi mặc định thành `false`; bật lại được qua Firebase Remote Config nếu cần nhịp đều như bản Unity.

### UI
- (Đã thay bằng flow mới ở trên) Nhận quà bồn hoa xong ở lại Deco hub.

### Gameplay (chốt an toàn)
- Bonus Time (finale.js `drainMoves`) dừng ngay nếu ván đổi giữa chừng; không còn tự chơi rồi xử thắng ván mới (bảng "Level Complete" 0 sao, không lưu tiến độ).
  Người chơi thường không vào được tình huống này (Home / Restart bị khoá lúc Bonus Time); lộ ra khi máy test bấm thẳng tab giữa ván.

### Tools (dev)
- `?level=N` (nút "Chơi thử trong game" của Level Editor): đóng popup Home vừa tự bật (quà 7 ngày) trước khi vào màn.
  Trước đó popup đè lên màn chơi và bảng thắng chồng lên popup.

### Đã rà lại (không lỗi)
- Quà bồn hoa: bấm "Yay!" ở lại Deco, tab Home dùng được, không lỗi JS.
- Popup vật cản: 7 câu giới thiệu đều khớp đúng ảnh, đủ file ảnh.
- Layout tablet 1024×768 / 768×1024: ví + nút cài đặt cùng vị trí ở Home / Deco / Shop, nền màn chơi phủ kín.
- Bonus Time nhịp nhanh chạy hết màn bình thường (bot tự chơi màn 13).

### Ghi chú
- Thanh điểm màn chơi tô xanh lá là chủ ý từ HUD bản 19/10 (`game/ui/play/hud.css`), chưa đổi — chờ chốt màu.

### Đã có trước đó trong ngày (theo bản Unity)
- Bonus Time cùng nhịp mọi màn (nay đã tắt mặc định, xem trên); Deco đảo chiều xoay camera.
- Popup giới thiệu vật cản hiện hình vật cản thay mèo cam.
- Onboarding vào thẳng màn kế sau Okay! / Yay! (nay Yay! ở lại Deco, xem trên); nút mắt Deco hiện từ lần vào đầu.
- Layout tablet: nút rìa bám mép màn, nền màn chơi phủ kín.
- Thêm ảnh chat-emotes.
