# affine_cipher
Affine cipher và chứng minh linh tinh

Hôm nay t tìm hiểu về Affine cipher, cách hoạt động như thế này:
- Chọn khóa key = {a, b} (a, b bất kì thuộc N && gcd(a, 26) = 1 mới tồn tại a^(-1)%26)
- Với từng kí tự lần lượt, gọi là x, mã hóa: y = (a*x + b) % 26
- Với từng kí tự lần lượt, gọi là y, giải mã: x = (y - b)/a % 26 = (y - b)*a^(-1) % 26

Sau khi triển khai thuật toán thành code, t mới tự hỏi rằng "tại sao gcd(a, 26) lại phải bằng 1 thì a^(-1)%26 mới tồn tại", sau đó t khái quát nó lên thành "tại sao gcd(a, m) lại phải bằng 1 thì a^(-1)%m mới tồn tại", sau 10' nháp các kiểu, thì đây là cách t chứng minh:
- T chứng minh bằng phản chứng
- Cho gcd(a, m) = k (k != 1)
- T đang muốn a * a^(-1) % m = 1 <=> a * a^(-1) = m * h + 1 (h là số nguyên dương bất kì) <=> k * p * a^(-1) = k * f * h + 1 (p = a/k, f = m/k)
- Sau một lúc chiêm nghiệm, t mới nhận ra rằng đẳng thức bên trái (tức k * p * a^(-1)) là bội của k, mà bội của k không bao giờ có dạng k * f * h + 1 TRỪ KHI k = 1
- Vậy kết luận: chỉ có k = 1 (gcd(a, m) = 1) mới có thể khiến cho a * a^(-1) % m = 1

Thế thôi ~~
