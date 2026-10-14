<div align="center">

# Nhật ký thay đổi</div>

<div align="center" style="font-size:xx-small">(✨: Tính năng, chức năng mới. 🐛: Chỉnh lỗi. ☑: Giải quyết công việc, issue) </div>

#

## [v.3.26.1014.1]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610141-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610141-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610141-NasDHSolutions.json)</sup></sup></sub>
- ✨: Bổ sung 4 trường CCHN (Mã CCHN, Ngày cấp, Nơi cấp, Phạm vi hành nghề), form Quản lý tệp đính kèm nhân sự FrmDinhKemNhanVien (hồ sơ Bằng cấp, Chứng chỉ, HĐLĐ) kèm bộ Icon trực quan, cố định độ rộng cột lưới cân đối; tích hợp 3 báo cáo nhân sự mới (Báo cáo tổng hợp, NV đang làm việc từ ngày đến ngày, NV nghỉ việc từ ngày đến ngày) xuất file Excel (CSV UTF-8).
- 🐛: Mở rộng trường nhập mã số thuế TNCN txtMSThue cho phép nhập từ 10 đến 20 ký tự (chấp nhận CCCD 12 số hoặc MST chuẩn, không còn bị bắt cứng 13 số); đồng bộ trường macc_hanhnghe_cv2348 sang HRM; khắc phục triệt để lỗi mã hóa font tiếng Việt (mojibake) và co đè layout tại cụm CCHN tab Thông tin cá nhân.
- ☑: https://i.dh-his.com/hdhiswork/YEUCAU/issues/963
- ☑: https://i.dh-his.com/hdhiswork/YEUCAU/issues/945
- ☑: https://i.dh-his.com/hdhiswork/YEUCAU/issues/923
- 📗: CSDL bảng current.dmnhanvien bổ sung ngaycap_cchn (date), noicap_cchn (varchar 255), phamvihanhnghe (varchar 500); tạo bảng mới hrm.dinhkem_nhanvien lưu trữ file đính kèm dạng bytea. Thực hiện theo mô tả [Mô tả cập nhật MST TNCN, bổ sung CCHN, đính kèm tệp tin và báo cáo nhân sự HRM](https://github.com/dhhiswork/Mo-ta-he-thong/blob/main/HRM/Mo-ta-hrm-issue-963-945-923.md).
- 📕: Phân hệ Quản lý Nhân sự (HRM) được nâng cấp toàn diện: Hồ sơ nhân viên quản lý chính xác MST và Chứng chỉ hành nghề; hỗ trợ lưu trữ tệp đính kèm điện tử và cung cấp đầy đủ các mẫu báo cáo thống kê nhân sự cho phòng TCCB.
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-963/debug-image-hrm-frmnhanvien-mst-tncn-proof.png)
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-963/debug-image-hrm-frmnhanvien-cchn-layout-proof.png)
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-963/debug-image-hrm-frmdinhkem-cchn-hdld-proof.png)

## [v.3.26.1014.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610140-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610140-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610140-NasDHSolutions.json)</sup></sup></sub>
- ✨: [HosHRM.DataAccess][HosHrm] Chuẩn hóa toàn diện xử lý OID theo TOLAPTRINH Issue #161 qua ClsSqlOidHelper (OTH.Common); đồng bộ cấu hình CSDL sequence id và xử lý xóa lương an toàn.
- 🐛: [HosHRM.DataAccess][HosHrm] Khắc phục triệt để lỗi Thêm lương (not-null constraint id / InvalidCastException) và lỗi Xóa lương (operator does not exist: oid = numeric / thiếu bind objLuong.luong.oid) tại Tab Quá trình hưởng lương.
- ☑: https://i.dh-his.com/hdhiswork/LOI/issues/1043
- ☑: https://i.dh-his.com/hdhiswork/TOLAPTRINH/issues/161
- 📗: CSDL bảng hrm.qthuongluong khôi phục thuộc tính DEFAULT nextval('hrm.qthuongluong_id_seq'::regclass) cho cột id. Cập nhật DLL liên quan: HosHRM.DataAccess, HosHrm. Thực hiện theo mô tả [Mô tả chuẩn hóa OID theo TOLAPTRINH 161 và sửa lỗi tab Lương HRM](https://github.com/dhhiswork/Mo-ta-he-thong/blob/main/HRM/Mo-ta-hrm-chuan-hoa-oid-va-sua-loi-tab-luong.md).
- 📕: Mở phân hệ Quản lý Nhân sự HRM -> Quản lý nhân sự -> Hồ sơ nhân viên -> Tab Lương: Thao tác Thêm, Sửa, Xóa quá trình lương nhân viên hoạt động chính xác.
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-1043/debug-image-hrm-frmmain-fullflow-main.png)
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-1043/debug-image-hrm-frmmain-fullflow.png)
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-1043/debug-image-hrm-frmnhanvien-tabluong-direct.png)
![](https://qbsuhafypjhbdmwkygfy.supabase.co/storage/v1/object/public/nguyenvietvinh/issues/issue-1043/debug-image-hrm-frmnhanvien-tester-proof.png)

## [v.3.26.1007.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610070-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610070-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32610070-NasDHSolutions.json)</sup></sup></sub>
- ✨: Tích hợp chuẩn hóa giao diện bản quyền DH.HIS HRM (Nhân sự & Tiền lương) khi kích hoạt DHHIS_BANQUYEN
- 🐛: Đồng bộ nhận diện thương hiệu DH.HIS, thanh trạng thái 4 ô logoDH và tiêu đề Form Home
- ☑: https://i.dh-his.com/hdhiswork/DUAN/issues/34#issuecomment-47093 (hdhiswork/DUAN#34)
- 📗: Không thay đổi CSDL
- 📕: Chuẩn hóa nhận diện thương hiệu DH.HIS theo biến môi trường DHHIS_BANQUYEN = 1
![](https://xgtqkapnwmjscfabjeod.supabase.co/storage/v1/object/public/votranh415/issues/issue-34/debug-image-libraryapp-statusbar-thanhtrangthai-dhhis.png)
![](https://xgtqkapnwmjscfabjeod.supabase.co/storage/v1/object/public/votranh415/issues/issue-34/debug-image-libraryapp-frmhome-tieude-12phanhe.png)

## [v.3.26.0911.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32609110-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32609110-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32609110-NasDHSolutions.json)</sup></sup></sub>
- ✨: Tích hợp cấu hình BuildZip|AnyCPU (xuất bin\BuildZip) + Pre/PostBuildEvent gọi visualstudio-external-tool.js; nhận Resources/Roo.Exe.dll.zip đóng gói tự động khi build Roo.Exe
- ☑: https://i.dh-his.com/hdhiswork/YEUCAU/issues/845
- 📕: Updater Roo.Exe trong phân hệ luôn là bản mới nhất, thống nhất nguồn tải cập nhật remote/local
- Thực hiện theo mô tả [Mô tả bổ sung cấu hình AppUpdate Postgres App tách biệt DB HIS chính](https://github.com/dhhiswork/Mo-ta-he-thong/blob/main/Quan-tri-Admin/Mo-ta-bo-sung-cau-hinh-appupdate-postgres-app-tru-db-his-chinh.md)

![](https://images-worker.tlt11.workers.dev/i/01a08e79-8ad8-7ce3-944c-604c313576cc)
![](https://images-worker.tlt10.workers.dev/i/01a08e79-d157-7b05-94ff-19611903d50b)
![](https://images-worker.tlt02.workers.dev/i/01a08f3b-912b-7723-8dc2-6350fb2e951c)

> ⚠️ **Lộ trình triển khai an toàn:** bản client cũ không biết CSDL remote (chỉ đọc `{DB}_app` local). Phải publish bản mới bằng **cách cũ** cho mọi trạm xong, rồi mới tạo/bật remote (`EOptionAdmin.Enabled = true`), sau đó mới publish tiếp lên remote. Không bật remote khi còn trạm cũ.

## [v.3.26.0306.1]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603061-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603061-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603061-NasDHSolutions.json)</sup></sup></sub>

- 🐛: Sửa lỗi bảng kê tiền trực không lưu được.
![](https://lh3.googleusercontent.com/pw/AP1GczNOv9AL1Py14OnloJkNoRIyEVznzED8BYctY8l9WTV1KVbn_jbBLb-LWVU-HbSzrTGMjCBuXqQoFeGdBWAgBSq1-Scne-owPfAr84Fxn7ZIkVBUHbM88TUuwD3hK9hPeazVacygvxBbOD1Sy5vrK0Xk=w1654-h879-s-no-gm?authuser=0)
- ☑: https://i.dh-his.com/hdhiswork/LOI/issues/779

## [v.3.26.0306.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603060-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603060-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32603060-NasDHSolutions.json)</sup></sup></sub>

- 🐛: Sửa lỗi bảng kê tiền trực không lưu được.
![](https://lh3.googleusercontent.com/pw/AP1GczMQoLCI0T3Q2i6s0LCdYY62pdA8pN8ItDBBfDILIpIPWgnzhJDWX-XsRKlMex_5-2hZH_pst7cP4b5_qApvvV5yxI4TmuYwWtJLC1YYxzHvwlOhHd3dCHOfInHuXEuLLe50SxPW8oAwgTs4MPNb_HcB=w1654-h879-s-no-gm?authuser=0)
- ☑: https://i.dh-his.com/hdhiswork/LOI/issues/779

## [v.3.26.0226.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32602260-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32602260-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32602260-NasDHSolutions.json)</sup></sup></sub>

- 🐛: Sửa lỗi load danh sách `[CĐHA chưa thực hiện]` khi phiếu TT/PT được lập không phải tại khoa CĐHA.
![](https://lh3.googleusercontent.com/pw/AP1GczN7BKnx5WUc84s6RM9zfAg2pBV12edmw_kpeFYXU2sFPU0qbvDl_l81TL_zrTGjoggz-MHs2yPImUN8_dGYCUGSFoNQYi7gncyZ4Ia980p3jF6rh-3ZSUaifm-F_klSCH8jdxLCp_GivAuMzfoWP838=w1654-h879-s-no-gm?authuser=0)
- ☑: https://i.dh-his.com/hdhiswork/LOI/issues/758

## [v.3.25.0419.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32504190-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32504190-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32504190-NasDHSolutions.json)</sup></sup></sub>
- ✨: Yêu cầu - HRM: Bổ sung nhật ký khi xóa bảng chấm công
![](https://i.imgur.com/6rxINlJ.gif)
- ☑: https://i.dh-his.com/hdhiswork/YEUCAU/issues/182

## [v.3.24.1124.0]() <sub><sup><sup>[⬇️OneDrive](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411240-OneDrive.json) [⬇️GoogleStorage](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411240-GoogleStorage.json) [⬇️NasDHSolutions](https://code-dh-hospital.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411240-NasDHSolutions.json)</sup></sup></sub>
- 🐛: `HRM lấy sai số ngày nghỉ phép năm`
- ☑: `https://github.com/dhhiswork/Loi/issues/19`

![](https://i.imgur.com/qWFkk0j.png)

## [v.3.24.1121.0]()
- 🐛: `HRM không lấy sai số ngày nghỉ phép năm`
- ☑: `https://github.com/dhhiswork/Loi/issues/19`

![](https://i.imgur.com/3bHCFyW.png)

## [v.3.24.1112.1]() <sub><sup><sup>[⬇️OneDrive](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411121-OneDrive.json) [⬇️GoogleStorage](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411121-GoogleStorage.json) [⬇️NasDHSolutions](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411121-NasDHSolutions.json)</sup></sup></sub>
- 🐛: Lỗi - HRM bị mất dữ liệu khám sức khỏe (BV Da Liễu)
- ☑: https://github.com/dh-his/Ghi_Nhan_Loi/issues/39

## [v.3.24.1112.0]() <sub><sup><sup>[⬇️OneDrive](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411120-OneDrive.json) [⬇️GoogleStorage](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411120-GoogleStorage.json) [⬇️NasDHSolutions](https://tolaptrinh.github.io/directTo/?&redirect_url=https%3A%2F%2Fo-dh-007-default-rtdb.asia-southeast1.firebasedatabase.app%2FdirectTo%2FHRMexe%2F32411120-NasDHSolutions.json)</sup></sup></sub>
- 🐛: Lỗi - HRM không lấy được tổng số ngày nghỉ phép năm
- ☑: https://github.com/dh-hos/dhg.hospitalhrm/issues/9

## [v.3.24.0627.1]()
- 🐛: Fix lỗi ma_giuong_bak_ trong bảng chidinhcls
- ☑: https://github.com/dh-hos/To_Lap_Trinh/issues/403

## [v.3.24.0627.0]()
- 🐛: Fix lỗi ma_giuong_bak_ trong bảng chidinhcls
- ☑: https://github.com/dh-hos/To_Lap_Trinh/issues/403
## [v3.23.1203.1]()
- #️⃣: <https://github.com/dh-hos/To_Lap_Trinh/issues/191>
- 🐛: Thêm chức năng ẩn hiện menu theo cấu hình [Theo mô tả](https://github.com/dh-hos/Mo-ta-he-thong/blob/main/HRM/Hau-cau-hinh-menu.md)
## [v3.23.0713.1]()
- #️⃣: <https://github.com/dh-hos/dhg.hospitalhrm/issues/7>
- 🐛: Fix Lỗi - Các nút không tác dụng
## [v3.23.0704.2]()
- #️⃣: <https://github.com/dh-hos/dhg.hospitalhrm/issues/6>
- 🐛: Fix Lỗi - Không cài đặt được module service khi máy có cài module HRM
## [v3.23.0704.1]()
- #️⃣: <https://github.com/dh-hos/dhg.hospitalhrm/issues/6>
- 🐛: Fix Lỗi - Không cài đặt được module service khi máy có cài module HRM
## [v3.23.0622.1]()
- #️⃣: <https://github.com/dh-hos/dhg.hospitalhrm/issues/5>
- ✨: Bổ sung chức năng bảng kê Chi phí phẫu thuật đối với mabv=95006 chỉ lấy những toa vật tư không tính phí được sử dụng cho 1 CLS cụ thể
## [v3.22.0928.1]()
-  ✨: Cập nhật bản quyền đối với Mã BV 87190 - BỆNH VIỆN DA LIỄU ĐỒNG THÁP
-  #️⃣: https://github.com/dh-hos/DH.HIS/issues/4
## [v3.22.0721.1]()
-  🐛: Bổ sung license mabvbh=77150
-  #️⃣: https://github.com/dh-hos/DH.HIS/issues/2
## [v3.22.0704.1]()
-  #️⃣: Tab Lương của nhân viên, khi thêm hệ số lương mới, bỏ check Đang hưởng hệ số cũ nhưng lưu lại, nó vẫn còn check Đan hưởng
-  🐛: https://github.com/dh-hos/dhg.hrm/issues/2