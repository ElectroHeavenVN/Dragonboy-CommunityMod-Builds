# Dragonboy-CommunityMod-Builds - VI | [EN](README_EN.md)
Tự động checkout và biên dịch [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) bằng GitHub Actions hàng ngày. Có thể chạy thủ công khi cần thiết.

Các nền tảng được hỗ trợ: Windows, Linux, Android. Hệ điều hành iOS sẽ không được hỗ trợ do những giới hạn về thực thi mã động được tạo trong thời gian chạy.
## Tải xuống
Có 2 phương pháp để tải xuống:
<details>
<summary>Phương pháp 1 (Không yêu cầu tài khoản GitHub): Tải xuống thông qua Release</summary>

- Chọn [Latest build](../../releases/tag/latest) trong phần [Releases](../../releases).
- Chọn file phù hợp với hệ điều hành của bạn trong phần `Assets`.

</details>
<details>
<summary>Phương pháp 2 <u><b>(yêu cầu có tài khoản GitHub)</b></u>: Tải xuống thông qua Artifact</summary>

- Chọn tab [Actions](../../actions) ở trên cùng.
- Chọn workflow [Biên dịch QLTK và Game](../../actions/workflows/build.yml) ở danh sách workflow bên trái.
- Chọn `workflow run` chạy thành công mới nhất.
- Chọn file phù hợp với hệ điều hành của bạn trong phần `Artifacts`.
  
</details>

## Setup
Để tự build dự án [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) bằng Github Actions, bạn cần làm theo các bước sau:
- Fork repository này
- Vào phần `Settings` của repository bạn vừa fork, sau đó chọn phần `Actions` trong phần `Secrets and variables`.
- Tại phần `Repository secrets`, nhấn `New repository secrets`.
- Ở trường `Name`, nhập `UNITY_EMAIL`, trường `Secret` nhập email Unity của bạn.
- Nhấn `Add secret` để thêm secret.
- Làm lại các bước trên với giá trị của trường `Name` và trường `Secret` lần lượt như sau:
    + `UNITY_PASSWORD`: mật khẩu Unity của bạn
    + `UNITY_LICENSE`: nội dung tệp `Unity_lic.ulf` (tham khảo tài liệu của [GameCI](https://game.ci/) [tại đây](https://game.ci/docs/github/activation/#activating-a-license-file) để biết đường dẫn tệp `Unity_lic.ulf`)
    + `ANDROID_KEYSTORE_BASE64`: nội dung tệp keystore đã mã hóa base64 của bạn
    + `ANDROID_KEYSTORE_PASS`: mật khẩu keystore của bạn
    + `ANDROID_KEYALIAS_NAME`: tên alias trong tệp keystore của bạn
    + `ANDROID_KEYALIAS_PASS`: mật khẩu alias trong tệp keystore của bạn
    + (Tùy chọn) `DISCORD_WEBHOOK`: URL Webhook Discord để thông báo kết quả biên dịch

Tham khảo phần [Deploy to Google Play](https://game.ci/docs/github/deployment/android/) của [GameCI](https://game.ci/) để biết thêm thông tin về phần keystore của Android.
