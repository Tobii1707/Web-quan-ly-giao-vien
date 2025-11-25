<div align="center">

# 🎓 PHẦN MỀM QUẢN LÝ & TÍNH TIỀN DẠY GIÁO VIÊN
### Đại học Phenikaa - Khoa Công Nghệ Thông Tin

![Version](https://img.shields.io/badge/Version-1.0.0-blue.svg?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-success.svg?style=flat-square)
![Team](https://img.shields.io/badge/Team-Group_10-orange.svg?style=flat-square)

---

<p align="center">
    <em>"Giải pháp tin học hóa toàn diện quy trình quản lý đào tạo và tự động hóa tính lương giảng dạy, <br> mang lại sự chính xác, minh bạch và hiệu quả."</em>
</p>

</div>

## 📑 Mục Lục
- [Giới thiệu](#-giới-thiệu)
- [Đội ngũ phát triển](#-đội-ngũ-phát-triển)
- [Kiến trúc hệ thống](#-kiến-trúc-hệ-thống)
- [Chức năng chi tiết](#-chức-năng-chi-tiết)
- [Công nghệ sử dụng](#-công-nghệ-sử-dụng)
- [Cài đặt & Hướng dẫn](#-cài-đặt--hướng-dẫn)

---

## 📖 Giới thiệu

Dự án được xây dựng nhằm giải quyết bài toán quản lý khối lượng giảng dạy khổng lồ và quy trình tính lương phức tạp tại trường Đại học. Hệ thống thay thế phương pháp thủ công bằng quy trình khép kín: Từ lúc phân công giảng dạy (Trưởng khoa) đến khi chốt lương và thanh toán (Kế toán).

**Mục tiêu chính:**
* ✅ **Chính xác:** Loại bỏ sai sót trong tính toán hệ số, đơn giá.
* ✅ **Tốc độ:** Giảm thời gian tổng hợp báo cáo từ vài ngày xuống vài giây.
* ✅ **Minh bạch:** Giảng viên có thể tra cứu chi tiết thu nhập của mình.

---

## 👨‍💻 Đội ngũ phát triển

Dự án được phân chia rõ ràng thành 2 phân hệ lớn (**Trưởng Khoa** & **Kế Toán**) với sự phối hợp chặt chẽ giữa Backend và Frontend.

| Phân hệ (Module) | Vai trò | Thành viên | MSSV | Nhiệm vụ chính |
| :--- | :---: | :--- | :---: | :--- |
| **🎓 TRƯỞNG KHOA**<br>*(Quản lý Đào tạo)* | **Backend** | **Hà Nam Khánh** | 22010149 | Xây dựng Core API quản lý nhân sự, lớp học phần, thuật toán phân công & thống kê giờ dạy. |
| | **Frontend** | **Trần Duy Việt Hoàng** | 22010142 | Thiết kế giao diện Dashboard quản lý, Form nhập liệu lớp học, tra cứu hồ sơ giảng viên. |
| | | | | |
| **💸 KẾ TOÁN**<br>*(Quản lý Tài chính)* | **Backend** | **Dương Nhật Minh** 👑 | 22010366 | Xây dựng API cấu hình tham số lương, Engine tính toán lương tự động, xuất báo cáo tài chính. |
| | **Frontend** | **Nguyễn Thị Kiều Loan** | 22010278 | Xây dựng giao diện bảng lương, màn hình cấu hình hệ số, biểu đồ thống kê tài chính. |

---

## 🚀 Kiến trúc hệ thống

Hệ thống phân quyền chặt chẽ dựa trên vai trò người dùng:

1.  **Module Trưởng Khoa (Academic Module):** Nơi khởi tạo dữ liệu. Trưởng khoa thiết lập các lớp học, gán giáo viên. Dữ liệu này là đầu vào cho module Kế toán.
2.  **Module Kế Toán (Financial Module):** Nơi xử lý dữ liệu. Kế toán thiết lập đơn giá, hệ số và hệ thống tự động tính ra số tiền cuối cùng.

---

## ✨ Chức năng chi tiết

### 1️⃣ Phân hệ Trưởng Khoa (Backend: Nam Khánh)
> *Tập trung vào nghiệp vụ quản lý đào tạo và nhân sự.*

* **🗂 Quản lý dữ liệu nền:**
    * CRUD Khoa, Bộ môn.
    * Quản lý danh mục Bằng cấp (Thạc sĩ, Tiến sĩ...) & Chức danh.
* **👨‍🏫 Quản lý Giáo viên:**
    * Quản lý hồ sơ chi tiết giảng viên.
    * Theo dõi lịch sử công tác.
* **📚 Quản lý Lớp & Giảng dạy:**
    * Tạo và quản lý Môn học, Học kỳ.
    * Mở lớp học phần (Sĩ số, Hệ số lớp, Quy đổi tiết chuẩn).
    * **Phân công:** Gán giảng viên phụ trách lớp học.
    * **Tracking:** Theo dõi tổng số tiết dạy thực tế của từng giáo viên.

### 2️⃣ Phân hệ Kế Toán (Backend: Nhật Minh)
> *Tập trung vào nghiệp vụ tài chính và báo cáo.*

* **⚙️ Cấu hình tham số lương:**
    * Thiết lập `Đơn giá tiết dạy` theo từng kỳ/năm.
    * Cài đặt `Hệ số lương` theo bằng cấp/học hàm.
* **💰 Engine Tính lương:**
    * **Tự động:** Tính toán lương dựa trên công thức: *(Số tiết quy đổi x Đơn giá x Hệ số)*.
    * Cập nhật tức thời khi tham số thay đổi.
* **📊 Báo cáo & Thống kê:**
    * Xuất bảng lương tổng hợp theo Học kỳ/Năm học.
    * Báo cáo chi phí giảng dạy theo từng Khoa.
    * Quản lý trạng thái thanh toán (Đã chi/Chưa chi).

---

## 🛠 Công nghệ sử dụng


| Lĩnh vực | Công nghệ |
| :--- | :--- |
| **Backend** | ![Java](https://img.shields.io/badge/Java-Spring_Boot-ED8B00?style=flat-square&logo=java&logoColor=white) |
| **Frontend** | ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)  |
| **Database** | ![MySQL](https://img.shields.io/badge/MySQL-005C84?style=flat-square&logo=mysql&logoColor=white) |
| **Tools** | Postman, Git/GitHub, intellij |

---

## 📸 Hình ảnh Demo

*(Nơi dán các ảnh chụp màn hình sản phẩm của nhóm)*

<details>
  <summary><strong>Xem giao diện Trưởng Khoa</strong></summary>
  <br>
  <img src="link_anh_truong_khoa.png" alt="Giao diện Trưởng khoa" width="100%">
</details>

<details>
  <summary><strong>Xem giao diện Kế Toán</strong></summary>
  <br>
  <img src="link_anh_ke_toan.png" alt="Giao diện Kế toán" width="100%">
</details>

---

## 📝 Ghi chú

Dự án này là sản phẩm thuộc môn học **Đánh Giá Và Kiểm Định Chất Lượng Phần Mềm**, tuân thủ nghiêm ngặt các quy trình:
1.  Đặc tả yêu cầu (SRS).
2.  Phân tích & Thiết kế hệ thống (UML).
3.  Kiểm thử phần mềm (Manual & Automation Testing).

---

<div align="center">

**Code with ❤️ by Group 10 - Phenikaa University**

</div>
