# Dragonboy-CommunityMod-Builds
tự động build [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) bằng Github Actions.
Các nền tảng được hỗ trợ: Windows, Linux, Android
## Tải xuống
Chọn tab [Actions](https://github.com/ElectroHeavenVN/Dragonboy-CommunityMod-Builds/actions) sau đó chọn workflow chạy thành công mới nhất. Chọn file phù hợp với hệ điều hành của bạn trong phần `Artifacts`.

## Setup
Để tự build dự án [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) bằng Github Actions, bạn cần làm theo các bước sau:
- Fork repository này
- Vào phần `Settings` của repository bạn vừa fork, sau đó chọn phần `Actions` trong phần `Secrets and variables`
- Tại phần `Repository secrets`, nhấn `New repository secrets`
- Ở trường `Name`, nhập `UNITY_EMAIL`, trường `Secret` là email Unity của bạn
- Nhấn `Add secret` để thêm secret
- Làm lại các bước trên với giá trị của trường `Name` và trường `Secret` lần lượt như sau:
    + `UNITY_PASSWORD`: mật khẩu Unity của bạn
    + `UNITY_LICENSE`: nội dung tệp `Unity_lic.ulf` (tham khảo tài liệu của [GameCI](https://game.ci/) [tại đây](https://game.ci/docs/github/activation/#activating-a-license-file) để biết đường dẫn tệp `Unity_lic.ulf`)
    + `ANDROID_KEYSTORE_BASE64`: nội dung tệp keystore đã mã hóa base64 của bạn
    + `ANDROID_KEYSTORE_PASS`: mật khẩu keystore của bạn
    + `ANDROID_KEYALIAS_NAME`: tên alias trong tệp keystore của bạn
    + `ANDROID_KEYALIAS_PASS`: mật khẩu alias trong tệp keystore của bạn

Tham khảo phần [Deploy to Google Play](https://game.ci/docs/github/deployment/android/) của [GameCI](https://game.ci/) để biết thêm thông tin về phần keystore của Android.