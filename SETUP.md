# Đưa profile này lên GitHub

Thư mục này là một **profile repo** — repo đặc biệt có tên trùng với username GitHub. Khi public, `README.md` sẽ tự hiện ở trang cá nhân `github.com/TranLoiIT`.

## Có gì trong đây

| File | Vai trò |
|---|---|
| `README.md` | Nội dung profile: about, stack, dự án, stats, liên hệ |
| `assets/hero-dark.svg` | Banner cho GitHub dark mode (có animation nhẹ) |
| `assets/hero-light.svg` | Banner cho GitHub light mode |
| `SETUP.md` | Hướng dẫn này (không hiện trên profile) |

Banner tự đổi theo theme nhờ `<picture>` + `prefers-color-scheme`, không cần chỉnh gì.

---

## 1. Tạo repo

1. Mở https://github.com/new
2. **Repository name**: `TranLoiIT` — phải trùng username (không phân biệt hoa/thường).
3. Chọn **Public**.
4. **Không** tick "Add a README file" (đã có sẵn).
5. Bấm **Create repository**.

> Nếu tên repo không trùng username, GitHub sẽ không hiện README trên profile.

## 2. Push code

Thư mục này đã được `git init` và commit sẵn. Mở PowerShell và chạy:

```powershell
cd C:\Users\PC1\TranLoiIT
git branch -M main
git remote add origin https://github.com/TranLoiIT/TranLoiIT.git
git push -u origin main
```

Nếu push bị hỏi mật khẩu: GitHub không nhận mật khẩu tài khoản. Dùng một trong hai cách:

**Cách A — GitHub CLI (gọn nhất)**

```powershell
winget install --id GitHub.cli
gh auth login
```

**Cách B — Personal Access Token**

GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token → quyền **Contents: Read and write** → dùng token làm mật khẩu khi push.

## 3. Kiểm tra

- Mở https://github.com/TranLoiIT — README phải hiện ngay.
- Vào Settings → Appearance, đổi Light/Dark để xem banner đổi màu.
- Nếu ảnh chưa hiện: kiểm tra thư mục `assets/` đã được commit (`git ls-files assets`).

---

## 4. Tùy chỉnh

### Thêm email / LinkedIn / Facebook

Trong `README.md`, mục `05 — Say hi`, tìm dòng:

```html
<!-- Add your email / LinkedIn / Facebook badge here -->
```

Thay bằng badge tương ứng, ví dụ:

```html
<a href="mailto:ban@example.com"><img src="https://img.shields.io/badge/Email-0A0B0D?style=flat-square&logo=gmail&logoColor=C6FF4A" alt="Email"></a>
<a href="https://www.linkedin.com/in/username"><img src="https://img.shields.io/badge/LinkedIn-0A0B0D?style=flat-square&logo=linkedin&logoColor=C6FF4A" alt="LinkedIn"></a>
```

### Đổi màu nhấn

Màu lime hiện tại là `C6FF4A`, nền tối là `0A0B0D`. Muốn đổi, sửa đồng loạt trong:

- `README.md` (badge + query `title_color`, `icon_color`, `ring`, `fire`...)
- `assets/hero-dark.svg`
- `assets/hero-light.svg`

### Sửa dự án / link

Nằm ở mục `03 — Selected work` trong `README.md`. Các link hiện tại đều trỏ đúng repo của mày.

---

## 5. Việc nên làm thêm trên GitHub (quan trọng)

Profile đẹp nhưng repo trống mô tả thì vẫn loãng. Làm nhanh 4 việc này:

1. **Pin 6 repo** đẹp nhất: profile → **Customize your pins** → chọn `quan-ly-khach-hang-to-sheets`, `V-flix`, `api-Vflix`, `mobile-app-flix`, `thiep-cuoi-hong-ngoc`, `Project_IV_FE`.
2. **Thêm description + topics** cho từng repo (nút ⚙️ cạnh About). Ví dụ SheetDesk:
   - Description: `CRM dashboard on top of Google Sheets — Next.js 16, React 19, Tailwind v4`
   - Topics: `nextjs`, `typescript`, `crm`, `google-sheets`, `shadcn-ui`
   - Website: `https://quan-ly-khach-hang-to-sheets.vercel.app`
3. **Cập nhật profile bio**: tên, mô tả ngắn, location, website (nếu có).
4. Bật **Include private contributions** trong Settings → Profile nếu có đóng góp private.

---

## 6. Lưu ý

- Stats là widget bên thứ ba (`github-profile-summary-cards`). Đôi khi load chậm — reload là được. Repo cần public và có commit để có số liệu.
- Ảnh banner nằm trong repo, không phụ thuộc dịch vụ ngoài.
- Nếu đổi username sau này: đổi tên repo, đổi `username=TranLoiIT` trong các URL stats và link GitHub trong README.
- Muốn xem trước banner: mở trực tiếp `assets/hero-dark.svg` hoặc `assets/hero-light.svg` bằng trình duyệt (double-click).
