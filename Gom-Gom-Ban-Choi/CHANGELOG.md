# Changelog — Gom Gom Rotate (web prototype)

Ghi mỗi thay đổi người chơi thấy được, mới nhất ở trên. Định dạng: ngày → nhóm (Gameplay / UI / Deco / Tools / Docs) → mô tả ngắn.

## 2026-11-16

### Gameplay
- Bonus Time (xả lượt sau khi thắng) về lại nhịp nhanh cũ: lượt chỉ gom mèo có sẵn không còn phải chờ bằng lượt có mèo mọc.
  Cờ `TIMING.BONUS_EVEN_PACE` (tuning.mjs) đổi mặc định thành `false`; bật lại được qua Firebase Remote Config nếu cần nhịp đều như bản Unity.

### UI
- Onboarding: nhận quà bồn hoa đầu tiên ("Yay!") xong ở lại Deco hub, không vào thẳng màn kế nữa.
  Lời mèo cam đầu tiên ("Okay!") vẫn vào thẳng màn kế như bản Unity.

### Ghi chú
- Thanh điểm màn chơi tô xanh lá là chủ ý từ HUD bản 19/10 (`game/ui/play/hud.css`), chưa đổi — chờ chốt màu.

### Đã có trước đó trong ngày (theo bản Unity)
- Bonus Time cùng nhịp mọi màn (nay đã tắt mặc định, xem trên); Deco đảo chiều xoay camera.
- Popup giới thiệu vật cản hiện hình vật cản thay mèo cam.
- Onboarding vào thẳng màn kế sau Okay! / Yay! (nay Yay! ở lại Deco, xem trên); nút mắt Deco hiện từ lần vào đầu.
- Layout tablet: nút rìa bám mép màn, nền màn chơi phủ kín.
- Thêm ảnh chat-emotes.
