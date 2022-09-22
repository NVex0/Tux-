# Tux-

Từ challenge này là mình reveal flag luôn :D.
Đầu tiên mình kiểm tra file type của ảnh Tux.jpg, thấy file ảnh chứa 1 comment. 

`comment: "ICAgICAgUGFzc3dvcmQ6IExpbnV4MTIzNDUK"`

Hmm, nếu tiếp xúc nhiều bạn có thể nhận ra đây là mã base64. (Hoặc là đơn giản hơn là challenge của ông @kcbowhunter toàn dùng base64 thôi :v)

mình decode nó ra:

`echo ICAgICAgUGFzc3dvcmQ6IExpbnV4MTIzNDUK | base64 -d`

-> `Password: Linux12345`

Hmm, password của 1 cái gì đó sao?

Tiếp tục mình dùng:

`binwalk -e Tux.jpg` 

Bà extract được 2 file: 1 file zip và 1 file flag. 

Mở file zip sẽ yêu cầu và khi thử nhập pass ở trên thì nó thành công, ye, và lấy được flag rồi :D

`7z e 1570.zip`

![Screenshot (2438)](https://user-images.githubusercontent.com/113530029/191783300-de62712b-7433-481f-b28a-55a2c39f8e2d.png)

`cat flag`

`Flag: CTFlearn{Linux_Is_Awesome}`

