# S.d.m
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8" />
  <title>ساخت QR کد ساده</title>
  <style>
    body { font-family: Tahoma, sans-serif; padding: 20px; background: #f0f0f0; }
    h1 { color: #333; }
    #qrcode { margin-top: 20px; }
    input, button { padding: 10px; font-size: 16px; }
    button { cursor: pointer; }
  </style>
</head>
<body>

  <h1>ساخت QR کد آنلاین</h1>

  <input type="text" id="text" placeholder="متن یا لینک را وارد کنید" style="width: 300px;" />
  <button onclick="generateQR()">ساخت QR کد</button>

  <div id="qrcode"></div>

  <!-- کتابخانه QRCode.js -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

  <script>
    function generateQR() {
      var text = document.getElementById('text').value.trim();
      if(text === '') {
        alert('لطفا متن یا لینک را وارد کنید!');
        return;
      }
      // پاک کردن QR کد قبلی اگر وجود دارد
      document.getElementById('qrcode').innerHTML = '';

      // ساخت QR کد جدید
      new QRCode(document.getElementById('qrcode'), {
        text: text,
        width: 200,
        height: 200,
        colorDark : "#000000",
        colorLight : "#ffffff",
      });
    }
  </script>

</body>
</html>
