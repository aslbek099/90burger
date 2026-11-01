90 BURGER SHOVOT — Netlify uchun to'liq paket
=============================================

Papka tuzilishi:
  public/index.html            — sayt (mijoz + "Sotuvchi uchun" paneli)
  netlify/functions/order.mjs  — buyurtmani qabul qiladi (/api/order)
  netlify/functions/orders.mjs — sotuvchi paneli uchun ro'yxat/holat/o'chirish (/api/orders)
  package.json, netlify.toml   — sozlamalar

MUHIM: oddiy "papkani sudrab tashlash" (drag & drop) bu paketda ISHLAMAYDI,
chunki funksiyalar @netlify/blobs paketini talab qiladi. Ikki yo'ldan biri:

A) GitHub orqali (eng oson)
   1. GitHub'da yangi repozitoriy oching va shu papkadagi hamma narsani yuklang.
   2. Netlify > Add new site > Import from Git > shu repozitoriyni tanlang.
      (Build command bo'sh, Publish directory: public — netlify.toml'da yozilgan.)
   3. Pastdagi muhit o'zgaruvchilarini qo'ying va "Deploy" qiling.

B) Netlify CLI orqali
   npm install -g netlify-cli
   npm install
   netlify login
   netlify link          (mavjud 90burgeruz saytini tanlang)
   netlify deploy --prod

Muhit o'zgaruvchilari (Site configuration > Environment variables):
   ADMIN_PASSWORD      — sotuvchi paneli paroli (qo'ymasangiz 1234 bo'ladi — o'zgartiring!)
   TELEGRAM_BOT_TOKEN  — (ixtiyoriy) @BotFather bergan token
   TELEGRAM_CHAT_ID    — (ixtiyoriy) buyurtmalar keladigan chat ID

Telegram qo'yilsa, har bir buyurtma Telegram'ga ham xabar bo'lib keladi.
Panel va Telegram bir-biriga bog'liq emas: ikkalasi ham, yoki istalgan bittasi ishlaydi.
