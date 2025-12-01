<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carezone SOP Manual</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    
    <script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
    
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <script src="https://unpkg.com/lucide-react@0.263.1/dist/umd/lucide-react.min.js"></script>

    <style>
        /* Tùy chỉnh thanh cuộn cho đẹp hơn */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1; 
        }
        ::-webkit-scrollbar-thumb {
            background: #10b981; 
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #047857; 
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-900">

    <div id="root"></div>

    <script type="text/babel">
        // --- PHẦN KHỞI TẠO MÔI TRƯỜNG ---
        const { useState, useEffect, useRef } = React;
        
        // Lấy tất cả icon từ thư viện LucideReact đã nhúng ở trên
        // Thay thế dòng import dài của bạn bằng destructuring từ biến global
        const { 
            Book, Users, Clock, UserCheck, Droplets, Flame, Sparkles, Utensils, Wrench, FileText, 
            BarChart, Wallet, Menu, X, ChevronRight, Search, Info, Activity, ArrowRight, ArrowDown, 
            Thermometer, AlertTriangle, Star, Heart, Shield, GraduationCap, Briefcase, Network, 
            ChevronDown, Gavel, ClipboardList, CameraOff, Volume2, Coffee, Stethoscope, MessageSquare, 
            Music, Wind, Waves, Sun, Smile, Leaf, ChefHat, Receipt, Truck, UtensilsCrossed, Trash2, 
            AlertCircle, ArrowLeftRight, Zap, FireExtinguisher, Siren, CheckCircle, TrendingUp, Award, 
            HandHeart, Sparkle, MessageCircle, Send, Loader, RefreshCw 
        } = lucideReact;

        // --- BẮT ĐẦU CODE CỦA BẠN (Đã chỉnh sửa nhẹ phần export) ---

        const CarezoneSOP = () => {
          const [activeChapter, setActiveChapter] = useState(0);
          const [isSidebarOpen, setIsSidebarOpen] = useState(false);
          const [searchTerm, setSearchTerm] = useState('');
          
          // --- AI FEATURES STATES ---
          const [isChatOpen, setIsChatOpen] = useState(false);
          const [chatMessages, setChatMessages] = useState([
            { role: 'system', text: 'Xin chào! Tôi là trợ lý ảo Carezone. Bạn cần tra cứu quy trình nào?' }
          ]);
          const [userQuery, setUserQuery] = useState('');
          const [isAiThinking, setIsAiThinking] = useState(false);
          
          const [quizData, setQuizData] = useState(null);
          const [isQuizLoading, setIsQuizLoading] = useState(false);
          const chatEndRef = useRef(null);

          // API Key placeholder - provided by environment
          const apiKey = ""; 

          const scrollToBottom = () => {
            chatEndRef.current?.scrollIntoView({ behavior: "smooth" });
          };

          useEffect(() => {
            scrollToBottom();
          }, [chatMessages, isChatOpen]);

          // --- DATA ---
          const levelsData = {
            tap_su: {
              title: "KTV Tập sự (Level 1)",
              desc: "Học việc",
              color: "stone",
              culture: ["Ham học hỏi: Sẵn sàng ghi chép, thực hành.", "Tuân thủ: Đúng giờ, đúng đồng phục, quy trình vệ sinh.", "Trung thực: Báo cáo đúng sự thật."],
              skills: ["Massage cơ bản: Foot, Body Aroma, Gội đầu.", "Setup phòng: Thay ga, gấp khăn, đốt tinh dầu.", "Quan sát: Hỗ trợ các KTV chính."],
              knowledge: ["Sản phẩm: Tên & giá các gói dịch vụ cơ bản.", "Địa điểm: Sơ đồ phòng trị liệu, kho vật tư.", "Quy định: Nội quy Spa, an toàn lao động."]
            },
            chinh_thuc: {
              title: "KTV Chính thức (Level 2)",
              desc: "Thạo nghề",
              color: "emerald",
              culture: ["Chuyên nghiệp: Thái độ phục vụ ân cần, giọng nói nhẹ nhàng.", "Trách nhiệm: Tự quản lý phòng trị liệu và dụng cụ.", "Hợp tác: Hỗ trợ đồng nghiệp trong ca."],
              skills: ["Trị liệu nâng cao: Thái, Đá nóng, Bầu, Shiatsu.", "Tư vấn: Nhận biết tình trạng sức khỏe khách để gợi ý bài.", "Xử lý tình huống: Giải quyết thắc mắc cơ bản."],
              knowledge: ["Chuyên sâu: Huyệt đạo, công dụng tinh dầu.", "Quy trình: Check-in/Check-out, xử lý đồ vải.", "KPI: Hiểu cách tính lương & năng suất."]
            },
            truong_nhom: {
              title: "KTV Trưởng nhóm (Level 3)",
              desc: "Quản lý & Đào tạo",
              color: "purple",
              culture: ["Gương mẫu: Là hình mẫu về tay nghề và thái độ.", "Dẫn dắt: Động viên tinh thần nhân viên trong ca.", "Công bằng: Phân chia tour công tâm."],
              skills: ["Đào tạo: Hướng dẫn kỹ thuật cho nhân viên mới.", "Quản lý ca: Sắp xếp lịch trực, kiểm tra vệ sinh đầu/cuối ca.", "Giải quyết khiếu nại: Xử lý complaint cấp độ 1."],
              knowledge: ["Báo cáo: Làm báo cáo ngày, kiểm kê kho.", "Hệ thống: Sử dụng thành thạo phần mềm POS/CRM.", "Đánh giá: Kỹ năng đánh giá tay nghề nhân viên."]
            }
          };

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
                      <li><strong>Phiên bản:</strong> 2.8 (Tiếng Việt hóa)</li>
                      <li><strong>Ngày hiệu lực:</strong> 01/12/2025</li>
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
                      <h4 className="font-bold text-emerald-800 text-lg mb-2">Tầm nhìn</h4>
                      <p className="font-bold text-emerald-600 mb-2 text-lg">"Trở thành hệ thống chăm sóc sức khỏe số 1 Việt Nam."</p>
                      <ul className="list-disc pl-5 space-y-1 text-sm text-stone-700">
                        <li>Dẫn đầu trong lĩnh vực dịch vụ chăm sóc sức khỏe toàn diện tại Việt Nam.</li>
                        <li>Trở thành biểu tượng về mô hình THÂN - TÂM - TRÍ chuẩn quốc tế nhưng được bản địa hóa cho người Việt.</li>
                        <li>Lan tỏa triết lý “Sức Khỏe Vẹn Tròn” như một chuẩn mực sống lành mạnh, cân bằng cho cộng đồng.</li>
                      </ul>
                    </div>

                    <div className="mb-6 bg-white p-4 rounded border-l-4 border-emerald-500 shadow-sm">
                      <h4 className="font-bold text-emerald-800 text-lg mb-2">Sứ mệnh</h4>
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
                  {/* Cấp 1: Ban Lãnh Đạo */}
                  <div className="flex flex-col items-center relative z-10">
                    <div className="mb-2 text-emerald-800 font-bold uppercase tracking-widest text-xs">2.1. Cấp 1: Ban Lãnh Đạo</div>
                    <div className="w-64 bg-gradient-to-br from-emerald-900 to-emerald-700 text-white p-5 rounded-xl shadow-lg text-center border-4 border-emerald-100 transform transition hover:scale-105 duration-300">
                      <div className="font-bold text-xl tracking-wide">Giám đốc Chi nhánh</div>
                    </div>
                    
                    {/* Connector Line */}
                    <div className="h-8 w-0.5 bg-stone-300"></div>
                    
                    <div className="w-56 bg-white text-emerald-900 p-3 rounded-lg shadow-md text-center border border-stone-200 relative">
                      <div className="font-bold text-sm">Trợ lý Giám đốc</div>
                      {/* Downward connector for next level */}
                      <div className="absolute left-1/2 -bottom-8 h-8 w-0.5 bg-stone-300 transform -translate-x-1/2"></div>
                    </div>
                  </div>

                  {/* Cấp 2: Các Khối Chức Năng */}
                  <div className="relative pt-8">
                    <div className="text-center mb-6 text-emerald-800 font-bold uppercase tracking-widest text-xs">2.2. Cấp 2: Các Khối Chức Năng</div>
                    
                    {/* Main vertical line connecting all blocks */}
                    <div className="absolute top-0 left-6 md:left-8 bottom-8 w-0.5 bg-stone-200"></div>

                    <div className="space-y-8 relative">
                      
                      {/* BLOCK A: Office */}
                      <div className="relative pl-16 md:pl-20">
                        {/* Horizontal Connector */}
                        <div className="absolute left-6 md:left-8 top-6 w-8 md:w-10 h-0.5 bg-stone-200"></div>
                        {/* Circle Marker */}
                        <div className="absolute left-6 md:left-8 top-6 w-3 h-3 rounded-full bg-stone-400 transform -translate-x-1/2 -translate-y-1/2 border-2 border-white"></div>
                        
                        {/* Card */}
                        <div className="bg-white rounded-xl shadow-sm border-l-4 border-stone-400 overflow-hidden">
                          <div className="bg-stone-100 p-3 border-b border-stone-200 flex items-center gap-2">
                            <div className="w-8 h-8 rounded bg-stone-200 flex items-center justify-center text-stone-600 font-bold">A</div>
                            <h4 className="font-bold text-stone-700 uppercase text-sm">Khối Văn Phòng & Hỗ Trợ</h4>
                          </div>
                          <div className="p-4 grid md:grid-cols-2 gap-4">
                              <div className="space-y-1">
                                <strong className="text-emerald-800 text-sm flex items-center gap-2"><Users size={14}/> Hành chính - Nhân sự</strong>
                                <ul className="text-xs text-stone-600 pl-6 list-disc">
                                   <li>Chuyên viên HCNS tổng hợp</li>
                                   <li>Tạp vụ</li>
                                   <li className="font-semibold text-emerald-700">Bảo vệ</li>
                                </ul>
                              </div>
                              <div className="space-y-1">
                                <strong className="text-emerald-800 text-sm flex items-center gap-2"><Wallet size={14}/> Tài chính - Kế toán</strong>
                                <ul className="text-xs text-stone-600 pl-6 list-disc">
                                   <li>Kế toán trưởng</li>
                                   <li>Kế toán doanh thu / Thu ngân</li>
                                   <li>Nhân viên thu mua</li>
                                </ul>
                              </div>
                          </div>
                        </div>
                      </div>

                      {/* BLOCK B: Business */}
                      <div className="relative pl-16 md:pl-20">
                        <div className="absolute left-6 md:left-8 top-6 w-8 md:w-10 h-0.5 bg-stone-200"></div>
                        <div className="absolute left-6 md:left-8 top-6 w-3 h-3 rounded-full bg-blue-400 transform -translate-x-1/2 -translate-y-1/2 border-2 border-white"></div>
                        
                        <div className="bg-white rounded-xl shadow-sm border-l-4 border-blue-500 overflow-hidden">
                          <div className="bg-blue-50 p-3 border-b border-blue-100 flex items-center gap-2">
                            <div className="w-8 h-8 rounded bg-blue-200 flex items-center justify-center text-blue-700 font-bold">B</div>
                            <h4 className="font-bold text-blue-800 uppercase text-sm">Khối Kinh Doanh & Marketing</h4>
                          </div>
                          <div className="p-4">
                              <div className="space-y-1">
                                <strong className="text-blue-900 text-sm flex items-center gap-2"><Activity size={14}/> Phòng Sales & Marketing</strong>
                                <ul className="text-xs text-stone-600 pl-6 list-disc grid md:grid-cols-2 gap-x-4">
                                   <li>Trưởng phòng Marketing</li>
                                   <li>Chuyên viên Nội dung & Digital</li>
                                   <li>Nhân viên Sales / CSKH Online</li>
                                </ul>
                              </div>
                          </div>
                        </div>
                      </div>

                      {/* BLOCK C: Operations */}
                      <div className="relative pl-16 md:pl-20">
                        <div className="absolute left-6 md:left-8 top-6 w-8 md:w-10 h-0.5 bg-stone-200"></div>
                        <div className="absolute left-6 md:left-8 top-6 w-3 h-3 rounded-full bg-orange-400 transform -translate-x-1/2 -translate-y-1/2 border-2 border-white"></div>
                        
                        <div className="bg-white rounded-xl shadow-sm border-l-4 border-orange-500 overflow-hidden">
                          <div className="bg-orange-50 p-3 border-b border-orange-100 flex items-center gap-2">
                            <div className="w-8 h-8 rounded bg-orange-200 flex items-center justify-center text-orange-800 font-bold">C</div>
                            <h4 className="font-bold text-orange-800 uppercase text-sm">Khối Vận Hành Dịch Vụ</h4>
                          </div>
                          <div className="p-4 grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
                              <div className="bg-orange-50/30 p-2 rounded border border-orange-100">
                                <div className="font-bold text-xs text-orange-900 uppercase mb-1">CSKH Offline</div>
                                <ul className="text-[10px] text-stone-600 list-disc pl-4">
                                  <li>Trưởng bộ phận</li>
                                  <li>Nhân viên CSKH</li>
                                </ul>
                              </div>
                              <div className="bg-orange-50/30 p-2 rounded border border-orange-100">
                                <div className="font-bold text-xs text-orange-900 uppercase mb-1">Onsen & Jjimjilbang</div>
                                <ul className="text-[10px] text-stone-600 list-disc pl-4">
                                  <li>Quản lý khu vực</li>
                                  <li>Nhân viên trực khu</li>
                                </ul>
                              </div>
                              <div className="bg-orange-50/30 p-2 rounded border border-orange-100">
                                <div className="font-bold text-xs text-orange-900 uppercase mb-1">Spa & Massage</div>
                                <ul className="text-[10px] text-stone-600 list-disc pl-4">
                                  <li>Quản lý Spa</li>
                                  <li>Kỹ thuật viên</li>
                                </ul>
                              </div>
                              <div className="bg-orange-50/30 p-2 rounded border border-orange-100">
                                <div className="font-bold text-xs text-orange-900 uppercase mb-1">Nhà hàng</div>
                                <ul className="text-[10px] text-stone-600 list-disc pl-4">
                                  <li>Quản lý / Giám sát</li>
                                  <li>Bếp / Phụ bếp</li>
                                  <li>Phục vụ / Pha chế</li>
                                </ul>
                              </div>
                              <div className="bg-orange-50/30 p-2 rounded border border-orange-100 sm:col-span-2 lg:col-span-1">
                                <div className="font-bold text-xs text-orange-900 uppercase mb-1">Kỹ thuật</div>
                                <ul className="text-[10px] text-stone-600 list-disc pl-4">
                                  <li>NV Kỹ thuật & Bảo trì</li>
                                </ul>
                              </div>
                          </div>
                        </div>
                      </div>

                    </div>
                  </div>
                </div>
              )
            },
            {
              id: 3,
              title: "Hành trình khách hàng",
              icon: <Book size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                    <div className="bg-blue-50 p-3 rounded border border-blue-100 text-sm text-blue-800 flex items-start gap-2">
                    <Info size={16} className="mt-1 flex-shrink-0"/>
                    <div>Carezone áp dụng công nghệ quản lý hiện đại bằng <strong>vòng tay thông minh RFID</strong> để tạo ra trải nghiệm "không chạm" và "không tiền mặt" trong suốt hành trình của khách hàng (sau khi checkin).</div>
                  </div>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">3.1. Quy trình Đón tiếp và Check-in (Lễ tân)</h3>
                    <p className="text-sm text-stone-500 italic mb-2"><strong>Mục đích:</strong> Đảm bảo khách hàng được tiếp đón đầy đủ, tư vấn rõ ràng và hiểu rõ quy định trước khi vào khu vực dịch vụ.</p>
                    
                    <div className="space-y-4">
                      <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                        <h4 className="font-bold text-emerald-800 mb-1">1. Chào đón & Phân loại</h4>
                        <ul className="list-disc pl-4 text-sm text-stone-700">
                          <li>Nhân viên Lễ tân chào khách ngay khi khách bước vào sảnh.</li>
                          <li>Hỏi thông tin đặt lịch hoặc nhu cầu sử dụng dịch vụ (Onsen lẻ, Combo, Massage, Jjimjilbang).</li>
                        </ul>
                      </div>

                      <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                        <h4 className="font-bold text-emerald-800 mb-1">2. Tư vấn & Đăng ký</h4>
                        <ul className="list-disc pl-4 text-sm text-stone-700">
                          <li>Tư vấn các gói khuyến mãi hiện hành (ví dụ: Mua 1 tặng 1).</li>
                          <li>Xin khách cung cấp thông tin cơ bản (Họ tên, SĐT) để tích điểm hoặc kiểm tra Thẻ hội viên.</li>
                        </ul>
                      </div>

                      <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                        <h4 className="font-bold text-emerald-800 mb-1">3. Thu phí & Cấp vòng tay RFID</h4>
                        <ul className="list-disc pl-4 text-sm text-stone-700">
                          <li>Thực hiện thu tiền vé vào cửa (hoặc xác nhận voucher).</li>
                          <li>Kích hoạt vòng tay RFID trên hệ thống POS. (Vai trò: Chìa khóa tủ giày, tủ Locker, ví điện tử).</li>
                          <li>Giao vòng tay cho khách.</li>
                        </ul>
                      </div>

                      <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                        <h4 className="font-bold text-emerald-800 mb-1">4. Hướng dẫn ban đầu</h4>
                        <ul className="list-disc pl-4 text-sm text-stone-700">
                          <li>Hướng dẫn khách cởi giày tại khu vực tủ giày và sử dụng vòng tay để khóa tủ.</li>
                          <li><strong className="text-red-600">Lưu ý quan trọng:</strong> Nhắc nhở khách "Vui lòng không mang điện thoại/máy quay vào khu vực Onsen".</li>
                          <li>Mời khách di chuyển vào khu vực Locker Nam/Nữ riêng biệt.</li>
                        </ul>
                      </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">3.2. Quy trình tại khu vực Locker</h3>
                      <p className="text-sm text-stone-500 italic mb-2"><strong>Mục đích:</strong> Quản lý tư trang khách hàng an toàn và vệ sinh.</p>
                    
                    <div className="space-y-4">
                      {/* Tiếp nhận & Lưu trữ */}
                      <div className="bg-white p-4 rounded shadow-sm border border-stone-200">
                        <ul className="space-y-3 text-sm">
                          <li className="flex gap-2">
                            <div className="font-bold min-w-[120px] text-emerald-800">1. Tiếp nhận:</div>
                            <div>Nhân viên tại quầy Locker hướng dẫn khách quét vòng tay vào đúng số tủ để lấy quần áo và bộ khăn tắm (1 lớn, 1 nhỏ).</div>
                          </li>
                          <li className="flex gap-2">
                            <div className="font-bold min-w-[120px] text-emerald-800">2. Lưu trữ:</div>
                            <div>Khách sử dụng vòng tay chạm vào mặt cảm ứng để mở/đóng. Toàn bộ quần áo, túi xách phải được cất vào tủ.</div>
                          </li>
                        </ul>
                      </div>

                      {/* Hướng dẫn Quy trình trải nghiệm */}
                      <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100">
                        <h4 className="font-bold text-emerald-800 mb-3 flex items-center gap-2">
                          <Info size={18} /> Hướng dẫn khách quy trình trải nghiệm Carezone
                        </h4>
                        
                        {/* Flow Diagram */}
                        <div className="flex flex-col md:flex-row gap-2 mb-4 items-stretch">
                          <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700 flex items-center justify-center">1. Jjimjilbang</div>
                          <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={16}/></div>
                          <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700 flex items-center justify-center">2. Onsen</div>
                          <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={16}/></div>
                          
                          {/* Combined 3 & 4 with flexibility */}
                          <div className="flex-[2] flex flex-col justify-center gap-1 bg-white p-2 rounded border border-emerald-200 border-dashed relative group">
                              <div className="flex items-center justify-center gap-2">
                                  <span className="font-bold text-emerald-700">3. Spa Trị liệu</span>
                                  <ArrowLeftRight size={16} className="text-emerald-400" />
                                  <span className="font-bold text-emerald-700">4. Ăn uống</span>
                              </div>
                              <div className="text-[10px] text-center text-stone-500 font-medium leading-tight">
                                  (Có thể tùy chọn thứ tự)
                              </div>
                          </div>
                        </div>

                        {/* Explanation Box */}
                        <div className="bg-yellow-50 p-3 rounded border border-yellow-200 text-sm text-stone-700">
                          <strong className="text-yellow-800 block mb-1">Tư vấn viên giải thích lý do:</strong>
                          <p>
                            "Để đạt hiệu quả sức khỏe tốt nhất, anh/chị nên trải nghiệm <strong>Jjimjilbang trước</strong> để thải độc qua mồ hôi tại 7 phòng xông. Sau đó mới xuống tắm Onsen để làm sạch và thư giãn. Cuối cùng là Spa trị liệu."
                          </p>
                          <p className="mt-2 text-xs italic text-red-600">
                            *Lưu ý: Không nên tắm lại sau khi Spa trị liệu vì sẽ làm mất tác dụng của dầu massage và ảnh hưởng sức khỏe. Nếu tắm Onsen trước rồi mới qua Jjimjilbang thì hiệu quả thải độc sẽ giảm.
                          </p>
                        </div>
                      </div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">3.3. Quy trình Check-out và Thanh toán</h3>
                      <ol className="list-decimal pl-5 space-y-3 bg-white p-4 rounded shadow-sm text-sm">
                      <li><strong>Trả đồ:</strong> Khách trả đồng phục và khăn bẩn vào giỏ quy định tại quầy Locker.</li>
                      <li><strong>Kiểm tra vòng tay:</strong> Khách ra quầy Lễ tân, trả vòng tay RFID.</li>
                      <li>
                        <strong>Truy xuất dữ liệu:</strong> Lễ tân quét vòng tay kiểm tra dịch vụ phát sinh.
                        <ul className="list-disc pl-4 mt-1 text-stone-600">
                          <li><em>Nếu có phát sinh:</em> In hóa đơn tạm tính, mời khách kiểm tra.</li>
                          <li><em>Nếu không có:</em> Cảm ơn khách hàng.</li>
                        </ul>
                      </li>
                      <li><strong>Thanh toán:</strong> Thu tiền phát sinh (Tiền mặt/Thẻ/QR). Hệ thống mở khóa tủ giày (hoặc Lễ tân xác nhận) để khách lấy giày.</li>
                      <li><strong>Tiễn khách:</strong> Cúi chào, cảm ơn và hẹn gặp lại.</li>
                    </ol>
                  </section>
                </div>
              )
            },
            {
              id: 4,
              title: "Quy định Nhân sự (Kỹ thuật viên Spa)",
              icon: <UserCheck size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">4.1. Quy định về Ca làm việc (KTV)</h3>
                    <p className="mb-3 text-sm">Do đặc thù Spa cần phục vụ theo lịch hẹn của khách, nhân sự Kỹ thuật viên (KTV) cần tuân thủ nghiêm ngặt về giờ giấc và trạng thái sẵn sàng (Trực/Standby):</p>
                    <div className="overflow-x-auto">
                      <table className="min-w-full bg-white border border-stone-200 rounded-lg text-sm shadow-sm">
                        <thead className="bg-purple-100 text-purple-900">
                          <tr>
                            <th className="p-3 text-left border-b w-1/4">Ca làm việc</th>
                            <th className="p-3 text-left border-b w-1/4">Khung giờ</th>
                            <th className="p-3 text-left border-b">Yêu cầu đặc biệt</th>
                          </tr>
                        </thead>
                        <tbody className="divide-y divide-stone-100">
                          <tr>
                            <td className="p-3 font-bold text-purple-800">Ca Sáng (A)</td>
                            <td className="p-3 font-medium">
                                09:00 – 18:00<br/>
                                <span className="text-[10px] text-stone-500 font-normal">(Nghỉ trưa 1 tiếng)</span>
                            </td>
                            <td className="p-3 text-xs text-stone-600">
                                Chuẩn bị phòng đầu ngày (Đốt tinh dầu, kiểm tra khăn, nhiệt độ phòng). Sẵn sàng đón khách sớm.
                            </td>
                          </tr>
                          <tr>
                            <td className="p-3 font-bold text-purple-800">Ca Chiều (B)</td>
                            <td className="p-3 font-medium">
                                13:00 – 22:00<br/>
                                <span className="text-[10px] text-stone-500 font-normal">(Nghỉ chiều 1 tiếng)</span>
                            </td>
                            <td className="p-3 text-xs text-stone-600">
                                Vệ sinh, thu dọn toàn bộ khu vực Spa cuối ngày. Đảm bảo tắt hết thiết bị điện (máy xông, đèn, máy lạnh).
                            </td>
                          </tr>
                           <tr>
                            <td className="p-3 font-bold text-purple-800">Ca Gãy (C)</td>
                            <td className="p-3 font-medium">
                                10:00 – 14:00<br/>
                                17:00 – 21:00
                            </td>
                            <td className="p-3 text-xs text-stone-600">
                                Tăng cường vào giờ cao điểm. Linh động theo lượng khách đặt trước.
                            </td>
                          </tr>
                        </tbody>
                      </table>
                    </div>
                      <p className="mt-2 text-sm text-red-600 italic border-l-2 border-red-500 pl-2 bg-red-50 py-1">
                      * Quy tắc Trực (Standby): KTV chưa có tour phải ngồi tại phòng chờ nhân viên, không tụ tập tại quầy lễ tân gây ồn ào.
                    </p>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">4.2. Tiêu chuẩn Diện mạo & Vệ sinh</h3>
                    <p className="mb-3 text-sm italic">KTV Spa tiếp xúc trực tiếp lên cơ thể khách hàng, do đó tiêu chuẩn vệ sinh cá nhân là quan trọng nhất.</p>
                    
                    <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col md:flex-row">
                      <div className="md:w-1/3 h-64 bg-stone-100 flex items-center justify-center overflow-hidden border-r border-stone-200">
                         {/* Placeholder Image */}
                         <div className="text-stone-400 flex flex-col items-center"><UserCheck size={48} /><span>Hình minh họa</span></div>
                      </div>
                      <div className="p-6 flex-1">
                        <h4 className="font-bold text-purple-800 text-lg mb-3">Kỹ thuật viên Spa & Trị liệu</h4>
                        <div className="grid sm:grid-cols-2 gap-4">
                          <div>
                            <strong className="text-sm text-stone-800 block mb-1">Trang phục:</strong>
                            <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                              <li><strong>Đồng phục:</strong> Bộ quần áo Spa do Carezone cấp phát, sạch sẽ, phẳng phiu.</li>
                              <li><strong>Tóc:</strong> Búi cao gọn gàng, sử dụng lưới búi tóc. Không để tóc lòa xòa chạm vào mặt khách.</li>
                              <li><strong>Trang điểm:</strong> Nhẹ nhàng, tươi tắn. Không dùng nước hoa mùi quá nồng.</li>
                            </ul>
                          </div>
                          <div>
                            <strong className="text-sm text-stone-800 block mb-1">Đôi bàn tay (Công cụ lao động):</strong>
                            <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                              <li><strong>Móng tay:</strong> Cắt ngắn sát phần thịt, dũa tròn, sạch sẽ. Tuyệt đối không để móng dài/đính đá.</li>
                              <li><strong>Da tay:</strong> Mềm mại, không bị chai sần (thường xuyên dưỡng da tay).</li>
                              <li><strong>Nhiệt độ:</strong> Luôn làm ấm tay trước khi chạm vào người khách.</li>
                            </ul>
                          </div>
                          <div className="sm:col-span-2">
                            <strong className="text-sm text-stone-800 block mb-1">Sức khỏe:</strong>
                            <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                               <li>KTV đang bị ho, cảm cúm, bệnh ngoài da bắt buộc phải báo quản lý xin nghỉ để tránh lây nhiễm cho khách.</li>
                               <li>Hơi thở thơm tho.</li>
                            </ul>
                          </div>
                        </div>
                      </div>
                    </div>
                  </section>

                   <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">4.3. Thái độ ứng xử & Kỹ năng mềm</h3>
                    <div className="space-y-3">
                      <div className="flex gap-3 bg-white p-3 rounded border border-stone-200">
                        <div className="bg-purple-100 p-2 rounded h-fit text-purple-700"><Volume2 size={18}/></div>
                        <div>
                          <h4 className="font-bold text-sm">Giọng nói chuẩn Spa</h4>
                          <p className="text-xs text-stone-600">
                            - Luôn duy trì âm lượng nhỏ, trầm ấm, tốc độ nói chậm rãi.<br/>
                            - Tuyệt đối không nói chuyện riêng, cười đùa với KTV khác khi đang trong phòng trị liệu.<br/>
                            - Chỉ giao tiếp với khách khi cần thiết (hỏi lực massage, nhiệt độ phòng) để khách được nghỉ ngơi.
                          </p>
                        </div>
                      </div>
                      <div className="flex gap-3 bg-white p-3 rounded border border-stone-200">
                         <div className="bg-purple-100 p-2 rounded h-fit text-purple-700"><CameraOff size={18}/></div>
                         <div>
                          <h4 className="font-bold text-sm">Tôn trọng sự riêng tư</h4>
                          <p className="text-xs text-stone-600">
                            - Luôn gõ cửa trước khi vào phòng (kể cả khi cửa mở).<br/>
                            - Ra ngoài khi khách thay đồ. Dùng khăn che chắn cẩn thận các bộ phận nhạy cảm khi massage (Khăn che mắt, khăn che người).
                          </p>
                        </div>
                      </div>
                    </div>
                  </section>
                </div>
              )
            },
            {
              id: 5,
              title: "Quy trình Vận hành & Kiểm soát Spa",
              icon: <Sparkles size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <section className="mb-6">
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">5.1. Chuẩn bị trước khi khách đến</h3>
                     <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700 bg-white p-4 rounded shadow-sm border border-stone-100">
                        <li><strong>Vệ sinh phòng:</strong> Đảm bảo phòng sạch sẽ, thoáng mát. Thay ga trải giường, vỏ gối mới.</li>
                        <li><strong>Sắp xếp không gian:</strong> Điều chỉnh ánh sáng dịu nhẹ, bật nhạc thiền/spa âm lượng vừa phải, đốt tinh dầu hương liệu nhẹ nhàng.</li>
                        <li><strong>Chuẩn bị dụng cụ:</strong> Chuẩn bị sẵn khăn, dầu massage, đá nóng (nếu có).</li>
                        <li><strong>Nhiệt độ phòng:</strong> Duy trì ở mức 25-26°C.</li>
                     </ul>
                  </section>

                  <section className="mb-6">
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">5.2. Đón tiếp & Xác nhận dịch vụ</h3>
                     <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100 space-y-3">
                        <div className="flex gap-3 items-start">
                           <div className="font-bold text-emerald-800 min-w-[20px]">1.</div>
                           <div className="text-sm"><strong>Chào đón:</strong> Mỉm cười, cúi chào khách tại khu vực chờ của spa.</div>
                        </div>
                        <div className="flex gap-3 items-start">
                           <div className="font-bold text-emerald-800 min-w-[20px]">2.</div>
                           <div className="text-sm">
                              <strong>Kiểm tra thông tin:</strong>
                              <ul className="list-disc pl-4 mt-1 text-stone-600 text-xs space-y-1">
                                 <li>Quét vòng tay RFID của khách để xác nhận gói dịch vụ đã mua.</li>
                                 <li><em>Trường hợp khách chưa mua gói:</em> Tư vấn menu spa và thực hiện thao tác <strong>bán thêm (upsell)</strong> trực tiếp vào vòng tay trên máy POS.</li>
                              </ul>
                           </div>
                        </div>
                        <div className="flex gap-3 items-start">
                           <div className="font-bold text-emerald-800 min-w-[20px]">3.</div>
                           <div className="text-sm"><strong>Tư vấn sức khỏe:</strong> Hỏi thăm tình trạng sức khỏe, các vùng đau mỏi cần tập trung hoặc các lưu ý đặc biệt (chấn thương, dị ứng...).</div>
                        </div>
                     </div>
                  </section>

                  <section className="mb-6">
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">5.3. Quy trình Trị liệu</h3>
                     <div className="space-y-4">
                        <div className="border-l-4 border-emerald-500 pl-4 py-2 bg-white shadow-sm rounded-r">
                           <h4 className="font-bold text-emerald-800 text-sm mb-1">Bước 1: Mời khách vào phòng</h4>
                           <p className="text-xs text-stone-600">Hướng dẫn khách thay đồ (nếu cần), cất tư trang và nằm lên giường trị liệu đúng tư thế.</p>
                        </div>
                        <div className="border-l-4 border-emerald-500 pl-4 py-2 bg-white shadow-sm rounded-r">
                           <h4 className="font-bold text-emerald-800 text-sm mb-1">Bước 2: Thực hiện Massage</h4>
                           <ul className="list-disc pl-4 text-xs text-stone-600">
                              <li>Tiến hành bài trị liệu theo đúng quy trình kỹ thuật đã được đào tạo.</li>
                              <li>Thường xuyên hỏi thăm khách về lực đạo: <em>"Lực em đi như vậy có vừa không ạ?"</em>.</li>
                              <li>Giữ im lặng trong quá trình làm, chỉ giao tiếp khi cần thiết.</li>
                           </ul>
                        </div>
                     </div>
                  </section>

                  <section className="mb-6">
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">5.4. Kết thúc & Chăm sóc sau trị liệu</h3>
                     <ol className="list-decimal pl-5 space-y-3 bg-white p-4 rounded shadow-sm text-sm border border-stone-200">
                        <li><strong>Kết thúc bài:</strong> Thông báo nhẹ nhàng cho khách biết liệu trình đã kết thúc. Lau sạch dầu thừa trên cơ thể khách bằng khăn ấm.</li>
                        <li><strong>Mời trà & Đánh giá:</strong> Đỡ khách ngồi dậy, mời khách uống trà ấm/ăn nhẹ (nếu có). Cảm ơn khách và khéo léo nhờ khách đánh giá chất lượng dịch vụ (qua phiếu hoặc máy tính bảng).</li>
                        <li><strong>Hướng dẫn di chuyển:</strong> Hỗ trợ cung cấp thông tin để khách di chuyển sang khu vực trải nghiệm tiếp theo (ví dụ: Nhà hàng, Khu nghỉ ngơi, hoặc ra về).</li>
                        <li><strong>Tiễn khách:</strong> Cúi chào tạm biệt khách tại cửa Spa.</li>
                        <li><strong>Vệ sinh phòng:</strong> Thu dọn khăn, ga gối bẩn, vệ sinh phòng để sẵn sàng đón khách tiếp theo.</li>
                     </ol>
                  </section>

                   {/* Phần Kiểm soát & Báo cáo (Gộp từ Chương 7 cũ) */}
                   <section className="mb-6">
                      <h3 className="text-xl font-bold text-emerald-700 mb-3">5.5. Báo cáo vấn đề cho Quản lý</h3>
                      <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                         <div className="flex items-center gap-2 mb-3 font-bold text-stone-800">
                            <MessageSquare size={20} /> Nội dung báo cáo hàng ngày
                         </div>
                         <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                            <li><strong>Chất lượng KTV:</strong> Báo cáo các trường hợp KTV bị khách phàn nàn về thái độ hoặc lực tay không đạt yêu cầu.</li>
                            <li><strong>Cơ sở vật chất:</strong> Ghi nhận tình trạng phòng trị liệu (mùi ẩm mốc, đèn hỏng, nhạc không phát) để bảo trì xử lý.</li>
                            <li><strong>Vật tư tiêu hao:</strong> Báo cáo mức tiêu thụ dầu massage, khăn, đá nóng trong ngày và đề xuất nhập thêm nếu sắp hết.</li>
                            <li><strong>Sự cố y tế:</strong> Báo cáo ngay các trường hợp khách bị dị ứng dầu, đau tăng nặng sau khi massage để có hướng xử lý kịp thời.</li>
                         </ul>
                      </div>
                   </section>

                   <section>
                      <h3 className="text-xl font-bold text-emerald-700 mb-3">5.6. Danh sách kiểm tra KTV (Checklist)</h3>
                      <p className="text-sm text-stone-500 italic mb-3">Kỹ thuật viên (KTV) phải hoàn thành việc chuẩn bị phòng trước khi đón khách.</p>
                      
                      <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
                         <table className="min-w-full text-xs md:text-sm">
                            <thead className="bg-purple-100 text-purple-900 font-bold">
                               <tr>
                                  <th className="p-3 text-left border-b w-[25%]">Hạng mục</th>
                                  <th className="p-3 text-left border-b w-[45%]">Chi tiết kiểm tra & Tiêu chuẩn</th>
                                  <th className="p-3 text-center border-b w-[15%]">Ca 1<br/><span className="text-[10px] font-normal">(Đầu ca)</span></th>
                                  <th className="p-3 text-center border-b w-[15%]">Ca 2<br/><span className="text-[10px] font-normal">(Giao ca)</span></th>
                               </tr>
                            </thead>
                            <tbody className="divide-y divide-stone-100">
                               {/* 1. Chuẩn bị Phòng Trị liệu */}
                               <tr>
                                  <td className="p-3 font-bold text-purple-800 align-top" rowSpan="3">1. Chuẩn bị Phòng Trị liệu</td>
                                  <td className="p-3">
                                     <ul className="list-disc pl-4 space-y-1">
                                        <li><strong>Giường:</strong> Thay ga, vỏ gối mới, trải thẳng, không nhăn.</li>
                                        <li><strong>Khăn:</strong> Gấp hình thiên nga/hoa sen, đặt ngay ngắn.</li>
                                        <li><strong>Sàn nhà:</strong> Sạch sẽ, không tóc, không bụi.</li>
                                     </ul>
                                  </td>
                                  <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                                  <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                               </tr>
                               <tr>
                                  <td className="p-3">
                                     <strong>Không gian 5 giác quan:</strong><br/>
                                     - Nhiệt độ: 25-26°C.<br/>
                                     - Ánh sáng: Vàng ấm, dịu nhẹ.<br/>
                                     - Mùi hương: Tinh dầu sả chanh/oải hương thoang thoảng.<br/>
                                     - Âm nhạc: Nhạc thiền Spa âm lượng 20-30%.
                                  </td>
                                  <td className="p-3 text-center text-emerald-600">Kiểm tra</td>
                                  <td className="p-3 text-center text-emerald-600">Kiểm tra</td>
                               </tr>
                               <tr>
                                  <td className="p-3">
                                     <strong>Khu vực chậu ngâm chân:</strong><br/>
                                     - Chậu sạch, khô ráo.<br/>
                                     - Chuẩn bị sẵn muối thảo dược/gừng/chanh.
                                  </td>
                                  <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                                  <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                               </tr>

                               {/* 2. Vật tư & Dụng cụ */}
                               <tr>
                                  <td className="p-3 font-bold text-purple-800 align-top" rowSpan="2">2. Vật tư & Dụng cụ</td>
                                  <td className="p-3">
                                     <strong>Kiểm tra số lượng:</strong><br/>
                                     - Dầu massage (Baby oil/Dầu dừa): Đầy bình.<br/>
                                     - Đá nóng: Đủ bộ, nồi hấp đá hoạt động tốt.<br/>
                                     - Quần lót giấy: Đủ cho khách trong ca.
                                  </td>
                                  <td className="p-3 text-center text-emerald-600">Bổ sung đầy đủ</td>
                                  <td className="p-3 text-center text-emerald-600">Bổ sung đầy đủ</td>
                               </tr>
                               <tr>
                                  <td className="p-3">
                                     <strong>Trà & Mứt:</strong><br/>
                                     - Bình trà ấm, đủ nước nóng.<br/>
                                     - Hũ mứt gừng/hạt sen đầy đủ, sạch sẽ.
                                  </td>
                                  <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                                  <td className="p-3 text-center text-emerald-600">Châm thêm nước</td>
                               </tr>
                            </tbody>
                         </table>
                      </div>
                   </section>
                </div>
              )
            },
            {
              id: 6,
              title: "Lương, Phúc lợi & Lộ trình Thăng tiến",
              icon: <Wallet size={20} />,
              content: (
                <div className="space-y-6 text-stone-800">
                  <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100 mb-4">
                      <h3 className="font-bold text-emerald-800 text-lg mb-2 flex items-center gap-2"><Info size={20}/> Chính sách thu nhập & Phát triển</h3>
                      <p className="text-sm text-emerald-900">Carezone xây dựng lộ trình phát triển sự nghiệp rõ ràng cho KTV Spa, đi kèm với cơ chế lương minh bạch: <strong>Lương Cứng + Tiền Tour + Tip</strong>.</p>
                  </div>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-4">6.1. Cấu trúc Thu nhập Hàng tháng</h3>
                    
                    {/* 2 Pillars Structure */}
                    <div className="grid md:grid-cols-2 gap-4 mb-4">
                        {/* Box 1: Cố định */}
                        <div className="bg-white rounded-xl border border-stone-200 p-5 flex flex-col relative overflow-hidden shadow-sm">
                            <div className="bg-stone-600 text-white text-[10px] font-bold px-3 py-1 rounded-full w-fit mx-auto mb-3">1. CỐ ĐỊNH</div>
                            <div className="text-center mb-3">
                                <Briefcase size={32} className="mx-auto text-stone-600 mb-2"/>
                                <h4 className="font-bold text-stone-800 text-xl">Lương Cứng</h4>
                            </div>
                            <div className="space-y-3 text-sm text-stone-600 mb-4 flex-grow border-t border-stone-100 pt-3">
                                <div className="flex justify-between">
                                    <span>Lương Bậc:</span>
                                    <span className="font-bold">Theo tay nghề</span>
                                </div>
                                <div className="flex justify-between">
                                    <span>Phụ cấp:</span>
                                    <span className="font-bold">Cơm/Gửi xe</span>
                                </div>
                            </div>
                            <div className="bg-stone-100 text-stone-600 text-center text-xs font-bold py-2 rounded">Ổn định</div>
                        </div>

                        {/* Box 2: Cá nhân */}
                        <div className="bg-orange-50 rounded-xl border border-orange-200 p-5 flex flex-col relative overflow-hidden shadow-sm">
                            <div className="bg-orange-600 text-white text-[10px] font-bold px-3 py-1 rounded-full w-fit mx-auto mb-3">2. NĂNG SUẤT & TIP</div>
                            <div className="text-center mb-3">
                                <Award size={32} className="mx-auto text-orange-600 mb-2"/>
                                <h4 className="font-bold text-orange-800 text-xl">Tour & Tip</h4>
                            </div>
                            <div className="space-y-3 text-sm text-stone-600 mb-4 flex-grow border-t border-orange-100 pt-3">
                                 <div className="flex justify-between">
                                    <span>Tiền Tour:</span>
                                    <span className="font-bold">10% giá dịch vụ</span>
                                </div>
                                <div className="flex justify-between">
                                    <span>Tiền Tip:</span>
                                    <span className="font-bold">100% KTV nhận</span>
                                </div>
                            </div>
                            <div className="bg-orange-200 text-orange-800 text-center text-xs font-bold py-2 rounded">Không giới hạn</div>
                        </div>
                    </div>

                    {/* Formula Bar */}
                    <div className="bg-emerald-700 text-white p-3 rounded-lg shadow-md flex items-center justify-between mb-6">
                        <div className="font-bold flex items-center gap-2 text-sm md:text-base">
                            <Wallet size={20} className="text-emerald-300"/>
                            TỔNG THU NHẬP THỰC TẾ =
                        </div>
                        <div className="font-bold text-lg md:text-xl tracking-widest">(1) + (2)</div>
                    </div>
                  </section>

                  <section>
                    <h3 className="text-xl font-bold text-emerald-700 mb-3">6.2. Ví dụ Tính lương Thực tế</h3>
                    <div className="bg-white p-6 rounded-xl border border-stone-200 shadow-md">
                        <div className="flex items-center gap-4 mb-4 border-b border-stone-100 pb-4">
                            <div className="w-12 h-12 rounded-full bg-pink-100 text-pink-600 flex items-center justify-center font-bold text-xl">L</div>
                            <div>
                                <h4 className="font-bold text-stone-800 text-lg">Nhân viên: Lương Thị Lan</h4>
                                <p className="text-sm text-stone-500">Vị trí: KTV Chính thức (Cấp độ 2) • Làm việc: 26 công/tháng</p>
                            </div>
                        </div>

                        <div className="space-y-4 text-sm">
                            {/* Item 1 */}
                            <div className="flex justify-between items-center px-2">
                                <span className="text-stone-600 flex items-center gap-2"><div className="w-2 h-2 rounded-full bg-stone-400"></div> 1. Lương cứng:</span>
                                <span className="font-bold text-stone-800">5.000.000 đ</span>
                            </div>
                            
                            {/* Item 2 Detailed Breakdown */}
                            <div className="bg-orange-50 p-4 rounded-lg border border-orange-100">
                                <div className="flex justify-between items-start mb-3">
                                    <span className="text-stone-700 flex items-center gap-2 font-bold"><div className="w-2 h-2 rounded-full bg-orange-400"></div> 2. Thu nhập Biến đổi (Tour & Tip):</span>
                                    <span className="font-bold text-orange-600 text-lg">+ 7.800.000 đ</span>
                                </div>
                                
                                {/* Explicit Assumptions Table */}
                                <div className="bg-white rounded border border-orange-200 p-3 text-xs text-stone-600">
                                    <div className="font-bold text-orange-800 mb-2 border-b border-orange-100 pb-1">BẢNG TÍNH GIẢ ĐỊNH HIỆU SUẤT:</div>
                                    
                                    <div className="grid grid-cols-2 gap-x-4 gap-y-2 mb-3">
                                        <div>• Số ngày làm việc: <span className="font-bold text-stone-800">26 ngày</span></div>
                                        <div>• Năng suất TB: <span className="font-bold text-stone-800">3 tour/ngày</span></div>
                                        <div>• Tổng số Tour: <span className="font-bold text-stone-800">78 tour</span></div>
                                        <div>• Giá dịch vụ TB: <span className="font-bold text-stone-800">500.000 đ</span></div>
                                    </div>

                                    <div className="space-y-1 pt-2 border-t border-dashed border-stone-300">
                                        <div className="flex justify-between">
                                            <span>- Tiền Tour (10% x 500k x 78):</span>
                                            <span className="font-medium">3.900.000 đ</span>
                                        </div>
                                        <div className="flex justify-between">
                                            <span>- Tiền Tip TB (50k x 78):</span>
                                            <span className="font-medium">3.900.000 đ</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div className="mt-6 pt-4 border-t-2 border-dashed border-stone-200 flex justify-between items-end">
                            <span className="font-bold text-emerald-900 uppercase text-sm">TỔNG THU NHẬP (Trước thuế):</span>
                            <span className="font-bold text-2xl text-emerald-700">12.800.000 VNĐ</span>
                        </div>
                    </div>
                  </section>

                  {/* New Section: Lộ trình thăng tiến */}
                  <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-6">6.3. Lộ trình Thăng tiến & Yêu cầu Năng lực</h3>
                     
                     {/* List of Levels - Expanded View */}
                     <div className="space-y-8">
                       {Object.entries(levelsData).map(([key, level], index) => (
                         <div key={key} className="bg-white rounded-xl shadow-sm border border-stone-200 overflow-hidden">
                            {/* Header */}
                            <div className={`p-4 border-b border-stone-100 flex items-center justify-between ${
                                key === 'tap_su' ? 'bg-stone-50' : 
                                key === 'chinh_thuc' ? 'bg-emerald-50' : 
                                'bg-purple-50'
                            }`}>
                                <div className="flex items-center gap-3">
                                    <div className={`w-8 h-8 rounded-full flex items-center justify-center font-bold text-sm ${
                                        key === 'tap_su' ? 'bg-stone-200 text-stone-600' : 
                                        key === 'chinh_thuc' ? 'bg-emerald-200 text-emerald-700' : 
                                        'bg-purple-200 text-purple-700'
                                    }`}>
                                        0{index + 1}
                                    </div>
                                    <h4 className={`font-bold text-lg ${
                                        key === 'tap_su' ? 'text-stone-800' : 
                                        key === 'chinh_thuc' ? 'text-emerald-800' : 
                                        'text-purple-800'
                                    }`}>
                                        {level.title}
                                    </h4>
                                </div>
                                <span className="text-xs font-bold bg-white px-3 py-1 rounded-full shadow-sm border border-stone-100 text-stone-500 uppercase tracking-wider">
                                    {level.desc}
                                </span>
                            </div>

                            {/* Content Grid */}
                            <div className="p-5 grid md:grid-cols-3 gap-4">
                                {/* Culture */}
                                <div>
                                    <div className="flex items-center gap-2 mb-2 font-bold text-stone-700 border-b border-stone-100 pb-1">
                                        <Heart size={16} className="text-red-500"/> Văn hóa & Thái độ
                                    </div>
                                    <ul className="text-sm text-stone-600 space-y-2 list-disc pl-4">
                                        {level.culture.map((item, idx) => <li key={idx}>{item}</li>)}
                                    </ul>
                                </div>
                                {/* Skills */}
                                <div>
                                    <div className="flex items-center gap-2 mb-2 font-bold text-stone-700 border-b border-stone-100 pb-1">
                                        <Wrench size={16} className="text-blue-500"/> Kỹ năng Nghiệp vụ
                                    </div>
                                    <ul className="text-sm text-stone-600 space-y-2 list-disc pl-4">
                                        {level.skills.map((item, idx) => <li key={idx}>{item}</li>)}
                                    </ul>
                                </div>
                                {/* Knowledge */}
                                <div>
                                    <div className="flex items-center gap-2 mb-2 font-bold text-stone-700 border-b border-stone-100 pb-1">
                                        <Book size={16} className="text-orange-500"/> Kiến thức
                                    </div>
                                    <ul className="text-sm text-stone-600 space-y-2 list-disc pl-4">
                                        {level.knowledge.map((item, idx) => <li key={idx}>{item}</li>)}
                                    </ul>
                                </div>
                            </div>
                         </div>
                       ))}
                     </div>
                  </section>
                </div>
              )
            },
            {
              id: 7,
              title: "KPI & Báo cáo (Spa)",
              icon: <BarChart size={20} />,
              content: (
                 <div className="space-y-6 text-stone-800">
                   {/* 7.1 KPI */}
                   <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-4">7.1. Bộ Chỉ Số KPI Kỹ Thuật Viên</h3>
                     <div className="grid grid-cols-2 gap-4">
                        {/* Doanh thu */}
                        <div className="bg-white p-4 rounded-xl border border-stone-200 shadow-sm">
                           <div className="flex items-center justify-between mb-2">
                              <strong className="text-sm text-stone-700">1. Năng suất (Tour)</strong>
                              <span className="text-[10px] bg-emerald-100 text-emerald-700 px-2 py-1 rounded">Quan trọng nhất</span>
                           </div>
                           <p className="text-xs text-stone-500 mb-2">Số lượng tour thực hiện trong tháng.</p>
                           <div className="w-full bg-stone-100 h-2 rounded-full"><div className="bg-emerald-500 h-2 rounded-full w-[80%]"></div></div>
                           <p className="text-right text-xs font-bold mt-1 text-emerald-600">Mục tiêu: 100 Tour/tháng</p>
                        </div>

                        {/* Doanh thu Upsell (Renumbered to 2) */}
                        <div className="bg-white p-4 rounded-xl border border-stone-200 shadow-sm">
                           <div className="flex items-center justify-between mb-2">
                              <strong className="text-sm text-stone-700">2. Bán thêm (Upsell)</strong>
                              <span className="text-[10px] bg-yellow-100 text-yellow-700 px-2 py-1 rounded">Thưởng nóng</span>
                           </div>
                           <p className="text-xs text-stone-500 mb-2">Bán mỹ phẩm, tinh dầu, gói liệu trình.</p>
                           <div className="w-full bg-stone-100 h-2 rounded-full"><div className="bg-yellow-500 h-2 rounded-full w-[20%]"></div></div>
                           <p className="text-right text-xs font-bold mt-1 text-yellow-600">Thưởng 5-10% doanh số</p>
                        </div>

                        {/* Điểm hài lòng (Renumbered to 3 and full width for balance) */}
                        <div className="bg-white p-4 rounded-xl border border-stone-200 shadow-sm col-span-2">
                           <div className="flex items-center justify-between mb-2">
                              <strong className="text-sm text-stone-700">3. Đánh giá (Rating)</strong>
                              <span className="text-[10px] bg-purple-100 text-purple-700 px-2 py-1 rounded">Chất lượng</span>
                           </div>
                           <p className="text-xs text-stone-500 mb-2">Điểm trung bình khách đánh giá sau dịch vụ.</p>
                           <div className="w-full bg-stone-100 h-2 rounded-full"><div className="bg-purple-500 h-2 rounded-full w-[95%]"></div></div>
                           <p className="text-right text-xs font-bold mt-1 text-purple-600">Mục tiêu: &gt; 4.8 sao</p>
                        </div>
                     </div>
                   </section>

                   {/* 7.2 Báo cáo */}
                   <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">7.2. Quy định Báo cáo & Kiểm kê</h3>
                     
                     <div className="bg-white rounded-lg border border-stone-200 shadow-sm p-4 mb-4">
                          <div className="flex justify-between items-center mb-3">
                             <h4 className="font-bold text-stone-800 flex items-center gap-2">
                                <div className="bg-stone-100 p-1.5 rounded text-stone-700"><ClipboardList size={18}/></div>
                                Kiểm kê Vật tư tiêu hao
                             </h4>
                          </div>
                          <p className="text-xs text-stone-600 mb-3">Thực hiện vào cuối Ca Chiều mỗi ngày để bộ phận Kho bổ sung kịp thời.</p>
                          
                          <table className="w-full text-xs text-left border border-stone-200">
                              <thead className="bg-stone-50 font-bold">
                                  <tr>
                                      <th className="p-2 border-r">Mặt hàng</th>
                                      <th className="p-2 border-r">Đơn vị</th>
                                      <th className="p-2">Mức báo động (Đặt hàng ngay)</th>
                                  </tr>
                              </thead>
                              <tbody className="divide-y divide-stone-100">
                                  <tr>
                                      <td className="p-2 border-r">Dầu nền (Dừa/Oliu)</td>
                                      <td className="p-2 border-r">Lít</td>
                                      <td className="p-2 text-red-600">&lt; 2 Lít</td>
                                  </tr>
                                  <tr>
                                      <td className="p-2 border-r">Tinh dầu (Sả/Oải hương)</td>
                                      <td className="p-2 border-r">Chai 100ml</td>
                                      <td className="p-2 text-red-600">&lt; 1 Chai</td>
                                  </tr>
                                  <tr>
                                      <td className="p-2 border-r">Quần lót giấy</td>
                                      <td className="p-2 border-r">Cái</td>
                                      <td className="p-2 text-red-600">&lt; 20 Cái</td>
                                  </tr>
                                  <tr>
                                      <td className="p-2 border-r">Nến/Cồn đốt</td>
                                      <td className="p-2 border-r">Viên/Lít</td>
                                      <td className="p-2 text-red-600">&lt; 10 Viên</td>
                                  </tr>
                              </tbody>
                          </table>
                     </div>

                     <div className="bg-red-50 p-4 rounded-lg border border-red-200">
                        <h4 className="font-bold text-red-800 mb-2 text-sm flex items-center gap-2"><Siren size={18}/> Quy trình báo cáo Sự cố</h4>
                        <p className="text-xs text-stone-700 mb-2">Khi khách phàn nàn về dịch vụ (đau, ngứa, không hài lòng):</p>
                        <ol className="list-decimal pl-5 text-xs text-red-900 space-y-1">
                            <li>Dừng ngay thao tác. Xin lỗi khách chân thành.</li>
                            <li>Mời quản lý Spa vào xử lý. Không đôi co với khách.</li>
                            <li>Ghi nhận vào sổ "Nhật ký sự cố" để rút kinh nghiệm.</li>
                        </ol>
                     </div>
                   </section>

                   {/* 7.3 Đánh giá chất lượng (New Section based on Image) */}
                   <section>
                     <h3 className="text-xl font-bold text-emerald-700 mb-3">7.3. Bảng Tiêu Chí Đánh Giá Chất Lượng (QA)</h3>
                     <p className="text-sm text-stone-500 mb-3 italic">Bộ phận Kiểm soát chất lượng (QC) sẽ chấm điểm ngẫu nhiên. Điểm số này ảnh hưởng trực tiếp đến bậc lương và lộ trình thăng tiến.</p>
                     
                     <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm mb-6">
                        <table className="min-w-full text-xs text-left">
                           <thead className="bg-stone-100 text-stone-700 font-bold uppercase">
                              <tr>
                                  <th className="p-3 border-b w-[20%]">Hạng mục</th>
                                  <th className="p-3 border-b w-[60%]">Tiêu chí đánh giá (Lỗi thường gặp)</th>
                                  <th className="p-3 border-b w-[20%] text-right">Điểm trừ</th>
                              </tr>
                           </thead>
                           <tbody className="divide-y divide-stone-100 text-stone-600">
                              <tr>
                                  <td className="p-3 font-bold text-stone-800">1. Diện mạo</td>
                                  <td className="p-3">Tóc không gọn, móng tay dài/bẩn, trang điểm quá đậm hoặc không trang điểm, quên đeo bảng tên.</td>
                                  <td className="p-3 text-right font-bold text-red-500">-2đ / lỗi</td>
                              </tr>
                              <tr>
                                  <td className="p-3 font-bold text-stone-800">2. Thái độ</td>
                                  <td className="p-3">Nói chuyện riêng trong giờ làm, sử dụng điện thoại khi đang làm khách, không chào khách.</td>
                                  <td className="p-3 text-right font-bold text-red-500">-5đ / lỗi</td>
                              </tr>
                              <tr>
                                  <td className="p-3 font-bold text-stone-800">3. Quy trình</td>
                                  <td className="p-3">Quên mời nước, làm thiếu bước massage, không hỏi lực khách, làm sai thời gian (thiếu giờ).</td>
                                  <td className="p-3 text-right font-bold text-red-500">-5đ / lỗi</td>
                              </tr>
                              <tr>
                                  <td className="p-3 font-bold text-stone-800">4. Vệ sinh</td>
                                  <td className="p-3">Không thay ga gối sau mỗi khách, để dầu vương vãi trên sàn, phòng có mùi lạ/ẩm mốc.</td>
                                  <td className="p-3 text-right font-bold text-red-500">-3đ / lỗi</td>
                              </tr>
                           </tbody>
                        </table>
                     </div>

                     <h4 className="font-bold text-emerald-800 mb-3 flex items-center gap-2">
                        <Activity size={18}/> Quy chế Xét Duyệt Bậc Lương (Đánh giá Định Kỳ)
                     </h4>
                     <div className="grid md:grid-cols-2 gap-4">
                        {/* Thăng bậc */}
                        <div className="bg-emerald-50 p-4 rounded-xl border border-emerald-200 relative overflow-hidden">
                           <div className="absolute top-0 right-0 p-2 opacity-10"><ArrowRight size={100} className="text-emerald-500"/></div>
                           <strong className="text-emerald-800 block text-sm mb-3 uppercase">Điều kiện Thăng Bậc</strong>
                           <ul className="list-disc pl-4 text-xs text-stone-700 space-y-2 relative z-10">
                              <li>Điểm Đánh giá Chất lượng trung bình 3 tháng liên tiếp: <strong>≥ 96 điểm</strong> (Xuất sắc).</li>
                              <li>Không vi phạm lỗi Thái độ hoặc Kỷ luật lao động.</li>
                              <li>Đạt 100% chỉ tiêu Hiệu quả công việc (Năng suất Tour).</li>
                              <li className="font-bold text-emerald-700">→ Kết quả: Được xét tăng 1 bậc lương cứng (Ví dụ: Từ KTV1 lên KTV2).</li>
                           </ul>
                        </div>

                        {/* Hạ bậc */}
                        <div className="bg-red-50 p-4 rounded-xl border border-red-200 relative overflow-hidden">
                           <div className="absolute top-0 right-0 p-2 opacity-10"><ArrowDown size={100} className="text-red-500"/></div>
                           <strong className="text-red-800 block text-sm mb-3 uppercase">Quy định Hạ Bậc (Từ 95 điểm trở xuống)</strong>
                           <div className="space-y-3 relative z-10">
                              <div className="bg-white p-2 rounded border border-red-100">
                                 <div className="text-xs font-bold text-red-700 mb-1">Mức 1 (90 - 95 điểm):</div>
                                 <p className="text-[10px] text-stone-600">Nhắc nhở/Đào tạo lại. Nếu lặp lại <strong>3 tháng</strong> → Cắt thưởng/Hạ bậc.</p>
                              </div>
                              <div className="bg-white p-2 rounded border border-red-100">
                                 <div className="text-xs font-bold text-red-700 mb-1">Mức 2 (80 - dưới 90 điểm):</div>
                                 <p className="text-[10px] text-stone-600">Biên bản Cảnh cáo. Nếu lặp lại <strong>2 tháng</strong> → Hạ 1 bậc lương ngay lập tức.</p>
                              </div>
                              <div className="bg-white p-2 rounded border border-red-100">
                                 <div className="text-xs font-bold text-red-700 mb-1">Mức 3 (Dưới 80 điểm):</div>
                                 <p className="text-[10px] text-stone-600">Hạ bậc hoặc <strong>Sa thải</strong> (Do không đáp ứng tiêu chuẩn dịch vụ).</p>
                              </div>
                           </div>
                        </div>
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
                  <p className="text-xs text-emerald-300 mt-1">Sổ tay vận hành v2.8 (VN)</p>
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
                <main className="flex-1 overflow-y-auto p-6 md:p-10 bg-stone-50">
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
                  </div>
                </main>
              </div>
            </div>
          );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<CarezoneSOP />);
    </script>
</body>
</html>
