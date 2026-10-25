# 🎓 Thiệp Tốt Nghiệp — Nguyễn Thị Thuỳ Trang

> 🌐 **Live:** [https://tainguyencg.github.io/Thiep_tot_nghiep/](https://tainguyencg.github.io/Thiep_tot_nghiep/)

---

## 📁 Cây thư mục

```
Thiep/
├── index.html              ← Trang chính + đầy đủ SEO / OG tags
├── robots.txt              ← Cho phép crawler + trỏ tới sitemap
├── sitemap.xml             ← Khai báo URL + ảnh thumbnail cho Google
├── manifest.json           ← PWA — hiển thị tên khi thêm vào màn hình
├── README.md               ← File hướng dẫn này
└── assets/
    ├── background.jpg          ← Ảnh nền thiệp
    ├── selesaiwisuda.png       ← Ảnh thumbnail SEO (og:image)
    └── Anh_mau.jpg
```

---

## 🚀 Deploy lên GitHub Pages

### Bước 1 — Push code lên GitHub

```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

### Bước 2 — Bật GitHub Pages

1. Vào repo trên GitHub → **Settings** → **Pages**
2. Mục **Source** chọn: `Deploy from a branch`
3. Branch: **main** / Folder: **/ (root)** → nhấn **Save**
4. Chờ ~1-2 phút → GitHub tự tạo URL dạng:
   `https://<username>.github.io/<repo>/`

### Bước 3 — Kiểm tra thumbnail khi chia sẻ

Sau khi deploy, dùng công cụ sau để force-refresh cache và kiểm tra thumbnail:

| Nền tảng | Công cụ |
|---|---|
| **Facebook / Messenger** | [developers.facebook.com/tools/debug](https://developers.facebook.com/tools/debug/) → nhập URL → nhấn **Scrape Again** |
| **Zalo** | Xóa hội thoại cũ rồi gửi link lại |
| **Tổng quát** | [opengraph.xyz](https://www.opengraph.xyz/) |

> ⚠️ **Lưu ý:** Facebook cache link lần đầu tiên khi share. Nếu thumbnail chưa hiện, dùng công cụ debug ở trên để buộc Facebook quét lại.

---

## ✏️ Chỉnh sửa nội dung thiệp

Mở `index.html`, tìm khối `:root { ... }` trong thẻ `<style>`:

```css
:root {
  /* ===== MÀU SẮC ===== */
  --color-name:     #95575e;   /* Tên chính */
  --color-datetime: #754725;   /* Ngày giờ  */
  --color-address:  #754725;   /* Địa điểm  */
  --color-message:  #754725;   /* Câu nhắn  */
  --color-mylover:  #FCBBBB;   /* "My LOVER" */

  /* ===== CỠ CHỮ ===== */
  --size-name:      28px;
  --size-datetime:  18px;
  --size-address:   14px;
  --size-message:   14px;
  --size-mylover:   30px;
}
```

Chỉnh giá trị → lưu → `git add . && git commit -m "update" && git push` → GitHub Pages tự cập nhật sau ~1 phút.

---

## 📌 Lưu ý quan trọng

- **Đường dẫn ảnh** dùng tương đối (`assets/background.jpg`) để hoạt động đúng trên GitHub Pages (tránh dùng `/assets/...` bắt đầu bằng `/`)
- **Thumbnail** chỉ hiện khi trang đã online với URL `https://` — không hoạt động khi mở file trực tiếp trên máy
- **GitHub Pages** miễn phí cho repo public, cập nhật sau mỗi lần push ~1-2 phút
