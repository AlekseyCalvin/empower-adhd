<p align="center">
  <img src="./logo.png" alt="i-have-adhd" width="140" />
</p>
<p align="center">
  <strong align="center">Kết quả đầu ra thân thiện với ADHD. Không cần chẩn đoán ADHD!</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/ayghri/i-have-adhd?style=flat" alt="Giấy phép"></a>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a> ·
  <strong>Tiếng Việt</strong>
</p>


## Cài đặt

<details>
<summary><strong>Claude Code</strong></summary>

```bash
claude plugin marketplace add ayghri/i-have-adhd
claude plugin install i-have-adhd@i-have-adhd
```

Sau đó gõ `/i-have-adhd`. Không cần clone về máy: Claude Code sẽ tự tải repo và cập nhật.

Bạn muốn tự động bật trong mọi phiên làm việc? Chạy `touch ~/.claude/.i-have-adhd-always` (xem [INSTALL.md](./INSTALL.md)).

</details>

<details>
<summary><strong>Codex</strong></summary>

```bash
codex plugin marketplace add ayghri/i-have-adhd --ref main
codex plugin add i-have-adhd@i-have-adhd
```

Sau đó gõ `$i-have-adhd` để áp dụng phong cách đầu ra này một cách rõ ràng. Skill cũng có thể được tự động kích hoạt khi Codex thấy công việc phù hợp.

</details>

Hướng dẫn cài đặt cho các trợ lý lập trình khác có tại [INSTALL.md](./INSTALL.md).

## Tính năng

Một skill dành cho trợ lý lập trình giúp nó không chôn vùi câu trả lời trong những đoạn văn dài dòng. Hành động trước. Các bước đánh số. Không câu nệ kiểu "Hy vọng điều này sẽ giúp ích cho bạn!"


## Những gì thay đổi


<table>
<tr>
<td width="50%">

## Trước khi dùng

> Câu hỏi rất hay! Để tôi suy nghĩ về điều này. Luồng xác thực của bạn có một vài phần di chuyển: middleware, xác thực token và xử lý cookie. Nhìn vào `src/auth.ts`, hàm `verifyToken` (khoảng dòng 42-58) có vẻ đang dùng API `jsonwebtoken` cũ hơn. Một cách tiếp cận là cập nhật package và viết lại hàm đó. Sau khi thay đổi, bạn sẽ muốn chạy các bài kiểm tra xác thực để xác nhận không có gì bị hỏng. Nhân tiện, bạn cũng có thể muốn nhìn vào phiên bản các thư viện phụ thuộc tổng thể. Hy vọng điều này giúp ích! Cho tôi biết nếu bạn muốn đi sâu hơn.

</td>

<td width="50%">

## Sau khi dùng

> Chạy `npm install jsonwebtoken@latest`, sau đó sửa `src/auth.ts:42`.
>
> 1. Mở `src/auth.ts`
> 2. Thay thế `verifyToken` (dòng 42–58) bằng đoạn mã bên dưới
> 3. Chạy `npm test -- auth.spec.ts`
>
> Bước tiếp theo: dán dòng báo lỗi đầu tiên nếu có bài kiểm tra nào thất bại.

</td>
</tr>
</table>


## Các quy tắc

10 quy tắc. Nội dung chi tiết tại [SKILL.md](./skills/i-have-adhd/SKILL.md).

1. Bắt đầu ngay bằng hành động tiếp theo.
2. Đánh số các công việc nhiều bước.
3. Kết thúc bằng một bước tiếp theo cụ thể.
4. Loại bỏ các nội dung lan man.
5. Nhắc lại trạng thái hiện tại ở mỗi lượt.
6. Ước tính thời gian cụ thể (tính bằng phút, không nói chung chung).
7. Hiển thị tiến trình rõ ràng.
8. Báo lỗi một cách khách quan, thẳng thắn.
9. Giới hạn danh sách tối đa 5 mục.
10. Không lời mở đầu. Không tóm tắt. Không lời chào kết.

## Tùy chỉnh

Fork repo, chỉnh sửa `skills/i-have-adhd/SKILL.md`, sau đó chuyển sang dùng bản của bạn:

```bash
claude plugin uninstall i-have-adhd            # gỡ bản chính trước:
claude plugin marketplace remove i-have-adhd   # bản fork và bản chính dùng chung tên
claude plugin marketplace add <username-của-bạn>/i-have-adhd
claude plugin install i-have-adhd@i-have-adhd
```

Khởi động lại Claude Code, sau đó gọi lại `/i-have-adhd`.

## Ghi nhận tác giả (Credits)

Dựa trên cuốn sách *The Adult ADHD Tool Kit* của J. Russell Ramsay và Anthony L. Rostain. Được điều chỉnh phù hợp với cách LLM nên phản hồi, thay vì cách con người tự sắp xếp thời gian.

## Giấy phép

MIT.

Bấm ⭐ Star nếu nó giúp bạn tiết kiệm được một lần cuộn trang qua câu "Câu hỏi rất hay!"
