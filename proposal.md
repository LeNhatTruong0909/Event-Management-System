Event-Management-System proposal

# Thông tin

-   Nhóm

    -   Thành viên 1: Trần Quang Triều - 22002955

    -   Thành viên 2: Phan Nhật Trường - 22721621

    -   Thành viên 3: Nguyễn Văn Tùng - 22647011

    -   Thành viên 4: Lê Nhật Trường -- 22716321

-   Git repository:
    https://github.com/LeNhatTruong0909/Event-Management-System.git

# Ý tưởng

## Minimum Viable Product

 **Đăng nhập và đăng ký người dùng:**

-   Người dùng có thể tạo tài khoản và đăng nhập vào hệ thống.

-   Vai trò người dùng cơ bản: Participant (người tham dự).

 **Tạo và xem sự kiện:**

-   Organizer (người tổ chức) có thể tạo sự kiện với các thông tin cơ
    bản như tên, mô tả, ngày, và địa điểm.

-   Người dùng có thể xem danh sách các sự kiện đang có.

 **Đăng ký tham gia sự kiện:**

-   Người tham dự có thể đăng ký vào một sự kiện từ danh sách sự kiện.

-   Organizer có thể xem danh sách người tham dự cho sự kiện của mình.

## Complete Product

 **Quản lý sự kiện toàn diện:**

-   Organizer có thể tạo, cập nhật, xóa sự kiện.

-   Thêm các thông tin chi tiết như lịch trình, diễn giả, và các hoạt
    động trong sự kiện.

 **Quản lý người tham dự:**

-   Người tham dự có thể đăng ký, hủy đăng ký, và xem danh sách sự kiện
    đã đăng ký.

-   Organizer có thể xem, quản lý danh sách người tham dự, và gửi thông
    báo đến họ.

 **Quản lý địa điểm:**

-   Admin có thể thêm, cập nhật, xóa các địa điểm tổ chức sự kiện.

-   Organizer có thể chọn địa điểm từ danh sách có sẵn khi tạo sự kiện.

 **Quản lý người dùng và vai trò:**

-   Hỗ trợ các vai trò khác nhau: Admin, Organizer, Participant.

-   Admin có thể quản lý người dùng, phân quyền, và theo dõi hoạt động
    hệ thống.

 **Tìm kiếm và lọc sự kiện:**

-   Người dùng có thể tìm kiếm sự kiện theo tên, ngày, địa điểm, và các
    tiêu chí khác.

 **Gửi thông báo:**

-   Organizer có thể gửi thông báo đến người tham dự về các cập nhật sự
    kiện.

-   Người tham dự nhận thông báo qua giao diện hệ thống hoặc email.

# Phân Tích & Thiết Kế

## Chức năng

**Các actor:**

-   **Admin (Quản trị viên):** Có quyền quản lý toàn bộ hệ thống.

-   **Organizer (Người tổ chức):** Có quyền tạo và quản lý các sự kiện.

-   **Participant (Người tham dự):** Có quyền đăng ký và xem thông tin
    sự kiện.

**Các use case:**

-   **Admin:**

    -   Quản lý người dùng (thêm, xóa, cập nhật vai trò).

    -   Quản lý sự kiện (phê duyệt, xóa sự kiện).

    -   Quản lý địa điểm.

-   **Organizer:**

    -   Tạo sự kiện.

    -   Cập nhật thông tin sự kiện.

    -   Xem danh sách người tham dự.

    -   Gửi thông báo cho người tham dự.

-   **Participant:**

    -   Đăng ký sự kiện.

    -   Hủy đăng ký sự kiện.

    -   Xem thông tin sự kiện.

    -   Nhận thông báo.

## Lược đồ CSDL

**User (Người dùng):** Lưu thông tin người dùng.

-   Thuộc tính: user_id (PK), username, password, email, role (admin,
    organizer, participant).

**Event (Sự kiện):** Lưu thông tin sự kiện.

-   Thuộc tính: event_id (PK), name, description, date, location_id
    (FK), organizer_id (FK).

**Location (Địa điểm):** Lưu thông tin địa điểm tổ chức.

-   Thuộc tính: location_id (PK), name, address, capacity.

**Registration (Đăng ký):** Lưu thông tin đăng ký sự kiện.

-   Thuộc tính: registration_id (PK), event_id (FK), user_id (FK),
    registration_date.

**Notification (Thông báo):** Lưu thông tin thông báo.

-   Thuộc tính: notification_id (PK), event_id (FK), message, sent_date.

## Giao diện

-   **Trang chủ:** index.html

    -   Hiển thị danh sách sự kiện.

    -   Chức năng tìm kiếm và lọc sự kiện theo tên, ngày, địa điểm.

-   **Trang đăng nhập/đăng ký:** login.html / register.html

    -   Cho phép người dùng đăng nhập hoặc tạo tài khoản mới.

-   **Trang quản lý sự kiện (cho Organizer và Admin):**
    event_management.html

    -   Tạo, cập nhật, xóa sự kiện.

    -   Hiển thị danh sách các sự kiện đã tạo.

-   **Trang chi tiết sự kiện:** event_detail.html

    -   Hiển thị thông tin chi tiết của một sự kiện (tên, mô tả, ngày,
        địa điểm).

    -   Nút đăng ký/hủy đăng ký (cho Participant).

-   **Trang quản lý người tham dự (cho Organizer):**
    attendee_management.html

    -   Xem danh sách người tham dự của một sự kiện.

    -   Gửi thông báo đến người tham dự.

-   **Trang quản lý địa điểm (cho Admin):** location_management.html

    -   Thêm, cập nhật, xóa thông tin địa điểm.

-   **Trang quản lý người dùng (cho Admin):** user_management.html

    -   Thêm, xóa, cập nhật vai trò của người dùng.

-   **Trang thông báo:** notifications.html

    -   Hiển thị các thông báo được gửi đến người tham dự.

# Kế hoạch thực hiện

Liệt kê kế hoạch dự kiến trong 6 tuần

-   Tuần 1: Đặt nền tảng cho dự án bằng cách xác định yêu cầu và bắt đầu
    thiết kế.

-   Tuần 2: Hoàn thiện thiết kế giao diện và phát triển các trang cơ
    bản.

-   Tuần 3: Xây dựng API cơ bản và kết nối với giao diện người dùng.

-   Tuần 4: Thêm các tính năng phức tạp và cải thiện hệ thống.

-   Tuần 5: Đảm bảo hệ thống hoàn thiện và hoạt động ổn định.

-   Tuần 6: Đưa hệ thống vào vận hành và đánh giá hiệu quả.

# Câu hỏi/ Vấn đề

Liệt kê câu hỏi hoặc vấn đề của nhóm bạn tại đây
