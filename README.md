

## Thông tin sinh viên
- **Họ tên:** Huỳnh Thanh Nhân
- **MSSV:** 23110280


## Mô tả dự án
Hệ thống quản lý danh mục (Category Management System) được xây dựng bằng Spring Boot, Thymeleaf, và SQL Server. Dự án thực hiện đầy đủ các chức năng CRUD (Create, Read, Update, Delete) và tìm kiếm phân trang cho entity Category.

**Tính năng mới:**
- **Validator**: Kiểm tra dữ liệu form với thông báo lỗi tiếng Việt
- **Interceptor**: Phân quyền user/admin với session management
- **Login System**: Đăng nhập với tài khoản demo (admin/user)


## Cấu trúc dự án
```
src/
├── main/
│   ├── java/vn/iotstar/
│   │   ├── Controller/
│   │   │   ├── HomeController.java
│   │   │   ├── AuthController.java
│   │   │   ├── ContactController.java
│   │   │   ├── SearchController.java
│   │   │   ├── FileUploadController.java
│   │   │   ├── UserRegistrationController.java
│   │   │   ├── UserProfileController.java
│   │   │   ├── SettingsController.java
│   │   │   ├── admin/
│   │   │   │   ├── CategoryController.java
│   │   │   │   ├── ProductController.java
│   │   │   │   └── AdminHomeController.java
│   │   │   ├── user/
│   │   │   │   └── UserHomeController.java
│   │   │   └── api/
│   │   │       ├── CategoryAPIController.java
│   │   │       └── ProductAPIController.java
│   │   ├── Config/
│   │   │   ├── StaticResourceConfig.java
│   │   │   └── WebMvcConfig.java
│   │   ├── Entity/
│   │   │   ├── CategoryEntity.java
│   │   │   └── ProductEntity.java
│   │   ├── Model/
│   │   │   ├── CategoryModel.java
│   │   │   ├── ProductModel.java
│   │   │   ├── LoginModel.java
│   │   │   ├── UserRegistrationModel.java
│   │   │   ├── UserProfileModel.java
│   │   │   ├── ContactModel.java
│   │   │   ├── SettingsModel.java
│   │   │   ├── SearchFilterModel.java
│   │   │   ├── FileUploadModel.java
│   │   │   └── Response.java
│   │   ├── Validator/
│   │   │   ├── ValidVietnameseName.java
│   │   │   ├── VietnameseNameValidator.java
│   │   │   ├── ValidVietnamesePhone.java
│   │   │   ├── VietnamesePhoneValidator.java
│   │   │   ├── ValidEmail.java
│   │   │   ├── EmailValidator.java
│   │   │   ├── ValidPassword.java
│   │   │   ├── PasswordValidator.java
│   │   │   ├── ValidUsername.java
│   │   │   ├── UsernameValidator.java
│   │   │   ├── ValidPrice.java
│   │   │   ├── PriceValidator.java
│   │   │   ├── ValidQuantity.java
│   │   │   ├── QuantityValidator.java
│   │   │   ├── ValidDiscount.java
│   │   │   ├── DiscountValidator.java
│   │   │   ├── ValidFileSize.java
│   │   │   └── FileSizeValidator.java
│   │   ├── Interceptor/
│   │   │   ├── AuthInterceptor.java
│   │   │   ├── SecurityInterceptor.java
│   │   │   ├── LoggingInterceptor.java
│   │   │   └── RateLimitInterceptor.java
│   │   ├── Repository/
│   │   │   ├── CategoryRepository.java
│   │   │   └── ProductRepository.java
│   │   ├── Service/
│   │   │   ├── ICategoryService.java
│   │   │   ├── IProductService.java
│   │   │   ├── IFileUploadService.java
│   │   │   └── Impl/
│   │   │       ├── CategoryServiceImpl.java
│   │   │       ├── ProductServiceImpl.java
│   │   │       └── FileUploadServiceImpl.java
│   │   └── Springboot23110280HuynhThanhNhanSt56Application.java
│   └── resources/
│       ├── static/
│       │   ├── images/logo/avatar.jpg
│       │   └── js/
│       │       ├── category-ajax.js
│       │       └── product-ajax.js
│       ├── templates/
│       │   ├── index.html
│       │   ├── login.html
│       │   ├── contact.html
│       │   ├── search.html
│       │   ├── admin/
│       │   │   ├── layout-admin.html
│       │   │   ├── home.html
│       │   │   ├── fragments/
│       │   │   │   ├── header.html
│       │   │   │   ├── nav.html
│       │   │   │   └── footer.html
│       │   │   ├── categories/
│       │   │   │   ├── list.html
│       │   │   │   ├── addOrEdit.html
│       │   │   │   └── searchpaginated.html
│       │   │   └── products/
│       │   │       └── list.html
│       │   └── user/
│       │       ├── layout-user.html
│       │       ├── home.html
│       │       ├── dashboard.html
│       │       ├── profile.html
│       │       ├── settings.html
│       │       ├── upload.html
│       │       └── fragments/
│       │           ├── header.html
│       │           └── footer.html
│       ├── i18n/
│       │   ├── messages_vi.properties
│       │   └── messages_en.properties
│       └── application.properties
├── uploads/ (thư mục lưu file upload)
└── validator_interceptor_roles.md (tài liệu tham khảo)
```

## Cấu hình Database
Dự án sử dụng SQL Server. Cập nhật cấu hình trong `application.properties`:

## Hướng dẫn chạy ứng dụng

1. Tạo database `test_db` trong SQL Server
2. Cập nhật thông tin kết nối trong `application.properties`


### 4. Truy cập ứng dụng
- **Trang chủ:** http://localhost:8088 (redirect đến login)
- **Login:** http://localhost:8088/login
- **Admin Panel:** http://localhost:8088/admin/home
- **User Panel:** http://localhost:8088/user/home

**Tài khoản demo:**
- Admin: `admin` / `admin123`
- User: `user` / `user123`

## Các endpoint chính

| Method | URL | Mô tả |
|--------|-----|-------|
| GET | `/` | Redirect đến login |
| GET/POST | `/login` | Trang đăng nhập |
| GET | `/logout` | Đăng xuất |
| GET | `/admin/home` | Trang chủ admin |
| GET | `/user/home` | Trang chủ user |
| GET | `/admin/categories/list` | Danh sách categories |
| GET | `/admin/categories/add` | Form thêm category |
| POST | `/admin/categories/saveOrUpdate` | Lưu/cập nhật category |
| GET | `/admin/categories/edit/{id}` | Form sửa category |
| GET | `/admin/categories/delete/{id}` | Xóa category |
| GET/POST | `/admin/categories/searchpaginated` | Tìm kiếm và phân trang | 


