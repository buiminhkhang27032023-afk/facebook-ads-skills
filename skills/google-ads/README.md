# google-ads-skill

Skill tiếng Việt cho agent: playbook lên kế hoạch, dựng, audit và tối ưu chiến dịch Google Ads, tập trung lead-gen ngân sách thấp. Chắt lọc từ giáo trình 115 bài (cập nhật 2026).

## Cấu trúc
```
google-ads-skill/
├── SKILL.md              # frontmatter (name, description) + playbook vận hành ngắn gọn
├── README.md
└── references/
    └── notes.md          # toàn bộ giáo trình Bài 1–115 (kiến thức, mẹo, lỗi, checklist, nguồn)
```

## Cách dùng
- Copy thư mục vào nơi agent đọc skill (vd `~/.claude/skills/google-ads/` hoặc thư mục skills của agent bạn dùng).
- Agent đọc `SKILL.md` khi gặp tác vụ Google Ads; khi cần chi tiết thì mở `references/notes.md` và tìm `## Bài N`.
- Thông tin doanh nghiệp/định danh đã được ẩn bằng placeholder như `[thương hiệu]`, `[account ID]`, `[conversion ID]`.

Lưu ý: nội dung về tính năng/ngày tháng của Google Ads thay đổi nhanh — kiểm tra lại với Google Ads Help trước khi áp dụng.
