
# StackForge PaaS – Nền tảng triển khai ứng dụng doanh nghiệp

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/Mahiru-Chan-Phuc/PaaS/blob/main/LICENSE)
[![Version](https://img.shields.io/badge/version-3.0.0-brightgreen)](https://github.com/Mahiru-Chan-Phuc/PaaS)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/Mahiru-Chan-Phuc/PaaS/pulls)

**StackForge PaaS** là giao diện quản lý nền tảng Platform-as-a-Service được thiết kế dành riêng cho đội ngũ phát triển và vận hành. Dự án cung cấp một dashboard hiện đại, trực quan để quản lý ứng dụng, theo dõi tài nguyên, triển khai tự động và giám sát hệ thống theo thời gian thực.

## ✨ Tính năng chính

### 🚀 **Quản lý ứng dụng**
- **Dashboard tổng quan**: Xem nhanh số lượng ứng dụng, request/giây, thời gian phản hồi, tỷ lệ lỗi
- **Danh sách ứng dụng chi tiết**: Theo dõi trạng thái (running/building/crash), runtime, CPU, memory, uptime
- **Biểu đồ tài nguyên**: Trực quan hóa mức sử dụng CPU, RAM, DISK, Network

### 🔄 **Triển khai & Pipeline**
- **Quy trình CI/CD 6 bước**: Clone → Install → Test → Build → Push → Deploy
- **Theo dõi build real-time**: Cập nhật trạng thái từng bước với thời gian thực
- **Lịch sử deployment**: Xem lại toàn bộ các lần triển khai trước đó

### 📊 **Giám sát & Logging**
- **Log stream trực tiếp**: Xem log theo thời gian thực, hỗ trợ filter theo level (INFO/WARN/ERROR)
- **Activity feed**: Theo dõi mọi thay đổi (deploy, scale, cập nhật config, cảnh báo)
- **Metrics charts**: Biểu đồ traffic 24h, resource rings

### ⚙️ **Quản lý cấu hình**
- **Environment variables**: Quản lý biến môi trường (public/secret) với tính năng ẩn/hiện
- **Domains & SSL**: Thêm domain, tự động gia hạn SSL Let's Encrypt
- **Auto Scaling**: Cấu hình scale ngang dựa trên CPU/memory, policy chi tiết
- **Instance groups**: Xem danh sách instances và mức sử dụng tài nguyên

### 🛠️ **Addons & Tích hợp**
- **Databases**: Quản lý PostgreSQL, MongoDB
- **Redis Cache**: Cấu hình caching layer
- **Message Queue**: Hỗ trợ RabbitMQ, Kafka
- **Object Storage**: Tích hợp S3-compatible storage

## 🏗️ **Kiến trúc công nghệ**

### **Frontend**
- **HTML5/CSS3 thuần**: Không sử dụng framework CSS, tự xây dựng toàn bộ component
- **CSS Variables**: Quản lý màu sắc và kích thước tập trung
- **Flexbox/Grid**: Layout linh hoạt, responsive trên nhiều thiết bị
- **Fonts**: JetBrains Mono (code) + Familjen Grotesk (text)
- **Icons**: Unicode symbols + emoji, không dùng icon library

### **JavaScript**
- **DOM manipulation thuần**: Không jQuery, không framework
- **Simulation data**: Dữ liệu giả lập cho apps, builds, logs
- **Real-time effects**: Stream log animation, pipeline progress
- **Toast notifications**: Hệ thống thông báo tùy chỉnh
- **Modal dialog**: Form deploy với 3 tabs (Source/Runtime/Settings)

### **Tính năng đặc biệt**
- **Noise texture**: Hiệu ứng nhiễu nền tạo chiều sâu
- **Grid lines**: Đường kẻ mờ tạo cảm giác "tech"
- **Glow animation**: Hiệu ứng phát sáng cho các phần tử quan trọng
- **Sparklines**: Biểu đồ nhỏ trong metric cards
- **Custom scrollbar**: Thanh cuộn được thiết kế đồng bộ


## 🚀 **Hướng dẫn cài đặt & chạy**

### Yêu cầu hệ thống
- Trình duyệt web hiện đại (Chrome, Firefox, Edge, Safari)
- Kết nối internet (để tải Google Fonts)

### Các bước thực hiện

1. **Clone repository**
```bash
git clone https://github.com/Mahiru-Chan-Phuc/PaaS.git
cd PaaS
```

2. **Mở ứng dụng**
- Cách 1: Mở trực tiếp file `index.html` bằng trình duyệt
- Cách 2: Dùng Live Server (nếu dùng VS Code)
```bash
npx live-server
```

3. **Khám phá tính năng**
- Dashboard mặc định hiển thị view Overview
- Click vào menu sidebar để chuyển đổi các view khác nhau
- Nhấn "Deploy App" để mở modal tạo ứng dụng mới
- Xem log real-time tại tab Logs

## 🎯 **Các view chính**

| View | Mô tả | Đường dẫn (trong app) |
|------|-------|----------------------|
| **Overview** | Dashboard tổng quan với metrics, apps table, activity | `#dashboard` |
| **Applications** | Danh sách đầy đủ 12 ứng dụng + filter | `#apps` |
| **Deployments** | Lịch sử build chi tiết | `#deploys` |
| **Logs** | Stream log real-time với filter level | `#logs` |
| **Environments** | Quản lý biến môi trường | `#envs` |
| **Domains & SSL** | Quản lý domain, chứng chỉ SSL | `#domains` |
| **Auto Scaling** | Cấu hình scaling policy, instance groups | `#scaling` |

## 🧪 **Dữ liệu giả lập**

Dự án sử dụng dữ liệu mẫu để minh họa:

### **Ứng dụng (12 apps)**
- `api-gateway` (Node 20) - running
- `auth-service` (Go 1.22) - running
- `data-pipeline` (Python 3.12) - building
- `notification-svc` (Node 18) - crash
- `frontend-web` (Node 20) - running
- Và 7 ứng dụng khác

### **Build history (10 builds)**
- Mỗi build có: số hiệu, commit, message, trạng thái, thời gian, người thực hiện

### **Log messages (20+ dòng)**
- INFO, WARN, ERROR, DEBUG, OK levels
- Các loại log: request, database, cache, deploy, SSL, health check

## 🔧 **Tùy chỉnh & Phát triển**

### **Thay đổi theme màu**
Chỉnh sửa biến CSS trong `:root`:
```css
:root {
  --accent: #00e5ff;    /* Cyan - primary accent */
  --accent2: #00ff9d;   /* Green - secondary */
  --violet: #a78bfa;    /* Purple - tertiary */
  --danger: #ff3d5a;    /* Red - errors */
  --warn: #ffab00;       /* Yellow - warnings */
}
```

### **Thêm ứng dụng mới**
Sửa mảng `apps` trong JavaScript:
```javascript
const apps = [
  { name: 'your-app', url: 'your-app.stackforge.io', status: 'running', ... },
  // ...
];
```

### **Tùy chỉnh log stream**
Sửa mảng `logMessages` để thay đổi nội dung log:
```javascript
const logMessages = [
  {l:'info', m:'Your custom log message here'},
  // ...
];
```

### **Thay đổi pipeline steps**
Sửa trong HTML:
```html
<div class="pipeline-step">...</div>
```

## 🌟 **Điểm mạnh**

✅ **Không phụ thuộc framework**: Dễ dàng tích hợp vào bất kỳ dự án nào  
✅ **Hiệu suất cao**: CSS/JS thuần, không bundle quá khổ  
✅ **Responsive**: Hoạt động tốt trên desktop, tablet  
✅ **Dễ tùy chỉnh**: Code sạch, comment rõ ràng  
✅ **UX tốt**: Animation mượt, phản hồi tức thì  
✅ **Bảo mật**: Không gửi dữ liệu ra ngoài, hoàn toàn client-side  

## 📌 **Kế hoạch phát triển**

- [ ] **Backend API**: Kết nối với server thật (Node.js/Express)
- [ ] **Authentication**: Đăng nhập bằng GitHub, Google
- [ ] **Database**: Lưu trữ thông tin ứng dụng
- [ ] **WebSocket**: Log real-time thật (không giả lập)
- [ ] **Dark/Light mode**: Chuyển đổi theme
- [ ] **Mobile version**: Tối ưu cho điện thoại
- [ ] **Multi-language**: Hỗ trợ tiếng Anh, tiếng Việt
- [ ] **Export metrics**: Xuất dữ liệu ra CSV/PDF

## 🤝 **Đóng góp**

Mọi đóng góp đều được chào đón! Nếu bạn muốn cải thiện dự án:

1. Fork repository
2. Tạo branch mới (`git checkout -b feature/AmazingFeature`)
3. Commit thay đổi (`git commit -m 'Add some AmazingFeature'`)
4. Push lên branch (`git push origin feature/AmazingFeature`)
5. Mở Pull Request

## 📄 **Giấy phép**

Dự án được phân phối dưới giấy phép MIT. Xem file `LICENSE` để biết thêm chi tiết.

## 📞 **Liên hệ**

**Tác giả**: Le Thanh Phuc (Mahiru-Chan-Phuc)

- GitHub: [@Mahiru-Chan-Phuc](https://github.com/Mahiru-Chan-Phuc)
- Email: (anhem999111@gmail.com)

---

## 🙏 **Lời cảm ơn**

Cảm ơn bạn đã quan tâm đến StackForge PaaS. Dự án được xây dựng với mục đích học tập và minh họa, lấy cảm hứng từ các nền tảng:

- [Heroku](https://www.heroku.com/)
- [Vercel](https://vercel.com/)
- [Netlify](https://www.netlify.com/)
- [Railway](https://railway.app/)

---

**StackForge PaaS** - *Forge your stack, deploy with ease* ⚡
