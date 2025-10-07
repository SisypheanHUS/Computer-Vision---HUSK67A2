# Phân đoạn ảnh y khoa mơ hồ sử dụng mô hình khuếch tán (Diffusion Models)

Tổng quan

Dự án này nhằm phát triển một mô hình sinh dựa trên cơ chế khuếch tán (diffusion-based generative model), có khả năng tạo ra nhiều mặt nạ phân đoạn khả dĩ cho cùng một ảnh y khoa.
Thay vì chỉ tạo ra một mặt nạ cố định, phương pháp của chúng tôi hướng đến việc nắm bắt sự phân bố trong đánh giá của các chuyên gia, giúp hiểu rõ hơn về tính mơ hồ và bất định trong quá trình chẩn đoán hình ảnh y khoa.

Thành viên nhóm
STT	Họ tên	Mã sinh viên	Vai trò
1	Đinh Thái Tuấn	22000130	Nhóm trưởng
Vấn đề cần giải quyết

Các mô hình phân đoạn truyền thống (như U-Net, CNNs) chỉ tạo ra một kết quả duy nhất cho mỗi ảnh, không phản ánh được tính bất định và sự khác biệt giữa các chuyên gia trong quá trình gán nhãn ảnh y khoa.
Dự án này nghiên cứu cách mô hình khuếch tán xác suất (Diffusion Probabilistic Models - DPMs) có thể mô phỏng sự bất định này bằng cách sinh ra nhiều mặt nạ phân đoạn đa dạng và thực tế.

Công trình liên quan

Ambiguous Medical Image Segmentation by Diffusion Models (arXiv:2303.12345)

Denoising Diffusion Probabilistic Models (arXiv:1806.05034)

Bộ dữ liệu

Dự án sử dụng các bộ dữ liệu ảnh y khoa công khai:

LIDC-IDRI – Ảnh CT phổi với nhiều chú giải từ các chuyên gia

AMOS 2022 – Bộ dữ liệu thách thức phân đoạn đa cơ quan vùng bụng

Phương pháp

Phương pháp đề xuất kết hợp giữa U-Net và Diffusion Probabilistic Models:

Kiến trúc nền tảng:
U-Net được sử dụng làm mạng giải nhiễu (denoising backbone) trong khung mô hình khuếch tán.

Quá trình thuận (Forward Process):
Dần dần thêm nhiễu Gaussian vào mặt nạ phân đoạn trong giai đoạn huấn luyện.

Quá trình ngược (Reverse Process):
Mô hình học cách loại bỏ nhiễu theo từng bước để khôi phục và sinh ra nhiều mặt nạ phân đoạn hợp lý được điều kiện hóa theo ảnh y khoa đầu vào.

Chỉ số đánh giá

Dice Similarity Coefficient (DSC)

Structural Similarity Index (SSIM)

Các chỉ số đo đa dạng, ví dụ Jensen–Shannon Divergence giữa các mặt nạ được sinh ra
