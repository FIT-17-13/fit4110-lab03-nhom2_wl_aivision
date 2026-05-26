# Consumer–Provider Handshake

## Thông tin chung

- **Lab:** FIT4110 Lab 03
- **Ngày:** 26/05/2026
- **Provider team:** Nhóm 3
- **Consumer team:** Nhóm 2 - WL
- **Provider service:** CameraStream
- **Consumer service:** AI Vision

---

## Contract

- **Contract file:** `contracts/camera-stream.openapi.yaml`
- **Mock base URL:** `http://127.0.0.1:4012`
- **Auth method:** None (Chưa yêu cầu xác thực trong hợp đồng Mock)
- **Endpoint được test:** `POST /callbacks/alerts`

---

## Smoke test

### Request

```http
POST /callbacks/alerts
Content-Type: application/json

```

```json
{
  "detectionId": "123e4567-e89b-12d3-a456-426614174000",
  "riskLevel": "HIGH",
  "timestamp": "2026-05-19T08:00:02Z"
}

```

### Expected response

```json
{
  "status": "success",
  "message": "Alert logged successfully in Camera Stream core."
}

```

## Kết quả

* [x] Consumer gọi mock thành công.
* [x] Consumer parse được field cần dùng.
* [x] Consumer hiểu lỗi 4xx/5xx provider trả về.
* [x] Có Newman report hoặc screenshot.

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
| --- | --- | --- | --- |
| Bổ sung endpoint nhận callback cảnh báo từ AI Vision | Chưa có endpoint nhận thông báo | Đã thêm POST `/callbacks/alerts` nhận dữ liệu phân tích | Vũ Bích Hợp, Nguyễn Văn Vinh |

## Xác nhận

* Provider representative: Vũ Bích Hợp
* Consumer representative: Nguyễn Văn Vinh