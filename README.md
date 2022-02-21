# ChongPhanDong-API
API bao gồm các trang web tuyên truyền nội dung phản động để ngăn ngừa việc tuyên truyền nội dung phản động trên không gian mạng.

(API được cập nhật bằng tay nên có thể không đầy đủ. Tính năng đóng góp sẽ được phát triển sau.)

Chi tiết API:
```
Endpoint: https://chongphandong.cookiegmvn.xyz/api/v1/youtube/check
Params:
  url: Liên kết tới 1 video YouTube (kể cả link embed)
Example: https://chongphandong.cookiegmvn.xyz/api/v1/youtube/check?url=https://www.youtube.com/watch?v=wILjqOlsBjY
```
Data trả về (JSON)
```
code: Trạng thái của request biểu thị bằng HTTP Response Code (200/400)
  Data trả về: 
    200 khi đầy đủ và API hoạt động bình thường
    400 khi thiếu dữ liệu cần thiết
detected: Trạng thái của API đã phát hiện kênh nằm trong blacklist (true/false)
  Data trả về khi detected là true:
    channelName: Tên kênh chứa nội dung phản động
    channelOrg: Tổ chức phản động đứng sau kênh này
```
### Ví dụ API: 
Example: https://chongphandong.cookiegmvn.xyz/api/v1/youtube/check?url=https://www.youtube.com/watch?v=wILjqOlsBjY
Data trả về (JSON):
```json
{"code":200,"detected":true,"channelName":"N10Tv","channelOrg":"Việt Tân"}
```

Example: https://chongphandong.cookiegmvn.xyz/api/v1/youtube/check?url=https://www.youtube.com/watch?v=o6FnV96PXD8
```json
{"code":200,"detected":false}
```
