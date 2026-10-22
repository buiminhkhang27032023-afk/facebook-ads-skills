---
name: google-ads
description: Playbook Google Ads (tiếng Việt) để lên kế hoạch, dựng, audit và tối ưu chiến dịch Google Ads — đặc biệt lead-gen ngân sách thấp (Search, PMax, Demand Gen, đo lường chuyển đổi, Smart Bidding, RSA, landing page CRO). Dùng khi người dùng hỏi cách cấu trúc tài khoản, cài conversion tracking/Enhanced Conversions/GA4, chọn từ khoá & negative, chọn chiến lược giá thầu, loại trừ vị trí PMax, viết RSA, tối ưu trang đích, audit tài khoản hằng tuần hoặc chạy Ads với ngân sách nhỏ.
---

# Google Ads — Playbook vận hành

Bản chắt lọc từ giáo trình 115 bài (cập nhật 2026). Chi tiết, số liệu, nguồn và case study: xem `references/notes.md` (tìm theo "## Bài N").

## 0. Nguyên tắc chung
- Thứ tự ưu tiên: **tracking đúng → cấu trúc gọn → từ khoá/negative → bidding → quảng cáo → landing page → scale**. Phần lớn ca "Ads không hiệu quả" = tracking lỗi, thiếu negative, LP không khớp ad.
- Tối ưu theo **outcome** (CPL/CPA, lead chất lượng, ROAS) chứ không theo vanity metric (impression, CTR, Optimization score).
- Toán trước khi chạy: `CPA = CPC ÷ CR`. Đặt CPA trần từ biên lợi nhuận (vd ≤ 20–25% giá bán). 30 ngày đầu CR thường thấp hơn 30–50%.
- Mỗi lần đổi bid strategy/target lớn = học lại (2–4 tuần, "thuế học" 10–21 ngày). Không chỉnh dồn dập.

## 1. Cấu trúc tài khoản (Bài 1–115, 53, 58, 80, 103)
- Account → Campaign (ngân sách, bidding, geo, mạng) → Ad group (chủ đề) → Keyword + RSA.
- Chỉ **gộp** khi cùng dịch vụ, cùng vùng, cùng conversion goal, cùng mức CPA; khác thì tách. Ngân sách thấp: **1 campaign Search**, 2–3 ad group theo chủ đề (STAG, không SKAG).
- Brand tách campaign riêng ngân sách nhỏ (chỉ khi có người tìm brand). Đặt tên chuẩn: `SRCH_<Mục tiêu>_<Vùng>_<Sản phẩm>`.
- Location: **Presence** ("người ở/thường ở"), không dùng Presence or interest cho lead-gen địa phương (Bài 95, 106). Search Partners & Display **tắt** lúc đầu (Bài 101).

## 2. Conversion tracking (Bài 11, 12, 31, 50, 91, 99)
1. Google tag (gtag/GTM) trên mọi trang; auto-tagging ON; Consent Mode v2 nếu có người dùng EEA.
2. Conversion **Primary** = hành động có giá trị thật (lead form gửi thành công, xác nhận phía server, chống trùng bằng transaction/lead ID). Click chat/điện thoại → **Secondary** hoặc gán value thấp.
3. Lead: Count = **One**; window phù hợp chu kỳ mua.
4. **Enhanced Conversions for leads** (email/SĐT hash SHA-256) + lưu `gclid/gbraid/wbraid` + UTM vào lead (hidden field).
5. Khi đủ lead (≈ ≥30/tháng): **Offline Conversion Import** lead đủ chuẩn/đã mua → tối ưu theo lead thật.
6. GA4 import key events = Secondary (đối soát), tag Ads = Primary. Lệch Ads vs CRM >10% → sửa tracking trước mọi thay đổi khác.
7. Kiểm tra bằng Tag Assistant, Conversion diagnostics; khi tag lỗi vài giờ → thêm **Data exclusion**.

## 3. Từ khoá & negative (Bài 3, 51, 62, 72, 81, 83)
- Ngân sách thấp: **Phrase làm xương sống, Exact cho từ đã chứng minh hiệu quả**; Broad chỉ khi tracking chuẩn + đủ conversion (≥30/tháng) + Smart Bidding.
- Shared negative list **từ ngày đầu**: miễn phí, free, crack, tải, tuyển dụng, việc làm, là gì, PDF, đối thủ không muốn… Áp ở account-level/shared list; negative riêng sản phẩm ở campaign.
- Search terms **hằng tuần**: thêm 3–10 negative, n-gram tìm cụm lãng phí; search term chuyển đổi tốt → thêm Exact.
- Negative match type khác keyword thường (không tự mở rộng biến thể) — thêm đủ biến thể.

## 4. Thang giá thầu (Bài 5, 61, 71, 79, 89)
| Conv 30 ngày | Chiến lược |
|---|---|
| < 15 | Max Clicks **có trần CPC** hoặc Manual CPC |
| 15–30 | Maximize Conversions, ngân sách ngày cố định |
| > 30 ổn định | tCPA (tốt nhất portfolio có trần max CPC), đặt = CPA thực 30 ngày, hạ ~10%/2 tuần |
| Có value thật (OCI/giá trị) | Max Conv. Value / tROAS |
- Sau mỗi lần đổi: không chỉnh gì 14 ngày (chỉ thêm negative). Budget ≥ 2–3× tCPA/ngày nếu có thể. Scale **+20%/lần, cách ≥1 tuần**.
- Dưới Smart Bidding, bid adjustment schedule/location không có tác dụng (trừ device −100%); dùng ad schedule như công tắc (Bài 38, 94, 105).

## 5. Performance Max (Bài 7, 17, 24, 25)
- Chỉ chạy PMax khi tracking sạch và có ≥30 conv/tháng; ngân sách thấp ưu tiên Search.
- PMax không có placement exclusion cấp campaign → dùng **placement exclusion cấp tài khoản** (Content suitability; áp cả Search Partners) hoặc list ở MCC. Loại: app games/trẻ em, site/kênh rác từ placement report.
- **Brand exclusions** (loại brand của mình nếu đã có campaign Brand), account-level negatives, campaign negative keywords (2025+), Content suitability: inventory **Limited/Moderate**, loại sensitive content.
- Audience signals: Customer Match, remarketing, custom segment từ search term chuyển đổi tốt. Final URL expansion: tắt hoặc loại trừ URL.
- Đọc: search terms insights, channel/placement report, asset reporting. Rà placement **hằng tuần**.

## 6. RSA & assets (Bài 6, 59, 69, 77, 90, 98)
- 1–2 RSA/ad group; 10–15 headline khác biệt (USP, giá, CTA, keyword, địa điểm, bằng chứng xã hội), 4 description.
- Không chạy theo Ad Strength. Mặc định **không pin**; nếu cần, pin H1 = USP/keyword chính (có thể 2–3 biến thể ở 1 vị trí).
- Test: so sánh khi mỗi ad ≥ ~1.000 impression, chọn theo **conversions/1.000 impressions** + CPL, không chỉ CTR. Thay asset "Low" mỗi tháng 1 vòng.
- Assets: ≥4 sitelink, callout, structured snippet, call, image, lead form (lọc lead bằng câu hỏi qualifying, Bài 39/100).

## 7. Landing page CRO (Bài 26, 55, 64, 73, 84, 92, 104)
- Message match: headline LP khớp keyword/ad; 1 mục tiêu, 1 CTA rõ above the fold; mobile-first, tải < 3 s (Core Web Vitals).
- Ghi rõ **giá/điều kiện** để lọc lead rác; bằng chứng xã hội (số học viên/khách, review), FAQ, chính sách bảo mật dưới nút gửi.
- Form ngắn (hoặc 2 bước) + câu hỏi lọc; CTA nổi ở đáy màn hình mobile.
- A/B bằng Experiments (50/50, chỉ đổi Final URL), chạy ≥3–4 tuần hoặc ≥15 conv/bên; chọn theo CPL + tỷ lệ lead đủ chuẩn.

## 8. Checklist audit hằng tuần (Bài 18b, 30b, 54, 63, 65, 74, 93)
- [ ] Conversion status Active; số lead Ads ≈ CRM/Sheet (lệch ≤10%); tag không lỗi.
- [ ] Chi tiêu & pacing vs kế hoạch; số dư prepaid/billing (đứt quảng cáo = phá learning).
- [ ] Search terms → negative + Exact mới; n-gram lãng phí.
- [ ] CPL/CPA, CVR, CTR, CPC vs tuần trước & mục tiêu; Lost IS (budget vs rank).
- [ ] Bid strategy status (Learning/Limited); không đổi target nếu chưa đủ 2 tuần.
- [ ] RSA/asset performance; policy disapproved/limited.
- [ ] Placement/channel report (PMax/Display), Search Partners, location report (Presence đúng vùng).
- [ ] Change history: ai đổi gì; Recommendations chỉ áp dụng khi hợp KPI (tắt auto-apply nguy hiểm).
- [ ] Chất lượng lead: đánh dấu lead đạt/không đạt → OCI.
- Hằng tháng: cấu trúc, landing page, experiment, benchmark ngành (Bài 66, 85).

## 9. Quy tắc ngân sách thấp (Bài 56, 57, 68, 80, 81, 86, 89)
- Đủ **50–100 click/tuần** cho 1 campaign; nếu không đủ → thu hẹp từ khoá/vùng thay vì chia nhỏ.
- 1 campaign Search, 2–3 ad group, Phrase + Exact, Presence, tắt Search Partners/Display, ad schedule theo giờ ra lead.
- Không PMax/Display/YouTube cho tới khi Search ổn định và có ≥30 conv/tháng.
- Không kết luận trước 30/60/90 ngày; không pause/đổi budget mạnh vài tuần đầu.
- Chỉ tối ưu theo conversion "sạch" (form hợp lệ, cuộc gọi >60 s).

## Tra cứu chi tiết
`references/notes.md` — toàn bộ giáo trình (Bài 1–115): Search, Shopping, Display, Demand Gen/YouTube, App, Local, Hotel/Travel, GA4, Enhanced Conversions, sGTM, Scripts, API, SA360, MMM/Lift, policy, bảo mật, và các case study agency. Dùng `grep -n "## Bài"` để định vị.
