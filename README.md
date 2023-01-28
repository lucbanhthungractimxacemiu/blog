# Tôi đã khiến người lừa đảo bạn tôi khóc thét

## DES
* Loanh quanh hồi c2 tôi có một người bạn bị lừa đảo bằng cách mua acc game tạo sms gì đấy nhưng quan trọng bạn tôi đã chuyển cho kẻ xấu tiền trước và bị scam.

## MAIN
- Với một chút kiến thức về Social engineering (một hình thức tấn công mạng) và code ghẻ tôi đã đưa ra một vài phương hướng tấn công nhắm lấy thông tin của kẻ xấu.

-- Thăm dò :

* Với vài lời cơ bản tôi biết bạn ấy có sửa dụng một website nhận mã otp để tạo các tài khoản ảo từ đó tôi dẫn dụ đến web của tôi

![scam](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgR0xGkELMoPWBWwwo72Ey0ujPBCD6x746cTRzrIlSZ0kW82uwWmANsaVhVpkcrh_8RH1NDkjAZP92eS3wXx0vrnCPQsBNm00fZK2IhivEG_gLf3fkKKqa4zOpqgjjukLxfiK_bn2WpeYlgOSLe-AKNy0nsZsoCOmnD15WNszojlgVI-wAi2WwMgJ4I/s320/image_2022-11-15_115310353.png)

-- Tiến hành phân tích và đưa ra các phương thức tấn công

 * Một vòng ngó qua thì tôi thấy có các trang như IP Logger .. có thể lấy vài thông tin như trình duyệt thiết bị user-agent và ip của người dùng
[REMOTE_ADDR] chỉ qua việc click vào web site để log lại [nhưng tôi muốn nhiều hơn thế]

### SRC (JAVASCRIPT)

* Nếu bạn đã học qua js bạn sẽ biết google map và các web check webcam hoặc
chụp ảnh scan qr đúng không.

* Ta có thể truy suất camera nếu thiết bị có hỗ trợ thông qua tìm api camera qua navigator bằng đoạn script sau.

![maps](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHvvUpd-D7qvlblXzSY6uU5frRn4gM5ZyOjTN4te9-oxi9d7I3vYR3E6jAFEaw0y27ojnRV3aWdjdKYbjWCINRlCkrZemqF4lKmYex9ikX2w60adDNh0eD_Mk4DGXQ6iaB6CYcNvrsKhBm0dDefISvxjVYmDixUpzIiauZ8Vsr1i6WCa6AYhaOdTne/w640-h261/image_2022-11-15_120312374.png)

* Ngoài ra trong navigator còn có một api geolocation để lấy định vị bằng cách đưa ra toạ độ gồm Latitude(Vĩ Độ), Longitude(Kinh độ) từ đó dóng lên địa chỉ vật lý của mình trên google map với sai số cực ít ~ vài mét.

![nativigator](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDOgbwyz4oMswof8B_mPK28j1rRj_sAFgHzCTH4_XsvG6Ep1cEKi-IBNYmdg_Jg0CMHI8hBgtlAHzzqCuaUGeIe46_I-FrxqvaznieUtE7sx9bYsh-4m8J6MQ6zvGKc7NZ0ytA2tyjsgnQe8oRJgxZ8Ww8A7dDFQuF_Lw1an9fS5hlbt0N1D10zmOe/w640-h402/image_2022-11-15_121825525.png)

### Social engineering + Code

* Mạo danh 1 trang reg sms hoàn hảo để đánh lừa nạn nhân( vì lâu rồi mất code cũ nên tôi demo lại nhanh phèn phèn )

![fake](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhQPfx8OnaP6VQb1POpm3zpLvqQfr8FjwX5NMtKR-76CSaA-GSXBhyYf8qWnQ0Xb3lEBS6a0cFmKV-9XGnaS0jqTC-sH5279VH7hNYzNxC2Q4peI8y1hdsxgeRzJAs29LbraR4SLfX5mNitefvvP7QoPHZQAsDKN1gjbcmyHeak-XJavcP7IijZnXk3/w640-h324/image_2022-11-15_122444372.png)

* Phần tạo tài khoản sẽ là button gửi hình ảnh từ camera trước và gửi địa chỉ thật

![button](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjh-LqjZd7znhIoJlCUt8Fh2QR_0TNxO6mFAVlTzVmW5SedPgxMSqt59gi88NzyrJqins4JFWVlPW0mybY2orzFAHFHQhZqI5ow30QmHULyJYuACfGuTPsVyAwqmeFpHFogUYB3r59WnvIB_4OQno5P0wPMMw4ER41zM54RLe7paFevk44vqlcKMNY7/w640-h320/image_2022-11-15_122834760.png)

* Lưu ý các api này(định vị và camera) cần người dùng cấp quyền -> [nên tạo một web chuyên nghiệp và đến phần reg sms mới yêu cầu thông tin để đủ quyền reg nhé này web demo thôi] (Thường thì người dùng trên điện thoại sẽ quen tay bấm allow mà không biết nó là gì cả)

![allow](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiwc3bz_jYXuSDxDzRKp5ibwrqtxTLAI2T7cFLassnXTsVX1V_Uf0EWYRrNClNikyiUVsOS5bODjDHl_GBBJxtMfd3GtahvKjjPAeGNVqNqk-eXt8-bKtO85gDdfqi5D5RkU3g43Vw2HIGqbTcUx9LjzB8KU-1WNMIdreCUN9C4hQc3HkJql29fdKDh/w217-h128/image_2022-11-15_122914460.png)

* Vì api này hoạt động ổn định trên chrome nên tôi cũng code thêm một chức năng get user-agent để chuyển hướng người dùng vào web 404 nếu và không đúng duyệt tôi yêu cầu.

![chrome](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjy2R_Avu6ePLNYTGofKK2Fc6daAEwQ0WNEQDItN1ncsxCTAw11C5nFtUWmk6IZFJtImUG9yeE_3g73SRlVULOAl3cIIjIIOIcwJFE67qqqtgg827IkoVEnAzKvYKblOyPwXIXVwEMcUJNPIfUWFXy15vIr2uB2eWmwvNDd5hP79wEEUhoIV-OA5GbD/w640-h316/image_2022-11-15_123223246.png)

* ==> tiến hành gửi link cho kẻ xấu và tiến hành thuyết phục. 
* Sau 3 ngày ròng rã tôi cũng lượm lại chút trái ngọt
*  - Kẻ xấu đã thực sự cho phép các quyền và tôi đã lấy được ảnh và địa chỉ thật của kẻ xấu ;D

![map](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjIUN2rk7up4VTg1FoI8zzY2nXR9kJziJ-uZ1TKxmMi5SkXJ7mF4qtlSRXJDbXePq4-IZTBvJ77V4eKXJG7g_JDDIEo2zw3JhxLPJnHaksfjV1qL9KeR26Icc3I0NjNle8lpi7fIXh3HOE11pFJLR01rR6ciobbXtI7v_61je9OkFlQI5eoW9zielLH/w640-h316/image_2022-11-15_123610973.png)

* Chân dung kẻ xấu đã lừa đảo bạn tôi lưu ý ảnh đã được che đi để đỡ bị ảnh hưởng vi phạm

![niem](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgze7RN27Quww4YWwHV6cJCETtVO0QQxaTwIQNjDxhkS_42EnP3GpUT8fH6ujjyrNewHWFRDd0g5RTuSz-qCKF8mLn9H29LLBcumEZjMuIdKxsvY9dYKTrSU2AIiFQNz4iZMVIQvhoCf14VJJdq3rDXl1W1GeuOpOef6EZHZqHa2pKg-ZUTQSRXyCHt/s320/image_2022-11-15_123725438.png)

## END

-- Qua bài viết ta được được một số điều : 

* Học code không bao giờ là đủ
* Social engineering là một kỹ thuật nâng cao
* Ngoài ra ta còn phải đề phòng từ những web lạ để không bị dính sai lầm như cậu bé trên ảnh.

thanks for reading | khanhvu @ nglennk developer / pen





