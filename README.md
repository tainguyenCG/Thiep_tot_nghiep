# 🎓 Thiệp Tốt Nghiệp — Nguyễn Thị Thuỳ Trang

---

## 📁 Cây thư mục đã chuẩn để deploy

```
Thiep/
├── index.html          ← Trang chính + đầy đủ SEO tags
├── robots.txt          ← Cho phép crawler + trỏ tới sitemap
├── sitemap.xml         ← Khai báo URL + ảnh thumbnail cho Google
├── manifest.json       ← PWA, hiển thị tên khi share trên mobile
├── README.md           ← File hướng dẫn này
└── assets/
    ├── background.jpg      ← Ảnh nền thiệp
    ├── selesaiwisuda.jpg   ← Ảnh thumbnail SEO (og:image)
    └── Anh_mau.jpg
```

---

## 🚀 Checklist deploy (chỉ làm 1 lần)

### Bước 1 — Deploy lên Netlify Drop

1. Truy cập **[netlify.com/drop](https://app.netlify.com/drop)**
2. Kéo thả **toàn bộ thư mục `Thiep/`** vào vùng kéo thả trên trang đó
3. Chờ vài giây → Netlify tự tạo URL dạng `https://xxx-xxx-xxx.netlify.app`
4. Copy URL đó lại

### Bước 2 — Thay placeholder domain

Sau khi có URL thật, mở 3 file dưới đây và tìm & thay **tất cả** chỗ có `https://YOUR-DOMAIN.com` thành URL vừa copy:

| File | Số chỗ cần thay | Vị trí |
|---|---|---|
| `index.html` | **5 chỗ** | thẻ `<base>`, `canonical`, `og:url`, `og:image`, `twitter:image` |
| `sitemap.xml` | **2 chỗ** | `<loc>` trang và `<image:loc>` ảnh |
| `robots.txt` | **1 chỗ** | dòng `Sitemap:` |

> **Mẹo nhanh:** Dùng **Ctrl + H** (Find & Replace) trong VS Code  
> - Find: `https://YOUR-DOMAIN.com`  
> - Replace: `https://xxx-xxx-xxx.netlify.app`  
> → Replace All → Save → Kéo thả lại lên Netlify Drop

### Bước 3 — Kiểm tra thumbnail

Sau khi deploy xong, dán URL vào công cụ kiểm tra để xem thumbnail hiện đúng chưa:

- **Facebook / Zalo**: [developers.facebook.com/tools/debug](https://developers.facebook.com/tools/debug/)
- **Twitter / X**: [cards-dev.twitter.com/validator](https://cards-dev.twitter.com/validator)
- **Tổng quát**: [opengraph.xyz](https://www.opengraph.xyz/)

---

## ✏️ Chỉnh sửa nội dung thiệp

Mở `index.html`, kéo lên đầu phần `<style>`, tìm khối `:root { ... }`:

```css
:root {
  /* ===== MÀU SẮC ===== */
  --color-name:     #95575e;   /* Tên chính */
  --color-datetime: #754725;   /* Ngày giờ */
  --color-address:  #754725;   /* Địa điểm */
  --color-message:  #754725;   /* Câu nhắn */
  --color-mylover:  #FCBBBB;   /* "My LOVER" */

  /* ===== CỠ CHỮ ===== */
  --size-name:      28px;
  --size-datetime:  18px;
  --size-address:   14px;
  --size-message:   14px;
  --size-mylover:   30px;
}
```

Chỉnh trực tiếp giá trị → lưu → F5 trình duyệt là thấy kết quả ngay.

---

## 📌 Lưu ý

- Ảnh `og:image` chỉ hiện thumbnail trên Zalo/Facebook **khi trang đã được host online** (có URL `https://`)
- Khi chạy file `index.html` trực tiếp trên máy (double-click) thì ảnh nền và nội dung vẫn hiện đúng, nhưng SEO thumbnail chưa hoạt động
