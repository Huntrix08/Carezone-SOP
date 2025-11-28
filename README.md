import React, { useState } from 'react';
import { Book, Users, Clock, UserCheck, Droplets, Flame, Sparkles, Utensils, Wrench, FileText, BarChart, Wallet, Menu, X, ChevronRight, Search, Info, Activity, ArrowRight, ArrowDown, Thermometer, AlertTriangle, Star, Heart, Shield, GraduationCap, Briefcase, Network, ChevronDown, Gavel, ClipboardList, CameraOff, Volume2, Coffee, Stethoscope, MessageSquare, Music, Wind, Waves, Sun, Smile, Leaf, ChefHat, Receipt, Truck, UtensilsCrossed, Trash2, AlertCircle, ArrowLeftRight, Zap, FireExtinguisher, Siren, CheckCircle } from 'lucide-react';

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
              <li><strong>Phiên bản:</strong> 2.6 (Làm mới chương Bảo trì & An toàn)</li>
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
          {/* Cấp 1: Ban Lãnh Đạo */}
          <div className="flex flex-col items-center relative z-10">
            <div className="mb-2 text-emerald-800 font-bold uppercase tracking-widest text-xs">2.1. Cấp 1: Ban Lãnh Đạo</div>
            <div className="w-64 bg-gradient-to-br from-emerald-900 to-emerald-700 text-white p-5 rounded-xl shadow-lg text-center border-4 border-emerald-100 transform transition hover:scale-105 duration-300">
              <div className="font-bold text-xl tracking-wide">Giám đốc Chi nhánh</div>
              <div className="text-xs opacity-80 font-light tracking-wider mt-1 uppercase">Branch Director</div>
            </div>
            
            {/* Connector Line */}
            <div className="h-8 w-0.5 bg-stone-300"></div>
            
            <div className="w-56 bg-white text-emerald-900 p-3 rounded-lg shadow-md text-center border border-stone-200 relative">
              <div className="font-bold text-sm">Trợ lý Giám đốc</div>
              <div className="text-[10px] text-stone-500 uppercase">Executive Assistant</div>
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
                           <li>Chuyên viên Content & Digital</li>
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
      title: "Sơ đồ Quy trình tổng",
      icon: <Activity size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <div className="bg-white p-4 rounded-lg shadow-sm border border-stone-200">
             <h3 className="font-bold text-emerald-800 mb-3">Sơ đồ luồng vận hành (Flowchart)</h3>
             <div className="aspect-video bg-stone-100 flex flex-col items-center justify-center rounded border border-dashed border-stone-300 text-stone-500 mb-2 p-4 text-center">
                <Activity size={48} className="mb-2 text-stone-400" />
                <p className="font-medium">Khu vực hiển thị ảnh quy trình gốc</p>
                <p className="text-xs mt-1">(Vui lòng chèn file "Cz - Quy trình tổng.jpg" vào thư mục assets của ứng dụng)</p>
             </div>
             <p className="text-xs text-stone-500 italic text-center">Hình 3.1: Lưu đồ phối hợp giữa các bộ phận (Bảo vệ - CSKH - Thu ngân - Vận hành)</p>
           </div>

           {/* Bổ sung phần mô tả chi tiết quy trình */}
           <div className="bg-stone-50 p-4 rounded-lg border border-stone-200">
             <h3 className="font-bold text-emerald-800 text-lg mb-4 border-b border-emerald-200 pb-2">Mô tả chi tiết Luồng vận hành</h3>
             
             <div className="space-y-6">
               
               {/* GIAI ĐOẠN 1 */}
               <div>
                 <div className="flex items-center gap-2 mb-3">
                   <div className="bg-emerald-600 text-white text-xs font-bold px-2 py-1 rounded">GIAI ĐOẠN 1</div>
                   <h4 className="font-bold text-emerald-800">ĐÓN TIẾP & NHẬP MÔN (CHECK-IN)</h4>
                 </div>
                 <ul className="space-y-2 text-sm text-stone-700 bg-white p-3 rounded border border-stone-100 shadow-sm">
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B1</span> <span>Khách đến cổng. <strong>Bảo vệ</strong> hướng dẫn đậu xe.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B2</span> <span>Bảo vệ chào, che dù (nếu nắng), dẫn khách vào sảnh CSKH.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B3</span> <span><strong>CSKH</strong> chào khách và hướng dẫn khách tới vị trí ngồi.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B4</span> <span>Tư vấn các gói dịch vụ (Combo, lẻ...).</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B5</span> <span>Khách chốt gói &rarr; CSKH tạo đơn trên Tablet/POS đẩy sang Thu ngân.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B6</span> <span>Dẫn khách sang quầy Thu ngân.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B7</span> <span><strong>Thu ngân</strong> báo tổng tiền và thu phí.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B8</span> <span>Kích hoạt & giao vòng tay RFID cho khách.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-emerald-600">B9</span> <span>CSKH hỗ trợ đeo vòng, cất giày vào Locker giày, dẫn vào khu dịch vụ.</span></li>
                 </ul>
               </div>

               {/* GIAI ĐOẠN 2 */}
               <div>
                 <div className="flex items-center gap-2 mb-3">
                   <div className="bg-blue-600 text-white text-xs font-bold px-2 py-1 rounded">GIAI ĐOẠN 2</div>
                   <h4 className="font-bold text-blue-800">TRẢI NGHIỆM DỊCH VỤ (SERVICE)</h4>
                 </div>
                 <div className="grid md:grid-cols-3 gap-3">
                    <div className="bg-white p-3 rounded border border-stone-100 shadow-sm">
                      <strong className="text-orange-700 block text-sm mb-2 border-b pb-1">Tại Onsen / Jjimjilbang</strong>
                      <ul className="text-xs text-stone-700 space-y-2">
                        <li><span className="font-bold">B10:</span> Nhân viên trực chào khách, hướng dẫn khách dùng vòng tay để nhận đồ tại locker.</li>
                        <li><span className="font-bold">B11:</span> Hướng dẫn khách quy trình trải nghiệm tại Carezone.</li>
                        <li><span className="font-bold">B12:</span> Khách dùng thêm nước/đồ ăn? &rarr; Quét vòng tay ghi nợ.</li>
                        <li><span className="font-bold">B13:</span> Hỗ trợ khách thông tin để di chuyển giữa các khu vực trải nghiệm.</li>
                      </ul>
                    </div>
                    <div className="bg-white p-3 rounded border border-stone-100 shadow-sm">
                      <strong className="text-purple-700 block text-sm mb-2 border-b pb-1">Tại Spa</strong>
                      <ul className="text-xs text-stone-700 space-y-2">
                        <li><span className="font-bold">B14:</span> KTV tiếp đón, quét vòng tay xác nhận gói đã mua. Trường hợp khách chưa mua thì thêm dịch vụ vào vòng tay đã quét.</li>
                        <li><span className="font-bold">B15:</span> Mời khách vào phòng và thực hiện gói dịch vụ.</li>
                        <li><span className="font-bold">B16:</span> Kết thúc bài trị liệu, cảm ơn khách và nhờ khách đánh giá dịch vụ.</li>
                        <li><span className="font-bold">B17:</span> Hỗ trợ khách thông tin để di chuyển sang khu trải nghiệm (ví dụ như nhà hàng).</li>
                      </ul>
                    </div>
                    <div className="bg-white p-3 rounded border border-stone-100 shadow-sm">
                      <strong className="text-green-700 block text-sm mb-2 border-b pb-1">Tại Nhà hàng (F&B)</strong>
                      <ul className="text-xs text-stone-700 space-y-2">
                        <li><span className="font-bold">B18:</span> Phục vụ đưa menu, khách gọi món.</li>
                        <li><span className="font-bold">B19:</span> Quét vòng tay ghi nhận món.</li>
                        <li><span className="font-bold">B20:</span> Bếp ra món, phục vụ khách.</li>
                      </ul>
                    </div>
                 </div>
               </div>

               {/* GIAI ĐOẠN 3 */}
               <div>
                 <div className="flex items-center gap-2 mb-3">
                   <div className="bg-stone-600 text-white text-xs font-bold px-2 py-1 rounded">GIAI ĐOẠN 3</div>
                   <h4 className="font-bold text-stone-800">THANH TOÁN & RA VỀ (CHECK-OUT)</h4>
                 </div>
                 <ul className="space-y-2 text-sm text-stone-700 bg-white p-3 rounded border border-stone-100 shadow-sm">
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B21</span> <span>Khách quay lại quầy Lễ tân.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B22</span> <span>CSKH nhận vòng tay, quét kiểm tra lịch sử tiêu dùng.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B23</span> 
                      <span>
                        <strong>Xử lý phát sinh:</strong><br/>
                        - Không phát sinh (0đ): Sang B25.<br/>
                        - Có phát sinh: Thông báo số tiền khách cần trả thêm.
                      </span>
                   </li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B24</span> <span>Khách thanh toán tiền phát sinh.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B25</span> <span>Hoàn tất thủ tục, báo khách kiểm tra lại đồ đạc đã lấy đủ ở locker chưa để hướng dẫn khách nhận lại (quần áo, giày dép...).</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B26</span> <span>Chào tạm biệt.</span></li>
                   <li className="flex gap-2"><span className="font-bold min-w-[25px] text-stone-600">B27</span> <span>Bảo vệ hỗ trợ lấy xe, dắt xe, chào khách.</span></li>
                 </ul>
               </div>

             </div>
           </div>
        </div>
      )
    },
    {
      id: 4,
      title: "Hành trình khách hàng",
      icon: <Book size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <div className="bg-blue-50 p-3 rounded border border-blue-100 text-sm text-blue-800 flex items-start gap-2">
            <Info size={16} className="mt-1 flex-shrink-0"/>
            <div>Carezone áp dụng công nghệ quản lý hiện đại bằng <strong>vòng tay thông minh (RFID Wristband)</strong> để tạo ra trải nghiệm "không chạm" và "không tiền mặt" trong suốt hành trình của khách hàng (sau khi checkin).</div>
          </div>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">4.1. Quy trình Đón tiếp và Check-in (Lễ tân)</h3>
            <p className="text-sm text-stone-500 italic mb-2"><strong>Mục đích:</strong> Đảm bảo khách hàng được tiếp đón đầy đủ, tư vấn rõ ràng và hiểu rõ quy định trước khi vào khu vực dịch vụ.</p>
            
            <div className="space-y-4">
              <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                <h4 className="font-bold text-emerald-800 mb-1">1. Chào đón & Phân loại</h4>
                <ul className="list-disc pl-4 text-sm text-stone-700">
                  <li>Nhân viên Lễ tân chào khách ngay khi khách bước vào sảnh.</li>
                  <li>Hỏi thông tin đặt lịch (Booking) hoặc nhu cầu sử dụng dịch vụ (Onsen lẻ, Combo, Massage, Jjimjilbang).</li>
                </ul>
              </div>

              <div className="bg-white p-4 rounded shadow-sm border-l-4 border-emerald-500">
                <h4 className="font-bold text-emerald-800 mb-1">2. Tư vấn & Đăng ký</h4>
                <ul className="list-disc pl-4 text-sm text-stone-700">
                  <li>Tư vấn các gói khuyến mãi hiện hành (ví dụ: Mua 1 tặng 1).</li>
                  <li>Xin khách cung cấp thông tin cơ bản (Họ tên, SĐT) để tích điểm hoặc kiểm tra Membership.</li>
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
                  <li>Hướng dẫn khách cởi giày tại khu vực tủ giày (Shoe Locker) và sử dụng vòng tay để khóa tủ.</li>
                  <li><strong className="text-red-600">Lưu ý quan trọng:</strong> Nhắc nhở khách "Vui lòng không mang điện thoại/máy quay vào khu vực Onsen".</li>
                  <li>Mời khách di chuyển vào khu vực Locker Nam/Nữ riêng biệt.</li>
                </ul>
              </div>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">4.2. Quy trình tại khu vực Locker (Smart Locker)</h3>
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
                <div className="flex flex-col md:flex-row gap-2 mb-4">
                  <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700">1. Jjimjilbang</div>
                  <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={16}/></div>
                  <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700">2. Onsen</div>
                  <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={16}/></div>
                  <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700">3. Spa Trị liệu</div>
                  <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={16}/></div>
                  <div className="flex-1 bg-white p-2 rounded text-center border border-emerald-200 text-xs font-bold text-emerald-700">4. Ăn uống</div>
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
            <h3 className="text-xl font-bold text-emerald-700 mb-3">4.3. Quy trình Check-out và Thanh toán</h3>
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
      id: 5,
      title: "Quy định Nhân sự",
      icon: <UserCheck size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">5.1. Thời gian làm việc</h3>
            <p className="mb-3 text-sm">Do đặc thù ngành dịch vụ, Carezone áp dụng chế độ làm việc linh hoạt đảm bảo vận hành liên tục. Dưới đây là quy định chi tiết cho từng bộ phận:</p>
            <div className="overflow-x-auto">
              <table className="min-w-full bg-white border border-stone-200 rounded-lg text-sm shadow-sm">
                <thead className="bg-emerald-100 text-emerald-900">
                  <tr>
                    <th className="p-3 text-left border-b w-1/4">Bộ phận</th>
                    <th className="p-3 text-left border-b w-1/4">Ca làm việc</th>
                    <th className="p-3 text-left border-b w-1/4">Khung giờ</th>
                    <th className="p-3 text-left border-b">Ghi chú</th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* Khối Hành chính */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 border-r border-stone-200">Khối Hành chính</td>
                    <td className="p-3">Hành chính</td>
                    <td className="p-3 font-medium">08:00 – 17:30</td>
                    <td className="p-3 text-xs text-stone-600">Thứ 2 - Thứ 7. Nghỉ trưa <strong>90 phút</strong>.</td>
                  </tr>

                  {/* Thu ngân, Lễ tân, Onsen */}
                  <tr>
                    <td rowSpan="3" className="p-3 font-bold text-emerald-800 border-r border-stone-200 align-top bg-white">
                      Thu ngân<br/>Lễ tân<br/>Onsen
                    </td>
                    <td className="p-3">Ca A (Sáng)</td>
                    <td className="p-3 font-medium">09:00 – 19:00</td>
                    <td className="p-3 text-xs text-stone-600">Chịu trách nhiệm quy trình Mở cửa (Opening).</td>
                  </tr>
                  <tr>
                    <td className="p-3">Ca B (Chiều)</td>
                    <td className="p-3 font-medium">12:00 – 22:00</td>
                    <td className="p-3 text-xs text-stone-600">Chịu trách nhiệm quy trình Đóng cửa (Closing), chốt doanh thu.</td>
                  </tr>
                  <tr>
                    <td className="p-3">Ca C (Gãy)</td>
                    <td className="p-3 font-medium">09:00 – 22:00</td>
                    <td className="p-3 text-xs text-stone-600">Nghỉ giữa ca 2 tiếng. Áp dụng cuối tuần/Lễ tết.</td>
                  </tr>

                  {/* Kỹ thuật viên Spa */}
                  <tr className="bg-stone-50">
                    <td rowSpan="3" className="p-3 font-bold text-emerald-800 border-r border-stone-200 align-top bg-stone-50">
                      Kỹ thuật viên Spa
                    </td>
                    <td className="p-3">Ca A (Sáng)</td>
                    <td className="p-3 font-medium">10:00 – 20:00</td>
                    <td className="p-3 text-xs text-stone-600">Quy trình Opening khu vực Spa.</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">Ca B (Chiều)</td>
                    <td className="p-3 font-medium">12:00 – 22:00</td>
                    <td className="p-3 text-xs text-stone-600">Quy trình Closing khu vực Spa.</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">Ca C (Gãy)</td>
                    <td className="p-3 font-medium">10:00 – 22:00</td>
                    <td className="p-3 text-xs text-stone-600">Nghỉ giữa ca 2 tiếng. Áp dụng cuối tuần/Lễ tết.</td>
                  </tr>

                  {/* Tạp vụ */}
                  <tr>
                    <td rowSpan="2" className="p-3 font-bold text-emerald-800 border-r border-stone-200 align-top bg-white">
                      Tạp vụ
                    </td>
                    <td className="p-3">Ca A</td>
                    <td className="p-3 font-medium">07:00 – 17:30</td>
                    <td className="p-3 text-xs text-stone-600">Vệ sinh đầu giờ sáng.</td>
                  </tr>
                  <tr>
                    <td className="p-3">Ca B (Full)</td>
                    <td className="p-3 font-medium">07:00 – 20:00</td>
                    <td className="p-3 text-xs text-stone-600">Trực vệ sinh toàn thời gian.</td>
                  </tr>

                  {/* Bảo vệ */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 border-r border-stone-200">Bảo vệ</td>
                    <td className="p-3">Ca A</td>
                    <td className="p-3 font-medium">07:00 – 19:00</td>
                    <td className="p-3 text-xs text-stone-600">Trực an ninh, hướng dẫn đỗ xe.</td>
                  </tr>
                </tbody>
              </table>
            </div>
            <p className="mt-2 text-sm text-red-600 italic border-l-2 border-red-500 pl-2 bg-red-50 py-1">
              * Điểm danh: Vân tay/Face ID. Có mặt trước 15 phút để họp đầu ca (Briefing).
            </p>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">5.2. Tiêu chuẩn Diện mạo (Grooming)</h3>
            <p className="mb-3 text-sm italic">Diện mạo nhân viên phản ánh sự chuyên nghiệp của Carezone.</p>
            
            {/* Grid hiển thị ảnh và quy định */}
            <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
              {/* Lễ tân */}
              <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col">
                <div className="h-48 bg-stone-100 flex items-center justify-center overflow-hidden">
                   {/* Placeholder thay cho image_1d93b1.jpg */}
                   <img src="/api/placeholder/400/320" alt="Đồng phục Lễ tân" className="w-full h-full object-cover" />
                </div>
                <div className="p-3 flex-1">
                  <h4 className="font-bold text-emerald-800 text-center mb-2">Lễ tân (FO)</h4>
                  <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                    <li><strong>Áo dài:</strong> Cách tân màu xanh cốm nhẹ nhàng, thanh lịch.</li>
                    <li><strong>Giày:</strong> Búp bê/Cao gót bít mũi.</li>
                    <li><strong>Yêu cầu:</strong> Tóc búi cao, trang điểm nhẹ.</li>
                  </ul>
                </div>
              </div>

              {/* Onsen/Jjimjilbang */}
              <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col">
                <div className="h-48 bg-stone-100 flex items-center justify-center overflow-hidden">
                   {/* Placeholder thay cho image_1d9371.jpg */}
                   <img src="/api/placeholder/400/320" alt="Đồng phục Onsen" className="w-full h-full object-cover" />
                </div>
                <div className="p-3 flex-1">
                  <h4 className="font-bold text-emerald-800 text-center mb-2">Onsen / Jjimjilbang</h4>
                  <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                    <li><strong>Trang phục:</strong> Bộ đồ Spa cổ V màu xanh rêu đậm, viền họa tiết, thắt đai.</li>
                    <li><strong>Yêu cầu:</strong> Không sơn móng lòe loẹt, che hình xăm.</li>
                  </ul>
                </div>
              </div>

              {/* Kỹ thuật viên */}
              <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col">
                <div className="h-48 bg-stone-100 flex items-center justify-center overflow-hidden">
                   {/* Placeholder thay cho image_1d9317.png */}
                   <img src="/api/placeholder/400/320" alt="Đồng phục KTV" className="w-full h-full object-cover" />
                </div>
                <div className="p-3 flex-1">
                  <h4 className="font-bold text-emerald-800 text-center mb-2">Kỹ thuật viên (Therapist)</h4>
                  <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                    <li><strong>Trang phục:</strong> Scrubs màu xanh rêu trơn, cổ tim thoải mái vận động.</li>
                    <li><strong>Yêu cầu:</strong> Móng tay cắt ngắn sát da, dũa tròn.</li>
                  </ul>
                </div>
              </div>

              {/* Nhà hàng */}
              <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col">
                <div className="h-48 bg-stone-100 flex items-center justify-center overflow-hidden">
                   {/* Placeholder thay cho image_1d92de.jpg */}
                   <img src="/api/placeholder/400/320" alt="Đồng phục Nhà hàng" className="w-full h-full object-cover" />
                </div>
                <div className="p-3 flex-1">
                  <h4 className="font-bold text-emerald-800 text-center mb-2">Nhà hàng Thực dưỡng</h4>
                  <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                    <li><strong>Trang phục:</strong> Áo cổ tàu màu xanh rêu đậm, nẹp áo màu be.</li>
                    <li><strong>Yêu cầu:</strong> Bắt buộc đội mũ trùm tóc và đeo khẩu trang nhựa.</li>
                  </ul>
                </div>
              </div>

              {/* Bảo vệ */}
              <div className="bg-white rounded-lg border border-stone-200 overflow-hidden shadow-sm flex flex-col">
                <div className="h-48 bg-stone-100 flex items-center justify-center overflow-hidden">
                   {/* Placeholder thay cho image_1d92bb.jpg */}
                   <img src="/api/placeholder/400/320" alt="Đồng phục Bảo vệ" className="w-full h-full object-cover" />
                </div>
                <div className="p-3 flex-1">
                  <h4 className="font-bold text-emerald-800 text-center mb-2">Bảo vệ</h4>
                  <ul className="text-xs list-disc pl-4 space-y-1 text-stone-600">
                    <li><strong>Trang phục:</strong> Áo sơ mi bảo vệ tiêu chuẩn, cầu vai, cà vạt đen.</li>
                    <li><strong>Giày:</strong> Giày tây đen.</li>
                  </ul>
                </div>
              </div>
            </div>
            
            <div className="mt-4 bg-emerald-50 p-3 rounded text-sm text-emerald-800">
              <strong>Vệ sinh cá nhân chung:</strong> Tắm gội sạch sẽ hàng ngày, dùng khử mùi. Không dùng nước hoa quá nồng. Rửa tay 6 bước thường xuyên.
            </div>
          </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">5.3. Thái độ ứng xử</h3>
            <div className="space-y-3">
              <div className="flex gap-3">
                <div className="bg-emerald-100 p-2 rounded h-fit text-emerald-700"><Users size={16}/></div>
                <div>
                  <h4 className="font-bold text-sm">Chào hỏi</h4>
                  <p className="text-sm text-stone-600">Thực hiện cúi chào khi khách đến và đi. Khẩu hiệu: "Carezone xin chào quý khách" kèm nụ cười tươi tắn.</p>
                </div>
              </div>
              <div className="flex gap-3">
                 <div className="bg-emerald-100 p-2 rounded h-fit text-emerald-700"><Sparkles size={16}/></div>
                 <div>
                  <h4 className="font-bold text-sm">Giao tiếp</h4>
                  <p className="text-sm text-stone-600">Âm lượng vừa đủ. Tuyệt đối không hô to, gọi nhau í ới trong khu vực hành lang/thư giãn.</p>
                </div>
              </div>
              <div className="flex gap-3">
                 <div className="bg-emerald-100 p-2 rounded h-fit text-emerald-700"><UserCheck size={16}/></div>
                 <div>
                  <h4 className="font-bold text-sm">Quyền riêng tư</h4>
                  <p className="text-sm text-stone-600">Bảo mật thông tin khách. Nghiêm cấm dùng điện thoại cá nhân trong giờ làm việc (đặc biệt tại Locker/Onsen).</p>
                </div>
              </div>
            </div>
          </section>

          <section>
             <h3 className="text-xl font-bold text-emerald-700 mb-3">5.4. Kỷ luật và Ý thức trách nhiệm</h3>
             <div className="bg-red-50 border-l-4 border-red-500 p-4 rounded shadow-sm">
                <h4 className="font-bold text-red-800 flex items-center gap-2 mb-3">
                  <Gavel size={20}/> Quy định chung
                </h4>
                <ul className="list-disc pl-5 text-sm text-red-900 space-y-2">
                  <li>Có ý thức giữ gìn, bảo vệ uy tín của Công ty.</li>
                  <li>Nghiêm cấm việc tranh cãi với khách hàng và gây rối trật tự tại nơi làm việc.</li>
                  <li>Nghiêm túc chấp hành các quy định về Phòng cháy chữa cháy (PCCC), an toàn lao động và mọi quy định, quy trình, tiêu chuẩn công việc có liên quan.</li>
                  <li>Nghiêm túc chấp hành các chỉ đạo đúng thẩm quyền của cấp trên.</li>
                  <li>Khẩn trương thực hiện tốt, đúng hạn các nhiệm vụ được giao và báo cáo kết quả cho Cán bộ & Lãnh đạo giao việc. Nếu có vướng mắc không thể hoàn thành nhiệm vụ được giao phải báo cáo lại ngay từ khi sự việc phát sinh.</li>
                </ul>
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
          <p className="text-xs text-emerald-300 mt-1">SOP Manual v2.6</p>
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

export default CarezoneSOP;
