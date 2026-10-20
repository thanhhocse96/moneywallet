# .context/modules/MODULE_CALC.md — MoneyWallet
# Calculator / Formatter

[manual]
- Không dùng `double` rồi truncate về `long` (bug mất 1 cent). Chuyển sang `BigDecimal` + `HALF_UP`.
- `MoneyFormatter.normalize()`, `CurrencyConverterPicker.convert()`, `EquationSolver` — kiểm tra kỹ trước khi sửa.
[/manual]

### Rules

- `MoneyFormatter.normalize()` — dùng `BigDecimal.valueOf(money).movePointLeft(decimals).toPlainString()`.
- `CurrencyConverterPicker.convert()` — truyền đúng currency (fallback default) cho `MoneyPicker`.
- `EquationSolver` phép chia — dùng `BigDecimal` + `HALF_UP`.
- Unit test table-driven (~40 case) cho formatter/converter.
- Bắt buộc fix 1-cent bugs trước tính năng vàng (P2).
