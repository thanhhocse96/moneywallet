# .context/TENSIONS_OPEN.md — MoneyWallet
# Chỉ chứa Status: OPEN. Không load TENSIONS_HISTORY.md mặc định.

## Tag taxonomy

```text
agent
android
build
data-layer
ui
flavor
backup
security
permission
sql
proguard
migration
planning
```

Khi cần tag mới, update taxonomy trong file này trước khi dùng.

## Format entry

```markdown
## [YYYY-MM-DD HH:MM] | [module]
Tension:    Mô tả conflict ngắn gọn
Context:    Đang làm task gì
Proposal:   Agent muốn làm gì
Constraint: [manual] rule nào conflict (quote lại)
Severity:   low | high
Tags:       tag-one, tag-two
Milestone:  P0 / P1 / ...
Evidence:   [artifact nhìn được chứng minh tension có thật]
Default:    [severity low: phương án conservative + mốc nếu human không quyết. Severity high: luôn ghi "DỪNG chờ human"]
Status:     OPEN
Resolved:
Decision:   OPEN
```

Severity LOW → ghi tension → tiếp tục theo hướng conservative → báo human review sau.

Severity HIGH → ghi tension → DỪNG task → chờ human fill Decision.

Hiện tại không có tension OPEN nào.
