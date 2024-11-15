# Hồ Quốc Việt  
## Lab3: Xác định các phần tử thiết kế của hệ thống “Payroll System”

# Subsystem context diagrams 
![Diagram](https://www.planttext.com/api/plantuml/png/X5JBRjim4BpxAmYVtC89a2iFHTga0N9m6yG5UbwJQvknIAgxP02Zw9Vrq4_gBvICdcman0S3qiw-PcRrz_UVQmv08TfgiL0LC8i7E9ElgksP0rhnSo7oxu0E2GAce3gYEl5AfoSfRjF_EocUlT4by15hJu5NQElAdn7ljHJRGCOT4hm9DWarUONCtun51QHvLPHhem-Hr14Olv966Y2_kfa_jrswSKtVhNbsOB5yKyFPeWiR34V_7_Ze8_5tJoTCWRlAGpkfyjOQPkFTuylken131NGkNyMTDQ5RQqJNkcdGWjSYBKO7_1Bj3cd4qS11KwcWe2W7raSNsdglg6db_AYjSOP3qiPJHnDetJ7N2oLxCeiXD5OOy1Mwa7L0npeFsA7ltTvFPAo5IG4fDb0NoHHTvvx1A_q-dy2TIc-cdHplaUwYI_O1fHewkYPlq9D0OOlqR5JldZg_kyasdvpwhOB-2LNOW8C3PeibaM2NX1jEATKU9B_50ARYrOmD6cXcCBVeVRwyMegB2x5ylnITnOHidSAJiC8_8snvxZdXylB3S51Is9TDve2Jzf99sO2q1pMRDv9HfijoBd4sssEiaHIHvwUP9L-A7n79fCnMfvwsLfRXeaPVWVB-9nGQwLxmErEqi4xElKQdyxVt7m000F__0m00)  
**1. BankSystem (Hệ thống Ngân hàng)**  
- Xử lý tất cả các giao dịch tài chính. 
- Hệ thống lương yêu cầu chuyển khoản cho nhân viên chọn thanh toán qua tài khoản ngân hàng.  
**2. PrintService (Dịch vụ In ấn)**
- Đảm nhiệm việc in phiếu lương.
- Hệ thống lương gửi thông tin chi tiết về phiếu lương cho hệ thống này để in cho các nhân viên chọn nhận phiếu giấy.  
**3. ProjectManagementDatabase (Cơ sở Dữ liệu Quản lý Dự án)**
- Hệ thống lương truy vấn cơ sở dữ liệu này để lấy thông tin chi tiết về mã số công việc (charge number).
- Vì đây là hệ thống cũ (legacy), chỉ cho phép đọc dữ liệu.
### #. Analysis class to design element map
# Mapping: Analysis Classes to Design Elements

## BankSystem
| **Analysis**       | **Design Element** |
|---------------------|--------------------|
| PayrollController   | PayrollController  |
| IBankSystem         | IBankSystem        |
| BankSystem          | BankSystem         |
| Paycheck            | Paycheck           |
| BankInformation     | BankInformation    |

## PrintService
| **Analysis**       | **Design Element** |
|---------------------|--------------------|
| PrintController     | PrintController    |
| IPrintService       | IPrintService      |
| PrintService        | PrintService       |
| Report              | Report             |
| PrintInformation    | PrintInformation   |

## ProjectManagementDatabase
| **Analysis**              | **Design Element**            |
|----------------------------|-------------------------------|
| ProjectController          | ProjectController            |
| IProjectDatabase           | IProjectDatabase             |
| ProjectManagementDatabase  | ProjectManagementDatabase    |
| ChargeNumber               | ChargeNumber                 |
| ProjectData                | ProjectData                  |

---

# Mapping: Design Elements to "Owning" Packages

## BankSystem
| **Design Element**  | **"Owning" Package**              |
|----------------------|-----------------------------------|
| PayrollController    | Applications::Payroll            |
| IBankSystem          | Middleware::BankServices         |
| BankSystem           | Middleware::BankServices         |
| Paycheck             | Business Services::Payroll Artifacts |
| BankInformation      | Business Services::Bank Details  |

## PrintService
| **Design Element**  | **"Owning" Package**                  |
|----------------------|---------------------------------------|
| PrintController      | Applications::PrintManagement        |
| IPrintService        | Middleware::Services::Interfaces     |
| PrintService         | Middleware::Services                 |
| Report               | Business Services::DocumentArtifacts |
| PrintInformation     | Business Services::PrintSettings     |

## ProjectManagementDatabase
| **Design Element**          | **"Owning" Package**                |
|------------------------------|-------------------------------------|
| ProjectController            | Applications::ProjectManagement    |
| IProjectDatabase             | Middleware::DataAccess::Interfaces |
| ProjectManagementDatabase    | Middleware::DataAccess             |
| ChargeNumber                 | Business Services::ProjectArtifacts|
| ProjectData                  | Business Services::ProjectInfo     |

---
#. Architectural layers and their dependencies 
![Diagram](https://www.planttext.com/api/plantuml/png/X5GxRiCm3Drz2g5BfroXo6_9aA9enY83ep2E6bao9Bf1KEHa7NgaNg6IgpYMBADURF2HZ-GZwP-lxwabCDHKih0deMemKB4Q-0bAtD158ZF82LGfiIY2dJtCwbeA3YIqiW_iis3kUNk1Yz5IBhGY_qQp3NOZ56Mi-jqnz-tNNeQrsEybdi7WZR-3vg1E6pGVWcENlALSjSZ54bRRkpKrNcEs9H3CkADAk49z7jw1nHvXGDQW7465Al59-FELjfe4AA9EpTT8bNbZXNAbifIrymX3O3D3uW2SuhmEvKVafsobNYYsH08XuoWFhDH1cwgTU5v6pHklHJxlAzRQK3Omg9cFMnp1bFZSLBlRtWoYMy68X2gJLZtoNzKXkNTBWhlXzyRmw5Gr-cmPQRP7fGdTgqRblhb0MsGkW4qcJybYZdhTXpCucK0JhyU8rx3npArrXCcIZxh6aoYYbluyeXxZKdk5tQiV9BzvZLxNr4djVrI_0000__y30000)  
