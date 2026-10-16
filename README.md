---


---

<h1 id="🌱-🚀-smart-farm-–-hệ-thống-tưới-lan-thông-minh">🌱 🚀 Smart-Farm – Hệ thống tưới Lan thông minh</h1>
<blockquote>
<p><em>Smart-Farm ứng dụng IoT để theo dõi môi trường và hỗ trợ tưới nước cho trang trại Lan an toàn, tiết kiệm.</em></p>
</blockquote>
<h2 id="giới-thiệu-dự-án">1. Giới thiệu dự án</h2>
<p>Smart-Farm thu thập dữ liệu từ cảm biến, xử lý dữ liệu trên bộ điều khiển và quyết định khi nào cần tưới. Người nông dân có thể theo dõi nhiệt độ, độ ẩm đất và trạng thái máy bơm.</p>
<p>Hệ thống là mô hình minh họa. Ngưỡng tưới và thiết bị cần được kiểm tra, hiệu chỉnh theo điều kiện thực tế của vườn Lan.</p>
<h2 id="hướng-dẫn-cài-đặt">2. Hướng dẫn cài đặt</h2>
<h3 id="thiết-bị-cần-có">2.1. Thiết bị cần có</h3>
<ul>
<li>Raspberry Pi hoặc bộ điều khiển tương thích.</li>
<li>Cảm biến nhiệt độ/độ ẩm không khí và cảm biến độ ẩm đất.</li>
<li>Mạch relay phù hợp với máy bơm.</li>
<li>Nguồn điện đúng thông số của từng thiết bị.</li>
<li>Kết nối mạng nếu cần giám sát từ xa.</li>
</ul>
<h3 id="cài-đặt-môi-trường">2.2. Cài đặt môi trường</h3>
<p>Mở Terminal và kiểm tra Python:</p>
<pre class=" language-bash"><code class="prism  language-bash">python3 --version
</code></pre>
<p>Tạo môi trường ảo và cài các thư viện ví dụ:</p>
<pre class=" language-bash"><code class="prism  language-bash">python3 -m venv .venv
<span class="token function">source</span> .venv/bin/activate
python -m pip <span class="token function">install</span> --upgrade pip
python -m pip <span class="token function">install</span> gpiozero
</code></pre>
<p>Trên Windows, kích hoạt môi trường ảo bằng <code>.venv\\Scripts\\activate</code>. Lệnh điều khiển GPIO chỉ chạy trên phần cứng và hệ điều hành tương thích. Hãy cài thêm thư viện cảm biến đúng với mẫu thiết bị đang dùng.</p>
<h3 id="chạy-chương-trình">2.3. Chạy chương trình</h3>
<p>Lưu chương trình vào <code>smart_farm.py</code>, kiểm tra cấu hình chân GPIO và ngưỡng tưới trước khi chạy:</p>
<pre class=" language-bash"><code class="prism  language-bash">python smart_farm.py
</code></pre>
<p>Không nối máy bơm trực tiếp vào chân GPIO. Dùng mạch điều khiển phù hợp, có bảo vệ điện và kiểm tra hệ thống khi máy bơm chưa nối tải.</p>
<h2 id="tính-năng">3. Tính năng</h2>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Đọc dữ liệu nhiệt độ và độ ẩm từ cảm biến.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> So sánh độ ẩm đất với ngưỡng tưới đã cấu hình.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Bật/tắt máy bơm thông qua mạch relay phù hợp.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Hiển thị trạng thái hoạt động cho người vận hành.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Lưu nhật ký để theo dõi và tìm lỗi.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Kiểm tra cảnh báo khi cảm biến mất kết nối hoặc dữ liệu bất thường.</li>
</ul>
<h2 id="bảng-thông-số-tham-khảo">4. Bảng thông số tham khảo</h2>

<table>
<thead>
<tr>
<th>Thành phần</th>
<th>Thông số / vai trò</th>
<th>Ghi chú</th>
</tr>
</thead>
<tbody>
<tr>
<td>Cảm biến nhiệt độ</td>
<td>Ví dụ: DHT22</td>
<td>Chọn theo môi trường và yêu cầu độ chính xác</td>
</tr>
<tr>
<td>Cảm biến độ ẩm đất</td>
<td>Loại điện dung hoặc loại phù hợp</td>
<td>Hiệu chuẩn theo loại đất và giá thể</td>
</tr>
<tr>
<td>Bộ điều khiển</td>
<td>Raspberry Pi hoặc thiết bị tương thích</td>
<td>Cần kiểm tra chân giao tiếp</td>
</tr>
<tr>
<td>Mạch relay</td>
<td>Theo điện áp và dòng tải của máy bơm</td>
<td>Không điều khiển tải công suất lớn trực tiếp bằng GPIO</td>
</tr>
<tr>
<td>Máy bơm</td>
<td>Theo thiết kế hệ thống tưới</td>
<td>Dùng nguồn riêng đúng định mức</td>
</tr>
<tr>
<td>Kết nối</td>
<td>Wi-Fi hoặc LAN</td>
<td>Cần thiết nếu có giám sát từ xa</td>
</tr>
<tr>
<td>Ngưỡng tưới</td>
<td>Ví dụ: độ ẩm đất dưới 30%</td>
<td>Giá trị minh họa, phải hiệu chỉnh thực tế</td>
</tr>
</tbody>
</table><h2 id="sơ-đồ-hệ-thống">5. Sơ đồ hệ thống</h2>
<p><img src="images/so-do-smart-farm.svg" alt="Sơ đồ hệ thống Smart-Farm: cảm biến gửi dữ liệu đến bộ điều khiển, bộ điều khiển ra lệnh qua relay để vận hành máy bơm; dữ liệu có thể gửi lên màn hình hoặc đám mây."></p>
<p>Luồng cơ bản: <strong>Cảm biến → Bộ điều khiển/SoC → Mạch relay → Máy bơm</strong>. Dữ liệu trạng thái có thể được gửi đến giao diện giám sát.</p>
<h2 id="cpu-xử-lý-lệnh-tưới-theo-chu-kỳ-fetch–decode–execute">6. CPU xử lý lệnh tưới theo chu kỳ Fetch–Decode–Execute</h2>
<blockquote>
<ol>
<li><strong>Fetch (Lấy lệnh):</strong> CPU lấy lệnh tiếp theo của chương trình từ bộ nhớ.</li>
<li><strong>Decode (Giải mã):</strong> CPU giải mã lệnh để xác định thao tác cần thực hiện.</li>
<li><strong>Execute (Thực thi):</strong> CPU thực hiện phép tính hoặc thao tác, chẳng hạn so sánh giá trị độ ẩm với ngưỡng và yêu cầu bộ điều khiển bật/tắt relay.</li>
</ol>
<p>Chu kỳ này diễn ra liên tục khi chương trình chạy. Lệnh bật máy bơm vẫn phải đi qua phần mềm và mạch điều khiển phù hợp; CPU không cấp điện trực tiếp cho máy bơm.</p>
</blockquote>
<h2 id="mô-hình-dikw-từ-dữ-liệu-đến-hành-động">7. Mô hình DIKW: từ dữ liệu đến hành động</h2>
<ol>
<li><strong>Data – Dữ liệu:</strong> Cảm biến ghi nhận nhiệt độ <code>32°C</code> và độ ẩm đất <code>25%</code>.</li>
<li><strong>Information – Thông tin:</strong> Hệ thống xác định nhiệt độ đang cao và độ ẩm đất thấp hơn ngưỡng cài đặt <code>30%</code>.</li>
<li><strong>Knowledge – Kiến thức:</strong> Theo quy tắc đã hiệu chỉnh cho vườn Lan, đất dưới ngưỡng có thể cần được tưới; cần kiểm tra cảm biến và điều kiện thực tế.</li>
<li><strong>Wisdom – Trí tuệ / quyết định:</strong> Hệ thống quyết định bật máy bơm trong thời gian giới hạn, theo dõi lại độ ẩm và dừng tưới khi đạt điều kiện an toàn.</li>
</ol>
<pre class=" language-text"><code class="prism  language-text">             /----------------------\
            /  WISDOM – Quyết định   \
           /--------------------------\
          / KNOWLEDGE – Quy tắc tưới  \
         /------------------------------\
        / INFORMATION – Ý nghĩa dữ liệu  \
       /----------------------------------\
      / DATA – Giá trị cảm biến thô        \
     /--------------------------------------\
</code></pre>
<p>Các giá trị trên chỉ là ví dụ. Nhiệt độ cao không tự động có nghĩa là cần tưới; quyết định nên dựa vào độ ẩm đất, ngưỡng được hiệu chuẩn và giới hạn an toàn.</p>
<h2 id="kiến-thức-soc-và-ipo">8. Kiến thức SoC và IPO</h2>
<ul>
<li><strong>SoC (System on a Chip):</strong> Một chip tích hợp nhiều thành phần của hệ thống, có thể gồm CPU và các bộ điều khiển ngoại vi. Cấu hình cụ thể phụ thuộc thiết bị.</li>
<li><strong>IPO (Input – Process – Output):</strong>
<ul>
<li><strong>Input:</strong> Nhiệt độ, độ ẩm đất, cấu hình và lệnh người dùng.</li>
<li><strong>Process:</strong> Bộ điều khiển đọc dữ liệu, CPU chạy chương trình và so sánh với ngưỡng.</li>
<li><strong>Output:</strong> Hiển thị thông số, cập nhật nhật ký và điều khiển relay/máy bơm.</li>
</ul>
</li>
</ul>
<h2 id="lưu-ý-an-toàn-và-xử-lý-khi-ram-đầy">9. Lưu ý an toàn và xử lý khi RAM đầy</h2>
<p>Nếu RAM tăng cao do chương trình ghi nhật ký quá nhiều, hệ thống có thể chậm hoặc dừng hoạt động. Thực hiện theo thứ tự an toàn:</p>
<ol>
<li>Kiểm tra mức sử dụng RAM bằng <code>free -h</code> trên Linux hoặc <code>top</code>.</li>
<li>Xác định tiến trình gây tăng RAM; không kết thúc tiến trình hệ thống một cách tùy tiện.</li>
<li>Kiểm tra cấu hình ghi log. Dùng xoay vòng nhật ký (log rotation), giới hạn dung lượng và thời gian lưu.</li>
<li>Không lưu toàn bộ nhật ký vào một biến hoặc danh sách trong RAM; ghi theo từng dòng hoặc theo lô nhỏ.</li>
<li>Sao lưu log cần thiết trước khi dọn dẹp. Không dùng lệnh xóa hàng loạt như <code>rm -rf</code> khi chưa xác minh đường dẫn.</li>
<li>Nếu máy bơm đang chạy, chuyển hệ thống về trạng thái an toàn theo quy trình vận hành trước khi khởi động lại chương trình.</li>
<li>Chỉ khởi động lại dịch vụ khi đã xác định nguyên nhân và có thể kiểm tra lại cảm biến, relay, máy bơm sau đó.</li>
</ol>
<p><strong>Khuyến nghị:</strong> Đặt cảnh báo khi RAM vượt ngưỡng vận hành đã kiểm thử, giới hạn kích thước log và kiểm tra trạng thái máy bơm độc lập với việc ghi log.</p>
<h2 id="kiểm-thử-trước-khi-bàn-giao">10. Kiểm thử trước khi bàn giao</h2>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> So sánh số đo cảm biến với thiết bị đo tham chiếu.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Thử tình huống độ ẩm thấp hơn ngưỡng.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Thử tình huống độ ẩm bằng hoặc cao hơn ngưỡng.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Kiểm tra máy bơm dừng khi chương trình kết thúc hoặc gặp lỗi.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Kiểm tra mất kết nối cảm biến và phản ứng an toàn.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Kiểm tra nhật ký có giới hạn dung lượng và RAM ổn định.</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Hướng dẫn người vận hành cách dừng hệ thống khẩn cấp.</li>
</ul>

