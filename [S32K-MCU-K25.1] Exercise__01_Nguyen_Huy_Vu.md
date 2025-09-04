I. RISC
	RISC là viết tắt của Reduced Instruction Set Computer, nghĩa là máy tính với tập lệnh rút gọn.
RISC là một kiến trúc tập lệnh (ISA) mã nguồn mở, được thiết kế để đơn giản, linh hoạt và dễ mở rộng.
Đây là một xu hướng đang phát triển mạnh mẽ trong lĩnh vực vi xử lý, đặc biệt trong các ứng dụng nhúng, IoT, và cả máy chủ.
hiện tại RISC đã có phiên bản thứ 5 RISC-V
 
Đặc điểm nổi bật của RISC-V:
Đơn giản và dễ hiểu: Tập lệnh nhỏ gọn, dễ học, dễ triển khai.
Modular: Có thể mở rộng với các phần mở rộng như:
RV32I, RV64I (32-bit và 64-bit)
M (Multiply/Divide), A (Atomic), F/D (Floating-point), C (Compressed), V (Vector)...
Mã nguồn mở: Không bị ràng buộc bởi giấy phép thương mại như ARM hay x86.
Hiệu năng cao: Dù đơn giản, RISC-V vẫn có thể đạt hiệu năng tương đương các ISA thương mại.
Ứng dụng rộng rãi: Từ vi điều khiển nhỏ đến máy chủ hiệu năng cao.
 
Ứng dụng thực tế:
Vi điều khiển trong thiết bị IoT
Chip AI và học máy
Máy tính giáo dục (như SiFive, Kendryte)
Các hệ điều hành như Linux đã hỗ trợ RISC-V
 
Tùy biến theo nhu cầu:
Một điểm mạnh của RISC-V là bạn có thể chọn hoặc bỏ các phần mở rộng tùy theo mục đích:
 
Thiết bị IoT: có thể chỉ cần RV32IC
Máy chủ: cần RV64GCV hoặc thêm H, S để hỗ trợ OS và ảo hóa
AI: cần V để xử lý vector
 
Ví dụ về code:
 
	li t0, 5        # Load immediate 5 vào thanh ghi t0
	li t1, 10       # Load immediate 10 vào thanh ghi t1
	add t2, t0, t1  # Cộng t0 và t1, lưu vào t2
	sw t2, 0(sp)    # Lưu t2 vào bộ nhớ tại địa chỉ sp (stack pointer)
 
II. CISC
	CISC (Complex Instruction Set Computer) là một loại kiến trúc tập lệnh trong thiết kế vi xử lý, đặc trưng bởi việc sử dụng tập lệnh phức tạp và đa dạng.
Mục tiêu của CISC là giảm số lượng lệnh cần thiết trong chương trình, bằng cách cho phép mỗi lệnh thực hiện nhiều thao tác phức tạp.
 
Đặc điểm chính của CISC:
1. Tập lệnh phong phú:
	Có hàng trăm lệnh khác nhau.
	Một số lệnh có thể thực hiện nhiều bước (ví dụ: truy cập bộ nhớ, tính toán, lưu kết quả).
2. Lệnh có độ dài không cố định:
	Có thể từ 1 byte đến vài chục byte.
	Gây khó khăn cho việc giải mã lệnh và tối ưu pipeline.
3. Truy cập bộ nhớ trực tiếp trong lệnh:
	Ví dụ: ADD [mem1], [mem2] có thể cộng trực tiếp hai giá trị trong bộ nhớ.
4. Thiết kế phần cứng phức tạp hơn:
	Do phải xử lý nhiều loại lệnh và chế độ định địa chỉ.
	Tối ưu hóa cho lập trình viên:
5. Giúp viết mã ngắn gọn hơn, dễ hiểu hơn.
	Phù hợp với thời kỳ bộ nhớ đắt đỏ và trình biên dịch chưa tối ưu.
	
💡 Kiến trúc CISC phổ biến:
	x86 / x86-64: Dùng trong hầu hết máy tính cá nhân, laptop, máy chủ.
	VAX: Một kiến trúc CISC cổ điển.
	Motorola 68000: Dùng trong máy Mac đời đầu.
 
ví dụ về code:
 
	MOV AX, [1234h]   ; Lấy dữ liệu từ địa chỉ 1234h vào thanh ghi AX
	ADD AX, [5678h]   ; Cộng dữ liệu từ địa chỉ 5678h vào AX
	MOV [9ABCh], AX   ; Lưu kết quả vào địa chỉ 9ABCh
 
III. so sánh giữa CISC với RISC
 
Tiêu chí						RISC (Reduced Instruction Set Computer)			CISC (Complex Instruction Set Computer)
Tập lệnh						Ít, đơn giản									Nhiều, phức tạp
Độ dài lệnh						Cố định(thường 32-bit)							Không cố định (1–15 byte hoặc hơn)
Thời gian thực thi lệnh			Nhanh, thường 1 chu kỳ							Chậm hơn, có thể nhiều chu kỳ
Thiết kế phần cứng				Đơn giản, dễ mở rộng							Phức tạp, khó mở rộng
Tối ưu hóa pipeline				Dễ thực hiện									Khó thực hiện do lệnh không đồng nhất
Truy cập bộ nhớ					Qua thanh ghi trung gian						Có thể truy cập trực tiếp trong lệnh
Hiệu năng tổng thể				Cao hơn trong các hệ thống hiện đại				Tốt trong các hệ thống cũ hoặc phần mềm kế thừa
Tối ưu hóa trình biên dịch		Dễ dàng hơn										Phức tạp hơn
Ứng dụng phổ biến				ARM, RISC-V, MIPS (thiết bị nhúng, di động)		x86, x86-64 (PC, laptop, máy chủ)
Chi phí sản xuất				Thấp hơn										Cao hơn do phần cứng phức tạp
Kích thước mã máy				Lớn hơn do nhiều lệnh đơn giản					Nhỏ hơn do lệnh phức tạp

Khi nào dùng RISC hay CISC:
Tình huống								Kiến trúc phù hợp
Thiết bị nhúng, tiết kiệm năng lượng	RISC (ARM, RISC-V)
Máy tính cá nhân, phần mềm kế thừa		CISC (x86, x86-64)
Hệ thống cần mở rộng, tùy biến			RISC
Hệ thống cần tương thích phần mềm cũ	CISC