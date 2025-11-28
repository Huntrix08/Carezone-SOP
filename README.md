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
    },
    {
      id: 6,
      title: "Bãi xe & Tiếp đón (Bảo vệ)",
      icon: <Shield size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">6.1. Quy định vị trí</h3>
            <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
              <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700">
                <li><strong>Vị trí trực:</strong> Cổng chính và khu vực bãi xe. Luôn đảm bảo có người trực tại các vị trí trọng yếu.</li>
                <li><strong>Tác phong:</strong> Đứng thẳng, nghiêm túc, trang phục chỉnh tề theo quy định. Không làm việc riêng (sử dụng điện thoại, hút thuốc) trong giờ trực.</li>
                <li><strong>Quan sát:</strong> Luôn bao quát tình hình an ninh trật tự khu vực cổng và bãi xe.</li>
              </ul>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">6.2. Quy trình Đón khách (Welcome)</h3>
            <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-200 shadow-sm">
              <ol className="list-decimal pl-5 space-y-3 text-sm text-stone-800">
                <li><strong>Quan sát từ xa:</strong> Khi thấy khách đến, chủ động tiến lại gần.</li>
                <li><strong>Hướng dẫn xe:</strong> Ra hiệu lệnh rõ ràng để hướng dẫn khách vào khu vực đậu xe (xe máy/ô tô) đúng quy định.</li>
                <li><strong>Hỗ trợ:</strong> Mở cửa xe ô tô hoặc hỗ trợ dắt xe máy cho khách (đặc biệt với phụ nữ, người lớn tuổi). Che dù cho khách nếu trời nắng/mưa.</li>
                <li><strong>Chào hỏi:</strong> Cúi chào thân thiện, mỉm cười và nói: <em>"Carezone xin chào quý khách!"</em>.</li>
                <li><strong>Hướng dẫn lối vào:</strong> Chỉ dẫn khách lối đi vào sảnh Lễ tân/CSKH.</li>
              </ol>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">6.3. Quy trình Quản lý Bãi xe</h3>
            <div className="grid md:grid-cols-2 gap-4">
              <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                <h4 className="font-bold text-stone-800 mb-2 text-sm">Sắp xếp & Ghi vé</h4>
                <ul className="list-disc pl-5 space-y-1 text-xs text-stone-600">
                  <li>Sắp xếp xe gọn gàng, thẳng hàng, phân khu vực xe máy và ô tô riêng biệt.</li>
                  <li>Ghi thẻ xe/vé xe đầy đủ thông tin.</li>
                  <li>Che yên xe cho khách khi trời nắng.</li>
                  <li>Tuyệt đối không để xe cản trở lối đi lại hoặc lối thoát hiểm.</li>
                </ul>
              </div>
              <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                <h4 className="font-bold text-stone-800 mb-2 text-sm">An toàn & PCCC</h4>
                <ul className="list-disc pl-5 space-y-1 text-xs text-stone-600">
                  <li>Thường xuyên tuần tra, kiểm tra an toàn phòng chống cháy nổ tại bãi xe.</li>
                  <li>Nhắc nhở khách không để vật dụng dễ cháy nổ trên xe.</li>
                  <li>Sẵn sàng xử lý các tình huống sự cố theo quy trình PCCC.</li>
                </ul>
              </div>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">6.4. Quy trình Tiễn khách (Farewell)</h3>
            <div className="bg-blue-50 p-4 rounded-lg border border-blue-200 shadow-sm">
              <ol className="list-decimal pl-5 space-y-3 text-sm text-stone-800">
                <li><strong>Quan sát:</strong> Khi thấy khách từ sảnh đi ra, chủ động tiếp cận.</li>
                <li><strong>Hỗ trợ lấy xe:</strong> Nhận thẻ xe, hỗ trợ dắt xe ra vị trí thuận tiện cho khách. Mở cửa xe ô tô.</li>
                <li><strong>Chào tạm biệt:</strong> Cúi chào, mỉm cười và nói: <em>"Cảm ơn và hẹn gặp lại quý khách!"</em>.</li>
                <li><strong>Điều tiết giao thông:</strong> Hướng dẫn khách lái xe ra đường an toàn.</li>
              </ol>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">6.5. Quy trình xử lý khi khách mất vé xe</h3>
            <div className="bg-red-50 p-4 rounded-lg border border-red-200 shadow-sm">
              <h4 className="font-bold text-red-800 mb-2 flex items-center gap-2"><AlertTriangle size={18}/> Các bước xử lý:</h4>
              <ol className="list-decimal pl-5 space-y-2 text-sm text-stone-800">
                <li><strong>Xác minh thông tin:</strong> Yêu cầu khách cung cấp giấy tờ tùy thân (CCCD/CMND/GPLX) và Giấy đăng ký xe (Cavet) để đối chiếu.</li>
                <li><strong>Kiểm tra dữ liệu:</strong> Phối hợp với bộ phận An ninh/Camera trích xuất hình ảnh lúc xe vào để xác nhận đúng người, đúng biển số xe.</li>
                <li><strong>Lập biên bản:</strong> Yêu cầu khách điền đầy đủ thông tin và ký vào "Biên bản mất thẻ xe/vé xe", cam kết chịu trách nhiệm nếu có tranh chấp.</li>
                <li><strong>Giải quyết cho xe ra:</strong> Sau khi hoàn tất xác minh và thủ tục, bảo vệ cho xe ra về và lưu hồ sơ sự vụ báo cáo cuối ca.</li>
              </ol>
            </div>
          </section>
        </div>
      )
    },
    {
      id: 7,
      title: "Chăm sóc khách hàng (Lễ tân)",
      icon: <Smile size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">7.1. Quy trình Đón tiếp & Tư vấn</h3>
            <div className="space-y-4">
               <div className="bg-emerald-50 p-4 rounded border border-emerald-100 shadow-sm">
                  <h4 className="font-bold text-emerald-800 mb-2 text-sm">Bước 1: Chào đón (Greeting)</h4>
                  <ul className="text-sm text-stone-700 list-disc pl-5 space-y-1">
                     <li>Khi khách bước vào cửa (cách 2m): Chủ động mỉm cười, cúi chào 30 độ.</li>
                     <li>Khẩu hiệu: <em>"Carezone xin chào quý khách!"</em></li>
                     <li>Hỏi thăm xem khách đã có đặt hẹn trước chưa (Booking).</li>
                  </ul>
               </div>

               <div className="bg-emerald-50 p-4 rounded border border-emerald-100 shadow-sm">
                  <h4 className="font-bold text-emerald-800 mb-2 text-sm">Bước 2: Tư vấn dịch vụ (Consultation)</h4>
                  <ul className="text-sm text-stone-700 list-disc pl-5 space-y-1">
                     <li>Mời khách ngồi, mời trà thảo mộc/nước uống chào mừng.</li>
                     <li>Lắng nghe nhu cầu của khách (thư giãn, trị liệu đau mỏi, đi cùng gia đình...).</li>
                     <li>Giới thiệu các gói dịch vụ phù hợp (Combo Onsen + Jjimjilbang, các bài Massage trị liệu đặc biệt).</li>
                     <li>Thông báo rõ ràng về giá cả, các chương trình khuyến mãi đang áp dụng.</li>
                  </ul>
               </div>

               <div className="bg-emerald-50 p-4 rounded border border-emerald-100 shadow-sm">
                  <h4 className="font-bold text-emerald-800 mb-2 text-sm">Bước 3: Tạo đơn hàng (Ordering)</h4>
                  <ul className="text-sm text-stone-700 list-disc pl-5 space-y-1">
                     <li>Xác nhận lại dịch vụ khách chọn.</li>
                     <li>Tạo order trên hệ thống phần mềm POS/Tablet.</li>
                     <li>Xin thông tin khách hàng để tích điểm/đăng ký thành viên (Họ tên, SĐT).</li>
                  </ul>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">7.2. Bàn giao & Điều phối</h3>
            <div className="grid md:grid-cols-2 gap-4">
               <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                  <strong className="text-stone-800 text-sm block mb-2">Chuyển khách sang Thu ngân</strong>
                  <p className="text-sm text-stone-600">Dẫn khách sang quầy thu ngân để thanh toán và nhận vòng tay. Bàn giao thông tin order chính xác cho thu ngân.</p>
               </div>
               <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                  <strong className="text-stone-800 text-sm block mb-2">Hướng dẫn vào khu vực</strong>
                  <p className="text-sm text-stone-600">Sau khi khách có vòng tay: Hướng dẫn khách cất giày, nhắc lại quy định không mang điện thoại vào Onsen, và chỉ dẫn lối vào khu Locker Nam/Nữ.</p>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">7.3. Xử lý Phàn nàn & Hỗ trợ</h3>
            <div className="bg-stone-50 p-4 rounded-lg border border-stone-200 shadow-sm">
               <ol className="list-decimal pl-5 space-y-2 text-sm text-stone-700">
                  <li><strong>Lắng nghe:</strong> Chăm chú lắng nghe vấn đề của khách, không ngắt lời. Thể hiện sự đồng cảm.</li>
                  <li><strong>Xin lỗi:</strong> Xin lỗi chân thành vì trải nghiệm chưa tốt (dù lỗi do ai). <em>"Em rất xin lỗi vì sự bất tiện này ạ."</em></li>
                  <li><strong>Giải quyết:</strong> Đưa ra phương án xử lý trong thẩm quyền hoặc báo ngay cho Quản lý/Giám sát để hỗ trợ.</li>
                  <li><strong>Theo dõi:</strong> Đảm bảo vấn đề đã được giải quyết và khách hàng hài lòng trước khi rời đi.</li>
               </ol>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">7.4. Báo cáo & Bàn giao (Reporting)</h3>
            <div className="space-y-4">
              
              {/* Báo cáo cuối ca */}
              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <h4 className="font-bold text-emerald-800 flex items-center gap-2 mb-2">
                   <FileText size={18}/> 1. Báo cáo cuối ca (End of Shift Report)
                </h4>
                <ul className="list-disc pl-5 text-sm text-stone-700 space-y-1">
                   <li><strong>Doanh thu:</strong> Tổng kết doanh thu trong ca, phân loại theo hình thức thanh toán (Tiền mặt, Thẻ, Chuyển khoản, QR).</li>
                   <li><strong>Lượng khách (Pax):</strong> Thống kê số lượng khách check-in theo từng loại dịch vụ (Onsen, Massage, Jjimjilbang...).</li>
                   <li><strong>Voucher/Coupon:</strong> Tổng hợp số lượng voucher đã thu về hoặc phát hành trong ca.</li>
                </ul>
              </div>

              {/* Sổ giao ca */}
              <div className="bg-yellow-50 p-4 rounded border border-yellow-200 shadow-sm">
                <h4 className="font-bold text-emerald-800 flex items-center gap-2 mb-2">
                   <Book size={18}/> 2. Sổ giao ca (Logbook)
                </h4>
                <p className="text-xs text-stone-600 italic mb-2">Ghi chú chi tiết các vấn đề cần lưu ý bàn giao cho ca sau:</p>
                <ul className="list-disc pl-5 text-sm text-stone-700 space-y-1">
                   <li>Thông tin khách VIP hoặc khách đoàn đang sử dụng dịch vụ.</li>
                   <li>Các đồ đạc khách để quên (Lost & Found) vừa tiếp nhận.</li>
                   <li>Các vấn đề kỹ thuật/cơ sở vật chất chờ xử lý (bóng đèn cháy, máy POS lỗi...).</li>
                   <li>Các khiếu nại của khách hàng chưa được giải quyết dứt điểm.</li>
                </ul>
              </div>

              {/* Kiểm kê */}
              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <h4 className="font-bold text-emerald-800 flex items-center gap-2 mb-2">
                   <CheckCircle size={18}/> 3. Kiểm kê & Bàn giao tài sản
                </h4>
                <ul className="list-disc pl-5 text-sm text-stone-700 space-y-1">
                   <li><strong>Tiền mặt:</strong> Kiểm đếm tiền mặt tại quỹ (Cash count), niêm phong và có chữ ký xác nhận của cả người giao và người nhận.</li>
                   <li><strong>Vòng tay RFID:</strong> Kiểm kê số lượng vòng tay (Tổng = Đang khách đeo + Trong kho). Đảm bảo không thất thoát.</li>
                </ul>
              </div>

            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">7.5. Checklist Chuẩn bị Đầu ca (Pre-shift Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Nhân viên cần có mặt và hoàn thành checklist trước giờ nhận khách ít nhất 15 phút.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-emerald-100 text-emerald-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hạng mục</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết công việc</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 1<br/><span className="text-[10px] font-normal">(Bắt đầu 09:00)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 2<br/><span className="text-[10px] font-normal">(Bắt đầu 11:00)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  <tr>
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="2">1. Diện mạo & Tác phong</td>
                    <td className="p-3">Trang phục ủi phẳng, đầu tóc gọn gàng, trang điểm nhẹ theo quy chuẩn.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr>
                    <td className="p-3">Đeo thẻ tên, nhận bộ đàm, tai nghe và kiểm tra pin.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="3">2. Vệ sinh & Không gian</td>
                    <td className="p-3">Vệ sinh quầy Lễ tân, máy tính, điện thoại sạch bụi. Sắp xếp ấn phẩm ngay ngắn.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-stone-400">-</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">Kiểm tra sảnh chờ: Ghế ngay ngắn, sàn sạch, không rác, cửa kính sạch.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3"><strong>Tiêu chuẩn 5 Giác quan:</strong> Nhạc nhẹ, Tinh dầu thơm, Nhiệt độ 25°C.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra lại</td>
                  </tr>

                  <tr>
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="2">3. Công cụ & Thiết bị</td>
                    <td className="p-3">Khởi động POS, Tablet, Máy in bill. Đăng nhập hệ thống.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-stone-400">-</td>
                  </tr>
                  <tr>
                    <td className="p-3">Kiểm tra số lượng Vòng tay RFID, Menu, Phiếu đánh giá tại quầy.</td>
                    <td className="p-3 text-center text-emerald-600">Đếm đủ số lượng</td>
                    <td className="p-3 text-center text-emerald-600">Bổ sung nếu thiếu</td>
                  </tr>

                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="2">4. Thông tin vận hành</td>
                    <td className="p-3">Kiểm tra Booking trong ngày, note lại khách VIP hoặc đoàn đông.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600">Cập nhật phát sinh</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">Đọc Logbook/Group Zalo để nắm các sự cố/lưu ý từ ca trước hoặc hôm qua.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                </tbody>
              </table>
            </div>
           </section>
        </div>
      )
    },
    {
      id: 8,
      title: "Vận hành Onsen",
      icon: <Droplets size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           {/* 6.1. Quy trình nhân viên trực khu Onsen (MỚI) */}
           <section className="mb-6">
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.1. Quy trình Nhân viên Trực khu Onsen</h3>
            <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
               <div className="space-y-4 text-sm text-stone-700">
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B1</div>
                     <div><strong>Chào đón khách:</strong> Mỉm cười, cúi chào. "Anh/Chị mời theo lối này để thay đồ ạ..."</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B2</div>
                     <div><strong>Tiếp nhận thông tin:</strong> Xác nhận dịch vụ (Onsen/Combo). Ghi nhận yêu cầu đặc biệt.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B3</div>
                     <div><strong>Tư vấn quy định:</strong> Giữ vệ sinh, trật tự, không dùng điện thoại.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B4</div>
                     <div><strong>Hướng dẫn tủ đồ:</strong> Cách dùng vòng tay mở/đóng tủ. Nhắc giữ vòng tay.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B5</div>
                     <div><strong>Cấp phát:</strong> Khăn tắm, đồng phục, quần lót giấy (theo tiêu chuẩn).</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B6</div>
                     <div><strong>Giám sát trải nghiệm:</strong> Quan sát đảm bảo an toàn. Kiểm tra nhiệt độ, độ sạch.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B7</div>
                     <div className="space-y-2 w-full">
                        <div><strong>Quy trình trải nghiệm:</strong></div>
                        
                        {/* Embedded Experience Guide - Updated Layout */}
                        <div className="bg-emerald-50 p-3 rounded border border-emerald-200 text-xs">
                          <div className="font-bold text-emerald-800 mb-2 flex items-center gap-1"><Info size={14}/> Hướng dẫn khách quy trình trải nghiệm Carezone:</div>
                          
                          <div className="flex flex-col md:flex-row gap-2 mb-3 items-stretch">
                            <div className="flex-1 bg-white p-1.5 rounded text-center border border-emerald-200 font-bold text-emerald-700 flex items-center justify-center">1. Jjimjilbang</div>
                            <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={12}/></div>
                            <div className="flex-1 bg-white p-1.5 rounded text-center border border-emerald-200 font-bold text-emerald-700 flex items-center justify-center">2. Onsen</div>
                            <div className="hidden md:flex items-center text-emerald-400"><ArrowRight size={12}/></div>
                            
                            {/* Combined 3 & 4 with flexibility */}
                            <div className="flex-[2] flex flex-col justify-center gap-1 bg-white p-1.5 rounded border border-emerald-200 border-dashed relative group">
                                <div className="flex items-center justify-center gap-2">
                                    <span className="font-bold text-emerald-700">3. Spa</span>
                                    <ArrowLeftRight size={14} className="text-emerald-400" />
                                    <span className="font-bold text-emerald-700">4. Ăn uống</span>
                                </div>
                                <div className="text-[9px] text-center text-stone-500 font-medium leading-tight">
                                    (Có thể đảo thứ tự)
                                </div>
                            </div>
                          </div>

                          <div className="bg-white p-2 rounded border border-emerald-100 text-stone-600 italic mb-3">
                             "Để đạt hiệu quả sức khỏe tốt nhất, anh/chị nên trải nghiệm <strong>Jjimjilbang trước</strong> để thải độc. Sau đó mới xuống tắm Onsen để làm sạch và thư giãn."
                             <br/>
                             <span className="text-red-500">*Không nên tắm lại sau khi Spa trị liệu.</span>
                          </div>
                        </div>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B8</div>
                     <div><strong>Hỗ trợ thông tin:</strong> Hướng dẫn, cung cấp thông tin khi khách hàng cần.</div>
                  </div>
                   <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 text-center">B9</div>
                     <div><strong>Chào tạm biệt:</strong> Khi khách rời khỏi phân khu đang trực: "Chúc Anh/Chị có buổi trải nghiệm tuyệt vời."</div>
                  </div>
               </div>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.2. Nguyên tắc chung</h3>
            <div className="bg-red-50 border-l-4 border-red-500 p-4 rounded shadow-sm mb-4">
               <div className="flex items-center gap-2 text-red-700 font-bold text-base mb-2">
                  <Flame size={20}/> NGUYÊN TẮC VÀNG: TẮM SẠCH TRƯỚC KHI NGÂM
               </div>
               <p className="text-sm text-stone-700">Khách bắt buộc tắm gội sạch sẽ bằng xà phòng và xả sạch bọt tại khu vực tắm tráng trước khi bước xuống bất kỳ hồ ngâm nào.</p>
            </div>

            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
               <h4 className="font-bold text-emerald-800 mb-2 text-sm uppercase">Các quy định bắt buộc khác:</h4>
               <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700">
                  <li><strong className="text-red-600">Cấm quay phim, chụp ảnh:</strong> Tuyệt đối không mang điện thoại/camera vào khu vực Onsen để đảm bảo riêng tư.</li>
                  <li><strong>Không mang đồ ăn, thức uống:</strong> Giữ vệ sinh chung cho khu vực hồ ngâm.</li>
                  <li><strong>Giữ trật tự:</strong> Đi nhẹ, nói khẽ, duy trì không gian thư giãn tĩnh lặng.</li>
                  <li><strong>Trang phục:</strong> Khách <span className="underline">không mặc đồng phục</span> khi xuống hồ (có thể mặc quần lót giấy do Carezone phát hoặc nude 100%).</li>
                  <li><strong>Vệ sinh hồ ngâm:</strong> Khăn nhỏ đội trên đầu hoặc để trên thành hồ, <span className="text-red-600">tuyệt đối không nhúng vào nước hồ</span>. Không nhảy hoặc bơi trong hồ.</li>
               </ul>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-4">8.3. Quy trình Ngâm tắm chuẩn (7 Bước) tại osen</h3>
            <div className="relative pl-4 md:pl-8 py-2">
              {/* Vertical Line */}
              <div className="absolute left-4 md:left-8 top-0 bottom-0 w-0.5 bg-stone-200 transform -translate-x-1/2"></div>

              {/* Step 1 */}
              <div className="relative mb-6 pl-8">
                <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-stone-100 border-2 border-emerald-500 text-emerald-700 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">1</div>
                <div className="bg-white p-4 rounded-lg shadow-sm border border-stone-100">
                  <h4 className="font-bold text-stone-800">Tắm tráng (Kakeyu)</h4>
                  <p className="text-xs text-stone-500">Làm sạch cơ thể trước khi xuống hồ. Giúp cơ thể làm quen nhiệt độ.</p>
                </div>
              </div>

              {/* Step 2 - Hot */}
              <div className="relative mb-6 pl-8">
                <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-orange-50 border-2 border-orange-400 text-orange-600 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">2</div>
                <div className="bg-orange-50 p-4 rounded-lg shadow-sm border border-orange-100">
                  <h4 className="font-bold text-orange-800">Xông ướt (Steam Sauna)</h4>
                  <p className="text-xs text-orange-700">Giãn nở lỗ chân lông, đào thải độc tố.</p>
                </div>
              </div>

              {/* Step 3 - Hot */}
              <div className="relative mb-6 pl-8">
                 <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-orange-50 border-2 border-orange-400 text-orange-600 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">3</div>
                <div className="bg-orange-50 p-4 rounded-lg shadow-sm border border-orange-100">
                  <h4 className="font-bold text-orange-800">Xông khô (Dry Sauna)</h4>
                  <p className="text-xs text-orange-700">Kích thích tuyến mồ hôi, thư giãn cơ bắp.</p>
                </div>
              </div>

              {/* Step 4 - Hot */}
              <div className="relative mb-6 pl-8">
                 <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-red-50 border-2 border-red-500 text-red-600 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">4</div>
                <div className="bg-red-50 p-4 rounded-lg shadow-sm border border-red-100">
                  <h4 className="font-bold text-red-800">Ngâm bồn nóng (Hot Bath)</h4>
                  <p className="text-xs text-red-700">Nhiệt độ 38-42°C. Thúc đẩy tuần hoàn máu.</p>
                </div>
              </div>

              {/* Step 5 - Warm */}
              <div className="relative mb-6 pl-8">
                 <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-pink-50 border-2 border-pink-400 text-pink-600 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">5</div>
                <div className="bg-pink-50 p-4 rounded-lg shadow-sm border border-pink-100">
                  <h4 className="font-bold text-pink-800">Ngâm bồn lụa (Silk Bath)</h4>
                  <p className="text-xs text-pink-700">Bọt khí siêu nhỏ massage nhẹ nhàng, làm mịn da.</p>
                </div>
              </div>

              {/* Step 6 - Cold */}
              <div className="relative mb-6 pl-8">
                 <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-blue-50 border-2 border-blue-500 text-blue-600 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">6</div>
                <div className="bg-blue-50 p-4 rounded-lg shadow-sm border border-blue-100">
                  <h4 className="font-bold text-blue-800">Ngâm bồn lạnh (Cold Bath)</h4>
                  <p className="text-xs text-blue-700">Se khít lỗ chân lông, tăng cường miễn dịch. (Ngâm nhanh 1-2p).</p>
                </div>
              </div>

              {/* Step 7 - Neutral */}
              <div className="relative pl-8">
                 <div className="absolute left-0 top-0 w-8 h-8 rounded-full bg-emerald-100 border-2 border-emerald-600 text-emerald-800 flex items-center justify-center font-bold z-10 transform -translate-x-1/2">7</div>
                <div className="bg-emerald-50 p-4 rounded-lg shadow-sm border border-emerald-100">
                  <h4 className="font-bold text-emerald-900">Tắm tráng lại</h4>
                  <p className="text-xs text-emerald-700">Làm sạch lần cuối, kết thúc quy trình.</p>
                </div>
              </div>
            </div>
          </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.4. Quản lý chất lượng nước (Water Quality)</h3>
            <p className="text-sm mb-2 text-stone-600">Bộ phận Kỹ thuật chịu trách nhiệm kiểm soát liên tục.</p>
            <div className="overflow-x-auto mb-4">
              <table className="min-w-full bg-white border border-stone-200 rounded-lg text-sm">
                <thead className="bg-stone-100 text-stone-700">
                  <tr>
                    <th className="p-2 border-b text-left">Chỉ số</th>
                    <th className="p-2 border-b text-left">Mức tiêu chuẩn</th>
                    <th className="p-2 border-b text-left">Tần suất</th>
                    <th className="p-2 border-b text-left">Phương pháp xử lý</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td className="p-2 border-b font-medium text-red-700">Nhiệt độ (Hot)</td>
                    <td className="p-2 border-b">38°C - 42°C</td>
                    <td className="p-2 border-b">2 giờ/lần</td>
                    <td className="p-2 border-b text-xs">Điều chỉnh van cấp nhiệt/Heat pump.</td>
                  </tr>
                  <tr>
                    <td className="p-2 border-b font-medium text-blue-700">Nhiệt độ (Cold)</td>
                    <td className="p-2 border-b">16°C - 18°C</td>
                    <td className="p-2 border-b">2 giờ/lần</td>
                    <td className="p-2 border-b text-xs">Kiểm tra hệ thống làm lạnh (Chiller).</td>
                  </tr>
                  <tr>
                    <td className="p-2 border-b font-medium">Độ pH</td>
                    <td className="p-2 border-b">7.2 - 7.6</td>
                    <td className="p-2 border-b">4 giờ/lần</td>
                    <td className="p-2 border-b text-xs">Châm hóa chất pH+/pH- tự động hoặc thủ công.</td>
                  </tr>
                  <tr>
                    <td className="p-2 border-b font-medium">Clo dư</td>
                    <td className="p-2 border-b">0.4 - 1.0 ppm</td>
                    <td className="p-2 border-b">4 giờ/lần</td>
                    <td className="p-2 border-b text-xs">Điều chỉnh bơm Clo. Nếu {'>'}3.0: sục khí/thay nước.</td>
                  </tr>
                   <tr>
                    <td className="p-2 border-b font-medium">Độ đục/Màu</td>
                    <td className="p-2 border-b">Trong vắt</td>
                    <td className="p-2 border-b">Liên tục</td>
                    <td className="p-2 border-b text-xs">KT lọc cát/lọc giấy. Backwash bình lọc.</td>
                  </tr>
                </tbody>
              </table>
            </div>

            <div className="bg-red-50 border-l-4 border-red-500 p-4 rounded shadow-sm">
              <h4 className="font-bold text-red-800 flex items-center gap-2 mb-2">
                <AlertTriangle size={20}/> Quy trình xử lý sự cố nước ô nhiễm
              </h4>
              <ul className="list-decimal pl-5 text-sm text-red-900 space-y-1">
                <li>Phát hiện chất thải (nôn, bài tiết...): Nhân viên trực khu <strong>lập tức mời khách ra khỏi hồ</strong>.</li>
                <li>Cô lập hồ, treo biển "Bảo trì".</li>
                <li>Xả toàn bộ nước, cọ rửa bằng Chloramine B.</li>
                <li>Cấp nước mới, gia nhiệt và kiểm tra chỉ số (Mất 4-6 tiếng).</li>
              </ul>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.5. Vệ sinh và Bảo trì khu vực Onsen</h3>
            <div className="grid md:grid-cols-3 gap-4">
              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <div className="flex items-center gap-2 font-bold text-emerald-700 mb-2">
                  <Sparkles size={18}/> Vệ sinh thường xuyên
                </div>
                <p className="text-xs text-stone-600">
                  Tạp vụ liên tục lau khô sàn chống trượt. Sắp xếp ghế tắm, xô gỗ ngay ngắn sau khi khách dùng.
                </p>
              </div>

              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <div className="flex items-center gap-2 font-bold text-blue-700 mb-2">
                  <Clock size={18}/> Vệ sinh cuối ngày
                </div>
                <p className="text-xs text-stone-600">
                  Cọ rửa sàn, tường, phòng xông bằng hóa chất chuyên dụng.
                </p>
              </div>

              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <div className="flex items-center gap-2 font-bold text-orange-700 mb-2">
                  <Wrench size={18}/> Bảo trì định kỳ
                </div>
                <p className="text-xs text-stone-600">
                  Kiểm tra bơm, lọc, nồi hơi hàng tuần. Thay cát lọc/lõi lọc định kỳ theo khuyến cáo.
                </p>
              </div>
            </div>
          </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.6. Hỗ trợ khách gặp khó khăn hoặc có dấu hiệu choáng</h3>
            <div className="bg-orange-50 border-l-4 border-orange-500 p-4 rounded shadow-sm mb-4">
               <h4 className="font-bold text-orange-800 flex items-center gap-2 mb-3">
                  <Stethoscope size={20}/> Quy trình xử lý khẩn cấp
               </h4>
               <ol className="list-decimal pl-5 text-sm text-orange-900 space-y-2">
                  <li><strong>Nhận thông tin:</strong> Xác nhận khách hàng đang có vấn đề sức khỏe.</li>
                  <li><strong>Sơ cứu ban đầu:</strong> Hỗ trợ khách di chuyển ra khu vực thoáng khí để khách dễ thở.</li>
                  <li><strong>Báo cáo Quản lý:</strong> Thông báo ngay cho Quản lý trực ca.</li>
                  <li><strong>Hỗ trợ y tế:</strong> Báo cáo ngay cho bác sĩ/nhân viên y tế khu trị liệu để sang hỗ trợ kịp thời.</li>
                  <li><strong>Trường hợp nghiêm trọng:</strong> Nếu tình trạng nguy hiểm, báo ngay cho Ban Lãnh Đạo (BLD) và gọi cấp cứu 115.</li>
               </ol>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.7. Báo cáo vấn đề cho Quản lý</h3>
            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
               <h4 className="font-bold text-stone-800 flex items-center gap-2 mb-3">
                  <MessageSquare size={20}/> Nội dung báo cáo hàng ngày
               </h4>
               <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                  <li><strong>Checklist công việc:</strong> Báo cáo tình trạng hoàn thành các hạng mục vệ sinh, vận hành trong ca.</li>
                  <li><strong>Phản hồi khách hàng:</strong> Ghi nhận các thắc mắc, than phiền của khách trong ngày để xử lý.</li>
                  <li><strong>Vấn đề nội bộ:</strong> Báo cáo các mâu thuẫn phát sinh trong đội ngũ (nếu có).</li>
                  <li><strong>Khó khăn vận hành:</strong> Chia sẻ những khó khăn, vướng mắc trong quá trình làm việc để được hỗ trợ.</li>
               </ul>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">8.8. Checklist Vận hành & Vệ sinh (Onsen Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Nhân viên trực khu Onsen cần hoàn thành kiểm tra các hạng mục sau đầu mỗi ca trực.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-orange-100 text-orange-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hạng mục</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết kiểm tra</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 1<br/><span className="text-[10px] font-normal">(Opening)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 2<br/><span className="text-[10px] font-normal">(Mid-shift)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* 1. Thiết bị & Điện */}
                  <tr>
                    <td className="p-3 font-bold text-orange-800 align-top" rowSpan="3">1. Thiết bị & Điện</td>
                    <td className="p-3">
                        <ul className="list-disc pl-4 space-y-1">
                            <li>Mở đèn toàn bộ khu vực Onsen.</li>
                            <li>Mở máy lạnh (khi có khách đầu tiên).</li>
                            <li>Bật phòng xông khô, kiểm tra nhiệt độ phòng.</li>
                        </ul>
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-stone-400">Kiểm tra lại</td>
                  </tr>
                  <tr>
                    <td className="p-3">Máy sấy còn hoạt động tốt, dây điện quấn gọn gàng, đủ số lượng.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr>
                    <td className="p-3">Thác bể lụa hoạt động bình thường. Vòi nước không bị rò rỉ.</td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 2. Vật tư tiêu hao (Amenities) */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-orange-800 align-top" rowSpan="4">2. Vật tư tiêu hao</td>
                    <td className="p-3">
                        <strong>Khăn:</strong> Đủ số lượng dự trữ, cất gọn gàng.<br/>
                        <span className="text-xs text-stone-500 italic">(Chuẩn: 150 Khăn đầu, 150 Khăn tắm, 150 Khăn lau)</span>
                    </td>
                    <td className="p-3 text-center text-emerald-600">Đếm đủ</td>
                    <td className="p-3 text-center text-emerald-600">Refill</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Đồ lót giấy:</strong> Đủ dự trữ (200 bộ), cất gọn.<br/>
                        <strong>Quần áo:</strong> Đủ dự trữ (100 Quần, 100 Áo L, 100 Áo XL).
                    </td>
                    <td className="p-3 text-center text-emerald-600">Đếm đủ</td>
                    <td className="p-3 text-center text-emerald-600">Refill</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        Lược chải tóc: Không hư hỏng, không vướng tóc, đủ số lượng, xếp ngăn nắp.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        Lượng xà phòng trong bình {'>'} 70%. Bình đặt ngay ngắn đúng vị trí (Khu tắm ngồi/Lavabo).
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600">Châm thêm</td>
                  </tr>

                  {/* 3. Hồ ngâm & Chất lượng nước */}
                  <tr>
                     <td className="p-3 font-bold text-orange-800 align-top" rowSpan="2">3. Hồ ngâm & Nước</td>
                     <td className="p-3">
                        <strong>Kiểm tra nhiệt độ chuẩn:</strong><br/>
                        - Bể lụa: 36-37°C<br/>
                        - Bể lạnh: 17-19°C<br/>
                        - Bể nóng: 41-43°C
                     </td>
                     <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                     <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                  </tr>
                  <tr>
                     <td className="p-3">
                        Mực nước đạt chuẩn (thấp hơn thành hồ 5-7cm).<br/>
                        Sạch rác, tóc, vật dụng thừa trong/quanh hồ.
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 4. Vệ sinh & Sắp xếp */}
                  <tr className="bg-stone-50">
                     <td className="p-3 font-bold text-orange-800 align-top" rowSpan="5">4. Vệ sinh & Sắp xếp</td>
                     <td className="p-3">Sạch rác xung quanh khu vực. Sàn sạch, không đọng nước, không trơn trượt. Không có mùi hôi.</td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">Thùng rác sạch, có lót bao, không bị đầy. Sọt quần áo dơ trống.</td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600">Thay bao</td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">Ghế, gương đặt đúng vị trí, không nứt bể. Gương sạch không mờ/ố.</td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">Lỗ thoát nước: Không có tóc, xà phòng bị đọng.</td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">
                        <strong>Khu vực WC:</strong><br/>
                        - Bồn cầu không nghẹt, xả nước tốt, nắp không lỏng.<br/>
                        - Lavabo sạch, không bám cặn.<br/>
                        - Không có đồ cá nhân khách bỏ quên.
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 5. Tủ Locker */}
                  <tr>
                     <td className="p-3 font-bold text-orange-800 align-top">5. Tủ Locker</td>
                     <td className="p-3">
                        Mỗi tủ có đủ bộ vật dụng chuẩn:<br/>
                        (2 móc treo, 1 bộ đồ, 3 cái khăn, 1 túi cầm tay)
                     </td>
                     <td className="p-3 text-center text-emerald-600">Kiểm tra ngẫu nhiên</td>
                     <td className="p-3 text-center text-emerald-600">Setup lại tủ trống</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </section>
        </div>
      )
    },
    {
      id: 9,
      title: "Vận hành Jjimjilbang",
      icon: <Flame size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
          {/* 9.1. Quy trình nhân viên trực khu JJB */}
          <section className="mb-6">
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.1. Quy trình Nhân viên Trực khu Jjimjilbang</h3>
            <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
               <div className="space-y-4 text-sm text-stone-700">
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B1</div>
                     <div><strong>Chào đón khách:</strong> Thân thiện, mỉm cười. "Em chào anh/chị, mời mình vào khu Jjimjilbang ạ."</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B2</div>
                     <div><strong>Tiếp nhận thông tin:</strong> Kiểm tra khách từ Onsen lên hoặc từ CSKH. Ghi nhận yêu cầu đặc biệt.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B3</div>
                     <div><strong>Tư vấn & Hướng dẫn:</strong> Giới thiệu các phòng xông. Nhắc thời gian an toàn (10-15p/lượt).</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B4</div>
                     <div><strong>Khách order nước:</strong> Tư vấn menu phù hợp.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B5</div>
                     <div><strong>Quét vòng tay:</strong> Ghi nhận dịch vụ thêm. Báo lại khách đã order gì.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B6</div>
                     <div><strong>Kiểm tra vệ sinh:</strong> An toàn khu vực theo checklist.</div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B7</div>
                     <div><strong>Hướng dẫn chuyển khu:</strong> Mời khách sang khu khác khi dùng xong 1 khu.</div>
                  </div>
                   <div className="flex gap-3">
                     <div className="font-bold text-orange-800 w-8 text-center">B8</div>
                     <div><strong>Chào tạm biệt:</strong> "Chúc Anh/Chị có buổi trải nghiệm tuyệt vời."</div>
                  </div>
               </div>
            </div>
          </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.2. Quy định chung</h3>
            <p className="text-sm italic mb-2 text-stone-600">Khu vực Jjimjilbang là không gian sinh hoạt chung (unisex), khách hàng mặc đồng phục và thư giãn cùng gia đình.</p>
            <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700">
              <li><strong>Đồng phục:</strong> Bắt buộc mặc đồng phục Carezone. Không mặc đồ thường, đồ bơi hay chỉ quấn khăn.</li>
              <li><strong>Vệ sinh:</strong> Không mang thức ăn, đồ uống (trừ nước lọc/nước gạo trong bình kín) vào phòng xông.</li>
              <li><strong>Văn hóa:</strong> Đi nhẹ, nói khẽ, không gây ồn ào ảnh hưởng đến người khác.</li>
            </ul>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.3. Các phòng chức năng</h3>
            <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
              {[
                { name: "Phòng xông hơi khô", desc: "Đào thải độc tố sâu, giảm đau nhức xương khớp và phục hồi sinh lực.", icon: <Flame className="text-orange-500"/> },
                { name: "Phòng xông hơi ướt", desc: "Thải độc da, hỗ trợ đường hô hấp và giảm căng thẳng mệt mỏi.", icon: <Droplets className="text-blue-500"/> },
                { name: "Bể ngâm lạnh", desc: "Giảm sưng viêm, phục hồi cơ bắp nhanh chóng và giúp tỉnh táo tức thì.", icon: <Thermometer className="text-blue-400"/> },
                { name: "Bể ngâm nóng", desc: "Thư giãn sâu, xoa dịu đau nhức cơ thể và tái tạo năng lượng.", icon: <Thermometer className="text-red-500"/> },
                { name: "Bể lụa", desc: "Làm sạch sâu lỗ chân lông, dưỡng da mềm mịn và cân bằng cảm xúc.", icon: <Sparkles className="text-pink-400"/> },
                { name: "Phòng xông cỏ", desc: "Thanh lọc cơ thể, xoa dịu căng thẳng và cải thiện chất lượng giấc ngủ.", icon: <Wind className="text-green-500"/> },
                { name: "Phòng xông đất hoàng thổ", desc: "Kích thích tuần hoàn máu, tăng cường sức đề kháng và làm đẹp da.", icon: <Sun className="text-yellow-600"/> },
                { name: "Phòng xông thuốc bắc", desc: "Giảm đau nhức xương khớp, lưu thông khí huyết và phục hồi sinh lực.", icon: <Coffee className="text-stone-700"/> },
                { name: "Phòng thư giãn Oxi", desc: "Tái tạo năng lượng tế bào, làm sáng da và cân bằng tinh thần.", icon: <Wind className="text-cyan-400"/> },
                { name: "Hang hồng ngoại", desc: "Đào thải độc tố kim loại nặng, giảm đau cơ khớp và hỗ trợ trị liệu sâu.", icon: <Sun className="text-red-600"/> },
                { name: "Massage Cá", desc: "Loại bỏ tế bào chết, làm mịn da và mang lại trải nghiệm giải trí thú vị.", icon: <Waves className="text-blue-600"/> },
                { name: "Ngâm chân nóng", desc: "Kích thích huyệt đạo, tăng cường lưu thông máu và hỗ trợ giấc ngủ ngon.", icon: <Thermometer className="text-red-400"/> },
                { name: "Ngâm chân lạnh", desc: "Giảm sưng viêm, làm dịu đôi chân mệt mỏi và tăng cường sự tỉnh táo.", icon: <Thermometer className="text-blue-300"/> },
                { name: "Phòng thiền âm thanh", desc: "Chữa lành tâm trí bằng sóng âm, giải tỏa âu lo và đạt trạng thái thư giãn sâu.", icon: <Music className="text-purple-500"/> },
              ].map((room, idx) => (
                <div key={idx} className="bg-white p-3 rounded-lg border border-stone-200 shadow-sm hover:shadow-md transition-shadow">
                  <div className="flex items-center gap-2 mb-2">
                    {room.icon}
                    <h4 className="font-bold text-sm text-stone-800">{room.name}</h4>
                  </div>
                  <p className="text-xs text-stone-600">{room.desc}</p>
                </div>
              ))}
            </div>
          </section>
          
           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.4. Các Quy trình Xông hơi chuẩn (Jjimjilbang Cycle)</h3>
            <div className="space-y-4">
              
              {/* Cycle 1: Kết nối */}
              <div className="bg-orange-50 p-4 rounded-lg border border-orange-200 shadow-sm">
                <h4 className="font-bold text-orange-800 mb-3 flex items-center gap-2">
                  <span className="bg-orange-600 text-white w-6 h-6 rounded-full flex items-center justify-center text-xs">1</span>
                  Jjimjilbang kết nối
                </h4>
                <div className="flex flex-col md:flex-row gap-2 items-center text-xs md:text-sm">
                   <div className="bg-white p-2 rounded border border-orange-200 text-center font-medium w-full">Phòng Thảo mộc</div>
                   <ArrowRight className="hidden md:block text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <ArrowDown className="md:hidden text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <div className="bg-white p-2 rounded border border-orange-200 text-center font-medium w-full">Phòng Hoàng thổ</div>
                   <ArrowRight className="hidden md:block text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <ArrowDown className="md:hidden text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <div className="bg-white p-2 rounded border border-orange-200 text-center font-medium w-full">Phòng Thảo dược</div>
                   <ArrowRight className="hidden md:block text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <ArrowDown className="md:hidden text-orange-600 font-bold" size={20} strokeWidth={3} />
                   <div className="bg-white p-2 rounded border border-orange-200 text-center font-medium w-full">Phòng Oxi / Hang hồng ngoại</div>
                </div>
                 <div className="mt-2 text-xs text-orange-800 font-bold bg-white/50 p-2 rounded">
                  *Lưu ý: Mỗi phòng nên dùng trong khoảng 15p là tốt nhất. Sau khi trải nghiệm xong 1 phòng nên ra sảnh nghỉ ngơi, uống nước trong 5-10 phút.
                </div>
              </div>

              {/* Cycle 2: Tỉnh thức */}
              <div className="bg-blue-50 p-4 rounded-lg border border-blue-200 shadow-sm">
                <h4 className="font-bold text-blue-800 mb-3 flex items-center gap-2">
                   <span className="bg-blue-600 text-white w-6 h-6 rounded-full flex items-center justify-center text-xs">2</span>
                   Jjimjilbang tỉnh thức
                </h4>
                <div className="flex flex-col md:flex-row gap-2 items-center text-xs md:text-sm">
                   <div className="bg-white p-2 rounded border border-blue-200 text-center font-medium w-full">Phòng Đá muối Himalaya</div>
                   <ArrowRight className="hidden md:block text-blue-600 font-bold" size={20} strokeWidth={3} />
                   <ArrowDown className="md:hidden text-blue-600 font-bold" size={20} strokeWidth={3} />
                   <div className="bg-white p-2 rounded border border-blue-200 text-center font-medium w-full">
                      Thư giãn<br/>
                      <span className="text-[10px] text-stone-500 font-normal">(Thiền Âm thanh / Hang Hồng ngoại / Massage cá / Ốc đảo)</span>
                   </div>
                   <ArrowRight className="hidden md:block text-blue-600 font-bold" size={20} strokeWidth={3} />
                   <ArrowDown className="md:hidden text-blue-600 font-bold" size={20} strokeWidth={3} />
                   <div className="bg-white p-2 rounded border border-blue-200 text-center font-medium w-full">Phòng Băng tuyết</div>
                </div>
                <div className="mt-2 text-xs text-blue-800 font-bold bg-white/50 p-2 rounded">
                  *Lưu ý: Mỗi phòng nên dùng trong khoảng 15p là tốt nhất. Sau khi trải nghiệm xong 1 phòng nên ra sảnh nghỉ ngơi, uống nước trong 5-10 phút.
                </div>
              </div>

            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.5. Báo cáo vấn đề cho Quản lý</h3>
            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <h4 className="font-bold text-stone-800 flex items-center gap-2 mb-3">
                  <MessageSquare size={20}/> Nội dung báo cáo hàng ngày
                </h4>
                <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                  <li><strong>Tình trạng thiết bị phòng xông:</strong> Kiểm tra và báo cáo nhiệt độ thực tế các phòng (đạt/không đạt), hư hỏng đèn, loa nhạc hoặc hệ thống sưởi sàn.</li>
                  <li><strong>Vệ sinh & Mùi:</strong> Ghi nhận các vấn đề về mùi lạ, vệ sinh tại khu vực hang hồng ngoại, sàn nghỉ chung để đội tạp vụ xử lý ngay.</li>
                  <li><strong>Sự cố khách hàng:</strong> Báo cáo ngay các trường hợp khách có dấu hiệu sức khỏe bất thường (choáng, ngất) hoặc khách vi phạm quy định (mang đồ ăn vào phòng, gây ồn ào).</li>
                  <li><strong>Tài sản & Vật tư:</strong> Báo cáo số lượng gối gỗ, gối thảo dược, thảm nằm bị rách, hỏng hoặc thất lạc cuối mỗi ca trực.</li>
                </ul>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">9.6. Checklist Vận hành & Vệ sinh (Jjimjilbang Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Nhân viên trực khu Jjimjilbang (JJB) hoàn thành kiểm tra các hạng mục sau để đảm bảo tiêu chuẩn vận hành.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-orange-100 text-orange-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hạng mục</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết kiểm tra & Tiêu chuẩn</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 1<br/><span className="text-[10px] font-normal">(Opening)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 2<br/><span className="text-[10px] font-normal">(Mid/Closing)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* 1. Môi trường & Sảnh chung */}
                  <tr>
                    <td className="p-3 font-bold text-orange-800 align-top" rowSpan="3">1. Môi trường & Sảnh chung</td>
                    <td className="p-3">
                        <ul className="list-disc pl-4 space-y-1">
                            <li><strong>Thiết bị:</strong> Mở đèn khu vực JJB. Mở máy lạnh.</li>
                            <li><strong>Rèm cửa:</strong> Kéo sát xuống dưới (che nắng).</li>
                            <li><strong>Vệ sinh:</strong> Không rác/vật thừa. Sắp xếp sọt rác, ly nước ngay ngắn.</li>
                            <li><strong>Kệ dép:</strong> Đủ số lượng dép, xếp ngay ngắn.</li>
                        </ul>
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr>
                    <td className="p-3">
                        <strong>Gối - Nệm:</strong><br/>
                        - Đủ số lượng (Mỗi bục gỗ: 2 thảm + gối).<br/>
                        - Sắp xếp ngay ngắn, đúng vị trí.<br/>
                        - Không bị rách, hư hỏng.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra & Sắp xếp</td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra & Sắp xếp</td>
                  </tr>
                  <tr>
                    <td className="p-3">
                        <strong>Bàn - Bục gỗ:</strong> Lau sạch nước/rác trên bàn. Lau bục gỗ tròn sạch sẽ.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 2. Các Phòng Xông (Nhiệt độ) */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-orange-800 align-top" rowSpan="4">2. Các Phòng Xông<br/><span className="text-[10px] font-normal">(Kiểm tra Nhiệt độ & Thảm gối)</span></td>
                    <td className="p-3">
                        <div className="grid grid-cols-2 gap-2">
                           <div><strong>Phòng Thảo mộc:</strong> 52°C</div>
                           <div><strong>Phòng Hoàng thổ:</strong> 56°C</div>
                           <div><strong>Phòng Thuốc bắc:</strong> 57°C</div>
                           <div><strong>Phòng Đá muối:</strong> 54°C</div>
                        </div>
                        <div className="mt-1 text-xs text-stone-500 italic">- Thảm, gối đầy đủ, ngăn nắp.</div>
                    </td>
                    <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                    <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">
                        <strong>Phòng Thư giãn Oxi:</strong> 24°C<br/>
                        <strong>Phòng Oxi âm thanh:</strong> 23°C<br/>
                        <span className="text-xs text-stone-500 italic">- Thảm, gối đầy đủ.</span>
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">
                        <strong>Phòng Xông Lạnh:</strong> 0 - 2°C<br/>
                        <span className="text-xs text-stone-500 italic">- Không có vật dụng thừa, sạch sẽ.</span>
                     </td>
                     <td className="p-3 text-center text-emerald-600">Kiểm tra độ lạnh</td>
                     <td className="p-3 text-center text-emerald-600">Kiểm tra độ lạnh</td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">
                        <strong>Hang Hồng Ngoại:</strong> Bật đèn hồng ngoại.<br/>
                        <span className="text-xs text-stone-500 italic">- Thảm, gối đầy đủ từng hang.</span>
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 3. Khu vực Ngâm chân & Cá */}
                  <tr>
                     <td className="p-3 font-bold text-orange-800 align-top" rowSpan="2">3. Khu Ngâm chân & Massage Cá</td>
                     <td className="p-3">
                        <strong>Bể Massage Cá (Ria):</strong><br/>
                        <ul className="list-disc pl-4 space-y-0.5">
                           <li>Không có cá chết. Bật sục Oxi.</li>
                           <li>Mực nước cách bậc thứ 2 khoảng 5-7cm.</li>
                           <li>Không mùi tanh. Nước chảy hoạt động tốt.</li>
                           <li>Không rác trong/ngoài bể. Thềm khô ráo.</li>
                        </ul>
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr>
                     <td className="p-3">
                        <strong>Bể Ngâm chân:</strong><br/>
                        - Bể Nóng: <strong>38 - 42°C</strong><br/>
                        - Bể Lạnh: <strong>8 - 15°C</strong><br/>
                        <span className="text-xs text-stone-500 italic">- Không có rác, tóc, cặn thành bồn.</span>
                     </td>
                     <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                     <td className="p-3 text-center text-emerald-600">Đo nhiệt độ</td>
                  </tr>

                  {/* 4. Vệ sinh WC & Kết thúc */}
                  <tr className="bg-stone-50">
                     <td className="p-3 font-bold text-orange-800 align-top">4. Vệ sinh (WC) & Đóng ca</td>
                     <td className="p-3">
                        <strong>Kiểm tra WC:</strong> Sàn khô, không rác/mùi. Thùng rác không đầy. Bồn cầu/Lavabo sạch. Đủ giấy/xà phòng.<br/>
                        <strong>Tắt thiết bị (Cuối ngày):</strong> Tắt máy lạnh, Tắt phòng xông, Tắt đèn. Rèm cửa kéo lên (nếu trời mát).
                     </td>
                     <td className="p-3 text-center text-emerald-600">Kiểm tra WC</td>
                     <td className="p-3 text-center text-emerald-600"><strong>Thực hiện Closing</strong></td>
                  </tr>
                </tbody>
              </table>
            </div>
          </section>
        </div>
      )
    },
    {
      id: 10,
      title: "Dịch vụ Trị liệu (Spa)",
      icon: <Sparkles size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.1. Chuẩn bị trước khi khách đến</h3>
            <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
               <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700">
                  <li><strong>Vệ sinh phòng:</strong> Đảm bảo phòng sạch sẽ, thoáng mát. Thay ga trải giường, vỏ gối mới.</li>
                  <li><strong>Setup không gian:</strong> Điều chỉnh ánh sáng dịu nhẹ, bật nhạc thiền/spa volume vừa phải, đốt tinh dầu hương liệu nhẹ nhàng.</li>
                  <li><strong>Chuẩn bị dụng cụ:</strong> Chuẩn bị sẵn khăn, dầu massage, đá nóng (nếu có), chậu ngâm chân nước ấm.</li>
                  <li><strong>Nhiệt độ phòng:</strong> Duy trì ở mức 25-26°C.</li>
               </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.2. Đón tiếp & Xác nhận dịch vụ</h3>
            <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-200 shadow-sm">
               <ol className="list-decimal pl-5 space-y-3 text-sm text-stone-800">
                  <li><strong>Chào đón:</strong> Mỉm cười, cúi chào khách tại khu vực chờ của spa.</li>
                  <li><strong>Kiểm tra thông tin:</strong> 
                     <ul className="list-disc pl-5 mt-1 text-stone-600 text-xs">
                        <li>Quét vòng tay RFID của khách để xác nhận gói dịch vụ đã mua.</li>
                        <li><strong>Trường hợp khách chưa mua gói:</strong> Tư vấn menu spa và thực hiện thao tác <strong>thêm dịch vụ (upsell)</strong> trực tiếp vào vòng tay trên máy POS.</li>
                     </ul>
                  </li>
                  <li><strong>Tư vấn sức khỏe:</strong> Hỏi thăm tình trạng sức khỏe, các vùng đau mỏi cần tập trung hoặc các lưu ý đặc biệt (chấn thương, dị ứng...).</li>
               </ol>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.3. Quy trình Trị liệu (Treatment)</h3>
            <div className="space-y-4">
               <div className="border-l-4 border-emerald-500 pl-4">
                  <h4 className="font-bold text-emerald-800 text-sm">Bước 1: Mời khách vào phòng</h4>
                  <p className="text-xs text-stone-600">Hướng dẫn khách thay đồ (nếu cần), cất tư trang và nằm lên giường trị liệu đúng tư thế.</p>
               </div>
               <div className="border-l-4 border-emerald-500 pl-4">
                  <h4 className="font-bold text-emerald-800 text-sm">Bước 2: Thực hiện Massage</h4>
                  <p className="text-xs text-stone-600">
                     - Tiến hành bài trị liệu theo đúng quy trình kỹ thuật đã được đào tạo.<br/>
                     - Thường xuyên hỏi thăm khách về lực đạo: <em>"Lực em đi như vậy có vừa không ạ?"</em>.<br/>
                     - Giữ im lặng trong quá trình làm, chỉ giao tiếp khi cần thiết.
                  </p>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.4. Kết thúc & Chăm sóc sau trị liệu</h3>
            <div className="bg-blue-50 p-4 rounded-lg border border-blue-200 shadow-sm">
               <ol className="list-decimal pl-5 space-y-3 text-sm text-stone-800">
                  <li><strong>Kết thúc bài:</strong> Thông báo nhẹ nhàng cho khách biết liệu trình đã kết thúc. Lau sạch dầu thừa trên cơ thể khách bằng khăn ấm.</li>
                  <li><strong>Mời trà & Đánh giá:</strong> Đỡ khách ngồi dậy, mời khách uống trà ấm/ăn nhẹ (nếu có). Cảm ơn khách và khéo léo nhờ khách đánh giá chất lượng dịch vụ (qua phiếu hoặc tablet).</li>
                  <li><strong>Hướng dẫn di chuyển:</strong> Hỗ trợ cung cấp thông tin để khách di chuyển sang khu vực trải nghiệm tiếp theo (ví dụ: Nhà hàng, Khu nghỉ ngơi, hoặc ra về).</li>
                  <li><strong>Tiễn khách:</strong> Cúi chào tạm biệt khách tại cửa Spa.</li>
                  <li><strong>Vệ sinh phòng:</strong> Thu dọn khăn, ga gối bẩn, vệ sinh phòng để sẵn sàng đón khách tiếp theo.</li>
               </ol>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.5. Báo cáo vấn đề cho Quản lý</h3>
            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
               <h4 className="font-bold text-stone-800 flex items-center gap-2 mb-3">
                  <MessageSquare size={20}/> Nội dung báo cáo hàng ngày
               </h4>
               <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                  <li><strong>Chất lượng KTV:</strong> Báo cáo các trường hợp KTV bị khách phàn nàn về thái độ hoặc lực tay không đạt yêu cầu.</li>
                  <li><strong>Cơ sở vật chất:</strong> Ghi nhận tình trạng phòng trị liệu (mùi ẩm mốc, đèn hỏng, nhạc không phát) để bảo trì xử lý.</li>
                  <li><strong>Vật tư tiêu hao:</strong> Báo cáo mức tiêu thụ dầu massage, khăn, đá nóng trong ngày và đề xuất nhập thêm nếu sắp hết.</li>
                  <li><strong>Sự cố y tế:</strong> Báo cáo ngay các trường hợp khách bị dị ứng dầu, đau tăng nặng sau khi massage để có hướng xử lý kịp thời.</li>
               </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">10.6. Checklist Vận hành Spa (Therapist Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Kỹ thuật viên (KTV) phải hoàn thành việc setup phòng trước khi đón khách.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-purple-100 text-purple-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hạng mục</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết kiểm tra & Tiêu chuẩn</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 1<br/><span className="text-[10px] font-normal">(Đầu ca)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 2<br/><span className="text-[10px] font-normal">(Giao ca)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* 1. Setup Phòng */}
                  <tr>
                    <td className="p-3 font-bold text-purple-800 align-top" rowSpan="3">1. Setup Phòng Trị liệu</td>
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
                        - Âm nhạc: Nhạc thiền Spa volume 20-30%.
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

                  {/* 2. Vật tư tiêu hao */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-purple-800 align-top" rowSpan="2">2. Vật tư & Dụng cụ</td>
                    <td className="p-3">
                        <strong>Kiểm tra số lượng:</strong><br/>
                        - Dầu massage (Baby oil/Dầu dừa): Đầy bình.<br/>
                        - Đá nóng: Đủ bộ, nồi hấp đá hoạt động tốt.<br/>
                        - Quần lót giấy: Đủ cho khách trong ca.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Refill đầy đủ</td>
                    <td className="p-3 text-center text-emerald-600">Refill đầy đủ</td>
                  </tr>
                  <tr className="bg-stone-50">
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
      id: 11,
      title: "Quy trình Thu ngân (Cashier)",
      icon: <Receipt size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.1. Chuẩn bị đầu ca (Opening)</h3>
            <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
               <ul className="list-disc pl-5 space-y-2 text-sm text-stone-700">
                  <li><strong>Nhận bàn giao quỹ (Float):</strong> Kiểm đếm chính xác số tiền lẻ nhận từ ca trước/Thủ quỹ để thối lại cho khách. Ký xác nhận vào sổ quỹ.</li>
                  <li><strong>Kiểm tra thiết bị:</strong> Đảm bảo máy POS, máy quẹt thẻ (EDC), máy in hóa đơn hoạt động tốt. Kiểm tra giấy in bill còn đủ dùng trong ca không.</li>
                  <li><strong>Vệ sinh quầy:</strong> Sắp xếp chứng từ, kẹp file, máy tính gọn gàng, sạch sẽ.</li>
                  <li><strong>Cập nhật thông tin:</strong> Nắm bắt các chương trình khuyến mãi (Promotion) đang chạy trong ngày để áp dụng đúng cho khách.</li>
               </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.2. Quy trình Thu ngân Check-in (Check-in Payment)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Quy trình thu phí vé vào cổng và kích hoạt vòng tay trước khi khách sử dụng dịch vụ.</p>
            <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-200">
               <div className="space-y-4">
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 h-8 flex items-center justify-center bg-white rounded-full border border-emerald-200 shadow-sm flex-shrink-0">B1</div>
                     <div className="text-sm text-stone-700">
                        <strong>Tiếp nhận Order:</strong>
                        <p className="text-xs text-stone-500 mt-1">Nhận thông tin order từ bộ phận CSKH chuyển sang (trên phần mềm hoặc phiếu order). Xác nhận lại với khách: Số lượng vé, Gói dịch vụ (Combo/Lẻ), Voucher giảm giá.</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 h-8 flex items-center justify-center bg-white rounded-full border border-emerald-200 shadow-sm flex-shrink-0">B2</div>
                     <div className="text-sm text-stone-700">
                        <strong>Thu tiền (Payment):</strong>
                        <p className="text-xs text-stone-500 mt-1">Thông báo tổng số tiền cần thanh toán. Thực hiện thu tiền (Tiền mặt/Thẻ/QR Code).</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 h-8 flex items-center justify-center bg-white rounded-full border border-emerald-200 shadow-sm flex-shrink-0">B3</div>
                     <div className="text-sm text-stone-700">
                        <strong>Kích hoạt Vòng tay (Activate):</strong>
                        <p className="text-xs text-stone-500 mt-1">Quét mã vòng tay RFID lên máy để kích hoạt tài khoản. Gán gói dịch vụ vào chip của vòng tay.</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-emerald-800 w-8 h-8 flex items-center justify-center bg-white rounded-full border border-emerald-200 shadow-sm flex-shrink-0">B4</div>
                     <div className="text-sm text-stone-700">
                        <strong>Bàn giao (Handover):</strong>
                        <p className="text-xs text-stone-500 mt-1">Giao vòng tay và biên lai thu tiền cho khách. Hướng dẫn khách: <em>"Đây là vòng tay của anh/chị, dùng để mở tủ và mua đồ ăn trong khu vực. Chúc anh/chị vui vẻ ạ."</em></p>
                     </div>
                  </div>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.3. Quy trình Thanh toán Check-out (Final Payment)</h3>
            <div className="bg-stone-50 p-4 rounded-lg border border-stone-200">
               <div className="space-y-4">
                  <div className="flex gap-3">
                     <div className="font-bold text-stone-600 w-8 text-center bg-stone-200 rounded">B1</div>
                     <div className="text-sm text-stone-700">
                        <strong>Nhận vòng tay (Wristband):</strong>
                        <p className="text-xs text-stone-500 mt-1">Mỉm cười chào khách. Nhận vòng tay từ khách hoặc Lễ tân. Kiểm tra tình trạng vòng tay (có nứt vỡ không).</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-stone-600 w-8 text-center bg-stone-200 rounded">B2</div>
                     <div className="text-sm text-stone-700">
                        <strong>Truy xuất dữ liệu (Scan):</strong>
                        <p className="text-xs text-stone-500 mt-1">Đặt vòng lên đầu đọc RFID để hiện toàn bộ danh sách dịch vụ/món ăn khách đã sử dụng thêm (Phát sinh).</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-stone-600 w-8 text-center bg-stone-200 rounded">B3</div>
                     <div className="text-sm text-stone-700">
                        <strong>Xác nhận & Thu phát sinh (Settle):</strong>
                        <p className="text-xs text-stone-500 mt-1">In "Phiếu tạm tính" đưa khách xem. Thu số tiền phát sinh (nếu có). Nếu bằng 0đ thì bỏ qua bước thu tiền.</p>
                     </div>
                  </div>
                  <div className="flex gap-3">
                     <div className="font-bold text-stone-600 w-8 text-center bg-stone-200 rounded">B4</div>
                     <div className="text-sm text-stone-700">
                        <strong>Kết thúc (Closing):</strong>
                        <p className="text-xs text-stone-500 mt-1">In hóa đơn chính thức. Trả lại tiền thừa (nếu có). Cảm ơn khách. Kích hoạt mở khóa tủ giày (nếu hệ thống tự động).</p>
                     </div>
                  </div>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.4. Xử lý tình huống đặc biệt</h3>
            <div className="grid md:grid-cols-2 gap-4">
               <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm mb-2">Hủy món / Hủy Bill (Void/Cancel)</h4>
                  <p className="text-xs text-stone-600">
                     Chỉ thực hiện khi có xác nhận của Quản lý (Key thẻ Admin). Phải ghi rõ lý do hủy (Khách đổi ý, Order nhầm...) vào mặt sau liên in lưu trữ.
                  </p>
               </div>
               <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm mb-2">Tách Bill / Gộp Bill</h4>
                  <p className="text-xs text-stone-600">
                     Hỗ trợ khi khách đi đoàn đông nhưng muốn thanh toán riêng. Thao tác cẩn thận để tránh sót món.
                  </p>
               </div>
               <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm mb-2">Mất vòng tay RFID</h4>
                  <p className="text-xs text-stone-600">
                     Thu phí phạt mất vòng theo quy định (thường là 200.000đ - 300.000đ). Kiểm tra lịch sử camera để xác định dịch vụ khách đã dùng trước đó.
                  </p>
               </div>
               <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm mb-2">Khách thiếu tiền/Quên ví</h4>
                  <p className="text-xs text-stone-600">
                     Giữ lại giấy tờ tùy thân hoặc tài sản giá trị. Lập biên bản xác nhận nợ có chữ ký khách và Quản lý. Hẹn thời gian thanh toán.
                  </p>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.5. Chốt ca & Báo cáo (Closing)</h3>
            <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-200 shadow-sm">
               <ol className="list-decimal pl-5 space-y-2 text-sm text-stone-800">
                  <li><strong>In báo cáo tổng kết (Z-Report):</strong> In báo cáo doanh thu cuối ca từ máy POS.</li>
                  <li><strong>Kiểm đếm tiền mặt:</strong> Đếm tổng tiền mặt thực tế tại két. Tách riêng tiền quỹ (Float) để lại cho ca sau.</li>
                  <li><strong>Đối chiếu (Reconciliation):</strong> So sánh Doanh thu trên máy POS = Tiền mặt + Thẻ + QR. Nếu lệch phải giải trình ngay.</li>
                  <li><strong>Niêm phong & Nộp tiền:</strong> Cho tiền doanh thu vào túi niêm phong, ghi rõ Số tiền, Tên thu ngân, Ngày giờ. Bỏ vào két sắt an toàn hoặc nộp cho Thủ quỹ.</li>
                  <li><strong>Sắp xếp chứng từ:</strong> Bấm ghim các bill thẻ, voucher giảm giá cùng với báo cáo Z-Report để nộp cho Kế toán.</li>
               </ol>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">11.6. Checklist Thu ngân (Cashier Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Đảm bảo sự chính xác tuyệt đối về tiền mặt và chứng từ.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-emerald-100 text-emerald-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hạng mục</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết kiểm tra</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 1<br/><span className="text-[10px] font-normal">(Opening)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca 2<br/><span className="text-[10px] font-normal">(Closing)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  <tr>
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="2">1. Tiền & Quỹ</td>
                    <td className="p-3">
                        <strong>Quỹ đầu ca (Float):</strong> Kiểm đếm đủ số tiền lẻ (ví dụ: 2.000.000đ) để thối. Tiền không rách, đủ mệnh giá.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Đếm & Ký nhận</td>
                    <td className="p-3 text-center text-emerald-600">Đếm & Ký nhận</td>
                  </tr>
                   <tr>
                    <td className="p-3">
                        <strong>Két sắt:</strong> Khóa an toàn hoạt động tốt. Không để tiền cá nhân trong két.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top" rowSpan="3">2. Thiết bị & Vật tư</td>
                    <td className="p-3">
                        <strong>Hệ thống POS & Máy tính:</strong> Khởi động, đăng nhập thành công. Ngày giờ hệ thống chính xác.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-stone-400">-</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Máy cà thẻ (EDC) & QR:</strong> Kết nối mạng ổn định. Test in thử (Settlement test) nếu cần.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Check tín hiệu</td>
                    <td className="p-3 text-center text-emerald-600">In kết toán (Settlement)</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Giấy in Bill:</strong> Còn đủ dùng. Có sẵn 2-3 cuộn dự phòng ngay tại quầy.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra</td>
                    <td className="p-3 text-center text-emerald-600">Bổ sung</td>
                  </tr>

                  <tr>
                    <td className="p-3 font-bold text-emerald-800 align-top">3. Vệ sinh & Chứng từ</td>
                    <td className="p-3">
                        - Quầy thu ngân sạch bụi, gọn gàng.<br/>
                        - Sắp xếp Bill, Voucher, Phiếu hủy theo thứ tự.<br/>
                        - Bàn giao sổ sách rõ ràng.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600">Niêm phong</td>
                  </tr>
                </tbody>
              </table>
            </div>
           </section>
        </div>
      )
    },
    {
      id: 12,
      title: "Nhà hàng Thực dưỡng",
      icon: <Utensils size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.1. Nguyên tắc & Bảo quản</h3>
            <p className="text-sm text-stone-600 italic mb-2">"Thực túc - An nhiên" - Chú trọng sự tươi ngon và nguồn gốc nguyên liệu.</p>
            <div className="grid md:grid-cols-2 gap-4">
               <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-emerald-800 text-sm flex items-center gap-2 mb-2">
                     <Truck size={16}/> Nhập & Lưu kho (Receiving & Storage)
                  </h4>
                  <ul className="list-disc pl-5 space-y-1 text-xs text-stone-700">
                     <li><strong>Nhập hàng:</strong> Kiểm tra kỹ rau, củ, nấm mỗi sáng. Từ chối hàng héo, úa, dập nát.</li>
                     <li><strong>Sơ chế:</strong> Rửa rau củ kỹ tại khu vực riêng để loại bỏ đất cát/dư lượng.</li>
                     <li><strong>Lưu kho:</strong> Tuân thủ <strong>FIFO</strong> (Nhập trước xuất trước). Dán nhãn ngày nhập.</li>
                  </ul>
               </div>
               <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-emerald-800 text-sm flex items-center gap-2 mb-2">
                     <UtensilsCrossed size={16}/> Khu vực Bếp
                  </h4>
                  <ul className="list-disc pl-5 space-y-1 text-xs text-stone-700">
                     <li>Giữ vệ sinh an toàn thực phẩm nghiêm ngặt.</li>
                     <li>Phân khu sơ chế sống/chín riêng biệt để tránh nhiễm khuẩn chéo.</li>
                  </ul>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.2. Quy trình Phục vụ (Service Flow)</h3>
            <div className="bg-stone-50 p-4 rounded-lg border border-stone-200">
               <div className="space-y-4">
                  <div className="flex items-start gap-3">
                     <div className="w-8 h-8 rounded-full bg-emerald-600 text-white flex items-center justify-center font-bold flex-shrink-0">1</div>
                     <div className="bg-white p-3 rounded flex-1 border border-emerald-100 shadow-sm">
                        <strong className="text-emerald-800 text-sm">Đón khách</strong>
                        <p className="text-xs text-stone-600 mt-1">Mời khách vào bàn. Phong cách phục vụ thoải mái nhưng lịch sự (khách thường mặc đồ Jjimjilbang).</p>
                     </div>
                  </div>
                  
                  <div className="flex items-start gap-3">
                     <div className="w-8 h-8 rounded-full bg-emerald-600 text-white flex items-center justify-center font-bold flex-shrink-0">2</div>
                     <div className="bg-white p-3 rounded flex-1 border border-emerald-100 shadow-sm">
                        <strong className="text-emerald-800 text-sm">Order món</strong>
                        <ul className="text-xs text-stone-600 mt-1 list-disc pl-4">
                           <li>Dùng Tablet ghi order.</li>
                           <li><strong>Quét vòng tay RFID</strong> để ghi nợ (Không thu tiền mặt tại bàn).</li>
                           <li>Tư vấn thực đơn theo nguyên tắc cân bằng dinh dưỡng <strong>Ngũ hành</strong>.</li>
                        </ul>
                     </div>
                  </div>

                  <div className="flex items-start gap-3">
                     <div className="w-8 h-8 rounded-full bg-emerald-600 text-white flex items-center justify-center font-bold flex-shrink-0">3</div>
                     <div className="bg-white p-3 rounded flex-1 border border-emerald-100 shadow-sm">
                        <strong className="text-emerald-800 text-sm">Lên món (Serving)</strong>
                        <p className="text-xs text-stone-600 mt-1">
                           Thứ tự: <strong>Khai vị/Salad &rarr; Súp/Canh &rarr; Món chính/Cơm &rarr; Tráng miệng</strong>.<br/>
                           Giới thiệu tên món và nguyên liệu chính khi đặt xuống bàn.
                        </p>
                     </div>
                  </div>

                  <div className="flex items-start gap-3">
                     <div className="w-8 h-8 rounded-full bg-emerald-600 text-white flex items-center justify-center font-bold flex-shrink-0">4</div>
                     <div className="bg-white p-3 rounded flex-1 border border-emerald-100 shadow-sm">
                        <strong className="text-emerald-800 text-sm">Thanh toán</strong>
                        <p className="text-xs text-stone-600 mt-1">Nhắc khách thanh toán tổng bill tại quầy Lễ tân khi Check-out.</p>
                     </div>
                  </div>
               </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.3. Vệ sinh & An toàn thực phẩm</h3>
            <div className="grid md:grid-cols-2 gap-4">
              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <h4 className="font-bold text-stone-800 mb-2 flex items-center gap-2 text-sm"><Trash2 size={16}/> Quy định vệ sinh</h4>
                <ul className="list-disc pl-5 text-xs text-stone-600 space-y-1">
                   <li>Vệ sinh bàn ghế ngay sau khi khách rời đi.</li>
                   <li>Lau chùi sàn nhà, quầy bar định kỳ trong ca.</li>
                   <li>Phân loại rác thải hữu cơ và vô cơ đúng quy định.</li>
                </ul>
              </div>
              <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
                <h4 className="font-bold text-stone-800 mb-2 flex items-center gap-2 text-sm"><AlertCircle size={16}/> An toàn thực phẩm</h4>
                <ul className="list-disc pl-5 text-xs text-stone-600 space-y-1">
                   <li>Nhân viên bếp đeo khẩu trang, găng tay khi chế biến.</li>
                   <li>Bảo quản thực phẩm sống và chín riêng biệt.</li>
                   <li>Kiểm tra nhiệt độ tủ lạnh/tủ đông thường xuyên.</li>
                </ul>
              </div>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.4. Xử lý tình huống thường gặp</h3>
            <div className="bg-stone-50 p-4 rounded-lg border border-stone-200">
              <ul className="space-y-3 text-sm text-stone-700">
                 <li className="bg-white p-2 rounded shadow-sm">
                    <strong>Khách phàn nàn về món ăn (mặn/nhạt/nguội):</strong><br/>
                    <span className="text-xs">Xin lỗi khách &rarr; Xin phép mang vào bếp kiểm tra &rarr; Đổi món mới hoặc làm nóng lại &rarr; Mời khách dùng thử.</span>
                 </li>
                 <li className="bg-white p-2 rounded shadow-sm">
                    <strong>Khách làm đổ đồ ăn/vỡ ly tách:</strong><br/>
                    <span className="text-xs">Nhanh chóng hỗ trợ khách (lau dọn, kiểm tra xem khách có bị thương không) &rarr; Dọn dẹp hiện trường &rarr; Báo quản lý nếu cần thiết.</span>
                 </li>
              </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.5. Báo cáo vấn đề cho Quản lý</h3>
            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
               <h4 className="font-bold text-stone-800 flex items-center gap-2 mb-3">
                  <MessageSquare size={20}/> Nội dung báo cáo hàng ngày
               </h4>
               <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                  <li><strong>Chất lượng món ăn (Food Quality):</strong> Báo cáo số lượng món bị khách trả lại hoặc phàn nàn (lý do: mặn, nguội, có dị vật...).</li>
                  <li><strong>Hủy món/Hủy Bill (Void/Cancel):</strong> Giải trình lý do hủy món hoặc hủy bill trong ca để Kế toán kiểm soát (do khách đổi ý hay nhân viên order sai).</li>
                  <li><strong>Tồn kho & Hàng hỏng (Spoilage):</strong> Báo cáo số lượng nguyên liệu bị hư hỏng phải đổ bỏ trong ngày và lý do.</li>
                  <li><strong>Thiết bị bếp:</strong> Báo cáo tình trạng tủ đông, tủ mát, bếp từ... nếu có dấu hiệu hoạt động không ổn định.</li>
               </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">12.6. Checklist Nhà hàng (Restaurant Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Áp dụng cho cả bộ phận Bếp (BOH) và Phục vụ (FOH).</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-green-100 text-green-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Khu vực</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết công việc</th>
                    <th className="p-3 text-center border-b w-[20%]">Ca Sáng<br/><span className="text-[10px] font-normal">(Opening)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Ca Chiều<br/><span className="text-[10px] font-normal">(Closing)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* Bàn & Sảnh (FOH) */}
                  <tr>
                    <td className="p-3 font-bold text-green-800 align-top" rowSpan="3">1. Phục vụ (FOH)<br/><span className="text-[10px] font-normal">(Sảnh ăn uống)</span></td>
                    <td className="p-3">
                        <strong>Vệ sinh bàn ghế:</strong> Lau sạch bằng cồn/nước sát khuẩn. Xếp ghế ngay ngắn. Sàn nhà sạch, khô.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>
                  <tr>
                    <td className="p-3">
                        <strong>Setup bàn ăn:</strong><br/>
                        - Đủ gia vị (nước tương, ớt bột).<br/>
                        - Đủ giấy ăn, tăm.<br/>
                        - Menu sạch sẽ, không rách.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Setup đủ</td>
                    <td className="p-3 text-center text-emerald-600">Refill</td>
                  </tr>
                  <tr>
                    <td className="p-3">
                        <strong>Khu vực nước uống tự phục vụ:</strong> Đủ ly, nước lọc/trà đá đầy bình.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600">Dọn dẹp</td>
                  </tr>

                  {/* Bếp (BOH) */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-green-800 align-top" rowSpan="3">2. Bếp (BOH)<br/><span className="text-[10px] font-normal">(Chế biến)</span></td>
                    <td className="p-3">
                        <strong>Nguyên liệu đầu ngày:</strong> Kiểm tra hàng nhập (rau, thịt, cá) tươi ngon. Loại bỏ hàng hỏng.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra & Nhập</td>
                    <td className="p-3 text-center text-stone-400">-</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Thiết bị lạnh:</strong> Nhiệt độ tủ mát (0-4°C), Tủ đông (&lt;-18°C).
                    </td>
                    <td className="p-3 text-center text-emerald-600">Ghi log nhiệt độ</td>
                    <td className="p-3 text-center text-emerald-600">Ghi log nhiệt độ</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Vệ sinh cuối ca:</strong><br/>
                        - Chà rửa bếp, thớt, dao.<br/>
                        - Đổ rác, thay bao rác mới.<br/>
                        - Tắt gas, khóa van an toàn.
                    </td>
                    <td className="p-3 text-center text-stone-400">-</td>
                    <td className="p-3 text-center text-emerald-600"><strong>Quan trọng</strong></td>
                  </tr>
                </tbody>
              </table>
            </div>
           </section>
        </div>
      )
    },
    {
      id: 13,
      title: "Bảo trì & An toàn",
      icon: <Wrench size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">13.1. Quy trình Ứng phó Y tế (Emergency Response)</h3>
            <div className="grid md:grid-cols-2 gap-4">
               {/* Code Blue */}
               <div className="bg-red-50 p-4 rounded-lg border border-red-200">
                  <h4 className="font-bold text-red-800 mb-2 flex items-center gap-2"><Stethoscope size={18}/> Code Blue: Khách ngất xỉu/Sốc nhiệt</h4>
                  <ol className="list-decimal pl-5 text-xs text-red-900 space-y-2">
                     <li><strong>Đánh giá (Assess):</strong> Tiếp cận nhanh, kiểm tra tri giác, hô hấp. Gọi hỗ trợ ngay lập tức.</li>
                     <li><strong>Sơ cứu (First Aid):</strong> Đưa khách ra nơi thoáng mát. Nới lỏng quần áo. Chườm mát trán, nách, bẹn. Cho uống Oresol nếu tỉnh.</li>
                     <li><strong>Gọi cấp cứu 115:</strong> Nếu khách bất tỉnh, co giật hoặc khó thở.</li>
                     <li><strong>Báo cáo:</strong> Ghi nhận sự việc vào Logbook và báo cáo Giám đốc.</li>
                  </ol>
               </div>
               
               {/* First Aid Box */}
               <div className="bg-white p-4 rounded-lg border border-stone-200">
                  <h4 className="font-bold text-emerald-800 mb-2 flex items-center gap-2"><Briefcase size={18}/> Tủ thuốc Sơ cấp cứu</h4>
                  <ul className="list-disc pl-5 text-xs text-stone-700 space-y-1">
                     <li><strong>Vị trí:</strong> Đặt tại Quầy Lễ tân và Phòng trực Onsen.</li>
                     <li><strong>Danh mục bắt buộc:</strong> Bông, băng gạc, cồn sát khuẩn, nước muối sinh lý, dầu gió, băng cá nhân, thuốc giảm đau (Paracetamol), Oresol.</li>
                     <li><strong>Kiểm tra:</strong> HCNS kiểm tra hạn sử dụng và bổ sung thuốc vào ngày 01 hàng tháng.</li>
                  </ul>
               </div>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">13.2. Phòng cháy chữa cháy (PCCC)</h3>
            <div className="bg-orange-50 p-4 rounded-lg border border-orange-200 shadow-sm">
               <div className="flex gap-4">
                  <div className="hidden md:block bg-orange-100 p-3 rounded-full h-fit text-orange-600">
                     <FireExtinguisher size={32} />
                  </div>
                  <div>
                     <h4 className="font-bold text-orange-800 mb-2">Quy trình xử lý khi có báo cháy</h4>
                     <ol className="list-decimal pl-5 text-sm text-stone-800 space-y-2">
                        <li><strong>Báo động (Alarm):</strong> Hô to "CHÁY! CHÁY!" và ấn nút báo cháy khẩn cấp gần nhất.</li>
                        <li><strong>Cúp điện:</strong> Ngắt cầu dao điện khu vực xảy ra cháy.</li>
                        <li><strong>Chữa cháy tại chỗ:</strong> Sử dụng bình bột/CO2 để dập tắt đám cháy nhỏ (nếu an toàn).</li>
                        <li><strong>Sơ tán (Evacuate):</strong> Hướng dẫn khách hàng và nhân viên di chuyển ra lối thoát hiểm (Exit) theo tư thế cúi thấp, dùng khăn ẩm che mũi miệng.</li>
                        <li><strong>Gọi 114:</strong> Gọi cứu hỏa chuyên nghiệp nếu đám cháy lan rộng không kiểm soát được.</li>
                     </ol>
                  </div>
               </div>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">13.3. An ninh & An toàn tài sản</h3>
             <ul className="space-y-3 text-sm text-stone-700 bg-white p-4 rounded border border-stone-200 shadow-sm">
               <li className="flex gap-2">
                  <Shield size={18} className="text-emerald-600 flex-shrink-0"/>
                  <span><strong>Kiểm soát ra vào:</strong> Bảo vệ và Lễ tân phối hợp kiểm soát người lạ ra vào khu vực văn phòng/kho hàng.</span>
               </li>
               <li className="flex gap-2">
                  <CameraOff size={18} className="text-emerald-600 flex-shrink-0"/>
                  <span><strong>Camera giám sát:</strong> Hệ thống camera hoạt động 24/7 tại các khu vực chung (Sảnh, Hành lang, Bãi xe, Thu ngân). <span className="text-red-600 font-bold">*Tuyệt đối không lắp camera trong khu vực thay đồ và tắm.</span></span>
               </li>
                <li className="flex gap-2">
                  <Search size={18} className="text-emerald-600 flex-shrink-0"/>
                  <span><strong>Đồ thất lạc (Lost & Found):</strong> Tài sản khách bỏ quên phải được niêm phong, ghi vào sổ theo dõi và lưu kho trong vòng 30-90 ngày chờ khách nhận lại.</span>
               </li>
             </ul>
          </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">13.4. Báo cáo vấn đề cho Quản lý</h3>
            <div className="bg-white p-4 rounded border border-stone-200 shadow-sm">
               <h4 className="font-bold text-stone-800 flex items-center gap-2 mb-3">
                  <MessageSquare size={20}/> Nội dung báo cáo hàng ngày
               </h4>
               <ul className="list-disc pl-5 text-sm text-stone-700 space-y-2">
                  <li><strong>Sự cố Kỹ thuật:</strong> Báo cáo chi tiết các thiết bị hỏng hóc trong ngày, tình trạng đã sửa chữa hay đang chờ linh kiện.</li>
                  <li><strong>Tai nạn/Sự cố An toàn:</strong> Báo cáo mọi trường hợp tai nạn lao động hoặc sự cố sức khỏe của khách hàng (dù nhỏ nhất).</li>
                  <li><strong>An ninh trật tự:</strong> Ghi nhận các vụ việc gây rối, mất cắp hoặc nghi ngờ mất cắp để trích xuất camera.</li>
                  <li><strong>Tiêu hao vật tư sửa chữa:</strong> Báo cáo số lượng bóng đèn, vòi nước... đã thay thế trong ngày.</li>
               </ul>
            </div>
           </section>

           <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">13.5. Checklist Bảo trì Kỹ thuật (Maintenance Checklist)</h3>
            <p className="text-sm text-stone-500 italic mb-3">Nhân viên kỹ thuật thực hiện kiểm tra (Daily Inspection) toàn bộ hệ thống vận hành 2 lần/ngày.</p>
            
            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs md:text-sm">
                <thead className="bg-slate-100 text-slate-900 font-bold">
                  <tr>
                    <th className="p-3 text-left border-b w-[20%]">Hệ thống</th>
                    <th className="p-3 text-left border-b w-[40%]">Chi tiết kiểm tra</th>
                    <th className="p-3 text-center border-b w-[20%]">Đầu ca Sáng<br/><span className="text-[10px] font-normal">(07:30 - 08:30)</span></th>
                    <th className="p-3 text-center border-b w-[20%]">Đầu ca Chiều<br/><span className="text-[10px] font-normal">(14:00 - 15:00)</span></th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* 1. Điện & Ánh sáng */}
                  <tr>
                    <td className="p-3 font-bold text-slate-800 align-top" rowSpan="2">1. Điện & Ánh sáng</td>
                    <td className="p-3">
                        <strong>Tủ điện tổng:</strong> Các chỉ số (V, A) ổn định. Không có mùi khét, tiếng ồn lạ tại tủ điện.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Ghi log chỉ số</td>
                    <td className="p-3 text-center text-emerald-600">Ghi log chỉ số</td>
                  </tr>
                  <tr>
                    <td className="p-3">
                        <strong>Hệ thống đèn:</strong> Toàn bộ đèn chiếu sáng, đèn trang trí, đèn bảng hiệu hoạt động 100%. Thay thế ngay nếu cháy.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 2. Cấp nhiệt & Nước (HVAC + Plumbing) */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-slate-800 align-top" rowSpan="3">2. Nước & Nhiệt<br/><span className="text-[10px] font-normal">(Onsen/Sauna)</span></td>
                    <td className="p-3">
                        <strong>Heat Pump / Nồi hơi:</strong> Đạt nhiệt độ cài đặt (Nước nóng 50-60°C cấp cho hồ). Áp suất ổn định.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra áp suất</td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra áp suất</td>
                  </tr>
                  <tr className="bg-stone-50">
                    <td className="p-3">
                        <strong>Phòng Xông (Sauna):</strong> Máy xông ướt xả hơi đều. Máy xông khô đủ nhiệt. Đá xông xếp đúng cách, không vỡ vụn.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Test vận hành</td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra nhiệt</td>
                  </tr>
                  <tr className="bg-stone-50">
                     <td className="p-3">
                        <strong>Bơm & Lọc:</strong> Bơm chạy êm, không rò rỉ nước tại các khớp nối. Đồng hồ áp bình lọc ở mức xanh (an toàn).
                     </td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                     <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 3. An toàn & PCCC */}
                  <tr>
                    <td className="p-3 font-bold text-slate-800 align-top">3. An toàn & PCCC</td>
                    <td className="p-3">
                        - Tủ báo cháy trung tâm không báo lỗi.<br/>
                        - Đèn Exit/Sự cố sáng.<br/>
                        - Lối thoát hiểm thông thoáng, không bị chặn.<br/>
                        - Van Gas khóa (nếu không sử dụng) hoặc không rò rỉ.
                    </td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                    <td className="p-3 text-center text-emerald-600"><CheckCircle size={16} className="inline"/></td>
                  </tr>

                  {/* 4. Tiện ích khác */}
                  <tr className="bg-stone-50">
                    <td className="p-3 font-bold text-slate-800 align-top">4. Tiện ích chung</td>
                    <td className="p-3">
                        - <strong>Máy lạnh (AC):</strong> Hoạt động mát, không chảy nước, không kêu to.<br/>
                        - <strong>Wifi/Loa:</strong> Tín hiệu tốt, nhạc phát đều các khu vực.<br/>
                        - <strong>Locker:</strong> Khóa từ đóng/mở tốt.
                    </td>
                    <td className="p-3 text-center text-emerald-600">Kiểm tra</td>
                    <td className="p-3 text-center text-emerald-600">Xử lý sự cố</td>
                  </tr>
                </tbody>
              </table>
            </div>
           </section>
        </div>
      )
    },
    {
      id: 14,
      title: "Lương & Phúc lợi",
      icon: <Wallet size={20} />,
      content: (
        <div className="space-y-6 text-stone-800">
          <div className="bg-emerald-50 p-4 rounded-lg border border-emerald-100 mb-4">
             <h3 className="font-bold text-emerald-800 text-lg mb-2 flex items-center gap-2"><Info size={20}/> Chính sách đãi ngộ toàn diện (Total Rewards)</h3>
             <p className="text-sm text-emerald-900">Tại Carezone, chúng tôi xây dựng chính sách thu nhập cạnh tranh dựa trên năng lực và hiệu quả công việc, đi kèm với hệ thống phúc lợi chăm sóc sức khỏe độc đáo.</p>
          </div>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">14.1. Cấu trúc Thu nhập (Income Structure)</h3>
            <div className="grid md:grid-cols-2 gap-4 mb-4">
               <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm border-b pb-2 mb-2">Thu nhập cố định (Fixed)</h4>
                  <ul className="space-y-2 text-xs text-stone-700">
                     <li className="flex justify-between"><span>Lương cơ bản:</span> <span className="font-bold">Theo 3 bậc năng lực</span></li>
                     <li className="flex justify-between"><span>Phụ cấp gửi xe:</span> <span className="font-bold">Miễn phí</span></li>
                     <li className="flex justify-between"><span>Phụ cấp trách nhiệm:</span> <span className="font-bold">Tùy vị trí</span></li>
                  </ul>
               </div>
               <div className="bg-white p-4 rounded-lg border border-stone-200 shadow-sm">
                  <h4 className="font-bold text-stone-800 text-sm border-b pb-2 mb-2">Thu nhập biến đổi (Variable)</h4>
                  <ul className="space-y-2 text-xs text-stone-700">
                     <li className="flex justify-between"><span>Thưởng KPI/Doanh thu:</span> <span className="font-bold text-emerald-600">Theo % đạt được</span></li>
                     <li className="flex justify-between"><span>Tiền Tour (KTV):</span> <span className="font-bold text-emerald-600">Theo số lượng dịch vụ</span></li>
                     <li className="flex justify-between"><span>Tiền Tip (KTV):</span> <span className="font-bold text-emerald-600">100% thuộc về nhân viên</span></li>
                     <li className="flex justify-between"><span>Thưởng nóng:</span> <span className="font-bold text-emerald-600">Thành tích xuất sắc</span></li>
                  </ul>
               </div>
            </div>

            <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
              <table className="min-w-full text-xs">
                <thead className="bg-stone-100 text-stone-700 font-bold">
                  <tr>
                    <th rowSpan="2" className="p-2 text-left border-b align-middle w-[15%]">Vị trí</th>
                    <th colSpan="3" className="p-2 text-center border-b border-stone-300 w-[30%]">Lương Cứng (Triệu VNĐ)</th>
                    <th rowSpan="2" className="p-2 text-left border-b align-middle w-[35%]">Thu Nhập Biến Đổi<br/><span className="text-[9px] font-normal text-stone-500">(Các khoản thưởng thêm)</span></th>
                    <th rowSpan="2" className="p-2 text-right border-b align-middle bg-emerald-50 text-emerald-800 w-[20%]">Tổng Thu Nhập<br/><span className="text-[9px] font-normal">(Ước tính/tháng)</span></th>
                  </tr>
                  <tr>
                    <th className="p-2 text-center border-b bg-stone-50 text-[10px] text-stone-500">B1<br/>Junior</th>
                    <th className="p-2 text-center border-b bg-stone-50 text-[10px] text-stone-500 border-x border-stone-200">B2<br/>Senior</th>
                    <th className="p-2 text-center border-b bg-stone-50 text-[10px] text-stone-500">B3<br/>Master</th>
                  </tr>
                </thead>
                <tbody className="divide-y divide-stone-100">
                  {/* KTV Spa */}
                  <tr className="hover:bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top">KTV Spa</td>
                    <td className="p-3 text-center align-top">4.0</td>
                    <td className="p-3 text-center font-medium align-top border-x border-stone-100">5.5</td>
                    <td className="p-3 text-center font-bold align-top">7.0</td>
                    <td className="p-3 align-top">
                      <ul className="list-disc pl-4 space-y-1 text-[11px] text-stone-600">
                        <li><strong>Tiền Tip:</strong> Hưởng 100%.</li>
                        <li><strong>Hoa hồng:</strong> % Bán mỹ phẩm/Thẻ.</li>
                      </ul>
                    </td>
                    <td className="p-3 text-right font-bold text-base text-emerald-600 bg-emerald-50 align-top">15 - 30 Tr</td>
                  </tr>
                  
                  {/* Lễ tân */}
                  <tr className="hover:bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top">Lễ tân / CSKH</td>
                    <td className="p-3 text-center align-top">7.0</td>
                    <td className="p-3 text-center font-medium align-top border-x border-stone-100">8.0</td>
                    <td className="p-3 text-center font-bold align-top">9.0</td>
                    <td className="p-3 align-top">
                      <ul className="list-disc pl-4 space-y-1 text-[11px] text-stone-600">
                        <li><strong>Doanh thu:</strong> Thưởng % Team & Cá nhân.</li>
                        <li><strong>Voucher:</strong> Thưởng bán vé/thẻ hội viên.</li>
                        <li><strong>CSI:</strong> Thưởng đánh giá 5 sao.</li>
                      </ul>
                    </td>
                    <td className="p-3 text-right font-bold text-base text-emerald-600 bg-emerald-50 align-top">9 - 12 Tr</td>
                  </tr>

                  {/* Bếp */}
                  <tr className="hover:bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top">Bếp (Kitchen)</td>
                    <td className="p-3 text-center align-top">8.0</td>
                    <td className="p-3 text-center font-medium align-top border-x border-stone-100">11.0</td>
                    <td className="p-3 text-center font-bold align-top">14.0</td>
                    <td className="p-3 align-top">
                      <ul className="list-disc pl-4 space-y-1 text-[11px] text-stone-600">
                        <li><strong>Service Charge:</strong> Phí phục vụ.</li>
                        <li><strong>Food Cost:</strong> Thưởng tiết kiệm nguyên liệu.</li>
                        <li><strong>Món mới:</strong> Thưởng sáng tạo món.</li>
                      </ul>
                    </td>
                    <td className="p-3 text-right font-bold text-base text-emerald-600 bg-emerald-50 align-top">10 - 18 Tr</td>
                  </tr>

                  {/* Phục vụ */}
                  <tr className="hover:bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top">Phục vụ (Service)</td>
                    <td className="p-3 text-center align-top">6.0</td>
                    <td className="p-3 text-center font-medium align-top border-x border-stone-100">7.0</td>
                    <td className="p-3 text-center font-bold align-top">8.0</td>
                    <td className="p-3 align-top">
                      <ul className="list-disc pl-4 space-y-1 text-[11px] text-stone-600">
                        <li><strong>Service Charge:</strong> Phí phục vụ.</li>
                        <li><strong>Upsell:</strong> Thưởng bán thêm món/nước.</li>
                        <li><strong>Tiền Tip:</strong> Hưởng 100% tip bàn.</li>
                      </ul>
                    </td>
                    <td className="p-3 text-right font-bold text-base text-emerald-600 bg-emerald-50 align-top">8 - 11 Tr</td>
                  </tr>

                  {/* Tạp vụ / Bảo vệ */}
                  <tr className="hover:bg-stone-50">
                    <td className="p-3 font-bold text-emerald-800 align-top">Tạp vụ / Bảo vệ</td>
                    <td className="p-3 text-center align-top">6.0</td>
                    <td className="p-3 text-center font-medium align-top border-x border-stone-100">7.0</td>
                    <td className="p-3 text-center font-bold align-top">8.0</td>
                    <td className="p-3 align-top">
                      <ul className="list-disc pl-4 space-y-1 text-[11px] text-stone-600">
                        <li><strong>Chuyên cần:</strong> Thưởng đi làm đầy đủ.</li>
                        <li><strong>OT:</strong> Lương làm thêm giờ.</li>
                        <li><strong>Thưởng:</strong> Lễ/Tết/Tháng 13.</li>
                      </ul>
                    </td>
                    <td className="p-3 text-right font-bold text-base text-emerald-600 bg-emerald-50 align-top">7 - 10 Tr</td>
                  </tr>
                </tbody>
              </table>
              <p className="p-2 text-[10px] text-stone-500 italic bg-stone-50 text-right">* Đơn vị Lương cứng: Triệu VNĐ. Tổng thu nhập là ước tính thực tế.</p>
            </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">14.2. Phúc lợi Đặc biệt (Carezone Benefits)</h3>
             <div className="grid md:grid-cols-2 gap-3">
               <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex items-start gap-3">
                 <div className="bg-white p-2 rounded-full text-emerald-600 shadow-sm"><Heart size={20}/></div>
                 <div>
                    <strong className="block text-sm text-emerald-900">Wellness Day</strong>
                    <p className="text-xs text-stone-600">Miễn phí 01 vé Onsen & Jjimjilbang mỗi tháng cho nhân viên để trải nghiệm và thư giãn.</p>
                 </div>
               </div>
                <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex items-start gap-3">
                 <div className="bg-white p-2 rounded-full text-emerald-600 shadow-sm"><GraduationCap size={20}/></div>
                 <div>
                    <strong className="block text-sm text-emerald-900">Đào tạo & Phát triển</strong>
                    <p className="text-xs text-stone-600">Được đào tạo nghề Spa, kỹ năng mềm và tiếng Anh giao tiếp miễn phí.</p>
                 </div>
               </div>
                <div className="bg-emerald-50 p-3 rounded border border-emerald-100 flex items-start gap-3">
                 <div className="bg-white p-2 rounded-full text-emerald-600 shadow-sm"><Briefcase size={20}/></div>
                 <div>
                    <strong className="block text-sm text-emerald-900">An cư Lạc nghiệp</strong>
                    <p className="text-xs text-stone-600">Hỗ trợ chỗ ở tại Ký túc xá (KTX) đầy đủ tiện nghi cho nhân viên ở xa.</p>
                 </div>
               </div>
             </div>
             <div className="mt-4 p-3 bg-orange-50 border border-orange-200 rounded-lg text-sm text-orange-900 flex items-center gap-2 font-medium shadow-sm">
               <Star size={16} className="fill-orange-500 text-orange-500 flex-shrink-0" />
               <span>Ngoài ra còn có các phúc lợi theo luật lao động: <strong>BHXH, BHYT, BHTN, 12 ngày phép năm, thưởng Lễ/Tết/Sinh nhật/Hiếu hỉ.</strong></span>
             </div>
          </section>

          <section>
            <h3 className="text-xl font-bold text-emerald-700 mb-3">14.3. Lộ trình Thăng tiến (Career Path)</h3>
            <div className="relative pl-4 border-l-2 border-emerald-200 space-y-6 py-2">
               
               <div className="relative pl-6">
                  <div className="absolute -left-[21px] top-0 bg-emerald-100 w-10 h-10 rounded-full border-4 border-white flex items-center justify-center text-emerald-700 font-bold text-xs">1</div>
                  <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                     <h4 className="font-bold text-stone-800 text-sm">Nhân viên Tập sự / Học việc</h4>
                     <p className="text-xs text-stone-500">0 - 2 tháng đầu. Học quy trình, văn hóa và kỹ năng cơ bản. Hưởng 85% lương Bậc 1.</p>
                  </div>
               </div>

               <div className="relative pl-6">
                  <div className="absolute -left-[21px] top-0 bg-emerald-200 w-10 h-10 rounded-full border-4 border-white flex items-center justify-center text-emerald-800 font-bold text-xs">2</div>
                  <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                     <h4 className="font-bold text-stone-800 text-sm mb-2">Nhân viên Chính thức (Staff)</h4>
                     <div className="text-xs text-stone-600 space-y-3">
                        <div className="flex items-start gap-3 p-2 bg-stone-50 rounded border border-stone-100">
                           <div className="bg-stone-200 text-stone-600 font-bold px-2 py-1 rounded text-[10px] w-16 text-center mt-0.5">BẬC 1<br/>Junior</div>
                           <div>
                              <strong>Điều kiện:</strong> Vừa ký HĐLĐ chính thức.<br/>
                              <strong>Quyền lợi:</strong> Hưởng mức <em>Lương Cứng Bậc 1</em> theo bảng 14.1.
                           </div>
                        </div>
                        <div className="flex items-start gap-3 p-2 bg-emerald-50 rounded border border-emerald-100">
                           <div className="bg-emerald-200 text-emerald-800 font-bold px-2 py-1 rounded text-[10px] w-16 text-center mt-0.5">BẬC 2<br/>Senior</div>
                           <div>
                              <strong>Điều kiện:</strong> Thâm niên {'>'} 6 tháng, đạt KPI 2 quý liên tiếp, không vi phạm kỷ luật.<br/>
                              <strong>Quyền lợi:</strong> Tăng lên mức <em>Lương Cứng Bậc 2</em>. Được ưu tiên xếp ca đẹp.
                           </div>
                        </div>
                        <div className="flex items-start gap-3 p-2 bg-emerald-100 rounded border border-emerald-200">
                           <div className="bg-emerald-600 text-white font-bold px-2 py-1 rounded text-[10px] w-16 text-center mt-0.5">BẬC 3<br/>Master</div>
                           <div>
                              <strong>Điều kiện:</strong> Thâm niên {'>'} 12 tháng, kỹ năng xuất sắc, có khả năng đào tạo người mới (Mentor).<br/>
                              <strong>Quyền lợi:</strong> Tăng lên mức <em>Lương Cứng Bậc 3</em>. Được đề xuất thi tuyển lên Leader.
                           </div>
                        </div>
                     </div>
                  </div>
               </div>

               <div className="relative pl-6">
                  <div className="absolute -left-[21px] top-0 bg-emerald-400 w-10 h-10 rounded-full border-4 border-white flex items-center justify-center text-emerald-900 font-bold text-xs">3</div>
                  <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                     <h4 className="font-bold text-stone-800 text-sm mb-2">Chuyên viên / Trưởng nhóm (Team Leader)</h4>
                     <div className="text-xs text-stone-600 space-y-2">
                        <p><strong>Yêu cầu:</strong> Đạt Bậc 3 (Master) và vượt qua kỳ thi đánh giá năng lực quản lý.</p>
                        <div className="bg-emerald-50 p-2 rounded border border-emerald-100">
                           <div className="flex justify-between mb-1">
                              <span>Lương cơ bản:</span>
                              <span className="font-bold">Thỏa thuận (Cao hơn Bậc 3)</span>
                           </div>
                           <div className="flex justify-between">
                              <span>Phụ cấp trách nhiệm:</span>
                              <span className="font-bold text-emerald-700">1.000.000đ - 3.000.000đ</span>
                           </div>
                        </div>
                     </div>
                  </div>
               </div>

               <div className="relative pl-6">
                  <div className="absolute -left-[21px] top-0 bg-emerald-600 w-10 h-10 rounded-full border-4 border-white flex items-center justify-center text-white font-bold text-xs">4</div>
                  <div className="bg-white p-3 rounded border border-stone-200 shadow-sm">
                     <h4 className="font-bold text-stone-800 text-sm mb-2">Quản lý / Giám sát (Manager/Supervisor)</h4>
                     <div className="text-xs text-stone-600">
                        <p className="mb-2">Quản lý vận hành bộ phận. Tham gia vào việc ra quyết định và chiến lược.</p>
                        <div className="bg-emerald-600 p-2 rounded border border-emerald-700 text-white font-medium text-center shadow-sm">
                           Lương thỏa thuận + Thưởng Lợi nhuận (Profit Sharing) + ESOP
                        </div>
                     </div>
                  </div>
               </div>

            </div>
          </section>
        </div>
      )
    },
    {
      id: 15,
      title: "KPI & Báo cáo",
      icon: <BarChart size={20} />,
      content: (
         <div className="space-y-6 text-stone-800">
           <section>
             <h3 className="text-xl font-bold text-emerald-700 mb-3">15.1. Hệ thống Báo cáo (Reporting)</h3>
             <p className="text-sm text-stone-500 italic mb-3">Quy định chi tiết về chế độ báo cáo để đảm bảo thông tin vận hành được thông suốt.</p>
             
             <div className="space-y-4">
               {/* Báo cáo Ngày */}
               <div className="bg-white rounded-lg border border-stone-200 shadow-sm overflow-hidden">
                  <div className="bg-stone-100 px-4 py-2 font-bold text-stone-700 text-sm border-b border-stone-200 flex justify-between items-center">
                    <span>1. Báo cáo Ngày (Daily)</span>
                    <span className="text-xs font-normal bg-white px-2 py-0.5 rounded border border-stone-300">Deadline: Trước 23:00</span>
                  </div>
                  <div className="p-4 grid gap-4 sm:grid-cols-2">
                     <div className="space-y-2">
                        <strong className="text-emerald-800 text-xs uppercase block border-b border-emerald-100 pb-1">Bộ phận Thu ngân</strong>
                        <ul className="list-disc pl-4 text-xs text-stone-600 space-y-1">
                           <li><strong>Chốt ca (Z-Report):</strong> Tổng doanh thu tiền mặt, thẻ, chuyển khoản.</li>
                           <li><strong>Kiểm quỹ:</strong> Số dư đầu kỳ, cuối kỳ, chênh lệch (nếu có).</li>
                           <li><strong>Chứng từ:</strong> Nộp lại toàn bộ bill hủy, bill giảm giá có chữ ký xác nhận.</li>
                        </ul>
                     </div>
                     <div className="space-y-2">
                        <strong className="text-emerald-800 text-xs uppercase block border-b border-emerald-100 pb-1">Bộ phận Lễ tân / CSKH</strong>
                        <ul className="list-disc pl-4 text-xs text-stone-600 space-y-1">
                           <li><strong>Lượng khách (Pax):</strong> Tổng khách, chia theo khung giờ và loại khách (Vãng lai/Member).</li>
                           <li><strong>VOC (Voice of Customer):</strong> Tổng hợp các phàn nàn hoặc lời khen trong ngày.</li>
                        </ul>
                     </div>
                     <div className="space-y-2">
                        <strong className="text-emerald-800 text-xs uppercase block border-b border-emerald-100 pb-1">Bộ phận Spa & Massage</strong>
                        <ul className="list-disc pl-4 text-xs text-stone-600 space-y-1">
                           <li><strong>Tiêu hao (Consumables):</strong> Báo cáo lượng dầu massage, khăn, đá nóng đã sử dụng.</li>
                           <li><strong>Chất lượng KTV:</strong> Ghi nhận sự cố về kỹ thuật hoặc thái độ (nếu có khách phàn nàn).</li>
                        </ul>
                     </div>
                     <div className="space-y-2">
                        <strong className="text-emerald-800 text-xs uppercase block border-b border-emerald-100 pb-1">Bộ phận Nhà hàng (Bếp)</strong>
                        <ul className="list-disc pl-4 text-xs text-stone-600 space-y-1">
                           <li><strong>Hàng hỏng (Spoilage):</strong> Số lượng nguyên liệu hư hỏng phải đổ bỏ và lý do.</li>
                           <li><strong>Món trả lại (Void):</strong> Số lượng món khách từ chối nhận do lỗi chế biến (mặn/nguội/có dị vật).</li>
                        </ul>
                     </div>
                     <div className="space-y-2 sm:col-span-2">
                        <strong className="text-emerald-800 text-xs uppercase block border-b border-emerald-100 pb-1">Bộ phận Kỹ thuật</strong>
                        <ul className="list-disc pl-4 text-xs text-stone-600 space-y-1">
                           <li><strong>Chỉ số nước:</strong> pH, Clo, Nhiệt độ hồ (đo 3 lần/ngày).</li>
                           <li><strong>Sự cố:</strong> Các thiết bị hỏng hóc phát sinh và tình trạng xử lý.</li>
                        </ul>
                     </div>
                  </div>
               </div>

               {/* Báo cáo Tuần & Tháng */}
               <div className="grid sm:grid-cols-2 gap-4">
                  <div className="bg-white rounded-lg border border-stone-200 shadow-sm p-4">
                     <div className="font-bold text-stone-700 text-sm mb-2 flex justify-between">
                        <span>2. Báo cáo Tuần (Weekly)</span>
                        <span className="text-[10px] text-stone-400">Thứ 2 hàng tuần</span>
                     </div>
                     <ul className="list-disc pl-4 text-xs text-stone-600 space-y-2">
                        <li><strong>Quản lý bộ phận:</strong> Gửi lịch làm việc (Roster) tuần tới. Đề xuất đặt hàng vật tư.</li>
                        <li><strong>Kế toán:</strong> Báo cáo công nợ nhà cung cấp, tồn kho thực tế (kiểm kê xác suất).</li>
                     </ul>
                  </div>
                  <div className="bg-white rounded-lg border border-stone-200 shadow-sm p-4">
                     <div className="font-bold text-stone-700 text-sm mb-2 flex justify-between">
                        <span>3. Báo cáo Tháng (Monthly)</span>
                        <span className="text-[10px] text-stone-400">Ngày 01-05</span>
                     </div>
                     <ul className="list-disc pl-4 text-xs text-stone-600 space-y-2">
                        <li><strong>Kiểm kê toàn phần:</strong> Tài sản cố định & CCDC.</li>
                        <li><strong>HCNS:</strong> Bảng chấm công, tính lương, biến động nhân sự.</li>
                        <li><strong>Giám đốc:</strong> Báo cáo P&L (Lời lỗ), Phân tích hiệu quả kinh doanh.</li>
                     </ul>
                  </div>
               </div>
             </div>
           </section>

           <section>
             <h3 className="text-xl font-bold text-emerald-700 mb-3">15.2. KPI Trọng tâm theo Bộ phận</h3>
             <p className="text-sm text-stone-500 italic mb-3">Các chỉ số chính dùng để tính thưởng và đánh giá năng lực hàng tháng.</p>
             
             <div className="overflow-x-auto bg-white rounded-lg border border-stone-200 shadow-sm">
                <table className="min-w-full text-sm text-left">
                   <thead className="bg-emerald-50 text-emerald-800 font-bold uppercase text-xs">
                      <tr>
                         <th className="p-3 border-b">Bộ phận</th>
                         <th className="p-3 border-b">KPI Chính (Tính thưởng)</th>
                         <th className="p-3 border-b">Chỉ số Theo dõi (Kỷ luật)</th>
                      </tr>
                   </thead>
                   <tbody className="divide-y divide-stone-100 text-stone-700">
                      <tr>
                         <td className="p-3 font-bold">Lễ tân / Sales</td>
                         <td className="p-3">
                            <ul className="list-disc pl-4 space-y-1 text-xs">
                               <li><strong>Doanh thu:</strong> % đạt chỉ tiêu cá nhân/team.</li>
                               <li><strong>Bán thẻ:</strong> Số lượng Membership bán được.</li>
                            </ul>
                         </td>
                         <td className="p-3 text-xs">Tỷ lệ khách phàn nàn, Sai sót tiền nong.</td>
                      </tr>
                      <tr>
                         <td className="p-3 font-bold">KTV Spa</td>
                         <td className="p-3">
                            <ul className="list-disc pl-4 space-y-1 text-xs">
                               <li><strong>Năng suất:</strong> Tổng số Tour (giờ làm).</li>
                               <li><strong>Đánh giá:</strong> Điểm sao (Star rating) từ khách.</li>
                               <li><strong>Bán hàng:</strong> Doanh thu mỹ phẩm.</li>
                            </ul>
                         </td>
                         <td className="p-3 text-xs">Vi phạm quy trình, Đi muộn/Về sớm.</td>
                      </tr>
                      <tr>
                         <td className="p-3 font-bold">Bếp / Bar</td>
                         <td className="p-3">
                            <ul className="list-disc pl-4 space-y-1 text-xs">
                               <li><strong>Food Cost:</strong> Tỷ lệ hao hụt nguyên liệu.</li>
                               <li><strong>Tốc độ:</strong> Thời gian ra món trung bình.</li>
                            </ul>
                         </td>
                         <td className="p-3 text-xs">Vệ sinh ATTP, Số món bị trả lại.</td>
                      </tr>
                      <tr>
                         <td className="p-3 font-bold">Phục vụ</td>
                         <td className="p-3">
                            <ul className="list-disc pl-4 space-y-1 text-xs">
                               <li><strong>Upsell:</strong> Doanh thu bán thêm tại bàn.</li>
                               <li><strong>Hài lòng:</strong> Điểm đánh giá thái độ.</li>
                            </ul>
                         </td>
                         <td className="p-3 text-xs">Vỡ/Hỏng đồ, Sai order.</td>
                      </tr>
                      <tr>
                         <td className="p-3 font-bold">Tạp vụ / Bảo vệ</td>
                         <td className="p-3">
                            <ul className="list-disc pl-4 space-y-1 text-xs">
                               <li><strong>Hiệu quả:</strong> Điểm chấm chéo (Sạch sẽ/An toàn).</li>
                               <li><strong>Chuyên cần:</strong> Đảm bảo ngày công.</li>
                            </ul>
                         </td>
                         <td className="p-3 text-xs">Thái độ, Mất mát tài sản.</td>
                      </tr>
                   </tbody>
                </table>
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
