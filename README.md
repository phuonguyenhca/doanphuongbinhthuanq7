const express = require("express");
const app = express();

app.use(express.json()); // Middleware xử lý JSON

// Định nghĩa Webhook API
app.post("/webhook", (req, res) => {
    console.log("\ud83d\udce9 Nhận webhook từ Zalo:", req.body); // Log dữ liệu nhận được
    res.status(200).send("Webhook nhận thành công!");
});

// Chạy server trên cổng 3000 hoặc biến môi trường
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
    console.log(`\ud83d\ude80 Webhook server đang chạy tại http://localhost:${PORT}`);
});
