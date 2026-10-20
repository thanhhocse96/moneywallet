# .context/modules/MODULE_FLAVORS.md — MoneyWallet
# Flavors: floss/proprietary × gmap/osm

[manual]
- `floss`/`proprietary` × `gmap`/`osm`; giữ build khả thi trên mọi combo.
- `proprietary`: chứa Google Drive + Dropbox, yêu cầu API-key hợp lệ trong `gradle.properties`.
- `floss`: chỉ open source, không có Drive/Dropbox.
- `gmap`: dùng Google Map, yêu cầu API-key.
- `osm`: dùng OpenStreetMap.
- Bản release hiện tại dùng `proprietary` + `osm` + Crashlytics + In-App billing.
[/manual]

### Rules

- Không tự xóa flavor trừ khi human xác nhận.
- API key (Google Maps, Dropbox, Drive) phải ở `gradle.properties` / `local.properties`, KHÔNG commit.
- Mọi combo flavor phải build được (`assembleDebug` trên tất cả 4 combo).
