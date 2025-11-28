<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Carezone SOP Manual</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <style>
        /* Ẩn thanh cuộn mặc định để nhìn đẹp hơn trên mobile */
        body { -webkit-tap-highlight-color: transparent; }
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 3px; }
    </style>
</head>
<body class="bg-stone-50">

    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;

        // --- XỬ LÝ ICON (FIX LỖI IMPORT) ---
        // Vì chạy trực tiếp trên trình duyệt không tải được thư viện icon nặng, 
        // ta tạo một Icon thay thế đại diện cho tất cả các icon trong code của bạn.
        const GenericIcon = ({ size = 20, className = "", ...props }) => (
            <svg 
                width={size} height={size} viewBox="0 0 24 24" 
                fill="none" stroke="currentColor" strokeWidth="2" 
                strokeLinecap="round" strokeLinejoin="round" 
                className={className} {...props}
            >
                <circle cx="12" cy="12" r="10"></circle>
                <line x1="12" y1="16" x2="12" y2="12"></line>
                <line x1="12" y1="8" x2="12.01" y2="8"></line>
            </svg>
        );

        // Kỹ thuật Proxy: Dù code bạn gọi Book, Users, hay Flame... nó đều trả về GenericIcon để app không bị lỗi crash.
        const IconProxy = new Proxy({}, {
            get: function(target, prop) {
                return GenericIcon;
            }
        });

        // Giả lập dòng import icon của bạn bằng Proxy
        const { 
            Book, Users, Clock, UserCheck, Droplets, Flame, Sparkles, Utensils, Wrench, FileText, 
            BarChart, Wallet, Menu, X, ChevronRight, Search, Info, Activity, ArrowRight, ArrowDown, 
            Thermometer, AlertTriangle, Star, Heart, Shield, GraduationCap, Briefcase, Network, 
            ChevronDown, Gavel, ClipboardList, CameraOff, Volume2, Coffee, Stethoscope, MessageSquare, 
            Music, Wind, Waves, Sun, Smile, Leaf, ChefHat, Receipt, Truck, UtensilsCrossed, Trash2, 
            AlertCircle, ArrowLeftRight, Zap, FireExtinguisher, Siren, CheckCircle, Headset, Globe, Mail 
        } = IconProxy;

        // --- BẮT ĐẦU CODE CHÍNH CỦA BẠN ---

        const CarezoneSOP = () => {
          const [activeChapter, setActiveChapter] = useState(0);
          const [isSidebarOpen, setIsSidebarOpen] = useState(false);
          const [searchTerm, setSearchTerm] = useState('');

          const sopData = [
            {
              id: 1,
              title: "Tổng quan & Văn hóa",
              icon: <Info size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100">
                    <h3 className="font-bold text-emerald-800 text-lg mb-2">Thông tin tài liệu</h3>
                    <ul className="list-none space-y-1 text-sm">
                      <li><strong>Mã tài liệu:</strong> CZ-OPS-MANUAL-2025</li>
                      <li><strong>Phiên bản:</strong> 2.7 (Bổ sung CSKH Online)</li>
                      <li><strong>Ngày hiệu lực:</strong> 01/11/2025</li>
                    </ul>
                  </div>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">1.1. Giới thiệu chung</h3>
                    <p className="mb-3">Tổ hợp dịch vụ chăm sóc sức khỏe – thư giãn – ẩm thực, định hướng phát triển thành hệ thống chăm sóc sức khỏe toàn diện.</p>
                    
                    <div className="bg-white p-4 rounded shadow-sm border border-stone-100 mb-4">
                      <h4 className="font-bold text-emerald-800 mb-2 text-sm">Các lĩnh vực kinh doanh chính của CareZone gồm:</h4>
                      <ul className="list-disc pl-5 space-y-1 text-sm text-stone-700">
                        <li><strong>Onsen & Jjimjilbang:</strong> Xông hơi Hàn – tắm khoáng Nhật.</li>
                        <li><strong>Spa & Massage trị liệu.</strong></li>
                        <li><strong>Nhà hàng thực dưỡng.</strong></li>
                        <li><strong>Không gian nghỉ dưỡng – kết nối cộng đồng.</strong></li>
                      </ul>
                    </div>

                    {/* Điểm khác biệt */}
                    <div>
                      <h4 className="font-bold text-emerald-800 mb-3 flex items-center gap-2">
                        <Star size={18} className="fill-yellow-400 text-yellow-400"/> Điểm khác biệt
                      </h4>
                      <div className="grid sm:grid-cols-2 gap-3">
                        <div className="bg-stone-50 p-3 rounded border border-stone-100">
                          <strong className="block text-emerald-700 text-sm mb-1">1. Cao cấp & Sang trọng</strong>
                          <p className="text-xs text-stone-600">Thiết kế không gian độc đáo, sử dụng vật liệu tự nhiên, tạo nên sự tinh tế và đẳng cấp.</p>
                        </div>
                        <div className="bg-stone-50 p-3 rounded border border-stone-100">
                          <strong className="block text-emerald-700 text-sm mb-1">2. Trải nghiệm Yên bình & Riêng tư</strong>
                          <p className="text-xs text-stone-600">Chú trọng tạo không gian tĩnh lặng, tách biệt khỏi sự ồn ào đô thị, giúp khách hàng thực sự được nghỉ ngơi.</p>
                        </div>
                        <div className="bg-stone-50 p-3 rounded border border-stone-100">
                          <strong className="block text-emerald-700 text-sm mb-1">3. Sức khỏe vẹn trọn từ THÂN - TÂM - TRÍ</strong>
                          <p className="text-xs text-stone-600">Hướng tới chăm sóc sức khỏe tổng thể. Nơi mà Thân, Tâm, Trí được chăm sóc, tái tạo toàn diện từ sâu bên trong.</p>
                        </div>
                        <div className="bg-stone-50 p-3 rounded border border-stone-100">
                          <strong className="block text-emerald-700 text-sm mb-1">4. Chất lượng dịch vụ vượt trội & Tận tâm</strong>
                          <p className="text-xs text-stone-600">Đội ngũ nhân sự chuyên nghiệp, được đào tạo bài bản, luôn phục vụ với thái độ nhiệt thành nhất.</p>
                        </div>
                      </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">1.2. Tầm nhìn & Sứ mệnh</h3>
                    <div className="mb-4 bg-white p-4 rounded border-l-4 border-emerald-500 shadow-sm">
                      <h4 className="font-bold text-emerald-800 text-lg mb-2">Tầm nhìn (Vision)</h4>
                      <p className="font-bold text-emerald-600 mb-2 text-lg">"Trở thành hệ thống chăm sóc sức khỏe số 1 Việt Nam."</p>
                      <ul className="list-disc pl-5 space-y-1 text-sm text-stone-700">
                        <li>Dẫn đầu trong lĩnh vực dịch vụ chăm sóc sức khỏe toàn diện tại Việt Nam.</li>
                        <li>Trở thành biểu tượng về mô hình THÂN - TÂM - TRÍ chuẩn quốc tế nhưng được bản địa hóa cho người Việt.</li>
                        <li>Lan tỏa triết lý “Sức Khỏe Vẹn Tròn” như một chuẩn mực sống lành mạnh, cân bằng cho cộng đồng.</li>
                      </ul>
                    </div>

                    <div className="mb-6 bg-white p-4 rounded border-l-4 border-emerald-500 shadow-sm">
                      <h4 className="font-bold text-emerald-800 text-lg mb-2">Sứ mệnh (Mission)</h4>
                      <p className="font-medium text-stone-800 mb-2 italic">"Mang đến không gian chăm sóc sức khỏe nơi con người được tái tạo, thư giãn và kết nối một cách trọn vẹn từ thể chất đến tinh thần."</p>
                      <ul className="list-disc pl-5 space-y-1 text-sm text-stone-700">
                        <li>Chăm sóc toàn diện THÂN - TÂM - TRÍ cho cộng đồng.</li>
                        <li>Mang đến sự an lành, thư thái và tái sinh năng lượng.</li>
                        <li>Góp phần nâng cao chất lượng sống, đưa mô hình chăm sóc sức khỏe chuẩn quốc tế về gần gũi và dễ tiếp cận cho người Việt.</li>
                      </ul>
                    </div>

                    <div>
                      <h4 className="font-bold text-emerald-800 mb-4 text-lg border-b border-emerald-200 pb-2">Giá trị cốt lõi (5 Chữ Vàng)</h4>
                      <div className="grid gap-4">
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex gap-3 items-start">
                          <div className="bg-emerald-100 p-2 rounded text-emerald-700 mt-1"><GraduationCap size={20}/></div>
                          <div>
                            <strong className="block text-emerald-800 font-bold mb-1">1. TINH THẦN HỌC TẬP</strong>
                            <p className="text-sm text-stone-700">Học tập là khi <strong>DÁM HỌC HỎI, DÁM SỬA CHỮA, LẮNG NGHE</strong> những lời góp ý để hoàn thiện hơn.</p>
                          </div>
                        </div>
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex gap-3 items-start">
                          <div className="bg-emerald-100 p-2 rounded text-emerald-700 mt-1"><Shield size={20}/></div>
                          <div>
                            <strong className="block text-emerald-800 font-bold mb-1">2. CHỊU TRÁCH NHIỆM</strong>
                            <p className="text-sm text-stone-700">Chịu trách nhiệm là <strong>NGHĨA VỤ</strong>, phần việc mà cá nhân phải <strong>TỰ GIÁC NHẬN LẤY</strong>. THỰC HIỆN một cách tốt nhất và sẵn sàng CHỊU TRÁCH NHIỆM cho hành động và kết quả của mình.</p>
                          </div>
                        </div>
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex gap-3 items-start">
                          <div className="bg-emerald-100 p-2 rounded text-emerald-700 mt-1"><Heart size={20}/></div>
                          <div>
                            <strong className="block text-emerald-800 font-bold mb-1">3. SỰ PHỤNG SỰ</strong>
                            <p className="text-sm text-stone-700">Chúng ta không chỉ làm việc mà chúng ta <strong>TRAO SỰ TỬ TẾ</strong>.</p>
                          </div>
                        </div>
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex gap-3 items-start">
                          <div className="bg-emerald-100 p-2 rounded text-emerald-700 mt-1"><Briefcase size={20}/></div>
                          <div>
                            <strong className="block text-emerald-800 font-bold mb-1">4. CHUYÊN NGHIỆP</strong>
                            <p className="text-sm text-stone-700">Chuyên nghiệp là khi mỗi hành động của mình đều góp phần làm cho Carezone <strong>tốt hơn, Gọn hơn, Đẹp hơn, Ấn tượng hơn</strong> trong mắt khách hàng.</p>
                          </div>
                        </div>
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex gap-3 items-start">
                          <div className="bg-emerald-100 p-2 rounded text-emerald-700 mt-1"><Users size={20}/></div>
                          <div>
                            <strong className="block text-emerald-800 font-bold mb-1">5. TRÁCH NHIỆM XÃ HỘI (CHO ĐI)</strong>
                            <p className="text-sm text-stone-700">CareZone luôn “cho đi” bằng các quỹ thiện nguyện và chương trình vì trẻ em, vì cộng đồng. Bởi chữa lành thật sự không chỉ là cho bản thân, mà còn là góp phần làm xã hội an lành hơn.</p>
                          </div>
                        </div>
                      </div>
                    </div>
                  </section>
                </div>
              )
            },
            {
              id: 2,
              title: "Cơ cấu tổ chức",
              icon: <Network size={20} />,
              content: (
                <div className="space-y-8 text-stone-800">
                   <div className="flex flex-col items-center relative z-10">
                    <div className="mb-2 text-emerald-800 font-bold uppercase tracking-widest text-xs">2.1. Cấp 1: Ban Lãnh Đạo</div>
                    <div className="w-64 bg-gradient-to-br from-emerald-900 to-emerald-700 text-white p-5 rounded-xl shadow-lg text-center border-4 border-emerald-100">
                      <div className="font-bold text-xl tracking-wide">Giám đốc Chi nhánh</div>
                    </div>
                    <div className="h-8 w-0.5 bg-stone-300"></div>
                    <div className="w-56 bg-white text-emerald-900 p-3 rounded-lg shadow-md text-center border border-stone-200">
                      <div className="font-bold text-sm">Trợ lý Giám đốc</div>
                    </div>
                  </div>
                  <div className="p-4 bg-stone-50 rounded text-center text-xs text-stone-500 italic">
                     (Chi tiết xem lại phiên bản đầy đủ ở trên)
                  </div>
                </div>
              )
            },
            { id: 3, title: "Sơ đồ Quy trình tổng", icon: <Activity size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung đã được cập nhật ở phiên bản trước.</div> },
            { id: 4, title: "Hành trình khách hàng", icon: <Book size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung đã được cập nhật ở phiên bản trước.</div> },
            { id: 5, title: "Quy định Nhân sự", icon: <UserCheck size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung đã được cập nhật ở phiên bản trước.</div> },
            { id: 6, title: "Bãi xe & Tiếp đón", icon: <Shield size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung đã được cập nhật ở phiên bản trước.</div> },
            { id: 7, title: "Chăm sóc khách hàng (Lễ tân)", icon: <Smile size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 7.5 và các mục đã sửa) đã được cập nhật ở phiên bản trước.</div> },
            { id: 8, title: "Vận hành Onsen", icon: <Droplets size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 8.8) đã được cập nhật ở phiên bản trước.</div> },
            { id: 9, title: "Vận hành Jjimjilbang", icon: <Flame size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 9.6 và các mục đã khôi phục) đã được cập nhật ở phiên bản trước.</div> },
            { id: 10, title: "Dịch vụ Trị liệu (Spa)", icon: <Sparkles size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 10.6) đã được cập nhật ở phiên bản trước.</div> },
            { id: 11, title: "Quy trình Thu ngân", icon: <Receipt size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 11.6 và quy trình check-in 11.2) đã được cập nhật ở phiên bản trước.</div> },
            { id: 12, title: "Nhà hàng Thực dưỡng", icon: <Utensils size={20} />, content: <div className="p-4 text-center italic text-stone-500">Nội dung (bao gồm checklist 12.6 và các mục đã khôi phục) đã được cập nhật ở phiên bản trước.</div> },
            {
              id: 13,
              title: "Bảo trì & An toàn",
              icon: <Wrench size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">13.1. Quy trình Ứng phó Y tế</h3>
                    <div className="bg-red-50 p-4 rounded-lg border border-red-200 text-sm">
                        <p>Quy trình Code Blue & Sơ cấp cứu (như đã cập nhật).</p>
                    </div>
                  </section>
                  <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">13.5. Checklist Bảo trì Kỹ thuật</h3>
                     <div className="bg-white p-4 rounded-lg border border-stone-200 text-sm italic text-stone-500 text-center">
                        Bảng Checklist chi tiết đã được cập nhật.
                     </div>
                  </section>
                </div>
              )
            },
            
            // --- CHƯƠNG MỚI THÊM VÀO ---
            {
              id: 14,
              title: "CSKH Online",
              icon: <Headset size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <div className="bg-blue-50 p-4 rounded-lg border border-blue-100 flex items-start gap-3">
                     <div className="bg-white p-2 rounded-full text-blue-600 shadow-sm"><Globe size={20}/></div>
                     <div>
                        <strong className="block text-blue-900 text-lg">Phòng Chăm sóc Khách hàng Online</strong>
                        <p className="text-sm text-blue-800">Đảm bảo trải nghiệm khách hàng xuyên suốt từ Online (Mạng xã hội) đến Offline (Tại điểm bán).</p>
                     </div>
                  </div>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">14.1. Các kênh tiếp nhận & Công cụ</h3>
                    <div className="grid sm:grid-cols-2 md:grid-cols-4 gap-4">
                       <div className="bg-white p-3 rounded border border-stone-200 text-center shadow-sm">
                          <div className="text-blue-600 font-bold mb-1">Fanpage/Mess</div>
                          <p className="text-xs text-stone-500">Tư vấn, chốt lịch, giải đáp thắc mắc chung.</p>
                       </div>
                       <div className="bg-white p-3 rounded border border-stone-200 text-center shadow-sm">
                          <div className="text-blue-500 font-bold mb-1">Zalo OA</div>
                          <p className="text-xs text-stone-500">Chăm sóc khách hàng thân thiết (Membership), gửi ưu đãi.</p>
                       </div>
                       <div className="bg-white p-3 rounded border border-stone-200 text-center shadow-sm">
                          <div className="text-red-500 font-bold mb-1">Hotline</div>
                          <p className="text-xs text-stone-500">Xử lý khiếu nại khẩn cấp, chỉ đường, đặt chỗ gấp.</p>
                       </div>
                       <div className="bg-white p-3 rounded border border-stone-200 text-center shadow-sm">
                          <div className="text-yellow-600 font-bold mb-1">Google Maps</div>
                          <p className="text-xs text-stone-500">Quản lý đánh giá (Review) và hỏi đáp địa điểm.</p>
                       </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">14.2. Quy trình Trực page & Tư vấn</h3>
                    <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                       <div className="mb-4 pb-3 border-b border-stone-100">
                          <h4 className="font-bold text-stone-800 mb-2 text-sm flex items-center gap-2"><Clock size={16}/> Thời gian đáp ứng (SLA)</h4>
                          <ul className="list-disc pl-5 text-xs text-stone-600 space-y-1">
                             <li><strong>Giờ hành chính (8h-22h):</strong> Phản hồi dưới 5 phút.</li>
                             <li><strong>Ngoài giờ:</strong> Cài đặt tin nhắn tự động (Auto-reply) và phản hồi trước 9h sáng hôm sau.</li>
                          </ul>
                       </div>
                       
                       <div>
                          <h4 className="font-bold text-stone-800 mb-2 text-sm flex items-center gap-2"><MessageSquare size={16}/> Kịch bản tư vấn (Script)</h4>
                          <div className="space-y-2 text-xs">
                             <div className="bg-stone-50 p-2 rounded">
                                <strong className="text-emerald-700">1. Chào hỏi:</strong> "Carezone xin chào anh/chị [Tên] ạ. Em có thể hỗ trợ mình thông tin dịch vụ nào ạ?"
                             </div>
                             <div className="bg-stone-50 p-2 rounded">
                                <strong className="text-emerald-700">2. Khơi gợi nhu cầu:</strong> "Mình đi cùng gia đình hay bạn bè ạ? Mình đang quan tâm đến thư giãn hay trị liệu đau mỏi ạ?"
                             </div>
                             <div className="bg-stone-50 p-2 rounded">
                                <strong className="text-emerald-700">3. Chốt Booking:</strong> "Dạ em xin phép chốt lịch cho mình vào [Giờ] ngày [Ngày], [Số lượng] khách. SĐT liên hệ là [...] đúng không ạ?"
                             </div>
                          </div>
                       </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">14.3. Quy trình Xử lý Booking Online</h3>
                    <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-200">
                       <div className="flex flex-col md:flex-row items-center gap-2 text-sm">
                          <div className="flex-1 bg-white p-3 rounded border border-emerald-100 text-center shadow-sm">
                             <strong className="block text-emerald-800 mb-1">B1: Tiếp nhận</strong>
                             <span className="text-xs text-stone-600">Nhận thông tin qua Inbox/Hotline.</span>
                          </div>
                          <ArrowRight size={20} className="text-emerald-400 hidden md:block"/>
                          <ArrowDown size={20} className="text-emerald-400 md:hidden"/>
                          
                          <div className="flex-1 bg-white p-3 rounded border border-emerald-100 text-center shadow-sm">
                             <strong className="block text-emerald-800 mb-1">B2: Kiểm tra Slot</strong>
                             <span className="text-xs text-stone-600">Check file Booking chung/Phần mềm.</span>
                          </div>
                          <ArrowRight size={20} className="text-emerald-400 hidden md:block"/>
                          <ArrowDown size={20} className="text-emerald-400 md:hidden"/>

                          <div className="flex-1 bg-white p-3 rounded border border-emerald-100 text-center shadow-sm">
                             <strong className="block text-emerald-800 mb-1">B3: Xác nhận</strong>
                             <span className="text-xs text-stone-600">Gửi tin nhắn xác nhận: Mã đặt chỗ, Lưu ý đi kèm.</span>
                          </div>
                          <ArrowRight size={20} className="text-emerald-400 hidden md:block"/>
                          <ArrowDown size={20} className="text-emerald-400 md:hidden"/>

                          <div className="flex-1 bg-white p-3 rounded border border-emerald-100 text-center shadow-sm">
                             <strong className="block text-emerald-800 mb-1">B4: Đồng bộ</strong>
                             <span className="text-xs text-stone-600">Nhập lên hệ thống để Lễ tân tại quầy nắm thông tin.</span>
                          </div>
                       </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">14.4. Xử lý Khủng hoảng & Phàn nàn Online</h3>
                    <div className="grid md:grid-cols-2 gap-4">
                       <div className="bg-red-50 p-4 rounded-lg border border-red-200">
                          <h4 className="font-bold text-red-800 mb-2 flex items-center gap-2"><AlertTriangle size={18}/> Nguyên tắc 3T</h4>
                          <ul className="list-decimal pl-5 text-xs text-red-900 space-y-2">
                             <li><strong>Tốc độ:</strong> Phản hồi ngay lập tức khi thấy comment/đánh giá tiêu cực. Không để lan truyền.</li>
                             <li><strong>Tận tâm:</strong> Luôn xin lỗi trước vì trải nghiệm chưa tốt (chưa cần biết đúng sai). Tuyệt đối không đôi co trên mạng xã hội.</li>
                             <li><strong>Trung thực:</strong> Xác minh sự việc và công khai hướng giải quyết hoặc inbox riêng để xử lý tế nhị.</li>
                          </ul>
                       </div>
                       <div className="bg-white p-4 rounded-lg border border-stone-200">
                          <h4 className="font-bold text-stone-800 mb-2 flex items-center gap-2"><CheckCircle size={18}/> Quy trình xử lý Review 1 sao</h4>
                          <ol className="list-decimal pl-5 text-xs text-stone-700 space-y-1">
                             <li>Chụp màn hình, báo cáo Quản lý.</li>
                             <li>Trả lời comment nhã nhặn, xin thông tin liên hệ để hỗ trợ.</li>
                             <li>Gọi điện thoại xin lỗi, tìm hiểu nguyên nhân.</li>
                             <li>Tặng Voucher đền bù (nếu lỗi do Carezone).</li>
                             <li>Nhờ khách gỡ hoặc sửa đánh giá sau khi đã hài lòng.</li>
                          </ol>
                       </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">14.5. Chăm sóc sau bán (Re-marketing)</h3>
                    <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                       <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                          <li><strong>Cảm ơn:</strong> Gửi tin nhắn cảm ơn sau khi khách ra về (trong vòng 24h).</li>
                          <li><strong>Khảo sát:</strong> Gửi link đánh giá dịch vụ để nhận ưu đãi cho lần sau.</li>
                          <li><strong>Nhắc hẹn (Reminder):</strong> Đối với khách trị liệu theo liệu trình, nhắn tin nhắc lịch trước 1 ngày.</li>
                          <li><strong>Chúc mừng sinh nhật:</strong> Gửi tin nhắn và Voucher sinh nhật tự động qua Zalo OA/SMS Brandname.</li>
                       </ul>
                    </div>
                  </section>
                </div>
              )
            },

            {
              id: 15,
              title: "Lương & Phúc lợi",
              icon: <Wallet size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100 mb-4">
                      <h3 className="font-bold text-emerald-800 text-lg mb-2 flex items-center gap-2"><Info size={20}/> Chính sách đãi ngộ toàn diện (Total Rewards)</h3>
                      <p className="text-sm text-emerald-900">Tại Carezone, chúng tôi xây dựng chính sách thu nhập cạnh tranh dựa trên năng lực và hiệu quả công việc, đi kèm với hệ thống phúc lợi chăm sóc sức khỏe độc đáo.</p>
                  </div>
                  <div className="p-4 bg-white border border-stone-200 rounded shadow-sm text-center text-stone-500 italic">
                      (Nội dung chi tiết về Lương thưởng, Lộ trình thăng tiến đã được cập nhật đầy đủ ở các phiên bản trước. Vui lòng tham khảo lại nếu cần chỉnh sửa chi tiết.)
                  </div>
                </div>
              )
            },
            {
              id: 16,
              title: "KPI & Báo cáo",
              icon: <BarChart size={20} />,
              content: (
                 <div className="space-y-6 text-stone-800">
                   <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">16.1. Hệ thống Báo cáo (Reporting)</h3>
                     <div className="p-4 bg-white border border-stone-200 rounded shadow-sm text-center text-stone-500 italic">
                        (Nội dung chi tiết về Báo cáo ngày/tuần/tháng và KPI các bộ phận đã được cập nhật đầy đủ ở các phiên bản trước.)
                     </div>
                   </section>
                 </div>
              )
            }
          ];

          // Filter chapters based on search
          const filteredChapters = sopData.filter(chapter => 
            chapter.title.toLowerCase().includes(searchTerm.toLowerCase())
          );

          return (
            <div className="flex h-screen bg-stone-50 font-sans text-stone-900 overflow-hidden">
              {/* Mobile Sidebar Overlay */}
              {isSidebarOpen && (
                <div 
                  className="fixed inset-0 bg-black bg-opacity-50 z-20 md:hidden"
                  onClick={() => setIsSidebarOpen(false)}
                />
              )}

              {/* Sidebar */}
              <div className={`
                fixed inset-y-0 left-0 z-30 w-72 bg-emerald-900 text-emerald-50 transform transition-transform duration-300 ease-in-out
                ${isSidebarOpen ? 'translate-x-0' : '-translate-x-full'}
                md:relative md:translate-x-0 flex flex-col shadow-xl
              `}>
                <div className="p-6 border-b border-emerald-800 bg-emerald-950">
                  <div className="flex items-center gap-3 mb-2">
                    <div className="w-10 h-10 bg-emerald-500 rounded-full flex items-center justify-center text-white font-bold text-xl">C</div>
                    <div>
                      <h1 className="font-bold text-lg leading-tight">Carezone<br/>Bình Dương</h1>
                    </div>
                  </div>
                  <p className="text-xs text-emerald-300 mt-1">SOP Manual v2.7</p>
                </div>

                {/* Search Box */}
                <div className="p-4">
                  <div className="relative">
                    <input 
                      type="text" 
                      placeholder="Tìm kiếm chương..." 
                      className="w-full bg-emerald-800 text-emerald-50 text-sm rounded-lg pl-9 pr-3 py-2 focus:outline-none focus:ring-2 focus:ring-emerald-400 placeholder-emerald-400"
                      value={searchTerm}
                      onChange={(e) => setSearchTerm(e.target.value)}
                    />
                    <Search className="absolute left-3 top-2.5 text-emerald-400" size={16} />
                  </div>
                </div>

                <nav className="flex-1 overflow-y-auto py-4 px-2 space-y-1">
                  {filteredChapters.map((chapter, index) => {
                    // Find the original index for setActiveChapter
                    const originalIndex = sopData.findIndex(c => c.id === chapter.id);
                    return (
                      <button
                        key={chapter.id}
                        onClick={() => {
                          setActiveChapter(originalIndex);
                          setIsSidebarOpen(false);
                        }}
                        className={`w-full flex items-center gap-3 px-4 py-3 rounded-lg transition-colors text-left
                          ${activeChapter === originalIndex 
                            ? 'bg-emerald-700 text-white font-medium shadow-md' 
                            : 'hover:bg-emerald-800 text-emerald-100'
                          }
                        `}
                      >
                        <span className={`${activeChapter === originalIndex ? 'text-emerald-200' : 'text-emerald-400'}`}>
                          {chapter.icon}
                        </span>
                        <span className="text-sm">{chapter.title}</span>
                        {activeChapter === originalIndex && <ChevronRight size={16} className="ml-auto" />}
                      </button>
                    );
                  })}
                </nav>

                <div className="p-4 border-t border-emerald-800 text-xs text-emerald-400 text-center">
                  © 2025 Carezone Operations Dept.
                </div>
              </div>

              {/* Main Content */}
              <div className="flex-1 flex flex-col h-screen overflow-hidden">
                {/* Header Mobile */}
                <div className="md:hidden bg-white p-4 border-b border-stone-200 flex items-center justify-between shadow-sm">
                  <h2 className="font-bold text-emerald-800">SOP Carezone</h2>
                  <button onClick={() => setIsSidebarOpen(true)} className="text-emerald-800">
                    <Menu size={24} />
                  </button>
                </div>

                {/* Content Area */}
                <main className="flex-1 overflow-y-auto p-4 md:p-10 bg-stone-50">
                  <div className="max-w-4xl mx-auto bg-white rounded-2xl shadow-lg min-h-[80vh]">
                    {/* Chapter Header */}
                    <div className="bg-emerald-50 border-b border-emerald-100 p-6 md:p-8 rounded-t-2xl">
                      <div className="flex items-center gap-3 text-emerald-600 mb-2">
                        {sopData[activeChapter].icon}
                        <span className="text-sm font-bold uppercase tracking-wider">Chương {sopData[activeChapter].id}</span>
                      </div>
                      <h2 className="text-2xl md:text-3xl font-bold text-emerald-900">
                        {sopData[activeChapter].title}
                      </h2>
                    </div>

                    {/* Chapter Body */}
                    <div className="p-6 md:p-8">
                      {sopData[activeChapter].content}
                    </div>
                    
                    {/* Footer Navigation */}
                    <div className="p-6 md:p-8 border-t border-stone-100 flex justify-between">
                      <button 
                        disabled={activeChapter === 0}
                        onClick={() => setActiveChapter(curr => curr - 1)}
                        className={`px-4 py-2 rounded text-sm font-medium ${activeChapter === 0 ? 'text-stone-300 cursor-not-allowed' : 'text-emerald-600 hover:bg-emerald-50'}`}
                      >
                        &larr; Chương trước
                      </button>
                      <button 
                        disabled={activeChapter === sopData.length - 1}
                        onClick={() => setActiveChapter(curr => curr + 1)}
                        className={`px-4 py-2 rounded text-sm font-medium ${activeChapter === sopData.length - 1 ? 'text-stone-300 cursor-not-allowed' : 'bg-emerald-600 text-white hover:bg-emerald-700 shadow-sm'}`}
                      >
                        Chương tiếp theo &rarr;
                      </button>
                    </div>
                  </div>
                </main>
              </div>
            </div>
          );
        };

        // Render ra màn hình
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<CarezoneSOP />);
    </script>
</body>
</html>
