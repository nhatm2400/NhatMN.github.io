---
title: "Blog 1"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
### **Tăng tốc Bộ công cụ Lượng tử cho Python (QuTiP) với cuQuantum trên AWS**

**bởi Boris Varbanov, Benchen Huang, Éric Giguère, Jin-Sung Kim, Khaldoon Ghanem, Tyler Takeshita và Timothy Brown | 9 THÁNG 8 NĂM 2025 | trong [Amazon Braket](https://aws.amazon.com/blogs/quantum-computing/category/quantum-technologies/amazon-braket/) , [Quantum Technologies](https://aws.amazon.com/blogs/quantum-computing/category/quantum-technologies/)**

Việc mô phỏng các hệ thống lượng tử bằng máy tính cổ điển vẫn là một thách thức về mặt tính toán. Trên thực tế, các tài nguyên cần thiết cho những mô phỏng này tăng theo cấp số nhân với quy mô của hệ thống được mô phỏng. Thực tế này là cốt lõi của động lực để chế tạo máy tính lượng tử. Máy tính lượng tử có tiềm năng vượt trội hơn cả những siêu máy tính mạnh nhất khi mô phỏng các hệ thống lượng tử từ tự nhiên. Chúng cũng được kỳ vọng sẽ tăng tốc độ cho một số vấn đề phức tạp, với các ứng dụng trải dài từ mật mã đến tối ưu hóa quy mô lớn. Tuy nhiên, việc giải quyết các vấn đề thực tế có liên quan sẽ yêu cầu các thuật toán thực hiện hàng tỷ phép tính trên hàng trăm nghìn qubit. Phần cứng lượng tử hiện tại còn lâu mới đáp ứng được những nhu cầu này: số lượng qubit vẫn còn hạn chế và tỷ lệ lỗi của các phép tính vẫn còn cao. Các nhà khoa học và kỹ sư trên toàn thế giới đang nỗ lực cải thiện thiết kế của các thành phần và hoạt động của máy tính lượng tử để cho phép tính toán lượng tử quy mô lớn.

Thiết kế các mô phỏng cổ điển hiệu suất cao cho các thiết bị lượng tử là một lĩnh vực nghiên cứu năng động và nằm ở giao điểm của khoa học thực nghiệm và khoa học tính toán. Các nhà nghiên cứu thường mô phỏng một phần nhỏ của hệ thống quan tâm để thu được kết quả trong một khoảng thời gian hợp lý, ví dụ, tập trung vào các trạng thái kích thích thấp và một vài qubit hoặc bộ ghép nối. Tuy nhiên, các nhà khoa học nhận thấy rằng việc hiểu biết toàn diện hơn về các hệ thống vật lý là điều cần thiết để cải thiện hiệu suất phần cứng và giảm tỷ lệ lỗi. Điều này đòi hỏi phải đưa thêm các yếu tố vật lý phức tạp, chẳng hạn như tương tác với các qubit khác trên thiết bị hoặc tác động của các trạng thái năng lượng cao hơn của hệ thống. Tuy nhiên, những mô phỏng thực tế hơn này lại tốn nhiều thời gian.

Trong bài viết này, các nhà nghiên cứu từ nhóm Lý thuyết Thiết bị Lượng tử Siêu dẫn tại Viện Lượng tử, Đại học Sherbrooke, NVIDIA và Amazon Web Services (AWS) đã hợp tác để tăng hiệu suất mô phỏng lượng tử mở với các tài nguyên tính toán cổ điển. Nhóm đã đạt được điều này thông qua việc tích hợp [NVIDIA cuQuantum](https://developer.nvidia.com/cuquantum-sdk) với [The Quantum Toolbox in Python (QuTiP),](https://qutip.org/) cho phép mô phỏng động lực học của thiết bị lượng tử được tăng tốc bằng GPU. Bằng cách tận dụng các phiên bản Amazon Elastic Compute Cloud (Amazon EC2), được tăng tốc bởi GPU NVIDIA, chúng tôi chứng minh tốc độ mô phỏng được tăng lên tới 4000 lần, giúp mô hình hóa các hệ thống đa qubit quy mô lớn với hiệu suất được cải thiện.

## **Plugin qutip-cuquantum**

QuTiP là một bộ công cụ mã nguồn mở dùng để mô phỏng động lực học của các hệ lượng tử mở và hướng đến việc cung cấp các mô phỏng số hiệu quả và thân thiện với người dùng cho nhiều loại Hamilton, bao gồm cả những Hamilton có phụ thuộc thời gian tùy ý, thường thấy trong nhiều ứng dụng vật lý như quang học lượng tử, ion bị bẫy, mạch siêu dẫn và bộ cộng hưởng nano cơ học lượng tử. NVIDIA cuQuantum là một bộ công cụ phát triển phần mềm (SDK) gồm các thư viện và công cụ được tối ưu hóa, giúp tăng tốc quá trình mô phỏng điện toán lượng tử ở cả cấp độ mạch và thiết bị.

Để mở rộng phạm vi của các thí nghiệm tính toán, nhóm của chúng tôi đã tích hợp cuQuantum với QuTiP thông qua  plugin [qutip-cuquantum](https://github.com/qutip/qutip-cuquantum)  có sẵn trên [PyPi](https://pypi.org/project/qutip-cuquantum/0.1.1/) . Plugin này tận dụng thư viện cuQuantum mới, [cuDensityMat,](https://docs.nvidia.com/cuda/cuquantum/latest/cudensitymat/index.html) được thiết kế để tăng tốc các bộ giải động lực học lượng tử tương tự, cung cấp khả năng tăng tốc cho sự tiến hóa theo thời gian của phương trình Schrödinger và phương trình Lindblad Master. cuDensityMat cung cấp các hàm nguyên thủy để tăng tốc các khuôn khổ động lực học hiện có, như [NVIDIA CUDA-Q Dynamics](https://developer.nvidia.com/cuda-q) và giờ là QuTiP, và để tăng tốc các bộ giải được xây dựng tùy chỉnh. Nó cung cấp chức năng cấp thấp để xác định các trạng thái lượng tử thuần túy hoặc hỗn hợp tùy ý, xác định các toán tử và siêu toán tử nhiều thân, tính toán tác động của các toán tử và siêu toán tử trên trạng thái. Nó cũng hỗ trợ chức năng cho các gradient và mô phỏng đa GPU, đa nút để dễ dàng mở rộng quy mô.

## **Kết quả**

Để đánh giá hiệu suất của plugin qutip-cuquantum, chúng tôi mô phỏng một qubit transmon siêu dẫn được ghép nối điện dung với một bộ cộng hưởng, được điều khiển bởi xung vi sóng. Hệ thống được vận hành trong chế độ phân tán, trong đó cường độ ghép nối qubit-bộ cộng hưởng nhỏ hơn nhiều so với độ lệch tần số của chúng. Cấu hình này là phương pháp tiếp cận tiêu chuẩn để đo qubit trong các bộ xử lý siêu dẫn. Về nguyên tắc, việc tăng biên độ điều khiển vi sóng có thể rút ngắn thời gian đo. Tuy nhiên, trên thực tế, điều này thường gây ra các chuyển đổi trạng thái qubit không mong muốn, kích thích hệ thống vượt xa không gian con tính toán. Việc nắm bắt chính xác những hiệu ứng này trong mô phỏng đòi hỏi phải xem xét nhiều trạng thái qubit và bộ cộng hưởng, điều này mở rộng kích thước không gian Hilbert của hệ thống và do đó làm cho việc mô phỏng động lực học của một hệ thống như vậy đòi hỏi tính toán cao. Ở đây, chúng tôi báo cáo kết quả mô phỏng cho các hệ thống có 512 trạng thái cộng hưởng và 32 và 64 trạng thái qubit, với Hamiltonian đầy đủ được xây dựng bằng QuTiP.

<p align="center">
  <img src="/images/pipeline.png"
       alt="Sơ đồ mạch của hệ thống được mô phỏng"
       style="max-width: 320px;">
</p>

<p style="font-size: 0.9rem; font-style: italic; text-align: center;">
  Hình 1 – Sơ đồ mạch của hệ thống được mô phỏng, trong đó qubit truyền dẫn
  (màu xanh lá cây) được ghép nối điện dung với bộ cộng hưởng (màu xanh lam)
  bằng ổ đĩa ngoài.
</p>

Nhóm đã tiến hành mô phỏng trên AWS với các phiên bản P4de, P5 và P5en được tăng tốc lần lượt bởi GPU [NVIDIA A100](https://www.nvidia.com/en-us/data-center/a100/) , [NVIDIA H100](https://www.nvidia.com/en-us/data-center/h100/) và [NVIDIA H200](https://www.nvidia.com/en-us/data-center/h200/) . Điểm chuẩn cho thấy thời gian chạy giảm đối với hệ thống trạng thái 32 qubit, đạt tốc độ tăng 725 lần trên một GPU H200 so với mô phỏng chỉ dùng CPU trên phiên bản Hpc7a. Tận dụng nhiều GPU H200 cho thấy tốc độ tăng thêm 1,2 lần, 2,2 lần và 3,7 lần cho 2, 4 và 8 GPU tương ứng. Mô phỏng trạng thái 64 qubit sử dụng 8 GPU H200 do yêu cầu về bộ nhớ và cho thấy tốc độ tăng 4.000 lần trên phiên bản P5en với 8 GPU. Cuối cùng, chúng tôi đã quan sát thấy sự cải thiện trên các GPU, với tốc độ tăng 1,5 lần và 1,9 lần khi chuyển từ các phiên bản P4de sang P5 và P5en.

Những tiến bộ này mở ra cánh cửa cho việc nghiên cứu động lực học và tương tác đa qubit liên quan đến các trạng thái kích thích cao, điều này rất quan trọng để tối ưu hóa các hoạt động như đọc dữ liệu và cổng hai qubit. Với những công cụ mới này, nhóm nghiên cứu hiện có thể khám phá vật lý transmon ở những quy mô trước đây nằm ngoài tầm với, đánh dấu một bước tiến quan trọng hướng tới thế hệ phần cứng lượng tử tiếp theo. Việc tích hợp khả năng tăng tốc GPU vào QuTiP cũng đảm bảo rằng những khả năng này có thể được sử dụng rộng rãi trong cộng đồng nghiên cứu.

THẺ: [Amazon Braket](https://aws.amazon.com/blogs/quantum-computing/tag/amazon-braket/) , [NVIDIA](https://aws.amazon.com/blogs/quantum-computing/tag/nvidia/) , [máy tính lượng tử](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-computing/) , [nghiên cứu lượng tử](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-research/) , [Công nghệ lượng tử](https://aws.amazon.com/blogs/quantum-computing/tag/quantum-technologies/)

---

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/boris.jpg"
         alt="Boris Varbanov"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Boris Varbanov</h3>
    <p style="margin:0;">
      Boris Varbanov là nghiên cứu sinh sau tiến sĩ tại Viện Lượng tử, Đại học Sherbrooke, nơi ông nghiên cứu
      cách các qubit siêu dẫn có thể được kích thích bên ngoài không gian con tính toán của chúng. Công trình của
      ông bao gồm mô phỏng tác động của các lỗi như vậy lên mã sửa lỗi lượng tử và phát triển các phương pháp hoặc
      cải tiến thiết kế phần cứng để loại bỏ các lỗi này. Ông nhận bằng Tiến sĩ Vật lý tại Đại học Công nghệ Delft.
      Lĩnh vực nghiên cứu của ông tập trung vào việc triển khai hiệu chỉnh lỗi lượng tử trong các bộ xử lý siêu dẫn,
      và ông thường hợp tác chặt chẽ với các nhóm thực nghiệm đang nỗ lực hướng tới mục tiêu này.
    </p>
  </div>

</div>
<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/BenchenHuang.png"
         alt="Benchen Huang"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Benchen Huang</h3>
    <p style="margin:0;">
      Benchen Huang là Kiến trúc sư Giải pháp Chuyên gia Cộng tác về Điện toán Lượng tử tại AWS, nơi ông làm việc
      với khách hàng để phát triển các giải pháp lai giữa lượng tử và cổ điển trên nền tảng đám mây. Benchen nhận
      bằng Tiến sĩ Hóa học tại Đại học Chicago. Lĩnh vực nghiên cứu của ông bao gồm ứng dụng điện toán lượng tử vào
      các vấn đề hóa học.
    </p>
  </div>

</div>
<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/eric.png"
         alt="Éric Giguère"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Éric Giguère</h3>
    <p style="margin:0;">
      Éric Giguère là Chuyên gia Nghiên cứu tại Đại học Sherbrooke. Ông là người duy trì dự án
      nguồn mở QuTiP. Ông nhận bằng Tiến sĩ tại Đại học Hokkaido, nơi ông nghiên cứu vật lý
      hạt lý thuyết.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/jin-sung.jpg"
         alt="Jin-Sung Kim"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Jin-Sung Kim</h3>
    <p style="margin:0;">
      Jin-Sung Kim là Quản lý Quan hệ Nhà phát triển mảng điện toán lượng tử tại NVIDIA,
      phụ trách các quan hệ đối tác và liên minh chiến lược. Trước khi gia nhập NVIDIA, ông
      là Nhân viên Nghiên cứu tại IBM Quantum. Jin-Sung có bằng Tiến sĩ Kỹ thuật Điện và
      Khoa học Vật liệu của Đại học Princeton và hiện đang làm việc tại San Francisco.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/image004-1.jpg"
         alt="Khaldoon Ghanem"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Khaldoon Ghanem</h3>
    <p style="margin:0;">
      Khaldoon Ghanem là Kỹ sư Công nghệ Phát triển Cấp cao tại NVIDIA, chuyên về điện toán
      lượng tử. Ông nhận bằng Tiến sĩ Vật lý lượng tử tính toán tại Đại học RWTH Aachen,
      hợp tác với Trung tâm Siêu máy tính Jülich. Trước khi gia nhập NVIDIA, ông là nhà
      nghiên cứu tại Quantinuum, phát triển các thuật toán lượng tử cho các ứng dụng vật lý
      vật chất ngưng tụ. Ông cũng đã dành nhiều năm tại Viện Max Planck ở Stuttgart, nghiên
      cứu các mô phỏng Monte Carlo lượng tử song song quy mô lớn.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/tyle.png"
         alt="Tyler Takeshita"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Tyler Takeshita</h3>
    <p style="margin:0;">
      Tyler Takeshita là Nhà khoa học Ứng dụng Cấp cao về Điện toán Lượng tử tại AWS. Trước
      khi gia nhập AWS, ông là Trưởng bộ phận Công nghệ Lượng tử tại Trung tâm Nghiên cứu và
      Phát triển Mercedes-Benz Bắc Mỹ, một công ty thuộc Daimler. Tyler nhận bằng Tiến sĩ
      Hóa học năm 2015 tại Đại học Illinois tại Urbana-Champaign, chuyên ngành hóa học lượng
      tử lý thuyết. Sau đó, ông tiếp tục làm nghiên cứu sinh sau tiến sĩ tại Khoa Hóa học,
      Đại học California, Berkeley.
    </p>
  </div>

</div>

<hr/>

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/timo.png"
         alt="Timothy Brown"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Timothy Brown</h3>
    <p style="margin:0;">
      Timothy Brown là Kiến trúc sư Giải pháp Chính về Điện toán &amp; HPC tại AWS. Ông đã làm
      việc trong lĩnh vực Điện toán Hiệu năng Cao trong 15 năm qua, đảm nhiệm nhiều vai trò
      khác nhau liên quan đến tính toán và tối ưu hóa, tập trung vào dự báo thời tiết số.
      Timothy có bằng Thạc sĩ và Cử nhân (Danh dự) từ Đại học Tây Úc (UWA), Úc.
    </p>
  </div>

</div>
