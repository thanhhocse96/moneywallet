# .context/modules/MODULE_BACKUP.md — MoneyWallet
# Backup layer: SAF, Google Drive, Dropbox

[manual]
- SAF (Storage Access Framework), Google Drive, Dropbox — không abort app khi lỗi.
- Không hardcode API key; lưu trong `gradle.properties` / `local.properties`, KHÔNG commit.
- `USE_FINGERPRINT` → Biometric API (`USE_BIOMETRIC`).
[/manual]

### Rules

- `proprietary` flavor: Google Drive + Dropbox backup.
- `floss` flavor: chỉ SAF local backup, không có cloud.
- Scoped storage: backup/export chuyển sang SAF (không còn `WRITE_EXTERNAL_STORAGE`).
- Lỗi backup không làm crash app (xem hotfix #177/#221).
