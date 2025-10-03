const iframe = document.createElement('iframe')
document.body.appendChild(iframe)
const originalConsole = iframe.contentWindow.console;

// Vô hiệu hóa các phương thức log của originalConsole để không hiển thị gì trong console
const noOp = () => {}; // Hàm không làm gì cả
const consoleMethodsToDisable = [
    'log', 'info', 'warn', 'error', 'debug', 'trace', 'dir', 'dirxml',
    'group', 'groupCollapsed', 'groupEnd', 'time', 'timeEnd', 'timeLog',
    'assert', 'clear', 'count', 'countReset', 'table', 'profile', 'profileEnd'
];
consoleMethodsToDisable.forEach(method => {
    if (typeof originalConsole[method] === 'function') {
        originalConsole[method] = noOp;
    }
});

const DOMAIN = 'https://hoathinh3d.gg'
const ACTION_URL = DOMAIN + '/wp-json/hh3d/v1/action'
const HH3D_AJAX_URL = DOMAIN + '/wp-content/themes/halimmovies-child/hh3d-ajax.php'
const ADMIN_AJAX_URL = DOMAIN + '/wp-admin/admin-ajax.php'
const LUANVO_URL = DOMAIN + '/wp-json/luan-vo/v1'
const TONGMON_URL = DOMAIN + '/wp-json/tong-mon/v1'
const LOTTERY_URL = DOMAIN + '/wp-json/lottery/v1'

const blessingMessages = [
    "🌠 Thiên duyên vạn kiếp, hội ngộ giữa hồng trần! Nguyện hai vị đạo hữu đồng tâm tu luyện, phi thăng cửu thiên, trường tồn cùng nhật nguyệt! ✨",
    "🌸 Duyên khởi từ tâm, đạo hợp bởi ý! Chúc hai vị đạo hữu đồng hành bất diệt, như gió xuân thổi mãi, như sóng biếc vỗ hoài! 🌊",
    "⚡️ Một bước nhập đạo, vạn kiếp thành tiên! Nguyện hai vị đạo hữu nắm tay tu luyện, phá vỡ thiên kiếp, cùng nhau phi thăng bất diệt! 🕊️",
    "🌟 Hữu duyên thiên định, nguyệt lão chỉ đường! Nguyện đạo lữ vững bền, đồng tâm hợp lực, trường tồn giữa trời đất bao la! 💞",
    "🌿 Trải qua ngàn kiếp luân hồi, cuối cùng tương ngộ! Nguyện hai vị đạo hữu tâm ý tương thông, đồng tu đồng tiến, chứng đắc đại đạo! ⚔️",
    "🏯 Đạo tình như trăng sáng, chiếu rọi mãi không phai! Chúc hai vị đạo hữu tu hành viên mãn, bước lên đài sen, hóa thành chân tiên! 🏹",
    "🌺 Nhân sinh hữu hẹn, tu hành hữu duyên! Nguyện hai vị đạo hữu song tu hòa hợp, cùng nhau vượt thiên địa, lưu danh bất hủ! 🏔️",
    "✨ Một ánh mắt giao hòa, vạn năm chẳng đổi! Nguyện hai vị đạo hữu đồng tâm song tiến, đạo nghiệp rạng rỡ, tu thành chính quả! 🚀",
    "🔥 Đạo tâm kiên định, tay nắm chặt chẳng rời! Chúc hai vị đạo hữu vượt qua muôn vàn thử thách, cùng nhau đăng đỉnh cửu thiên! 🌈",
    "🌌 Định mệnh an bài, thiên địa chứng giám! Nguyện hai vị đạo hữu tu luyện đại thành, nắm giữ chân lý, mãi mãi bên nhau! 🏆"
]

const blessingGifts = {
    "25623": [
        { friend_id: "30833", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "27677", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "74039", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "84629", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "13341", cost_type: "tien_ngoc", max: 3 } 
    ],
    "58779": [
        { friend_id: "42685", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "31398", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "9285", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "27677", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "74039", cost_type: "tien_ngoc", max: 3 }
    ],
    "42685": [
        { friend_id: "58779", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "51269", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "49213", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "69959", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "27677", cost_type: "tien_ngoc", max: 3 }
    ], 
    "28446": [
        { friend_id: "45315", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "97859", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "36199", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "30431", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "8111", cost_type: "tien_ngoc", max: 3 }
    ],
    "45315": [
        { friend_id: "28446", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "15618", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "24649", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "12767", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "74039", cost_type: "tien_ngoc", max: 3 }
    ], 
    "42362": [
        { friend_id: "1", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "43936", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "58714", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "58779", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "74039", cost_type: "tien_ngoc", max: 3 }
    ],  
    "82684": [
        { friend_id: "76165", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "38702", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "98562", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "84629", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "84632", cost_type: "tien_ngoc", max: 3 }
    ],    
    "84632": [
        { friend_id: "82684", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "29839", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "25623", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "27677", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "26577", cost_type: "tien_ngoc", max: 3 }
    ],     
    "84629": [
        { friend_id: "59007", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "82684", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "25623", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "35811", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "29839", cost_type: "tien_ngoc", max: 3 }
    ],      
    "19024": [
        { friend_id: "16066", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "18505", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "30431", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "25394", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "29606", cost_type: "tien_ngoc", max: 3 }
    ],    
    "59007": [
        { friend_id: "56110", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "45315", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "84629", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "145285", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "84787", cost_type: "tien_ngoc", max: 3 }
    ],    
    "145285": [
        { friend_id: "127286", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "19024", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "59007", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "34690", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "92722", cost_type: "tien_ngoc", max: 3 }
    ],  
    "28402": [
        { friend_id: "35811", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "9285", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "31981", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "50262", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "31398", cost_type: "tien_ngoc", max: 3 }
    ],   
    "26094": [
        { friend_id: "31398", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "28402", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "9285", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "50262", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "35811", cost_type: "tien_ngoc", max: 3 }
    ],       
    "35811": [
        { friend_id: "27677", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "28402", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "31157", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "74039", cost_type: "tien_ngoc", max: 3 },
        { friend_id: "52491", cost_type: "tien_ngoc", max: 3 }
    ],                                
}

const bossSkipChangeIds = ["65075", "41911", "25967", "50023", "38803", "17231", "35951", "34918", "25903", "18530", "32606", "68556", "84787", "85939"]

const quizBank = {
    "Ai là huynh đệ và cũng là người thầy mà Vương Lâm trong Tiên Nghịch kính trọng nhất ?": "Tư Đồ Nam",
    "Ai là mẹ của Đường Tam?": "A Ngân",
    "Ai là người đứng đầu Vũ Hồn Điện?": "Bỉ Bỉ Đông",
    "Ai là người thầy của Đường Tam?": "Đại Sư",
    "Ai là nhân vật chính trong bộ phim hoạt hình trung quốc Thần Mộ ?": "Thần Nam",
    "Ám tinh giới được xuất hiện trong bộ phim hoạt hình nào dưới đây ?": "Tinh Thần Biến",
    "Bách Lý Đông Quân là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Thiếu Niên Bạch Mã Tuý Xuân Phong",
    "Bạch Nguyệt Khôi là tên nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Linh Lung",
    "Bạch Tiểu Thuần là nhân vật chính trong bộ hoạt hình trung quốc nào ?": "Nhất Niệm Vĩnh Hằng",
    "Bạch Tiểu Thuần trong Nhất Niệm Vĩnh Hằng luôn được ai âm thầm giúp đỡ ?": "Đỗ Lăng Phỉ",
    "Bộ phim nào sau đây thuộc tiểu thuyết của tác giả Thiên Tằm Thổ Đậu": "Tất cả đáp án",
    "Các cấp bậc nào sau đây thuộc phim Đấu Phá Thương Khung ?": "Đấu Tông",
    "Cháu dượng của Bạch Tiểu Thuần trong Nhất Niệm Vĩnh Hằng là ai ?": "Tống Khuyết",
    "Chủ nhân đời trước của Vẫn Lạc Tâm Viêm trong Đấu Phá Thương Khung là ai ?": "Diệu Thiên Hoả",
    "Công pháp gì giúp Tiêu Viêm trong Đấu Phá Thương Khung hấp thụ nhiều loại dị hỏa ?": "Phần Quyết",
    "Công pháp nào sau đây là của Hàn Lập trong Phàm Nhân Tu Tiên ?": "Tất cả đáp án",
    "Cơ Tử Nguyệt là nhân vật trong các bộ hoạt hình trung quốc nào sau đây ?": "Già Thiên",
    "Dạ Táng còn là biệt danh của ai trong Nhất Niệm Vĩnh Hằng ?": "Bạch Tiểu Thuần",
    "Danh xưng Tàn Thi Bại Thuế là của nhân vật nào trong Hoạ Giang Hồ Chi Bất Lương Nhân ?": "Hàng Thần",
    "Diễm Linh Cơ là nhân vật trong phim hoạt hình trung quốc nào ?": "Thiên Hành Cửu Ca",
    "Diệp Phàm là nhân vật chính trong bộ hoạt hình trung quốc nào ?": "Già Thiên",
    "Diệp Thần trong Tiên Võ Đế Tôn gia nhập Tông Môn nào đầu tiên ?": "Chính Dương Tông",
    "Dược Trần trong Đấu Phá Thương Khung đã từng bị đồ đệ nào phản bội ?": "Hàn Phong",
    "Đại ca của Tiêu Viêm trong Đấu Phá Thương Khung tên gì ?": "Tiêu Đỉnh",
    "Đàm Vân là nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Nghịch Thiên Chí Tôn",
    "Đạo lữ của Hàn Lập là ai ?": "Nam Cung Uyển",
    "Đâu là nhân vật chính trong phim Bách Luyện Thành Thần ?": "La Chinh",
    "Đâu là Thái Cổ Thập Hung trong phim Thế Giới Hoàn Mỹ ?": "Tất cả đáp án",
    "Đâu là tuyệt kỹ số 1 Hạo Thiên Tông mà Đường Hạo dạy cho con trai trong Đấu La Đại Lục ?": "Đại Tu Di Chùy",
    "Đấu Sát Toàn Viên Kiếm là một kỹ năng trong bộ phim hoạt hình trung quốc nào ?": "Thần Ấn Vương Tọa",
    "Độc Cô Bác trong Đấu La Đại Lục có vũ hồn gì ?": "Bích Lân Xà",
    "Em trai ruột của Thạch Hạo trong Thế Giới Hoàn Mỹ là ai ?": "Tần Hạo",
    "Hàn lập sở hữu những vật phẩm nào dưới đây ?": "Thanh Trúc Phong Vân Kiếm",
    "Hàn Lập trong Phàm Nhân Tu Tiên đến Thất Huyền Môn bái ai làm thầy ?": "Mặc Đại Phu",
    "Hàn Lập trong Phàm Nhân Tu Tiên gia nhập môn phái nào đầu tiên ?": "Thất Huyền Môn",
    "Hàn Lập trong Phàm Nhân Tu Tiên từng cứu ai mà bị hấp thụ tu vi giảm xuống Luyện Khí Kỳ ?": "Nam Cung Uyển",
    "Hoang Thiên Đế là nhân vật chính trong bộ phim hoạt hình trung quốc nổi tiếng nào ?": "Thế Giới Hoàn Mỹ",
    "Hoắc Vũ Hạo là hậu nhân của ai trong Sử Lai Khắc ?": "Đái Mộc Bạch",
    "Hồn hoàn màu nào mạnh nhất?": "Đỏ",
    "Huân Nhi là công chúa của bộ tộc nào?": "Cổ tộc",
    "Khô Lâu Đà Chủ xuất hiện trong bộ phim hoạt hình nào dưới đây ?": "Võ Thần Chúa Tể",
    "Khi ở Già Nam Học Viện, Tiêu Viêm thu phục được loại dị hỏa nào ?": "Vẫn Lạc Tâm Viêm",
    "Kính Huyền trong Quyến Tư Lượng là hậu duệ của tộc nào ?": "Thần Tộc",
    "Lạc Ly trong Đại Chúa Tể là nhân vật trong Tộc nào ?": "Lạc Thần Tộc",
    "Lâm Động trong Vũ Động Càn Khôn học được Linh Võ Học nào khi vào bia cổ Đại Hoang ?": "Đại Hoang Tù Thiên Chỉ",
    "Lâm Động trong Vũ Động Càn Khôn luyện hóa Tổ Phù nào đầu tiên ?": "Thôn Phệ Tổ Phù",
    "Lâm Động trong Vũ Động Càn Khôn sử dụng vũ khí loại nào sau đây ?": "Thương",
    "Lâm Phong là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Vạn Giới Độc Tôn",
    "Lâm Thất Dạ là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Trảm Thần",
    "Lâm Thất Dạ trong Trảm Thần sở hữu sức mạnh của vị thần nào ?": "Thiên Sứ",
    "Long Tuyền Kiếm xuất hiện trong bộ phim hoạt hình nào dưới đây ?": "Họa Giang Hồ Chi Bất Lương Nhân",
    "Lục Tuyết Kỳ trong Tru Tiên thuộc Phong nào trong Thanh Vân Môn?": "Tiểu Trúc Phong",
    "Lý Tinh Vân trong Họa Giang Hồ Chi Bất Lương Nhân sử dụng vũ khí nào sau đây ?": "Long Tuyền Kiếm",
    "Lý Tinh Vân là một nhân vật trong bộ phim hoạt hình trung quốc nào sau đây ?": "Họa Giang Hồ Chi Bất Lương Nhân",
    "Lý Trường Thọ trong Sư Huynh A Sư Huynh xuyên không về Hồng Hoang bái sư ở đâu ?": "Độ Tiên Môn",
    "Man Hồ Tử trong phim \"Phàm Nhân Tu Tiên\" tu luyện công pháp nào?": "Thác Thiên Ma Công",
    "Mẫu thân của La Phong trong Thôn Phệ Tinh Không tên là gì ?": "Cung Tâm Lan",
    "Mẹ của Mạnh Xuyên trong Thương Nguyên Đồ tên là gì ?": "Bạch Niệm Vân",
    "Mẹ của Tần Trần là ai ?": "Tần Nguyệt Trì",
    "Mẹ của Thạch Hạo trong Thế Giới Hoàn Mỹ tên là gì": "Tần Di Ninh",
    "Mối tình đầu của Diệp Thần trong Tiên Võ Đế Tôn là ai ?": "Cơ Ngưng Sương",
    "Mục đích chính tu luyện của Tần Vũ trong Tinh Thần Biến là gì ??": "Vì muốn được cưới Khương Lập",
    "Mục đích tu luyện của Vương Lâm trong Tiên Nghịch theo diễn biến phim hiện tại là gì ?": "Báo Thù",
    "Mục Trần trong Đại Chúa Tể liên kết Huyết Mạch với ?": "Cửu U Tước",
    "Mục Vân là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Vô Thượng Thần Đế",
    "Nam chính trong bộ hoạt hình trung quốc Ám Hà Truyện là ai ?": "Tô Mộ Vũ",
    "Nam chính trong bộ Quyến Tư Lượng là ai ?": "Kính Huyền",
    "Nghịch Hà Tông là Tông Môn trong bộ hoạt hình trung quốc nào sau đây ?": "Nhất Niệm Vĩnh Hằng",
    "Nghịch Thiên Nhi Hành là một nhân vật trong bộ phim hh3d nào sau đây ?": "Vũ Canh Kỷ",
    "Ngụy Anh (Ngụy Vô Tiện) là nhân vật trong bộ hhtq nào sau đây ?": "Ma Đạo Tổ Sư",
    "Người bạn thuở nhỏ của Trương Tiểu Phàm trong Tru Tiên là ai ?": "Lâm Kinh Vũ",
    "Nhân vật Bách Lý Đồ Minh xuất hiện trong phim hoạt hình nào dưới đây ?": "Trảm Thần Chi Phàm Trần Thần Vực",
    "Nhân vật chính của \"Thần Ấn Vương Tọa\" là ai?": "Long Hạo Thần",
    "Nhân vật chính của Đấu La Đại Lục là ai?": "Đường Tam",
    "Nhân vật chính Lý Trường Thọ trong Sư Huynh A Sư Huynh đã tỏ tình với ai ?": "Vân Tiêu",
    "Nhân vật chính trong Thương Nguyên đồ là ai ?": "Mạnh Xuyên",
    "Nhân vật chính trong Yêu Thần Ký tên là gì ?": "Nhiếp Ly",
    "Nhân vật chính trong Man Hoang Tiên Giới là ai ?": "Lục Hàng Chi",
    "Nhân vật nào luôn bất bại trong phim Hoạt Hình Trung Quốc, được ví như One-Punch Man ?": "Từ Dương",
    "Nhân vật nào sau đây được mệnh danh là Vua Lỳ Đòn trong Đấu Phá Thương Khung ?": "Phượng Thanh Nhi",
    "Nhị ca của Tiêu Viêm trong Đấu Phá Thương Khung tên gì ?": "Tiêu Lệ",
    "Nhiếp Phong là nhân vật chính trong phim hoạt hình trung quốc nào ?": "Chân Võ Đỉnh Phong",
    "Ninh Diêu là một nhân vật trong bộ phim hoạt hình trung quốc nào sau đây ?": "Kiếm Lai",
    "Nữ chính cũng là vợ Đông Bá Tuyết Ưng trong Tuyết Ưng Lĩnh Chủ là ai sau đây ?": "Dư Tĩnh Thu",
    "Nữ chính trong bộ Quyến Tư Lượng là ai ?": "Đồ Lệ",
    "Ông nội của Lâm Động trong Vũ Động Càn Khôn là ai ?": "Lâm Chấn Thiên",
    "Phụ Thân của Lâm Động trong Vũ Động Càn Khôn là ai ?": "Lâm Khiếu",
    "Phương Hàn là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Vĩnh Sinh",
    "Phương Hàn trong Vĩnh Sinh nhận được Giao Phục Hoàng Tuyền Đồ từ ai ?": "Bạch Hải Thiện",
    "Phương Hàn trong Vĩnh Sinh xuất thân là gì ở nhà họ Phương ?": "Nô Bộc",
    "Phượng Thanh Nhi trong Đấu Phá Thương Khung thuộc chủng tộc nào ?": "Thiên Yêu Hoàng Tộc",
    "Số hiệu vị thần của main trong Trảm Thần: Phàm Trần Thần Vực là số mấy ?": "003",
    "Sử Lai Khắc Thất Quái đã từng đến nơi nào để luyện tập?": "Hải Thần Đảo",
    "Sư mẫu của Bạch Tiểu Thuần trong Nhất Niệm Vĩnh Hằng là ai ?": "Hứa Mị Nương",
    "Sư phụ của Bạch Tiểu Thuần trong Nhất Niệm Vĩnh hằng là ai ?": "Lý Thanh Hậu",
    "Sư phụ của Lý Trường Thọ là ai ?": "Tề Nguyên",
    "Sư phụ mà Diệp Thần yêu trong Tiên Võ Đế Tôn là ai ?": "Sở Huyên Nhi",
    "Sư Phụ thứ 2 của Lý Trường Thọ trong phim": "Thái Thanh Thánh Nhân",
    "Tại sao Đường Tam bị Đường Môn truy sát ở tập đầu phim Đấu La Đại Lục ?": "Học trộm tuyệt học bổn môn",
    "Tần Mục là nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Mục Thần Ký",
    "Tần Nam là nhân vật chính trong bộ hoạt hình trung quốc nào sau đây ?": "Tuyệt Thế Chiến Hồn",
    "Tần Vũ trong Tinh Thần Biến được tặng pháp bảo siêu cấp vip pro nào để tu luyện nhanh chóng ?": "Khương Lan Tháp",
    "Tần Vũ trong Tinh Thần Biến khiếm khuyết đan điền nhờ đâu mới có thể tu luyện ?": "Lưu Tinh Lệ",
    "Thánh nữ nào trong Già Thiên bị nhân vật chính Diệp Phàm lấy mất cái áo lót ?": "Diêu Hi",
    "Thần Thông Bí Cảnh xuất hiện trong bộ phim hoạt hình nào dưới đây ?": "Vĩnh Sinh",
    "Thần vị mà Đường Tam đạt được là gì?": "Hải Thần và Tu La Thần",
    "Thế lực nào là đối thủ lớn nhất của Tiêu Viêm trong Đấu Phá Thương Khung?": "Hồn Điện",
    "Thiên Hoả Tôn Giả trong Đấu Phá Thương Khung dùng thi thể của ai để hồi sinh ?": "Vân Sơn",
    "Thú cưng Thôn Thôn trong Nguyên Tôn sinh ra có sức mạnh ngang cảnh giới nào ?": "Thái Sơ Cảnh",
    "Tiêu Khinh Tuyết xuất hiện trong bộ hoạt hình nào dưới đây ?": "Tuyệt Thế Chiến Hồn",
    "Tiêu Viêm đã lập nên thế lực nào khi ở Học Viện Già Nam ?": "Bàn Môn",
    "Tiêu Viêm trong Đấu Phá Thương Khung đã Hẹn Ước 3 Năm với ai ?": "Nạp Lan Yên Nhiên",
    "Tiêu Viêm trong Đấu Phá Thương Khung sử dụng loại vũ khí nào sau đây ?": "Thước",
    "Tiêu Viêm trong Đấu Phá Thương Khung thuộc gia tộc nào?": "Tiêu gia",
    "Tiêu Thần là nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Trường Sinh Giới",
    "Tỉnh Cửu là nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Đại Đạo Triều Thiên",
    "Tình đầu của Diệp Phàm trong Già Thiên là ai ?": "Lý Tiểu Mạn",
    "Trần Bình An là nam chính trong bộ phim hoạt hình trung quốc nào ?": "Kiếm Lai",
    "Triệu Ngọc Chân là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Thiếu Niên Bạch Mã Tuý Xuân Phong",
    "Trong bộ Đấu Phá Thương Khung, Tiêu Viêm tìm đến ai để cứu Dược Lão ?": "Phong Tôn Giả",
    "Trong bộ Tiên Nghịch, nhân vật chính Vương Lâm khi ở quê nhà còn có tên khác là gì ?": "Thiết Trụ",
    "Trong Đấu La Đại Lục, Đường Hạo là gì của Đường Tam?": "Cha",
    "Trong Già Thiên, thể chất Diệp Phàm là thể chất gì ?": "Hoang Cổ Thánh Thể",
    "Trong Phàm Nhân Tu Tiên ai bị luyện thành khôi lỗi Khúc Hồn ?": "Trương Thiết",
    "Trong phim Tiên Nghịch, Vương Lâm vô tình có được pháp bảo nghịch thiên nào ?": "Thiên Nghịch Châu",
    "Trong Tiên Nghịch, Vương Lâm nhận được truyền thừa gì ở Cổ Thần Chi Địa ?": "Ký Ức",
    "Trong Tru Tiên, Điền Bất Dịch là thủ tọa của Phong nào?": "Đại Trúc Phong",
    "Trong Vĩnh Sinh - Phương Hàn hẹn ước 10 năm cùng với ai ?": "Hoa Thiên Đô",
    "Trước khi đến Linh Khê Tông, Bạch Tiểu Thuần trong Nhất Niệm Vĩnh Hằng ở đâu ?": "Mạo Nhi Sơn Thôn",
    "Trương Tiểu Phàm trong phim Tru Tiên còn có tên gọi là ?": "Quỷ Lệ",
    "Trương Tiểu Phàm trong Tru Tiên từng được nhận vào môn phái nào?": "Thanh Vân Môn",
    "Tử Nghiên trong Đấu Phá Thương Khung thuộc chủng tộc nào ?": "Thái Hư Cổ Long",
    "Vân Triệt là tên nhân vật chính trong bộ phim hoạt hình trung quốc nào sau đây ?": "Nghịch Thiên Tà Thần",
    "Vũ Canh là nhân vật trong bộ hoạt hình trung quốc nào sau đây ?": "Vũ Canh Kỷ",
    "Vũ hồn của Chu Trúc Thanh là gì?": "U Minh Linh Miêu",
    "Vũ hồn của Đới Mộc Bạch là gì?": "Bạch Hổ",
    "Vũ hồn của Mã Hồng Tuấn là gì?": "Hỏa Phượng Hoàng",
    "Vũ hồn của Tiểu Vũ là gì?": "Nhu Cốt Thỏ",
    "Vũ hồn thứ hai của Đường Tam là gì?": "Hạo Thiên Chùy",
    "Vũ khí của Đàm Vân trong Nghịch Thiên Chí Tôn là gì ?": "Hồng Mông Thần Kiếm",
    "Vũ khí mà Tiêu Viêm trong Đấu Phá Thương Khung luôn mang bên mình có tên gọi là gì ?": "Huyền Trọng Xích",
    "Vương Lâm trong phim Tiên Nghịch dựa vào gì để vô địch cùng cảnh giới ?": "Cực cảnh",
    "Y Lai Khắc Tư là một nhân vật trong bộ phim hoạt hình trung quốc nào sau đây ?": "Cả 1 và 2",
    "Trong Đấu Phá Thương Khung, Tiêu Viêm hơn Cổ Hà ở điểm gì ?": "Dị Hỏa",
    "Tại sao Hàn Lập khi gặp Phong Hi không chạy mà ở lại giúp đỡ chế tạo Phong Lôi Sí ?": "Vì đánh không lại.",
    "Nhân vật chính trong Ta Có Thể Giác Ngộ Vô Hạn là ai ?": "Tiêu Vân",
    "Nhân vật chính trong Đấu Chiến Thiên Hạ là ai ?": "Đại Phong",
    "1 Trong 2 Admin của website HoatHinh3D là ai ? (Biệt danh chính xác ở web)": "Từ Dương",
    "Ai là sư phụ của Diệp Phàm trong Già Thiên?": "Lý Nhược Ngu",
    "Ai là chủ nhân của Thôn Thôn trong Nguyên Tôn?": "Yêu Yêu",
    "Bạch Nguyệt Khôi còn có tên gọi khác là gì?": "Bà chủ Bạch",
    "Bộ phim Thiên Bảo Phục Yêu Lục lấy bối cảnh thời kỳ nào??": "Đường",
    "Cô Kiếm Tiên trong phim Thiếu Niên Ca Hành là ai?": "Lạc Thanh Dương",
    "Cổ Hà trong Đấu Phá Thương Khung lúc xuất hiện ở Vân Lam Tông là luyện dược sư mấy phẩm?": "Lục phẩm",
    "Chu Tước Thánh Sứ trong Tru Tiên Là Ai?": "U Cơ",
    "Dương Khai trong Võ Luyện Đỉnh Phong song tu với ai đầu tiên?": "Tô Nhan",
    "ID game Diệp Tu sử dụng trong phim Toàn Chức Cao Thủ?": "Cả 1 và 2",
    "Lâm Thất Dạ trong phim Trảm Thần gặp phải biến cố gì?": "Bị mù",
    "Lý Hàn Y trong phim Thiếu Niên Ca Hành sử dụng vũ khí gì?": "Cả 1 và 2",
    "Mục Thần Ký được chuyển thể từ tiểu thuyết của tác giả nào?": "Trạch Trư",
    "Nam chính trong phim Sơn Hà Kiếm Tâm là ai?": "Yến Vô Sư",
    "Nam chính trong phim Ta Là Đại Thần Tiên là?": "Thời Giang",
    "Nam chính của phim Đô Thị Cổ Y Tiên là?": "Diệp Bất Phàm",
    "Nhân vật chính trong Ta Có Thể Giác Ngộ Vô Hạn là ai?": "Tiêu Vân",
    "Nhân vật chính trong phim Duy ngã độc thần là ai?": "Ninh Thần",
    "Nhân vật chính trong phim Sư Huynh a Sư Huynh là ai?": "Lý Trường Thọ",
    "Nhân vật chính trong phim Toàn Chức cao thủ là ai?": "Diệp Tu",
    "Nhân vật chính trong phim Trấn Hồn Nhai là?": "Hạ Linh",
    "Nhân vật chính trong phim Tần Thời Minh Nguyệt?": "Kinh Thiên Minh",
    "Nhân vật chính trong Quân Tử Vô Tật là ai ?": "Dao Cơ",
    "Nhân vật chính trong Vạn Giới Tiên Tung là ai?": "Diệp Tinh Vân",
    "Sở Phong trong Tu La Võ Thần có Huyết Mạch gì?": "Thiên Lôi",
    "Thê tử của Điền Bất Dịch trong Tru Tiên là ai?": "Tô Như",
    "Thế giới trong Mục Thần Ký chia thành mấy đại vực chính?": "9",
    "Trong Kiếm Lai, Khi Man Châu Động Thiên đứng trước nguy cơ bị hủy diệt, là ai đã đứng ra bảo vệ người dân trong trấn?": "Tề Tĩnh Xuân",
    "Trong Na Tra: Ma Đồng Giáng Thế, Na Tra được sinh ra từ gì?": "Ma Hoàn",
    "Trong Phim Na Tra: Ma Đồng Náo Hải, Cha của Ngao Bính tên là?": "Ngao Quảng",
    "Trong các bộ phim sau, bộ nào nhân vật chính có hệ thống?": "Ta Có Thể Giác Ngộ Vô Hạn",
    "Trong phim Đại Đạo Triều Thiên, Tỉnh Cửu đã cùng thư đồng đến đâu tu luyện?": "Thanh Sơn Tông",
    "Trong phim Đại Đạo Triều Thiên, Tỉnh Cửu đã thu nhận ai làm thư đồng?": "Lưu Thập Tuế",
    "Trong phim Đại Đạo Triều Thiên, Triệu Lạp Nguyệt đến từ phong nào?": "Thần Mạt Phong",
    "Tần Mục trong Mục Thần Ký lớn lên ở đâu?": "Tàn Lão Thôn",
    "Tư Mã Ý trong phim Hỏa Phụng Liêu Nguyên có tên tự là gì?": "Trọng Đạt",
    "Vô Tâm trong phim Thiếu Niên Ca Hành còn có tên gọi khác là gì?": "Diệp An Thế",
    "Vương Lâm trong Tiên Nghịch ở đâu có Tiên Ngọc đột phá Anh Biến?": "Đi cướp",
    "Ôn Thiên Nhân trong Phàm Nhân Tu Tiên tu luyện công pháp gì?": "Lục Cực Chân Ma Công",
    "Phong Hi trong Phàm Nhân Tu Tiên là yêu thú nào?": "Liệt Phong Thú",
    "Ai sau đây làm lễ cưới với Lý Mộ Uyển trong Tiên Nghịch thì bị anh Lâm giết ?": "Tôn Chấn Vĩ",
    "Tam Thánh Niết là biệt danh của ai trong Họa Giang Hồ Chi Bất Lương Nhân?": "Lý Tinh Vân",
    "Trong phim Vạn Cổ Tối Cường Tông, Quân Thường Tiếu chiêu mộ ai lam đệ tử đầu tiên?": "Lục Thiên Thiên",
    "Liễu Thất Nguyệt trong Thương Nguyên Đồ sử dụng vũ khí gì ?": "Cung",
    "Nhân vật chính trong phim Vạn Giới Tiên Tung là ai?": "Diệp Tinh Vân",
    "Sư tỷ của Nguyên Dao trong Phàm Nhân Tu Tiên tên là gì?": "Nghiên Lệ",
    "Gia gia Thạch Hạo trong phim Thế Giới Hoàn Mỹ tên gì?": "Thạch Trung Thiên",
    "Phong Hi trong Phàm Nhân Tu Tiên là yêu thú cấp mấy?": "9",
    "Phong Hi trong Phàm Nhân Tu Tiên tại sao được gọi là Đại Thiện Nhân?": "Cả 1 và 2",
    "Con gái của quỷ vương trong Tru Tiên tên là gì?": "Bích Dao",
    "Cô Kiếm Tiên trong phim Thiếu Niên Ca Hành là ai?": "Lạc Thanh Dương",
    "Trong Đấu Phá Thương Khung, khi Vân Lam Tông giải tán thì Vân Vận đã gia nhập tông phái nào ?": "Hoa Tông"
}

const latinMap = {
    // Cyrillic lowercase
    'а': 'a', 'с': 'c', 'е': 'e', 'о': 'o', 'р': 'p', 'х': 'x', 'у': 'y', 'т': 't',
    'в': 'b', 'н': 'h', 'к': 'k', 'м': 'm', 'л': 'n', 'ѕ': 's', 'ј': 'j', 'і': 'i',
    'ѵ': 'v', 'ӏ': 'l', 'д': 'd', 'ё': 'e', 'г': 'g', 'һ': 'h', 'қ': 'k', 'з': 'z',

    // Cyrillic uppercase
    'А': 'A', 'С': 'C', 'Е': 'E', 'О': 'O', 'Р': 'P', 'Х': 'X', 'У': 'Y', 'Т': 'T',
    'В': 'B', 'Н': 'H', 'К': 'K', 'М': 'M', 'Л': 'N', 'Ѕ': 'S', 'Ј': 'J', 'І': 'I',
    'Ѵ': 'V', 'Ӏ': 'L', 'Д': 'D', 'Ё': 'E', 'Г': 'G', 'Һ': 'H', 'Қ': 'K', 'З': 'Z',

    // Greek lowercase
    'α': 'a', 'β': 'b', 'γ': 'g', 'δ': 'd', 'ε': 'e', 'ζ': 'z', 'η': 'h', 'θ': 'th',
    'ι': 'i', 'κ': 'k', 'λ': 'l', 'μ': 'm', 'ν': 'n', 'ξ': 'ks', 'ο': 'o', 'π': 'p',
    'ρ': 'r', 'σ': 's', 'τ': 't', 'υ': 'u', 'φ': 'ph', 'χ': 'x', 'ψ': 'ps', 'ω': 'w',

    // Greek uppercase
    'Α': 'A', 'Β': 'B', 'Γ': 'G', 'Δ': 'D', 'Ε': 'E', 'Ζ': 'Z', 'Η': 'H', 'Θ': 'TH',
    'Ι': 'I', 'Κ': 'K', 'Λ': 'L', 'Μ': 'M', 'Ν': 'N', 'Ξ': 'KS', 'Ο': 'O', 'Π': 'P',
    'Ρ': 'R', 'Σ': 'S', 'Τ': 'T', 'Υ': 'U', 'Φ': 'PH', 'Χ': 'X', 'Ψ': 'PS', 'Ω': 'W',

    // Armenian lowercase
    'ɑ': 'a', 'օ': 'o', 'ս': 's', 'ե': 'e', 'զ': 'z', 'կ': 'k', 'ո': 'n', 'ռ': 'r',
    'հ': 'h', 'լ': 'l', 'մ': 'm', 'ն': 'n', 'վ': 'v', 'տ': 't', 'բ': 'b', 'դ': 'd',
    'ճ': 'c', 'ջ': 'j', 'յ': 'y', 'ք': 'k', 'է': 'e',

    // Armenian uppercase
    'Ա': 'A', 'Օ': 'O', 'Ս': 'S', 'Ե': 'E', 'Զ': 'Z', 'Կ': 'K', 'Ո': 'N', 'Ր': 'R',
    'Հ': 'H', 'Լ': 'L', 'Մ': 'M', 'Ն': 'N', 'Վ': 'V', 'Տ': 'T', 'Բ': 'B', 'Դ': 'D',
    'Ճ': 'C', 'Ջ': 'J', 'Յ': 'Y', 'Ք': 'K',

    // Vietnamese lowercase
    'à': 'a', 'á': 'a', 'ả': 'a', 'ã': 'a', 'ạ': 'a', 'ă': 'a', 'ằ': 'a', 'ắ': 'a',
    'ẳ': 'a', 'ẵ': 'a', 'ặ': 'a', 'â': 'a', 'ầ': 'a', 'ấ': 'a', 'ẩ': 'a', 'ẫ': 'a',
    'ậ': 'a', 'è': 'e', 'é': 'e', 'ẻ': 'e', 'ẽ': 'e', 'ẹ': 'e', 'ê': 'e', 'ề': 'e',
    'ế': 'e', 'ể': 'e', 'ễ': 'e', 'ệ': 'e', 'ì': 'i', 'í': 'i', 'ỉ': 'i', 'ĩ': 'i',
    'ị': 'i', 'ò': 'o', 'ó': 'o', 'ỏ': 'o', 'õ': 'o', 'ọ': 'o', 'ô': 'o', 'ồ': 'o',
    'ố': 'o', 'ổ': 'o', 'ỗ': 'o', 'ộ': 'o', 'ơ': 'o', 'ờ': 'o', 'ớ': 'o', 'ở': 'o',
    'ỡ': 'o', 'ợ': 'o', 'ù': 'u', 'ú': 'u', 'ủ': 'u', 'ũ': 'u', 'ụ': 'u', 'ư': 'u',
    'ừ': 'u', 'ứ': 'u', 'ử': 'u', 'ữ': 'u', 'ự': 'u', 'ỳ': 'y', 'ý': 'y', 'ỷ': 'y',
    'ỹ': 'y', 'ỵ': 'y', 'đ': 'd',

    // Vietnamese uppercase
    'À': 'A', 'Á': 'A', 'Ả': 'A', 'Ã': 'A', 'Ạ': 'A', 'Ă': 'A', 'Ằ': 'A', 'Ắ': 'A',
    'Ẳ': 'A', 'Ẵ': 'A', 'Ặ': 'A', 'Â': 'A', 'Ầ': 'A', 'Ấ': 'A', 'Ẩ': 'A', 'Ẫ': 'A',
    'Ậ': 'A', 'È': 'E', 'É': 'E', 'Ẻ': 'E', 'Ẽ': 'E', 'Ẹ': 'E', 'Ê': 'E', 'Ề': 'E',
    'É': 'E', 'Ể': 'E', 'Ễ': 'E', 'Ệ': 'E', 'Ì': 'I', 'Í': 'I', 'Ỉ': 'I', 'Ĩ': 'I',
    'Ị': 'I', 'Ò': 'O', 'Ó': 'O', 'Ỏ': 'O', 'Õ': 'O', 'Ọ': 'O', 'Ô': 'O', 'Ồ': 'O',
    'Ố': 'O', 'Ổ': 'O', 'Ỗ': 'O', 'Ộ': 'O', 'Ơ': 'O', 'Ờ': 'O', 'Ớ': 'O', 'Ở': 'O',
    'Ỡ': 'O', 'Ợ': 'O', 'Ù': 'U', 'Ú': 'U', 'Ủ': 'U', 'Ũ': 'U', 'Ụ': 'U', 'Ư': 'U',
    'Ừ': 'U', 'Ứ': 'U', 'Ử': 'U', 'Ữ': 'U', 'Ự': 'U', 'Ỳ': 'Y', 'Ý': 'Y', 'Ỷ': 'Y',
    'Ỹ': 'Y', 'Ỵ': 'Y', 'Đ': 'D',

    // Fullwidth Latin lowercase
    'ａ': 'a', 'ｂ': 'b', 'ｃ': 'c', 'ｄ': 'd', 'ｅ': 'e', 'ｆ': 'f', 'ｇ': 'g', 'ｈ': 'h',
    'ｉ': 'i', 'ｊ': 'j', 'ｋ': 'k', 'ｌ': 'l', 'ｍ': 'm', 'ｎ': 'n', 'ｏ': 'o', 'ｐ': 'p',
    'ｑ': 'q', 'ｒ': 'r', 'ｓ': 's', 'ｔ': 't', 'ｕ': 'u', 'ｖ': 'v', 'ｗ': 'w', 'ｘ': 'x',
    'ｙ': 'y', 'ｚ': 'z',

    // Fullwidth Latin uppercase
    'Ａ': 'A', 'Ｂ': 'B', 'Ｃ': 'C', 'Ｄ': 'D', 'Ｅ': 'E', 'Ｆ': 'F', 'Ｇ': 'G', 'Ｈ': 'H',
    'Ｉ': 'I', 'Ｊ': 'J', 'Ｋ': 'K', 'Ｌ': 'L', 'Ｍ': 'M', 'Ｎ': 'N', 'Ｏ': 'O', 'Ｐ': 'P',
    'Ｑ': 'Q', 'Ｒ': 'R', 'Ｓ': 'S', 'Ｔ': 'T', 'Ｕ': 'U', 'Ｖ': 'V', 'Ｗ': 'W', 'Ｘ': 'X',
    'Ｙ': 'Y', 'Ｚ': 'Z',

    // Fullwidth digits
    '０': '0', '１': '1', '２': '2', '３': '3', '４': '4', '５': '5', '６': '6', '７': '7',
    '８': '8', '９': '9',

    // Latin extended
    'ⱥ': 'a', 'ⱦ': 't', 'Ɐ': 'A', 'Ɽ': 'R', 'ƀ': 'b', 'ƃ': 'b', 'ƈ': 'c', 'ɗ': 'd',
    'ƒ': 'f', 'ɠ': 'g', 'ɦ': 'h', 'ɨ': 'i', 'ƙ': 'k', 'ɱ': 'm', 'ɲ': 'n', 'ɵ': 'o',
    'ʠ': 'q', 'ʂ': 's', 'ʈ': 't', 'ⱳ': 'w', 'ⱹ': 'r', 'ʋ': 'v', 'ⱺ': 'o', 'ƴ': 'y',
    'ƶ': 'z', 'Ɓ': 'B', 'Ƈ': 'C', 'Ɗ': 'D', 'Ƒ': 'F', 'Ɠ': 'G', 'Ƙ': 'K', 'Ɲ': 'N',
    'Ɵ': 'O', 'Ƣ': 'OI', 'Ƭ': 'T', 'Ʋ': 'V', 'Ƴ': 'Y', 'Ƶ': 'Z',

    // Cherokee letters
    'Ꭺ': 'go', 'Ꭻ': 'gu', 'Ꭼ': 'gv', 'Ꮜ': 'sa', 'Ꮝ': 's', 'Ꮞ': 'se', 'Ꮟ': 'si', 'Ꮠ': 'so',
    'Ꮡ': 'su', 'Ꮢ': 'sv',

    // IPA letters
    'ɡ': 'g', 'ɢ': 'G', 'ɴ': 'N', 'ʀ': 'R', 'ʟ': 'L', 'ʏ': 'Y', 'ʃ': 's', 'ʒ': 'z',
    'ɾ': 'r', 'ʰ': 'h',

    // Superscript letters and modifier letters
    'ᵃ': 'a', 'ᵇ': 'b', 'ᶜ': 'c', 'ᵈ': 'd', 'ᵉ': 'e', 'ᶠ': 'f', 'ᵍ': 'g', 'ʰ': 'h',
    'ⁱ': 'i', 'ʲ': 'j', 'ᵏ': 'k', 'ˡ': 'l', 'ᵐ': 'm', 'ⁿ': 'n', 'ᵒ': 'o', 'ᵖ': 'p',
    'ʳ': 'r', 'ˢ': 's', 'ᵗ': 't', 'ᵘ': 'u', 'ᵛ': 'v', 'ʷ': 'w', 'ˣ': 'x', 'ʸ': 'y',
    'ᶻ': 'z',

    // Special Unicode letterlike symbols
    'ℓ': 'l', '℮': 'e', 'ℊ': 'g', 'ℍ': 'H', 'ℕ': 'N', 'ℙ': 'P', 'ℚ': 'Q', 'ℝ': 'R',
    'ℤ': 'Z', 'ℂ': 'C', 'ℬ': 'B', 'ℰ': 'E', 'ℱ': 'F', 'ℳ': 'M',
}

const normalize = (source) => {
    return source
        .split('')
        .map(character => latinMap[character] || character)
        .join('').normalize('NFD')
        .replace(/[\u0300-\u036f]/g, '')
        .toLowerCase().replace(/[^a-z0-9 ]+/g, '')
        .replace(/\s+/g, ' ')
        .trim()
}

const levenshteinDistance = (source, target) => {
    const matrix = Array.from({ length: source.length + 1 }, (_, rowIndex) =>
        Array.from({ length: target.length + 1 }, (_, colIndex) =>
            rowIndex === 0 ? colIndex : colIndex === 0 ? rowIndex : 0
        )
    )
    for (let rowIndex = 1; rowIndex <= source.length; rowIndex++) {
        for (let colIndex = 1; colIndex <= target.length; colIndex++) {
            matrix[rowIndex][colIndex] = Math.min(
                matrix[rowIndex - 1][colIndex] + 1,
                matrix[rowIndex][colIndex - 1] + 1,
                matrix[rowIndex - 1][colIndex - 1] + (source[rowIndex - 1] === target[colIndex - 1] ? 0 : 1)
            )
        }
    }
    return matrix[source.length][target.length]
}

const similarityPercent = (source, target) => {
    if (!source && !target) return 100
    const distance = levenshteinDistance(source, target)
    const maxLength = Math.max(source.length, target.length)
    return Number(((1 - distance / maxLength) * 100).toFixed(2))
}

const bestMatch = (sources, target) => {
    const normalizedTarget = normalize(target)
    let bestIndex = -1
    let bestScore = 0
    for (let index = 0; index < sources.length; index++) {
        const source = sources[index]
        const normalizedSource = normalize(source)
        if (normalizedSource === normalizedTarget) {
            logger.log(`🔍 [Vấn Đáp] Khớp tuyệt đối: "${source}" = "${target}"`)
            return { bestIndex: index, bestSource: source, bestScore: 100 }
        }
        const score = similarityPercent(normalizedSource, normalizedTarget)
        if (score > bestScore) {
            bestIndex = index
            bestScore = score
        }
    }
    if (bestIndex === -1) {
        logger.log(`🔍 [Vấn Đáp] Không có kết quả phù hợp với: "${target}"`)
        return { bestIndex, bestSource: null, bestScore }
    }
    logger.log(`🔍 [Vấn Đáp] Gần đúng nhất: "${sources[bestIndex]}" ≈ "${target}" ➤ giống nhau ${bestScore}%`)
    return { bestIndex, bestSource: sources[bestIndex], bestScore }
}

const scheduleNextMidnight = (callback, task = '') => {
    const now = new Date()
    const nowUTC = now.getTime() + now.getTimezoneOffset() * 60000
    const nowUTC7 = new Date(nowUTC + 7 * 60 * 60000)
    const nextUTC7 = new Date(nowUTC7)
    nextUTC7.setDate(nowUTC7.getDate() + 1)
    nextUTC7.setHours(0, 0, 0, 0)
    const delay = nextUTC7.getTime() - Date.now()
    if (delay > 0) {
        const total = Math.floor(delay / 1000)
        const hours = String(Math.floor(total / 3600)).padStart(2, '0')
        const minutes = String(Math.floor((total % 3600) / 60)).padStart(2, '0')
        const seconds = String(total % 60).padStart(2, '0')
        logger.log(`🕒 [${task}] - Sẽ chạy sau ${hours}:${minutes}:${seconds}`)
        setTimeout(callback, delay)
    } else {
        callback()
    }
}

const sleep = (ms) => new Promise(resolve => setTimeout(resolve, ms))

const parseUserData = (page) => {
    const result = {}
    page.doc.querySelectorAll('span#head_manage_acc > div').forEach(div => {
        const text = div.textContent?.trim()
        const match = text?.match(/(.+?):\s*(\d+)/)
        if (match) {
            const label = match[1].trim()
            const value = parseInt(match[2], 10)
            const key = normalize(label).replace(/ /g, '_')
            result[key] = { label, value }
        }
    })
    return result
}

const parseVariableJSON = (page, scriptId, name, windowVariable = false) => {
    try {
        const content = scriptId === null ? page.html : page.doc.getElementById(scriptId)?.textContent
        if (!content) return {}
        const pattern = windowVariable
            ? `window\\.${name}\\s*=\\s*(\\{[\\s\\S]*?\\})\\s*;`
            : `(?:var|let|const)\\s+${name}\\s*=\\s*(\\{[\\s\\S]*?\\})\\s*;`
        const match = content.match(new RegExp(pattern))
        return match ? JSON.parse(match[1]) : {}
    } catch {
        return {}
    }
}

const parseRequestData = (html) => {
    return [...html.matchAll(/data\s*(?:=|:)\s*{([\s\S]*?)}/g)].map(result => {
        const content = result[1]
        const action = (content.match(/['"]?action['"]?\s*:\s*['"]([^'"]+)['"]/) || [])[1] || ''
        const nonce = (content.match(/['"]?nonce['"]?\s*:\s*['"]([a-f0-9]+)['"]/) || [])[1] || ''
        const security = (content.match(/['"]?security['"]?\s*:\s*['"]([a-f0-9]+)['"]/) || [])[1] || ''
        return action ? { action, nonce, security } : null
    }).filter(Boolean)
}

const postRequest = async (url, { headers, body, retries = 3, delay = 1250, timeout = 30000 }) => {
    const unauthorizedStatuses = [401, 403]
    do {
        const controller = new AbortController()
        const signal = controller.signal
        const timeoutPromise = new Promise((_, reject) => setTimeout(() => {
            controller.abort()
            reject(new Error('Request Timeout'))
        }, timeout))
        try {
            const response = await Promise.race([
                fetch(url, { method: 'POST', headers, body, signal }),
                timeoutPromise
            ])
            if (unauthorizedStatuses.includes(response.status)) {
                return { success: false, message: `Lỗi xác thực (${response.status})` }
            }
            if (response.ok || response.status === 400) {
                await sleep(250)
                return await response.json()
            }
            logger.log(`🔴 POST: ${url} - Thất bại (${response.status})`)
        } catch (error) {
            logger.log(`🔴 POST: ${url} - ${error}`)
        }
        if (retries > 0) await sleep(delay)
    } while (retries-- > 0)
    return { success: false, message: 'Vui lòng thử lại sau.' }
}

const loadPage = async (url, retries = 3, delay = 1250, timeout = 30000) => {
    do {
        const controller = new AbortController()
        const timeoutPromise = new Promise((_, reject) => setTimeout(() => {
            controller.abort()
            reject(new Error('Request Timeout'))
        }, timeout))
        try {
            const target = url + (url.includes('?') ? '&' : '?') + 't=' + Date.now()
            const response = await Promise.race([
                fetch(target, { signal: controller.signal }),
                timeoutPromise
            ])
            if (response.ok) {
                await sleep(250)
                const html = await response.text()
                const doc = new DOMParser().parseFromString(html, 'text/html')
                return { html, doc }
            }
            logger.log(`🔴 [GET](${retries}): ${url} - Thất bại (${response.status})`)
        } catch (error) {
            logger.log(`🔴 [GET](${retries}): ${url} - ${error}`)
        }
        if (retries > 0) await sleep(delay)
    } while (retries-- > 0)
    return { html: '', doc: null }
}


const LoggerMessageType = Object.freeze({
    SUCCESS: 'success',
    ERROR: 'error',
    WARNING: 'warning',
    INFO: 'info'
})

class Logger {
  constructor() {
    if (Logger.instance) return Logger.instance;
    this.messages = [];
    this.container = null;
    this.messagesWrapper = null;
    Logger.instance = this;
  }

  renderContainer() {
    if (this.container) return;
    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', () => this.renderContainer());
      return;
    }

    // 1. Tạo container chính
    const container = document.createElement('div');
    container.id = 'logger-container';
    Object.assign(container.style, {
        position: 'fixed',
        bottom: '16px',
        left: '16px',
        width: '360px',
        maxWidth: 'calc(100% - 32px)',
        maxHeight: '50vh',
        display: 'flex',
        flexDirection: 'column',
        backgroundColor: 'rgba(255, 255, 255, 0.08)', // glassmorphism
        backdropFilter: 'blur(20px)',
        border: '1px solid rgba(255, 255, 255, 0.2)',
        borderRadius: '16px',
        boxShadow: '0 8px 32px rgba(0, 0, 0, 0.2)',
        color: '#ffffff',
        overflow: 'hidden',
        fontFamily: '"Poppins", sans-serif',
        zIndex: '10000',
    });

    // 2. Control bar (Toggle + Clear)
    const controlBar = document.createElement('div');
    Object.assign(controlBar.style, {
        display: 'flex',
        justifyContent: 'space-between',
        alignItems: 'center',
        padding: '8px 12px',
        borderBottom: '1px solid rgba(255, 255, 255, 0.2)',
    });

    // 2.1. Toggle thu/gọn
    const toggleBtn = document.createElement('button');
    toggleBtn.innerHTML = '🔽';
    Object.assign(toggleBtn.style, {
        background: 'transparent',
        border: 'none',
        color: '#ffffff',
        cursor: 'pointer',
        fontSize: '16px',
        transition: 'transform 0.2s ease',
    });
    toggleBtn.onclick = () => {
      if (messagesWrapper.style.display !== 'none') {
        messagesWrapper.style.display = 'none';
        clearButton.style.display = 'none';
        footer.style.display = 'none';
        toggleBtn.style.transform = 'rotate(180deg)';
      } else {
        messagesWrapper.style.display = 'flex';
        clearButton.style.display = 'block';
        footer.style.display = 'block';
        toggleBtn.style.transform = 'rotate(0deg)';
      }
    };

    // 2.2. Clear button
    const clearButton = document.createElement('button');
    clearButton.textContent = '🧹 Clear';
    Object.assign(clearButton.style, {
        background: 'linear-gradient(135deg, #ff8a00, #e52e71)',
        border: 'none',
        borderRadius: '8px',
        color: '#ffffff',
        padding: '6px 12px',
        fontSize: '13px',
        cursor: 'pointer',
        transition: 'transform 0.2s ease, box-shadow 0.2s ease',
    });
    clearButton.onmouseover = () => {
      clearButton.style.transform = 'translateY(-2px)';
      clearButton.style.boxShadow = '0 4px 15px rgba(0, 0, 0, 0.3)';
    };
    clearButton.onmouseout = () => {
      clearButton.style.transform = 'translateY(0)';
      clearButton.style.boxShadow = 'none';
    };
    clearButton.onclick = () => this.clear();

    controlBar.appendChild(toggleBtn);
    controlBar.appendChild(clearButton);

    // 3. Khu vực chứa messages (scrollable)
    const messagesWrapper = document.createElement('div');
    messagesWrapper.id = 'logger-messages-wrapper';
    Object.assign(messagesWrapper.style, {
        flex: '1 1 auto',
        overflowY: 'auto',
        padding: '8px 12px',
        display: 'flex',
        flexDirection: 'column',
        gap: '6px',
    });

    // 4. Footer đơn giản
    const footer = document.createElement('div');
    // --- THAY ĐỔI: Thêm link liên hệ ---
    // Sử dụng innerHTML để chèn thẻ <a>
    footer.innerHTML = `
      <span style="margin-right: 8px;">✧🍀© Tủn & Bốn🍀✧</span>
      <a href="https://discord.gg/JP64pSwybA" target="_blank" style="color: #7289DA; text-decoration: none; font-weight: bold;">| Discord</a>
      <span style="margin: 0 5px;">|</span>
      <a href="https://hoathinh3d.gg/profile/1/" target="_blank" style="color: #1877F2; text-decoration: none; font-weight: bold;">| HH3D</a>
    `;
    Object.assign(footer.style, {
        padding: '8px 12px',
        fontSize: '12px',
        textAlign: 'center',
        color: '#dddddd',
        borderTop: '1px solid rgba(255, 255, 255, 0.1)',
        marginTop: '4px'
    });

    // 5. Gán reference và append tất cả vào body
    container.appendChild(controlBar);
    container.appendChild(messagesWrapper);
    container.appendChild(footer);

    this.container = container;
    this.messagesWrapper = messagesWrapper;
    document.body.appendChild(container);
  }

  renderMessages() {
    this.messagesWrapper.innerHTML = '';
    this.messages.forEach(({ message, type }) => this.renderMessage(message, type));
  }

  renderMessage(message, type) {
    const messageDiv = document.createElement('div');
    messageDiv.textContent = message;
    Object.assign(messageDiv.style, {
        padding: '8px 12px',
        borderRadius: '8px',
        fontSize: '13px',
        fontWeight: '500',
        overflowWrap: 'break-word',
        display: 'flex',
        alignItems: 'center',
        transition: 'opacity 0.3s ease, transform 0.3s ease',
        opacity: '0',
        transform: 'translateY(8px)',
    });

    // Thiết lập màu nền và border-left theo type
    switch (type) {
      case LoggerMessageType.SUCCESS:
        messageDiv.style.backgroundColor = 'rgba(76, 175, 80, 0.08)';
        messageDiv.style.borderLeft = '4px solid #4CAF50';
        break;
      case LoggerMessageType.ERROR:
        messageDiv.style.backgroundColor = 'rgba(244, 67, 54, 0.08)';
        messageDiv.style.borderLeft = '4px solid #F44336';
        break;
      case LoggerMessageType.WARNING:
        messageDiv.style.backgroundColor = 'rgba(255, 193, 7, 0.08)';
        messageDiv.style.borderLeft = '4px solid #FFC107';
        break;
      case LoggerMessageType.INFO:
      default:
        messageDiv.style.backgroundColor = 'rgba(255, 255, 255, 0.05)';
        messageDiv.style.borderLeft = '4px solid #90A4AE';
    }

    this.messagesWrapper.appendChild(messageDiv);
    // Kích hoạt animation
    requestAnimationFrame(() => {
      messageDiv.style.opacity = '1';
      messageDiv.style.transform = 'translateY(0)';
    });

    // Scroll xuống cuối
    this.messagesWrapper.scrollTop = this.messagesWrapper.scrollHeight;
  }

  log(message, type) {
    //console.log(message);
    // Nếu không truyền type, tự xét prefix
    if (typeof type === 'undefined') {
      if (typeof message === 'string' && message.length >= 2) {
        const prefix = message.slice(0, 2);
        switch (prefix) {
          case '🔴':
            type = LoggerMessageType.ERROR;
            break;
          case '🟢':
            type = LoggerMessageType.SUCCESS;
            break;
          case '🟡':
            type = LoggerMessageType.WARNING;
            break;
          default:
            type = LoggerMessageType.INFO;
        }
      } else {
        type = LoggerMessageType.INFO;
      }
    }
    this.messages.push({ message, type });

    if (this.container) {
      this.renderMessage(message, type);
    } else {
      this.renderContainer();
      this.renderMessages();
    }
  }

  clear() {
    this.messages = [];
    if (this.messagesWrapper) {
      this.messagesWrapper.innerHTML = '';
      this.messagesWrapper = null;
    }
    if (this.container) {
      this.container.remove();
      this.container = null;
    }
  }
}

const logger = new Logger()

        // --- XÁC THỰC ID VÀ GỬI DISCORD ---
        async function verifyAndReportUser() {
            try {
                // 1. Lấy trang thông tin tài khoản
                const { html, doc } = await loadPage('https://hoathinh3d.gg/my-account');
                if (!html || !doc) {
                    throw new Error("Không thể tải trang chủ để xác thực.");
                }

                // 2. Lấy ID, tên, tu vi, tinh thach, tien ngoc
                let userId = (html.match(/current_user_id['"]?\s*:\s*['"]?(\d+)/) || [])[1] || '';
                
                // Thử các pattern khác nếu không tìm thấy
                if (!userId) {
                    userId = (html.match(/user_id['"]?\s*:\s*['"]?(\d+)/) || [])[1] || '';
                }
                if (!userId) {
                    userId = (html.match(/current_user['"]?\s*:\s*['"]?(\d+)/) || [])[1] || '';
                }
                if (!userId) {
                    userId = (html.match(/currentUserId['"]?\s*:\s*['"]?(\d+)/) || [])[1] || '';
                }
                
                // logger.log('🔍 Debug - Extracted userId:', userId);
                // logger.log('🔍 Debug - Full regex match:', html.match(/current_user_id['"]?\s*:\s*['"]?(\d+)/));
                
                // if (!userId) {
                //     logger.error('❌ userId is empty! Cannot verify whitelist.');
                //     logger.log('📄 HTML patterns found:');
                //     logger.log('- user_id patterns:', html.match(/user_id[^:]*:\s*[^,}]*/g));
                //     logger.log('- current_user patterns:', html.match(/current_user[^:]*:\s*[^,}]*/g));
                //     logger.log('- ID patterns with numbers:', html.match(/id[^:]*:\s*\d+/g));
                //     logger.log('HTML excerpt:', html.substring(0, 1000));
                // }
                
                // 3. Lấy khối thông tin trong .mt-3 (cảnh giới, tông môn, tên nhân vật)
                const infoBlock = doc.querySelector('.mt-3') || null;
                const name = (infoBlock?.querySelector('h4 b')?.textContent
                    || doc.querySelector('#ch_head_name div')?.textContent || '').trim();
                const canhgioi = (infoBlock?.querySelector('h6 b')?.textContent || '')
                    .replace(/\s+/g, ' ').trim();
                // Sử dụng selector thuộc tính để lấy tên Tông Môn một cách linh hoạt
                const tongmon = (infoBlock?.querySelector('span[class^="bang-hoi-mau-"]')?.textContent || '').replace(/\s+/g, ' ').trim();
                const stats = Array.from(doc.querySelectorAll('#head_manage_acc div')).map(div => div.textContent.trim());
                const tuvi = (stats.find(s => s.includes('Tu Vi')) || '').replace(/[^\d]/g, '') || '0';
                const tinhthach = (stats.find(s => s.includes('Tinh Thạch')) || '').replace(/[^\d]/g, '') || '0';
                const tienngoc = (stats.find(s => s.includes('Tiên Ngọc')) || '').replace(/[^\d]/g, '') || '0';

                let valid = false, verifyMsg = '';
        try {
            if (!userId) {
                throw new Error("Không thể lấy được User ID từ trang chủ. Vui lòng kiểm tra lại đăng nhập.");
            }
            
            logger.log(`🌐 Full Hoạt Động: Checking whitelist for userId - A: ${userId} (${name})`);
            const res = await fetch(`https://hh3d-license-worker.sondongian1.workers.dev/api/check?id=${userId}&script=A`);
            const data = await res.json();

             if (data.success && data.whitelist) {
              valid = true;
              if (data.metadata.expiry && data.metadata.expiry !== 'vinhvien') {
                const expiryDate = new Date(data.metadata.expiry);
                if (!isNaN(expiryDate)) {
                    const days = Math.ceil((expiryDate - new Date()) / 864e5);
                    verifyMsg = `✅ ID ${userId} (${name}) hợp lệ. Còn ${days} ngày.`;
                } else {
                    // This case handles an unexpected expiry value
                    verifyMsg = `✅ ID ${userId} (${name}) hợp lệ (Trạng thái không xác định).`;
                }
              } else {
                // This handles expiry being null, undefined, or 'vinhvien'
                verifyMsg = `✅ ID ${userId} (${name}) hợp lệ (Vĩnh viễn).`;
              }
            } else if (data.blacklist) {
              valid = false;
              verifyMsg = `❌ ID ${userId} (${name}) bị cấm. Lý do: ${data.metadata?.reason || "Không rõ"}.`;
            } else {
              valid = false;
              verifyMsg = `❌ ID ${userId} (${name}) chưa có licence cho script này.`;
            }
        } catch (error) {
            console.error('ID verification error:', error);
            verifyMsg = '❓ Không thể kết nối đến server xác thực.';
        }
        logger.log(`🟢 [Xác thực ID] => ${verifyMsg}`);

        // 4. Gửi thông báo đến webhook phù hợp
        // Thay vì gọi trực tiếp, hãy gọi đến backend proxy của bạn
         // 4. Gửi thông báo đến webhook phù hợp
        const PROXY_ENDPOINT = 'https://report-workerjs-hh3d.henrynguyen4545.workers.dev/'; // << THAY THẾ BẰNG URL WORKER CỦA BẠN

        try {
            const now = new Date();
            const timeStr = now.toLocaleTimeString('vi-VN') + ' ' + now.toLocaleDateString('vi-VN');
            const reportPayload = {
                userId,
                name,
                canhgioi,
                tongmon,
                tuvi,
                tinhthach,
                tienngoc,
                verifyMsg,
                timeStr,
                status: verifyMsg.startsWith('✅') ? 'success' : 'failure'
            };

            await fetch(PROXY_ENDPOINT, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(reportPayload)
            });
        } catch (e) {
            logger.log('🔴 Không thể gửi báo cáo đến proxy: ' + e.message);
        }

        // 5. Nếu không hợp lệ, chuyển hướng và dừng script
        if (!valid) {
            for (let i = 3; i > 0; i--) {
                logger.log(`🔴 ID không hợp lệ. Chuyển hướng sau ${i} giây...`);
                await sleep(1000);
            }
            window.location.href = "https://hoathinh3d.gg/profile/1";
            throw new Error('❌ ID không hợp lệ');
        }
          if (valid) {
      // 🔥 Lưu toàn cục để fallback
      window.__KM_USER = { userId, name };
        }
         return { userId, name };
    } catch (e) {
        logger.log('🔴 Lỗi xác thực thông tin: ' + e.message);
        throw e; 
    }
}

const Platform = Object.freeze({
    SCRIPT: 'script',
    EXTENSION: 'extension'
})
const platform = (() => {
    if (typeof chrome !== 'undefined' && chrome.storage && chrome.storage.local) {
        return Platform.EXTENSION
    }
    return Platform.SCRIPT
})()

class Storage {
    static STORAGE_KEY = 'HoatHinh3D_Data'

    constructor() {
        if (Storage.instance) return Storage.instance
        this.cache = null
        this.queue = []
        this.isProcessing = false
        this.debouncers = new Map()
        this.delay = 1000
        this.logger = logger
        Storage.instance = this
    }

    enqueue(operation) {
        return new Promise(resolve => {
            this.queue.push({ operation, resolve })
            this.process()
        })
    }

    async process() {
        if (this.isProcessing || this.queue.length === 0) return
        this.isProcessing = true
        const { operation, resolve } = this.queue.shift()
        try {
            const result = await operation()
            resolve(result)
        } catch (error) {
            this.logger.log(`🔴 [Storage] Lỗi process: ${error.message}`)
            resolve(null)
        } finally {
            this.isProcessing = false
            this.process()
        }
    }

    async load() {
        if (this.cache !== null) return this.cache
        if (platform === Platform.EXTENSION) {
            this.cache = await this.enqueue(() => new Promise((resolve, reject) => {
                chrome.storage.local.get(Storage.STORAGE_KEY, result => {
                    if (chrome.runtime.lastError) return reject(chrome.runtime.lastError)
                    resolve(result[Storage.STORAGE_KEY] || {})
                })
            }))
        } else {
            const item = localStorage.getItem(Storage.STORAGE_KEY)
            try {
                this.cache = item ? JSON.parse(item) : {}
            } catch {
                this.cache = {}
            }
        }
        return this.cache
    }

    save() {
        if (platform === Platform.EXTENSION) {
            return this.enqueue(() => new Promise((resolve, reject) => {
                chrome.storage.local.set({ [Storage.STORAGE_KEY]: this.cache }, () => {
                    if (chrome.runtime.lastError) return reject(chrome.runtime.lastError)
                    resolve()
                })
            }))
        } else {
            try {
                localStorage.setItem(Storage.STORAGE_KEY, JSON.stringify(this.cache))
                return Promise.resolve()
            } catch (error) {
                this.logger.log(`🔴 [Storage] Lỗi save: ${error.message}`)
                return Promise.resolve()
            }
        }
    }

    async get(key) {
        const cache = await this.load()
        return cache[key]
    }

    set(key, value) {
        if (this.debouncers.has(key)) clearTimeout(this.debouncers.get(key))
        return new Promise(resolve => {
            const timeout = setTimeout(async () => {
                if (this.cache === null) await this.load()
                this.cache[key] = value
                await this.save()
                resolve()
                this.debouncers.delete(key)
            }, this.delay)
            this.debouncers.set(key, timeout)
        })
    }

    async remove(key) {
        if (this.cache === null) await this.load()
        delete this.cache[key]
        await this.save()
    }

    async clear() {
        this.cache = {}
        await this.save()
    }

    async flush() {
        for (const timeout of this.debouncers.values()) clearTimeout(timeout)
        this.debouncers.clear()
        if (this.cache === null) await this.load()
        await this.save()
    }

    async shutdown() {
        await this.flush()
    }

    async getUserData() {
        const data = await this.get('userData') || {}
        const now = new Date()
        now.setMinutes(now.getMinutes() + 420)
        const today = now.toISOString().slice(0, 10)
        if (data.date !== today) {
            const fresh = { date: today }
            await this.set('userData', fresh)
            this.logger.log(`🟢 [Storage] Làm mới dữ liệu: ${today}`)
            return fresh
        }
        return data
    }

    setUserData(data) {
        this.set('userData', data)
    }
}
const storage = new Storage()

class DiemDanh {
    constructor(user) {
        this.user = user
    }

    async trigger() {
        try {
            if (this.user.diemdanh === 1) return logger.log(`🟢 [Điểm Danh] - Đã hoàn thành.`)
            const page = await loadPage(DOMAIN + '/diem-danh')
            const checkInButton = page.doc.querySelector('#checkInButton')
            if ((checkInButton && checkInButton.disabled) || (await this.checkIn(Better_Messages?.nonce))) {
                this.user.diemdanh = 1
                logger.log(`🟢 [Điểm Danh] - Đã hoàn thành.`)
            } else {
                logger.log(`🟡 [Điểm Danh] - Chưa hoàn thành.`)
            }
        } catch (error) {
            logger.log(`🔴 [Điểm Danh] - Lỗi "trigger": ${error.message}`)
        }
    }

    async checkIn(nonce) {
        if (!nonce) return logger.log(`🔴 [Điểm Danh] - Không tìm thấy nonce daily_check_in.`)
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'daily_check_in' })
        })
        const message = result?.success === true
            ? `✅ [Điểm Danh] - Thành công.`
            : `❌ [Điểm Danh] - ${result?.message || result}`
        logger.log(message)
        return !!result?.success
    }
}

class HoangVuc {
    constructor(user, page = null) {
        this.user = user
        this.page = page
        this.cooldown = getCooldown(Task.HOANG_VUC, user.vip)
    }

    async trigger() {
        try {
            const { user_id } = Better_Messages || {}
            if (!this.page) this.page = await loadPage(DOMAIN + '/hoang-vuc')
            if (await this.claimChest()) {
                this.page = await loadPage(DOMAIN + '/hoang-vuc')
                return await this.trigger()
            }
            const nonce = this.page.html.match(/var\s+ajax_boss_nonce\s*=\s*'([^']+)'/)?.[1]
            const hasBoss = this.page.doc.getElementById('battle-button')
            if (!hasBoss) return logger.log(`🟡 [Hoang Vực] - Boss chưa mở.`)
            const match = this.page.doc.querySelector('.remaining-attacks')?.textContent?.match(/\d+/)
            const remaining = match ? parseInt(match[0] || '0', 10) : 0
            if (remaining === 0) {
                this.user.hoangvuc = { attack: 5, change: true }
                return logger.log(`🟢 [Hoang Vực] - Đã hoàn thành.`)
            }
            if (typeof this.user.hoangvuc !== 'object' || this.user.hoangvuc === null) {
                this.user.hoangvuc = {}
            }
this.user.hoangvuc.attack = Math.max(0, 5 - remaining)
            if (this.user.hoangvuc.change !== true) {
                const DamageStatus = { decrease: 0, normal: 1, increase: 2 }
                const multiplier = { decrease: 0.85, normal: 1.0, increase: 1.15 }

                const boss_element = (this.page.doc.querySelector('.boss-name')?.className.match(/boss-(?!name)(\w+)/) || [])[1]
                const damageInfo = this.page.doc.querySelector('.damage-info span')
                let hasFreeChange = this.page.doc.querySelector('#user-free-change-status')?.textContent.trim() !== ''
                let status = 'normal'
                if (damageInfo?.classList.contains('increase-damage')) {
                    status = 'increase'
                } else if (damageInfo?.classList.contains('decrease-damage')) {
                    status = 'decrease'
                }
                logger.log(`🫥 [Hoang Vực] - Trạng thái hiện tại: ${status}`)
                let setting = { status: 'normal', ho_than_phu: false }
                const history = await this.getAttackHistory(nonce)
                const count = history.history.length
                const candidates = [
                    { status: "decrease", ho_than_phu: false },
                    { status: "decrease", ho_than_phu: true },
                    { status: "normal", ho_than_phu: false },
                    { status: "normal", ho_than_phu: true },
                    { status: "increase", ho_than_phu: false },
                    { status: "increase", ho_than_phu: true },
                ]
                    .filter(candidate => DamageStatus[status] <= DamageStatus[candidate.status])
                    .map(candidate => {
                        const min_damage = (candidate.ho_than_phu ? 460 : 440) * multiplier[candidate.status] * remaining
                        return { ...candidate, min_damage: Math.round(min_damage) }
                    }).sort((lhs, rhs) => lhs.min_damage - rhs.min_damage)
                if (count >= 15) {
                    const target = count >= 20 ? 12000 : 9000
                    const required = Math.max(0, target - history.total_damage)
                    const chosen = candidates.find(candidate => required <= candidate.min_damage)
                    if (chosen) {
                        const isSkipChange = target === 9000 && bossSkipChangeIds.includes(String(user_id))
                        if (!isSkipChange || status === chosen.status) {
                            setting = { status: chosen.status, ho_than_phu: chosen.ho_than_phu }
                            logger.log(`🎯 [Hoang Vực] - Mục tiêu: ${target} | Hiện tại: ${history.total_damage} | Số lượt: ${remaining} | Chọn: ${JSON.stringify(setting)}`)
                        }
                    } else {
                        logger.log(`🎯 [Hoang Vực] - Mục tiêu: ${target} | Hiện tại: ${history.total_damage} | Số lượt: ${remaining} | Không khả thi.`)
                    }
                }
                while ((hasFreeChange && status !== 'increase') || status === 'decrease' || DamageStatus[status] < DamageStatus[setting.status]) {
                    status = await this.changeUserElement(nonce, boss_element)
                    hasFreeChange = false
                }
                let items = null
                const hasHoThanPhu = this.page.doc.getElementById('ho-than-phu-container') != null
                if (setting.ho_than_phu && !hasHoThanPhu) {
                    if (!items) items = await this.getUserInventoryItems()
                    const hothanphu = items.find(item => item.item_type === 'ho_than_phu')
                    if (hothanphu) await this.handleItem(nonce, 'activate_phu_item', hothanphu, 1)
                }
                this.user.hoangvuc.change = true
            }
            const distance = await this.getNextAttackTime(remaining)
            if (distance == null) return this.user.last_hoangvuc = Date.now()
            if (distance > 0) return this.user.last_hoangvuc = Date.now() + Math.max(0, distance) - this.cooldown
            const bossId = this.page.html.match(/boss_id\s*==\s*"(\d+)"/)?.[1]
            if (await this.attackBoss(nonce, bossId, remaining)) this.user.hoangvuc.attack += 1
            this.user.last_hoangvuc = Date.now()
        } catch (error) {
            logger.log(`🔴 [Hoang Vực] - Lỗi "trigger": ${error.message}`)
        }
    }
    async claimChest() {
        if (!this.page) this.page = await loadPage(DOMAIN + '/hoang-vuc')
        const hasReward = !!this.page.doc.querySelector('#reward-button')
        if (!hasReward) return false
        const nonce = this.page.html.match(/var\s+ajax_boss_nonce\s*=\s*'([^']+)'/)?.[1]
        if (!nonce) return logger.log(`🔴 [Hoang Vực] - Không tìm thấy nonce claim_chest.`)
        const result = await postRequest(ADMIN_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'claim_chest', nonce })
        })
        if (result.error) {
            logger.log(`❌ [Hoang Vực] - ${result.error}`)
        } else {
            logger.log(`✅ [Hoang Vực] - Nhận thưởng thành công.`)
            const rewards = result.total_rewards || {}
            const rewardLogs = []
            if (rewards.tu_vi) rewardLogs.push(`✨ Tu Vi: ${rewards.tu_vi}`)
            if (rewards.tinh_thach) rewardLogs.push(`💎 Tinh Thạch: ${rewards.tinh_thach}`)
            if (rewards.tinh_huyet) rewardLogs.push(`🩸 Tinh Huyết: ${rewards.tinh_huyet}`)
            if (rewards.tien_ngoc) rewardLogs.push(`🔮 Tiên Ngọc: ${rewards.tien_ngoc}`)
            if (rewardLogs.length) logger.log(rewardLogs.join(' | '))
        }
        return true
    }

    async getNextAttackTime(remaining) {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'get_next_attack_time' })
        })
        if (result?.success && typeof result.data === 'number') {
            const now = Date.now()
            const distance = result.data - now
            const total = Math.floor(distance / 1000)
            const minutes = String(Math.floor((total % 3600) / 60)).padStart(2, '0')
            const seconds = String(total % 60).padStart(2, '0')
            if (distance > 0) logger.log(`🟡 [Hoang Vực] - Chưa đến thời gian đánh (${minutes}:${seconds}) - Còn lại ${remaining} lượt.`)
            return distance
        }
        logger.log(`🟡 [Hoang Vực] - Không xác định được thời gian đánh - Còn lại ${remaining} lượt.`)
        return null
    }

    async attackBoss(nonce, bossId, remaining) {
        if (!nonce) return logger.log(`🔴 [Hoang Vực] - Không tìm thấy nonce attack_boss.`)
        if (!bossId) return logger.log(`🔴 [Hoang Vực] - Không tìm thấy bossId attack_boss.`)
        const requestId = 'req_' + Math.random().toString(36).slice(2, 11) + '_' + Date.now()
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'attack_boss', boss_id: bossId, nonce, request_id: requestId })
        })
        const message = result?.success === true
            ? `🟢 [Hoang Vực] - Tấn công thành công - Còn lại ${remaining - 1} lượt.`
            : `🔴 [Hoang Vực] - Tấn công thất bại - ${result?.data?.error} - Còn lại ${remaining} lượt.`
        logger.log(message)
        return !!result?.success
    }

    async changeUserElement(nonce, boss_element) {
        if (!nonce) return logger.log(`🔴 [Hoang Vực] - Không tìm thấy nonce change_user_element.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'change_user_element', nonce })
        })
        const message = result?.success === true
            ? `🟢 [Hoang Vực] - Thay đổi ngũ hành thành công - ${result?.data?.new_element_name}`
            : `🔴 [Hoang Vực] - Thay đổi ngũ hành thất bại - ${result?.data?.error}`
        logger.log(message)
        const elements = {
            'kim': { 'khac': 'moc', 'bi_khac': 'hoa' },
            'moc': { 'khac': 'tho', 'bi_khac': 'kim' },
            'thuy': { 'khac': 'hoa', 'bi_khac': 'tho' },
            'hoa': { 'khac': 'kim', 'bi_khac': 'thuy' },
            'tho': { 'khac': 'thuy', 'bi_khac': 'moc' }
        }
        const user_element = result?.data?.new_element
        const element = elements[user_element]
        if (element) {
            if (element.khac === boss_element) return 'increase'
            if (element.bi_khac === boss_element) return 'decrease'
        }
        return 'normal'
    }

    async getAttackHistory(nonce) {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'get_attack_history', nonce })
        })
        const { history = [], total_damage = "0" } = result?.data || {}
        return { history, total_damage: parseInt(total_damage, 10) }
    }

    async getUserInventoryItems() {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'get_user_inventory_items' })
        })
        return result?.data || []
    }

    // action: [activate_phu_item, open_chest_item]
    async handleItem(nonce, action, item, quantity) {
        if (!nonce) return logger.log(`🔴 [Hoang Vực] - Không tìm thấy nonce activate_phu_item.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: action, item_id: item.id, item_type: item.item_type, quantity, nonce })
        })
        if (result?.success) {
            logger.log(`✅ [Hoang Vực] - ${result.data?.message || result.data || 'Kích hoạt thành công.'}`)
        } else {
            logger.log(`❌ [Hoang Vực] - ${result?.data?.message || result?.message || result?.data || 'Kích hoạt không thành công.'}`)
        }
        const rewards = result?.data?.rewards || []
        const rewardLogs = rewards.map(reward => `✨ ${reward.name}: ${reward.amount}`)
        if (rewardLogs.length) logger.log(rewardLogs.join(' | '))
        return !!result?.success
    }
}

class LuanVo {
    constructor(user, page = null) {
        this.user = user
        this.page = page
        this.battleData = null
    }

    async triggerReceive(isOn = true) {
        try {
            if (this.battleData === null) this.battleData = await this.prepareTrigger()
            if (this.battleData === null || this.battleData.reward) return
            if (this.battleData.received >= 5) return logger.log(`🟡 [Luận Võ] - Đã nhận tối đa.`)
            const receivedBadgeValue = parseInt(this.page.doc.querySelector('#ViewReceivedChallengesBtn .notification-badge')?.textContent.trim() || '0')
            if (isOn && receivedBadgeValue > 0) {
                await this.rejectAllReceivedChallenges()
            }
            if (this.battleData.isAutoOn !== isOn) {
                await this.toggleAutoAccept(isOn)
            } else {
                logger.log(`🟢 [Luận Võ] - Đang ${isOn ? 'bật' : 'tắt'} tự động khiêu chiến.`)
            }
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "triggerReceive": ${error.message}`)
            return { challenges: [], nonce: null }
        }
    }

    async triggerSend({ following = true, online = false, retries = 3 } = {}) {
        try {
            if (this.battleData === null) this.battleData = await this.prepareTrigger()
            if (this.battleData === null || this.battleData.reward) return
            if (this.battleData.sent >= 5) return logger.log(`🟢 [Luận Võ] - Đã gửi tối đa.`)
            await this.loadPageIfNeeded()
            const sentBadgeValue = parseInt(this.page.doc.querySelector('#ViewSentChallengesBtn .notification-badge')?.textContent.trim() || '0')
            if (sentBadgeValue > 0) {
                await this.rejectAllSentChallenges()
            }
            const variableJSON = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig')
            let users = []
            let targetUsers
            if (following) {
                users = await this.getUsers({ action: '/get-following-users', nonce: variableJSON.nonce, loadmore: true })
                targetUsers = users.filter(user => user.challenges_remaining > 0)
            } else if (online) {
                users = await this.getUsers({ action: '/online-users', nonce: variableJSON.nonce, loadmore: false })
                targetUsers = users.filter(user => user.auto_accept && user.challenges_remaining > 0)
            } else {
                return logger.log(`🟡 [Luận Võ] - Chưa hoàn thành gửi khiêu chiến.`)
            }
            let index = 0
            while (index < targetUsers.length && this.battleData.sent < 5) {
                const target = targetUsers[index]
                if (!target.auto_accept) {
                    index++
                    continue
                }
                if (target.challenges_remaining < 1) {
                    targetUsers.splice(index, 1)
                    continue
                }
                const sentData = await this.sendChallenge(target, variableJSON.nonce)
                if (typeof sentData === 'string' && sentData.toLowerCase().includes('tối đa')) {
                    if (sentData.toLowerCase().includes('nhận tối đa')) {
                        targetUsers.splice(index, 1)
                        continue
                    }
                    logger.log(`🟡 [Luận Võ] - Đã gửi tối đa - ${sentData}`)
                    await this.loadPageIfNeeded(true)
                    this.battleData = await this.prepareTrigger()
                    return
                }
                if (typeof sentData === 'object' && sentData !== null) {
                    const sentResult = await this.approveChallenge(sentData, variableJSON.nonce)
                    if (!sentResult) {
                        targetUsers.splice(index, 1)
                        continue
                    }
                    let remaining = parseInt(sentResult?.received_remaining, 10) || 0
                    target.challenges_remaining = Math.min(target.challenges_remaining - 1, remaining)
                    this.battleData.sent++
                    this.user.luanvo.sent = (this.user.luanvo.sent || 0) + 1
                } else {
                    targetUsers.splice(index, 1)
                }
                if (index < targetUsers.length && this.battleData.sent < 5) await sleep(5000)
            }
            if (this.battleData.sent >= 5) {
                await this.loadPageIfNeeded(true)
                this.battleData = await this.prepareTrigger()
                return logger.log(`🟢 [Luận Võ] - Đã gửi tối đa.`)
            }
            if (!targetUsers.length && retries > 0) return this.triggerSend({ following: false, online: true, retries: retries - 1 })
            logger.log(`🟡 [Luận Võ] - Chưa hoàn thành gửi khiêu chiến.`)
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "triggerSend": ${error.message}`)
            return { challenges: [], nonce: null }
        }
    }

    async rejectAllReceivedChallenges() {
        const { challenges, nonce } = await this.getReceivedChallenges()
        for (const challenge of challenges) {
            await this.rejectReceivedChallenge(challenge, nonce)
        }
    }

    async rejectAllSentChallenges() {
        const { challenges, nonce } = await this.getSentChallenges()
        for (const challenge of challenges) {
            await this.rejectSentChallenge(challenge, nonce)
        }
    }

    async prepareTrigger() {
        const getValue = (label, doc) => {
            const p = Array.from(doc.querySelectorAll('p')).find(p => p.textContent.trim().startsWith(label))
            const text = p?.querySelector('span.highlight')?.textContent || ''
            const match = text.match(/^(\d+)/)
            return match ? parseInt(match[1]) : 0
        }

        const luanvo = this.user.luanvo || (this.user.luanvo = {})
        if (luanvo.reward) {
            logger.log(`🟢 [Luận Võ] - Đã nhận thưởng.`)
            return { sent: 5, received: 5, isAutoOn: true, reward: true }
        }
        await this.loadPageIfNeeded()
        if (this.page.doc.getElementById('joinBattleImg')) {
            if (await this.joinBattle()) {
                this.page = await loadPage(DOMAIN + '/luan-vo-duong')
            } else {
                this.user.luanvo = luanvo
                return null
            }
        }
        const sent = getValue('Đã gửi:', this.page.doc)
        const received = getValue('Đã nhận:', this.page.doc)
        const isAutoOn = !!this.page.doc.getElementById('auto_accept_toggle')?.checked
        let reward = false
        if (sent >= 5 && received >= 5) {
            const rewardBtn = this.page.doc.getElementById('receive-reward-btn')
            const nonce = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig').nonce
            if (rewardBtn && nonce) {
                reward = await this.receiveReward(nonce)
            } else {
                logger.log(`🟢 [Luận Võ] - Đã nhận thưởng.`)
                reward = true
            }
        }
        this.user.luanvo = { sent, received, reward }
        return { sent, received, isAutoOn, reward }
    }

    async loadPageIfNeeded(force = false) {
        if (!this.page || force) this.page = await loadPage(DOMAIN + '/luan-vo-duong')
    }

    async getUsers({ action, nonce, page = 1, current = [], loadmore, maxPages = 10 }) {
        try {
            if (!nonce) {
                logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce ${action}.`)
                return []
            }
            const result = await postRequest(LUANVO_URL + action, {
                headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
                body: JSON.stringify({ page }),
            }, [400, 404])
            const { success, data } = result || {}
            const { users, load_more } = data || {}
            if (!success || !users) return current
            const allUsers = [...current, ...users]
            if (load_more === true && loadmore) {
                if (page >= maxPages) {
                    return allUsers
                }
                return await this.getUsers({ action, nonce, page: page + 1, current: allUsers, loadmore: true })
            }
            return allUsers
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "getUsers": ${error.message}`)
            return current
        }
    }

    async getReceivedChallenges() {
        try {
            await this.loadPageIfNeeded()
            const variableJSON = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig')
            const nonce = variableJSON.nonce
            if (!nonce) {
                logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce get_received_challenges.`)
                return { challenges: [], nonce: null }
            }
            const result = await postRequest(LUANVO_URL + '/get-received-challenges', {
                headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce }
            })
            if (!result?.success || !result.data?.html) {
                logger.log(`🔴 [Luận Võ] - Phản hồi không hợp lệ từ get_received_challenges.`)
                return { challenges: [], nonce }
            }
            const doc = new DOMParser().parseFromString(result.data.html, 'text/html')
            const challenges = Array.from(doc.querySelectorAll('tbody tr')).map(row => {
                const request = row.querySelector('.approve-request')
                const name = row.querySelector('.challenger-name')?.textContent.trim() || ''
                const target_user_id = request?.getAttribute('data-user-id').trim() || ''
                const challenge_id = request?.getAttribute('data-challenge-id').trim() || ''
                return { name, target_user_id, challenge_id }
            }).filter(challenge => challenge.target_user_id && challenge.challenge_id)
            return { challenges, nonce }
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "getReceivedChallenges": ${error.message}`)
            return { challenges: [], nonce: null }
        }
    }

    async getSentChallenges() {
        try {
            await this.loadPageIfNeeded()
            const variableJSON = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig')
            const nonce = variableJSON.nonce
            if (!nonce) {
                logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce get-sent-challenges.`)
                return { challenges: [], nonce: null }
            }
            const result = await postRequest(LUANVO_URL + '/get-sent-challenges', {
                headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce }
            })
            if (!result?.success || !result.data?.html) {
                logger.log(`🔴 [Luận Võ] - Phản hồi không hợp lệ từ get-sent-challenges.`)
                return { challenges: [], nonce }
            }
            const doc = new DOMParser().parseFromString(result.data.html, 'text/html')
            const challenges = Array.from(doc.querySelectorAll('tbody tr')).map(row => {
                const request = row.querySelector('.reject-request')
                const name = row.querySelector('.challenger-name')?.textContent.trim() || ''
                const target_user_id = request?.getAttribute('data-user-id').trim() || ''
                const challenge_id = request?.getAttribute('data-challenge-id').trim() || ''
                return { name, target_user_id, challenge_id }
            }).filter(challenge => challenge.target_user_id && challenge.challenge_id)
            return { challenges, nonce }
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "getSentChallenges": ${error.message}`)
            return { challenges: [], nonce: null }
        }
    }

    async rejectReceivedChallenge(challenge, nonce) {
        if (!nonce) return logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce reject-challenge`)
        const result = await postRequest(LUANVO_URL + '/reject-challenge', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
            body: JSON.stringify({ target_user_id: challenge.target_user_id, challenge_id: challenge.challenge_id })
        })
        const message = result?.success === true
            ? `✅ [Luận Võ] - Từ chối thành công yêu cầu của ${challenge.name} (${challenge.target_user_id})`
            : `❌ [Luận Võ] - Từ chối thất bại yêu cầu của ${challenge.name} (${challenge.target_user_id})`
        logger.log(message)
    }

    async rejectSentChallenge(challenge, nonce) {
        if (!nonce) return logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce cancel-challenge`)
        const result = await postRequest(LUANVO_URL + '/cancel-challenge', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
            body: JSON.stringify({ target_user_id: challenge.target_user_id, challenge_id: challenge.challenge_id })
        })
        const message = result?.success === true
            ? `✅ [Luận Võ] - Huỷ thành công yêu cầu đến ${challenge.name} (${challenge.target_user_id})`
            : `❌ [Luận Võ] - Huỷ thất bại yêu cầu đến ${challenge.name} (${challenge.target_user_id})`
        logger.log(message)
    }

    async sendChallenge(user, nonce) {
        if (!nonce) {
            logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce send_challenge`)
            return null
        }
        const result = await postRequest(LUANVO_URL + '/send-challenge', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
            body: JSON.stringify({ target_user_id: user.id })
        })
        const message = result?.success === true && result.data
            ? `⚔️ [Luận Võ] Đã gửi khiêu chiến đến ${user.name} (${user.id})`
            : `❌ [Luận Võ] Gửi khiêu chiến không thành công đến ${user.name} (${user.id})`
        logger.log(message)
        return result.data
    }

    async approveChallenge(challenge, nonce) {
        if (!nonce) {
            logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce auto-approve-challenge`)
            return null
        }
        const result = await postRequest(LUANVO_URL + '/auto-approve-challenge', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
            body: JSON.stringify({ target_user_id: challenge.target_user_id, challenge_id: challenge.challenge_id })
        })
        const message = result?.success === true && result.data
            ? `✅ [Luận Võ] Gửi khiêu chiến hoàn thành.`
            : `❌ [Luận Võ] Gửi khiêu chiến bất thành.`
        logger.log(message)
        return result.data
    }

    async joinBattle() {
        await this.loadPageIfNeeded()
        const nonce = Better_Messages?.nonce
        if (!nonce) {
            logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce join_battle_new.`)
            return false
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce },
            body: JSON.stringify({ action: 'join_battle_new' })
        })
        const message = result?.success === true
            ? `✅ [Luận Võ] - Tham gia thành công.`
            : `❌ [Luận Võ] - Tham gia thất bại.`
        logger.log(message)
        return !!result?.success
    }

    async toggleAutoAccept(isOn) {
        await this.loadPageIfNeeded()
        const nonce = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig').nonce
        if (!nonce) return logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce toggle_auto_accept.`)
        const result = await postRequest(LUANVO_URL + '/toggle-auto-accept', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce }
        })
        const message = result?.success === true
            ? `✅ [Luận Võ] - ${result.message || ''}`
            : `❌ [Luận Võ] - ${isOn ? 'Bật' : 'Tắt'} tự động nhận khiêu chiến thất bại.`
        this.battleData.isAutoOn = message.toLowerCase().includes('bật')
        logger.log(message)
    }

    async receiveReward(nonce) {
        if (!nonce) {
            logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce receive-reward.`)
            return false
        }
        const result = await postRequest(LUANVO_URL + '/receive-reward', {
            headers: { 'Content-Type': 'application/json', 'x-wp-nonce': nonce }
        })
        const message = result?.success === true
            ? `✅ [Luận Võ] - Nhận thưởng thành công - ${result.message}`
            : `❌ [Luận Võ] - Nhận thưởng thất bại - ${result?.message}`
        logger.log(message)
        return !!result?.success
    }

    async triggerFollow(ids, clean = false) {
        try {
            await this.loadPageIfNeeded()
            const variableJSON = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig')
            if (clean) {
                const users = await this.getUsers({ action: 'get_following_users', nonce: variableJSON.nonce, loadmore: true })
                const ids = users.map(user => user.id)
                await this.triggerUnfollow(ids, variableJSON)
            }
            const currentId = parseInt(variableJSON.current_user_id)
            if (!variableJSON.nonce) return logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce follow`)
            for (const id of ids) {
                if (id === currentId) continue
                const result = await postRequest(LUANVO_URL + '/follow', {
                    headers: { 'Content-Type': 'application/json', 'x-wp-nonce': variableJSON.nonce },
                    body: JSON.stringify({ unfollow_user_id: id })
                })
                const message = result?.success === true
                    ? `✅ [Luận Võ] - Theo dõi thành công ID: ${id}`
                    : `❌ [Luận Võ] - Theo dõi thất bại ID: ${id}`
                logger.log(message)
            }
            logger.log(`🟢 [Luận Võ] - Hoàn thành xử lý theo dõi.`)
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "triggerFollow": ${error.message}`)
        }
    }

    async triggerUnfollow(ids, variableJSON = null) {
        try {
            await this.loadPageIfNeeded()
            if (variableJSON === null) variableJSON = parseVariableJSON(this.page, 'luan-vo-main-js-extra', 'LuanVoConfig')
            if (!variableJSON.nonce) return logger.log(`🔴 [Luận Võ] - Không tìm thấy nonce unfollow`)
            const currentId = parseInt(variableJSON.current_user_id)
            for (let id of ids) {
                if (id === currentId) continue
                const result = await postRequest(LUANVO_URL + '/unfollow', {
                    headers: { 'Content-Type': 'application/json', 'x-wp-nonce': variableJSON.nonce },
                    body: JSON.stringify({ unfollow_user_id: id })
                })
                const message = result?.success === true
                    ? `✅ [Luận Võ] - Hủy theo dõi thành công ID: ${id}`
                    : `❌ [Luận Võ] - Hủy theo dõi thất bại ID: ${id}`
                logger.log(message)
            }
            logger.log(`🟢 [Luận Võ] - Hoàn thành xử lý hủy theo dõi.`)
        } catch (error) {
            logger.log(`🔴 [Luận Võ] - Lỗi "triggerUnfollow": ${error.message}`)
        }
    }
}

class PhucLoiDuong {
    constructor(user) {
        this.user = user
        this.cooldown = 60 * 60 * 1000
    }

    async trigger() {
        try {
            if (this.user.phucloi === 4) return logger.log(`🟢 [Phúc Lợi Đường] - Đã hoàn thành.`)
            const page = await loadPage(DOMAIN + '/phuc-loi-duong')
            await this.claimBonusReward(page)
            const security = page.html.match(/get_next_time_pl[\s\S]*?security\s*:\s*'([^']+)'/)?.[1]
            const { level, distance } = await this.getNextTime(security)
            if (level === null) return this.user.last_phucloi = Date.now()
            if (level === 4) return this.user.phucloi = 4
            this.user.phucloi = Math.max(0, level - 1)
            if (distance > 0) return this.user.last_phucloi = Date.now() + Math.max(0, distance) - this.cooldown
            if (await this.openChest(security, level + 1)) this.user.phucloi = level + 1
            this.user.last_phucloi = Date.now()
        } catch (error) {
            logger.log(`🔴 [Phúc Lợi Đường] - Lỗi "trigger": ${error.message}`)
        }
    }

    async claimBonusReward(page) {
        async function claimRequest(id, security) {
            const result = await postRequest(HH3D_AJAX_URL, {
                headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
                body: new URLSearchParams({ action: 'claim_bonus_reward', chest_id: id, security })
            })
            logger.log(`${result?.success === true ? '✅' : '❌'} [Phúc Lợi Đường] - ${result?.data?.message || result}`)
            return !!result?.success
        }

        if (!page) page = await loadPage(DOMAIN + '/phuc-loi-duong')
        const ids = Array.from(page.doc.querySelectorAll('.reward-progress-container .milestone'))
            .map(milestone => {
                const giftBox = milestone.querySelector('.gift-box')
                if (!giftBox) return null
                const classList = giftBox.classList
                const isActive = classList.contains('active')
                const isReceived = classList.contains('received-reward')
                const pointerEvents = (giftBox.getAttribute('style') || giftBox.getAttribute('data-cfstyle') || '').match(/pointer-events\s*:\s*([a-zA-Z-]+)/)
                const pointerValue = pointerEvents?.[1]?.trim()
                return (isActive && !isReceived && (!pointerValue || pointerValue === 'auto'))
                    ? milestone.getAttribute('data-id')
                    : null
            })
            .filter(Boolean)
        const requestData = parseRequestData(page.html)
        const security = requestData.find(value => value.action === 'claim_bonus_reward')?.security
        if (!security) return logger.log(`🔴 [Phúc Lợi Đường] - Không tìm thấy security claim_bonus_reward.`)
        for (const id of ids) {
            if (await claimRequest(id, security) && Number(id) === 3) {
                return await claimRequest(4, security)
            }
        }
    }

    async getNextTime(security) {
        if (!security) return logger.log(`🔴 [Phúc Lợi Đường] - Không tìm thấy security get_next_time_pl`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'get_next_time_pl', security })
        })
        const level = parseInt(result?.data?.chest_level, 10)
        const time = result?.data?.time
        if (result?.success === true && !isNaN(level)) {
            if (level >= 4) {
                logger.log(`🟢 [Phúc Lợi Đường] - Đã mở đủ 4 rương.`)
                return { level: Math.max(4, level), distance: null }
            }
            if (time !== '00:00') {
                const [minutes, seconds] = time.split(':').map((value, index) => {
                    const number = parseInt(value, 10)
                    return Number.isFinite(number) ? number : (index === 0 ? 60 : 0)
                })
                const distance = (minutes * 60 + seconds) * 1000
                logger.log(`🟡 [Phúc Lợi Đường] - Chưa đến thời gian mở | ${time || '--'}`)
                return { level: level, distance: distance }
            }
            return { level: level, distance: 0 }
        }
        logger.log(`🔴 [Phúc Lợi Đường] - Không lấy được dữ liệu get_next_time_pl.`)
        return { level: null, distance: null }
    }

    async openChest(security, next) {
        if (!security) return logger.log(`🔴 [Phúc Lợi Đường] - Không tìm thấy security open_chest_pl.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'open_chest_pl', security, chest_id: next })
        })
        const message = result?.success === true
            ? `🟢 [Phúc Lợi Đường] - Rương ${next} - ${result.data?.message}`
            : `🔴 [Phúc Lợi Đường] - Không thành công - ${result?.data?.message}`
        logger.log(message)
        return !!result?.success
    }
}

class DoThach {
    constructor(indices, amount = 20) {
        this.indices = Array.isArray(indices) ? indices : (typeof indices === 'number' ? [indices] : [1, 2])
        this.amount = amount
        this.tienngoc = 0
    }

    async trigger() {
        try {
            const page = await loadPage(DOMAIN + '/do-thach-hh3d')
            const userData = parseUserData(page)
            this.tienngoc = userData.tien_ngoc?.value || 0
            const requestData = parseRequestData(page.html)
            const hasGift = page.doc.querySelector('.custom-button.gift-button')
            if (hasGift) await this.giveNewbieGift(requestData)
            const hasReward = page.doc.querySelector('#claim-reward-button')
            if (hasReward) {
                await this.claimDoThachReward(requestData)
                return await this.trigger()
            }
            const stones = await this.loadDoThachData(requestData)
            if (!stones.length) return
            stones.sort((lhs, rhs) => (Number(rhs.reward_multiplier) || 0) - (Number(lhs.reward_multiplier) || 0))
            const placedStones = stones.filter(stone => stone.bet_placed === true)
            const remainingStones = stones.filter((_, index) => this.indices.includes(index + 1) && !placedStones.includes(stones[index]))
            const targetStones = placedStones.concat(remainingStones).slice(0, 2)
            for (const stone of targetStones) {
                if (stone.bet_placed === true) {
                    logger.log(`✅ [Đổ Thạch] - Đã đặt cược vào ${stone.name} (x${stone.reward_multiplier})`)
                } else {
                    await this.placeDoThachBet(requestData, stone, this.amount)
                }
            }
        } catch (error) {
            logger.log(`🔴 [Đổ Thạch] - Lỗi "trigger": ${error.message}`)
        }
    }

    async giveNewbieGift(requestData) {
        const security = requestData.find(value => value.action === 'give_newbie_gift')?.security
        if (!security) return logger.log(`🔴 [Đổ Thạch] - Không tìm thấy security give_newbie_gift.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'give_newbie_gift', security })
        })
        const message = result?.success === true
            ? `🟢 [Đổ Thạch] - Nhận quà tân thủ thành công`
            : `🔴 [Đổ Thạch] - Nhận quà tân thủ thất bại - ${result?.data || result}`
        logger.log(message)
    }

    async claimDoThachReward(requestData) {
        const security = requestData.find(value => value.action === 'claim_do_thach_reward')?.security
        if (!security) return logger.log(`🔴 [Đổ Thạch] - Không tìm thấy security claim_do_thach_reward.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'claim_do_thach_reward', security })
        })
        const message = result?.success === true
            ? `🟢 [Đổ Thạch] - Nhận thưởng thành công - ${result?.data?.message}`
            : `🔴 [Đổ Thạch] - ${result?.data?.message || result}`
        logger.log(message)
    }

    async loadDoThachData(requestData) {
        const security = requestData.find(value => value.action === 'load_do_thach_data')?.security
        if (!security) return logger.log(`🔴 [Đổ Thạch] - Không tìm thấy security load_do_thach_data.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'load_do_thach_data', security })
        })
        const { success, data } = result || {}
        const { stones, is_reward_time, winning_stone_id } = data || {}
        if (!success || !stones) {
            logger.log(`🔴 [Đổ Thạch] - Không lấy được dữ liệu load_do_thach_data.`)
            return []
        }
        if (!is_reward_time) return stones
        const rewardStone = stones.find(stone => stone.stone_id == winning_stone_id && stone.bet_placed === true)
        if (!rewardStone) {
            logger.log(`🟡 [Đổ Thạch] - Không có thưởng.`)
            return []
        }
        if (rewardStone.reward_claimed === true) {
            logger.log(`🟢 [Đổ Thạch] - Đã nhận thưởng.`)
            return []
        }
        await this.claimDoThachReward(requestData)
        return []
    }

    async placeDoThachBet(requestData, stone) {
        const security = requestData.find(value => value.action === 'place_do_thach_bet')?.security
        if (!security) return logger.log(`🔴 [Đổ Thạch] - Không tìm thấy security place_do_thach_bet`)
        if (this.tienngoc < this.amount) return logger.log(`🔴 [Đổ Thạch] - Hết Tiên Ngọc - Còn lại ${this.tienngoc}`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'place_do_thach_bet', security, stone_id: stone.stone_id, bet_amount: this.amount })
        })
        const message = result?.success === true
            ? `🟢 [Đổ Thạch] - Đặt cược thành công - ${stone.name} (x${stone.reward_multiplier}) - ${this.amount} Tiên Ngọc`
            : `🔴 [Đổ Thạch] - Đặt cược thất bại - ${result?.data || result}`
        logger.log(message)
        if (result?.success === true) this.tienngoc -= this.amount
    }
}

class ThiLuyenTongMon {
    constructor(user) {
        this.user = user
        this.cooldown = 60 * 60 * 1000
    }

    async trigger() {
        try {
            if (this.user.thiluyen === 3) return logger.log(`🟢 [Thí Luyện Tông Môn] - Đã hoàn thành.`)
            const page = await loadPage(DOMAIN + '/thi-luyen-tong-mon-hh3d')
            const security = page.html.match(/get_remaining_time_tltm[\s\S]*?security\s*:\s*'([^']+)'/)?.[1]
            const distance = await this.getRemainingTimeTLTM(security)
            if (distance === null) return this.user.last_thiluyen = Date.now()
            if (distance > 0) return this.user.last_thiluyen = Date.now() + Math.max(0, distance) - this.cooldown
            const count = await this.openChest(security)
            if (count) this.user.thiluyen = Math.min(3, (this.user.thiluyen || 0) + count)
            this.user.last_thiluyen = Date.now()
        } catch (error) {
            logger.log(`🔴 [Thí Luyện Tông Môn] - Lỗi "trigger": ${error.message}`)
        }
    }

    async getRemainingTimeTLTM(security) {
        if (!security) return logger.log(`🔴 [Thí Luyện Tông Môn] - Không tìm thấy security get_remaining_time_tltm`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'get_remaining_time_tltm', security })
        })
        const time = result.data?.time_remaining
        if (result?.success === true && typeof time === 'string') {
            if (time !== '00:00') {
                const [minutes, seconds] = time.split(':').map((value, index) => {
                    const number = parseInt(value, 10)
                    return Number.isFinite(number) ? number : (index === 0 ? 60 : 0)
                })
                const distance = (minutes * 60 + seconds) * 1000
                logger.log(`🟡 [Thí Luyện Tông Môn] - Chưa đến thời gian mở | ${time}`)
                return distance
            }
            return 0
        }
        logger.log(`🔴 [Thí Luyện Tông Môn] - Không lấy được dữ liệu get_remaining_time_tltm`)
        return null
    }

    async openChest(security) {
        if (!security) return logger.log(`🔴 [Thí Luyện Tông Môn] - Không tìm thấy security open_chest_tltm.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'open_chest_tltm', security })
        })
        if (result?.success === true) {
            logger.log(`🟢 [Thí Luyện Tông Môn] - Mở thành công - ${result.data?.message}`)
            return 1
        }
        const message = result.data?.message
        if (message && message.toLowerCase().includes('đã hoàn thành')) {
            logger.log(`🟡 [Thí Luyện Tông Môn] - ${message}`)
            return 3
        }
        logger.log(`🔴 [Thí Luyện Tông Môn] - Mở không thành công - ${message || result}`)
        return null
    }
}

class VanDap {
    constructor(user) {
        this.user = user
    }

    async trigger() {
        try {
            if (this.user.vandap === 5) return logger.log(`🟢 [Vấn Đáp] - Đã hoàn thành.`)
            const bank = Object.fromEntries(
                Object.entries(quizBank).map(([key, value]) => [normalize(key), value])
            )
            const questions = await this.loadQuizData()
            if (!questions.length) return
            for (const [index, value] of questions.entries()) {
                const correct = parseInt(value.is_correct, 10) || 0
                if (correct === 1) {
                    this.user.vandap = index + 1
                    logger.log(`✅ [Vấn Đáp] - Câu ${index + 1} ➤ Đúng`)
                } else if (correct === 2) {
                    this.user.vandap = index + 1
                    logger.log(`❌ [Vấn Đáp] - Câu ${index + 1} ➤ Sai`)
                } else {
                    const question = normalize(value.question)
                    const answer = bank[question] ?? ''
                    const options = value.options.map(option => typeof option === 'string' ? option : option.content)
                    const answerIndex = Math.max(0, Math.min(3, bestMatch(options, answer).bestIndex))
                    if (await this.saveQuizResult(value.id, answerIndex, index)) {
                        this.user.vandap = index + 1
                    } else {
                        return logger.log(`🟡 [Vấn Đáp] - Chưa hoàn thành.`)
                    }
                }
            }
            logger.log(`🟢 [Vấn Đáp] - Hoàn thành.`)
        } catch (error) {
            logger.log(`🔴 [Vấn Đáp] - Lỗi "trigger": ${error.message}`)
        }
    }

    async loadQuizData() {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'load_quiz_data' })
        })
        const { success, data = {} } = result || {}
        const { questions = [], completed } = data || {}
        if (!success || !questions.length) {
            logger.log('🔴 [Vấn Đáp] - Không lấy được dữ liệu load_quiz_data.')
            return []
        }
        if (completed) {
            logger.log('🟢 [Vấn Đáp] - Đã hoàn thành.')
            return []
        }
        return questions
    }

    async saveQuizResult(id, answer, index) {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'save_quiz_result', question_id: id, answer: answer })
        })
        if (result?.success === true) {
            const message = parseInt(result.data?.is_correct, 10) === 1
                ? `✅ [Vấn Đáp] - Câu ${index + 1} ➤ Đúng`
                : `❌ [Vấn Đáp] - Câu ${index + 1} ➤ Sai`
            logger.log(message)
            return true
        } else {
            logger.log(`⚠️ [Vấn Đáp] - Chưa trả lời câu ${index + 1}.`)
            return false
        }
    }
}

class TienDuyen {
    constructor(user, page = null) {
        this.user = user
        this.page = page
        this.tienngoc = 0
        this.tuvi = 0
    }

    async scanBlessing(tab = null, claimLiXi = true) {
        try {
            const { data: rooms = [], is_vip = false, unbless_count = 0, unopened_li_xi_count = 0 } = await this.getAllWeddings()
            if (rooms.length > 0) {
                const today = new Date().toISOString().slice(0, 10)
                const last = rooms[0].created_at?.slice?.(0, 10)
                this.user.last_wedding = (last === today) ? rooms[0].created_at : null
            } else {
                this.user.last_wedding = null
            }
            if (is_vip && (unbless_count > 0 || unopened_li_xi_count > 0)) {
                let success = false
                if (unbless_count > 0) {
                    success = success || await this.sendAllBlessings(unbless_count)
                }
                if (unopened_li_xi_count) {
                    success = success || await this.claimAllLiXis()
                }
                if (success) return await this.scanBlessing(tab, claimLiXi)
            }
            for (const room of rooms) {
                if (room.has_blessed !== true) {
                    logger.log(`⚠️ [Tiên Duyên] - Chưa chúc phúc phòng cưới ${room.wedding_room_id}.`)
                    if (this.tienngoc > 110 && this.tuvi > 9000) await this.triggerBlessing({ id: room.wedding_room_id, tab })
                } else if (room.has_sent_li_xi === true) {
                    if (claimLiXi && room.has_li_xi === true) await this.claimLiXi(room.wedding_room_id)
                } else {
                    logger.log(`⚠️ [Tiên Duyên] - Phòng cưới ${room.wedding_room_id} chưa phát Lì Xì.`)
                }
            }
            const message = rooms.length
                ? '🟢 [Tiên Duyên] - Đã quét xong.'
                : '🟡 [Tiên Duyên] - Không có phòng cưới nào.'
            logger.log(message)
        } catch (error) {
            logger.log(`🔴 [Tiên Duyên] - Lỗi "scanBlessing": ${error.message}`)
        }
    }

    async triggerGift() {
        try {
            const { nonce, user_id } = Better_Messages || {}
            const hoahong = this.user.hoahong || []
            const configuration = blessingGifts[String(user_id)]
            if (!configuration?.length) return logger.log(`🟡 [Tiên Duyên] - Không có cấu hình tặng hoa cho ${user_id}`)
            const targets = configuration.filter(target => {
                const record = hoahong.find(value => String(value.friend_id) === target.friend_id && value.cost_type === target.cost_type)
                return !record || record.sent < target.max
            })
            if (!targets.length) return logger.log(`🟢 [Tiên Duyên] - Đã gửi đủ Hoa Hồng.`)
            if (!this.page) {
                this.page = await loadPage(DOMAIN + '/tien-duyen')
                const userData = parseUserData(this.page)
                this.tienngoc = userData.tien_ngoc?.value || 0
                this.tuvi = userData.tu_vi?.value || 0
            }
            const friends = await this.getFriends(nonce)
            for (const { friend_id, cost_type, max } of targets) {
                if (cost_type == 'tien_ngoc' && this.tienngoc < 2000) continue
                const friend = friends.find(friend => String(friend.user_id) === String(friend_id))
                if (!friend) continue
                const remaining = Math.max(0, await this.checkGift(nonce, String(user_id), String(friend_id), cost_type))
                const sent = Math.max(0, (cost_type == 'tien_ngoc' ? 3 : 6) - remaining)
                let record = hoahong.find(value => String(value.friend_id) === String(friend_id) && value.cost_type === cost_type)
                if (record) {
                    record.sent = sent
                } else {
                    record = { friend_id, cost_type, sent }
                    hoahong.push(record)
                }
                const times = Math.min(max - sent, remaining)
                for (let i = 0; i < times; i++) {
                    if (await this.sendGift(nonce, String(friend_id), cost_type)) record.sent += 1
                }
            }
            this.user.hoahong = hoahong
        } catch (error) {
            logger.log(`🔴 [Tiên Duyên] - Lỗi "triggerGift": ${error.message}`)
        }
    }

    async triggerWish() {
        try {
            if (this.user.caunguyen === 1) return logger.log(`🟢 [Tiên Duyên] - Đã ước nguyện.`)
            if (!this.page) {
                this.page = await loadPage(DOMAIN + '/tien-duyen')
                const userData = parseUserData(this.page)
                this.tienngoc = userData.tien_ngoc?.value || 0
                this.tuvi = userData.tu_vi?.value || 0
            }
            if (this.page.doc.querySelector('.tien-duyen-btn.wish-tree-btn') === null) return
            const nonce = parseVariableJSON(this.page, 'better-messages-js-extra', 'Better_Messages').nonce
            const canWish = await this.checkWishTreeStatus(nonce)
            if (!canWish || await this.makeWishTree(nonce)) {
                this.user.caunguyen = 1
            }
        } catch (error) {
            logger.log(`🔴 [Tiên Duyên] - Lỗi "triggerWish": ${error.message}`)
        }
    }

    async triggerBlessing({ id, tab, retries = 5, delay = 10000, timeout = 15000 }) {
        const retry = async (reason = '') => {
            if (reason) logger.log(`↪️ [Tiên Duyên] - ${reason} ➤ Thử lại còn ${retries - 1} lần...`)
            if (tab && !tab.closed) tab.location.replace('about:blank')
            retries--
            await sleep(delay)
        }

        while (retries > 0) {
            const targetURLString = `${DOMAIN}/phong-cuoi?id=${id}`
            if (!tab || tab.closed) {
                const page = await loadPage(targetURLString)
                if (await this.sendBlessing(id, null, page.doc)) return
                await retry(`Chúc phúc phòng cưới ${id} thất bại`)
                continue
            }
            tab.location.replace(targetURLString)
            await sleep(250)
            const navigated = await new Promise(resolve => {
                const interval = setInterval(() => {
                    if (tab.location.href === targetURLString) {
                        clearInterval(interval)
                        resolve(true)
                    }
                }, 500)
                setTimeout(() => {
                    clearInterval(interval)
                    resolve(false)
                }, timeout)
            })
            if (!navigated) {
                await retry(`Không điều hướng được tới phòng cưới ${id}`)
                continue
            }
            try {
                const loaded = await this.waitForPage(id, tab, timeout)
                if (!loaded) {
                    await retry(`Không tải được trang phòng cưới ${id}`)
                    continue
                }
                if (tab.document.title.trim() === 'Phòng Cưới Không Tồn Tại') {
                    await retry(`Phòng cưới ${id} chưa mở`)
                    continue
                }
                if (tab.document.querySelector('.blessing-message')) {
                    tab.location.replace('about:blank')
                    return logger.log(`🟢 [Tiên Duyên] - Đã chúc phúc phòng cưới ${id}.`)
                }
                const token = await this.waitForCFTurnstile(tab, timeout)
                if (token === '') {
                    await retry(`Xác thực CF phòng cưới ${id} thất bại`)
                    continue
                }
                const success = await this.sendBlessing(id, token, tab.document)
                if (success) return tab.location.replace('about:blank')
                await retry(`Chúc phúc phòng cưới ${id} thất bại`)
            } catch (error) {
                await retry(`Lỗi xử lý trang phòng cưới ${id}: ${error.message || error}`)
            }
        }
        logger.log(`🔴 [Tiên Duyên] - Chúc phúc phòng cưới ${id} thất bại sau nhiều lần.`)
    }

    async waitForPage(id, tab, timeout = 15000) {
        return new Promise(resolve => {
            const interval = setInterval(() => {
                try {
                    if (tab.document && tab.document.readyState === 'complete') {
                        clearInterval(interval)
                        resolve(true)
                    }
                } catch (error) {
                    logger.log(`🔴 [Tiên Duyên] - Lỗi truy cập thông tin phòng cưới ${id}: ${error}`)
                    clearInterval(interval)
                    resolve(false)
                }
            }, 500)
            setTimeout(() => {
                clearInterval(interval)
                resolve(false)
            }, timeout)
        })
    }

    async waitForCFTurnstile(tab, timeout = 15000) {
        const observeValueChange = (input) => {
            return new Promise(resolve => {
                const observer = new MutationObserver(() => {
                    if (input.value && input.value.trim() !== '') {
                        observer.disconnect()
                        resolve(input.value)
                    }
                })
                observer.observe(input, { attributes: true, attributeFilter: ['value'] })
                setTimeout(() => {
                    observer.disconnect()
                    resolve('')
                }, timeout)
            })
        }

        const input = tab.document.querySelector('#cf-turnstile-response')
        if (!input) return null
        if (input.value && input.value.trim() !== '') return input.value
        return await observeValueChange(input)
    }

    async getAllWeddings() {
        if (!this.page) {
            this.page = await loadPage(DOMAIN + '/tien-duyen')
            const userData = parseUserData(this.page)
            this.tienngoc = userData.tien_ngoc?.value || 0
            this.tuvi = userData.tu_vi?.value || 0
        }
        const nonce = Better_Messages?.nonce
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce show_all_wedding.`)
            return []
        }
        return await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'show_all_wedding' })
        })
    }

    async claimLiXi(id) {
        const page = await loadPage(DOMAIN + '/phong-cuoi?id=' + id)
        const hasLiXiModal = page.doc.getElementById('liXiModal') !== null
        if (!hasLiXiModal) return
        const restNonce = Array.from(page.doc.querySelectorAll('script'))
            .map(script => script.textContent.match(/const\s+rest_nonce\s*=\s*['"]([^'"]+)['"]/))
            .find(match => match)?.[1]
        if (!restNonce) return logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce hh3d_receive_li_xi.`)
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': restNonce },
            body: JSON.stringify({ action: 'hh3d_receive_li_xi', wedding_room_id: id })
        })
        const message = result?.success === true
            ? `✅ [Tiên Duyên] - Mở Lì Xì thành công phòng ${id} - Nhận ${result.data?.amount} ${result.data?.name}`
            : `❌ [Tiên Duyên] - Mở Lì Xì thất bại - ${result?.data?.message || result}`
        logger.log(message)
    }

    async sendBlessing(id, token, doc) {
        const restNonce = Array.from(doc.querySelectorAll('script'))
            .map(script => script.textContent.match(/const\s+rest_nonce\s*=\s*['"]([^'"]+)['"]/))
            .find(match => match)?.[1]
        if (!restNonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce hh3d_add_blessing.`)
            return false
        }
        const message = blessingMessages[Math.floor(Math.random() * blessingMessages.length)]
        let bodyData = { action: 'hh3d_add_blessing', wedding_room_id: id, message }
        if (token) bodyData['cf-turnstile-response'] = token
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': restNonce },
            body: JSON.stringify(bodyData),
            retries: 0
        })
        if (result?.success === true) {
            logger.log(`🟢 [Tiên Duyên] - Chúc phúc thành công phòng cưới ${id}.`)
            this.tienngoc -= 30
            return true
        } else {
            logger.log(`🔴 [Tiên Duyên] - Chúc phúc thất bại phòng cưới ${id}:`, result?.message || result)
            return false
        }
    }

    async claimAllLiXis() {
        const nonce = Better_Messages?.nonce
        if (!nonce) return logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce hh3d_quick_open_all_li_xi.`)
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'hh3d_quick_open_all_li_xi' })
        })
        const summary = result?.summary || []
        const rewards = summary.map(item => `${item.icon || '🎁'} ${item.total || 0} ${item.name || ''}`).join(' | ')
        const message = result?.success === true
            ? `✅ [Tiên Duyên] - ${result.message || 'Mở Lì Xì thành công tất cả phòng cưới.'} - ${rewards}`
            : `❌ [Tiên Duyên] - ${result.message || 'Mở Lì Xì thất bại tất cả phòng cưới.'}`
        logger.log(message)
        return !!result?.success
    }

    async sendAllBlessings(count) {
        const nonce = Better_Messages?.nonce
        if (!nonce) return logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce hh3d_quick_bless_all.`)
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'hh3d_quick_bless_all' })
        })
        if (result?.success === true) {
            logger.log(`✅ [Tiên Duyên] - ${result.message || 'Chúc phúc thành công tất cả phòng cưới.'}`)
            this.tienngoc -= 30 * count
            return true
        } else {
            logger.log(`❌ [Tiên Duyên] - ${result.message || 'Chúc phúc thất bại tất cả phòng cưới.'}`)
            return false
        }
    }

    async getFriends(nonce) {
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce get_friends_td.`)
            return []
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'get_friends_td' })
        })
        const now = new Date()
        const friends = (Array.isArray(result) ? result : [])
            .filter(friend => {
                const time = new Date(friend.time)
                return ((now - time) / 86400000) >= 3
            })
        return friends
    }

    async checkGift(nonce, user_id, friend_id, cost_type) {
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce check_daily_gift_limit.`)
            return []
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'check_daily_gift_limit', user_id, friend_id, cost_type })
        })
        if (result?.success === true && result.cost_type === cost_type) {
            return result.remaining_free_gifts || 0
        }
        return 0
    }

    async sendGift(nonce, friend_id, cost_type) {
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce gift_to_friend.`)
            return []
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'gift_to_friend', friend_id, gift_type: 'hoa_hong', cost_type })
        })
        const message = result?.success === true
            ? `✅ [Tiên Duyên] - ${result.message || 'Gửi Hoa Hồng thành công.'} (${friend_id} - ${cost_type})`
            : `❌ [Tiên Duyên] - ${result?.message || 'Gửi Hoa Hồng không thành công.'} (${friend_id} - ${cost_type})`
        logger.log(message)
        if (result?.success === true) this.tienngoc -= 20
        return !!result?.success
    }

    async checkWishTreeStatus(nonce) {
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce check_wish_tree_status.`)
            return false
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'check_wish_tree_status' })
        })
        const canWish = result?.can_wish !== false
        const message = canWish
            ? `🟡 [Tiên Duyên] - ${result?.message || 'Chưa ước nguyện.'}`
            : `🟢 [Tiên Duyên] - ${result?.message || 'Đã ước nguyện.'}`
        logger.log(message)
        return canWish
    }

    async makeWishTree(nonce) {
        if (!nonce) {
            logger.log(`🔴 [Tiên Duyên] - Không tìm thấy nonce make_wish_tree.`)
            return []
        }
        const result = await postRequest(ACTION_URL, {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
            body: JSON.stringify({ action: 'make_wish_tree' })
        })
        const message = result?.success === true
            ? `✅ [Tiên Duyên] - ${result.message || 'Ước nguyện thành công.'}`
            : `❌ [Tiên Duyên] - ${result?.message || 'Ước nguyện không thành công.'}`
        logger.log(message)
        return !!result?.success
    }
}

class TongMon {
    constructor(user) {
        this.user = user
    }

    async triggerTeLe() {
        try {
            if (this.user.tele === 1) return logger.log(`🟢 [Tế Lễ] - Đã hoàn thành.`)
            const page = await loadPage(DOMAIN + '/danh-sach-thanh-vien-tong-mon')
            const nonce = parseVariableJSON(page, 'tong-mon-main-js-extra', 'TongMonConfig').nonce
            if ((await this.checkTeLeStatus(nonce)) || (await this.teLe(nonce))) {
                this.user.tele = 1
                logger.log(`🟢 [Tế Lễ] - Đã hoàn thành.`)
            } else {
                logger.log(`🟡 [Tế Lễ] - Chưa hoàn thành.`)
            }
        } catch (error) {
            logger.log(`🔴 [Tế Lễ] - Lỗi "triggerTeLe": ${error.message}`)
        }
    }

    async triggerBiCanh() {
        try {
            const page = await loadPage(DOMAIN + '/bi-canh-tong-mon')
            const variableJSON = parseVariableJSON(page, null, 'BossSystemConfig', true)
            const currentBoss = variableJSON.currentBoss || {}
            if (currentBoss.has_pending_reward === true) {
                await this.claimReward(variableJSON.nonce)
                return await this.triggerBiCanh()
            } else if (currentBoss.has_boss === true) {
                const { is_dead = false, time_remaining_to_expire = 0, boss_state = 'normal' } = currentBoss.boss || {}
                if (is_dead || time_remaining_to_expire === 0) {
                    logger.log(`🟡 [Bí Cảnh] - Boss đã chết hoặc hết hạn.`)
                    return await this.triggerBiCanh()
                }
                const { remaining = 0, can_attack = false } = currentBoss.attack_info || {}
                this.user.bicanh = Math.max(0, 5 - remaining)
                if (remaining === 0) {
                    logger.log(`🟢 [Bí Cảnh] - Đã hoàn thành.`)
                } else if (can_attack) {
                    const attack = await this.checkAttack(variableJSON.nonce) || {}
                    if (attack.can_attack === true) {
                        if (await this.attackBoss(variableJSON.nonce, remaining)) this.user.bicanh += 1
                        this.user.last_bicanh = Date.now()
                    } else {
                        this.user.last_bicanh = (typeof attack.last_attack_time === 'number' && isFinite(attack.last_attack_time))
                            ? attack.last_attack_time * 1000
                            : Date.now()
                        logger.log(`🟡 [Bí Cảnh] - ${attack.message || 'Chưa đến thời gian đánh'} - Còn lại ${remaining} lượt.`)
                    }
                } else {
                    logger.log(`🟡 [Bí Cảnh] - Chưa đến thời gian đánh - Còn lại ${remaining} lượt.`)
                }
            } else {
                this.user.bicanh = 5
                if (currentBoss.has_pending_boss === true) {
                    const { contribution_points = 0, required_points = 0, user_has_contributed = false } = currentBoss.boss_contribution || {}
                    if (contribution_points < required_points) {
                        if (user_has_contributed) {
                            logger.log(`🟡 [Bí Cảnh] - Đã hiến tế.`)
                        } else {
                            await this.hienTe(variableJSON.nonce)
                        }
                    }
                }
                logger.log(`🟡 [Bí Cảnh] - ${currentBoss.message || '...'}`)
            }
        } catch (error) {
            logger.log(`🔴 [Bí Cảnh] - Lỗi "triggerBiCanh": ${error.message}`)
        }
    }

    async checkTeLeStatus(nonce) {
        if (!nonce) return logger.log(`🔴 [Tế Lễ] - Không tìm thấy nonce check_te_le_status.`)
        const result = await postRequest(TONGMON_URL + '/check-te-le-status', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        return !!result?.success
    }

    async teLe(nonce) {
        if (!nonce) return logger.log(`🔴 [Tế Lễ] - Không tìm thấy nonce te_le_tong_mon.`)
        const result = await postRequest(TONGMON_URL + '/te-le-tong-mon', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        const message = result?.success === true
            ? `✅ [Tế Lễ] - Thành công.`
            : `❌ [Tế Lễ] - ${result?.message}`
        logger.log(message)
        return !!result?.success
    }

    async hienTe(nonce) {
        if (!nonce) return logger.log(`🔴 [Bí Cảnh] - Không tìm thấy nonce contribute_boss.`)
        const result = await postRequest(TONGMON_URL + '/contribute-boss', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        const message = result?.success === true
            ? `🟢 [Bí Cảnh] - Hiến tế thành công.`
            : `🟡 [Bí Cảnh] - ${result?.message}`
        logger.log(message)
    }

    async attackBoss(nonce, remaining) {
        if (!nonce) return logger.log(`🔴 [Bí Cảnh] - Không tìm thấy nonce attack_boss.`)
        const result = await postRequest(TONGMON_URL + '/attack-boss', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        const message = result?.success === true
            ? `🟢 [Bí Cảnh] - Khiếu chiến thành công - Còn lại ${remaining - 1} lượt.`
            : `🟡 [Bí Cảnh] - ${result?.message}remaining - Còn lại ${remaining} lượt.`
        logger.log(message)
        return !!result?.success
    }

    async checkAttack(nonce) {
        if (!nonce) return logger.log(`🔴 [Bí Cảnh] - Không tìm thấy nonce check-attack-cooldown.`)
        const result = await postRequest(TONGMON_URL + '/check-attack-cooldown', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        return result
    }

    async claimReward(nonce) {
        if (!nonce) return logger.log(`🔴 [Bí Cảnh] - Không tìm thấy nonce claim-boss-reward.`)
        const result = await postRequest(TONGMON_URL + '/claim-boss-reward', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        if (result?.error) return logger.log(`❌ [Bí Cảnh] - ${result.error}`)
        logger.log(`✅ [Bí Cảnh] - ${result?.message}`)
        const rewards = result?.reward_details?.total_rewards || {}
        const rewardLogs = []
        if (rewards.cong_hien) rewardLogs.push(`🏅 Cống Hiến: ${rewards.cong_hien}`)
        if (rewards.tu_vi) rewardLogs.push(`✨ Tu Vi: ${rewards.tu_vi}`)
        if (rewards.tinh_thach) rewardLogs.push(`💎 Tinh Thạch: ${rewards.tinh_thach}`)
        if (rewards.tien_ngoc) rewardLogs.push(`🔮 Tiên Ngọc: ${rewards.tien_ngoc}`)
        if (rewards.tinh_huyet) rewardLogs.push(`🩸 Tinh Huyết: ${rewards.tinh_huyet}`)
        if (rewardLogs.length) logger.log(rewardLogs.join(' | '))
    }
}

class HoatDongNgay {
    constructor(user) {
        this.user = user
    }

    async triggerReward() {
        try {
            if (this.user.hoatdongngay === 2) return logger.log(`🟢 [Hoạt Động Ngày] - Đã nhận 2 rương thưởng.`)
            const page = await loadPage(DOMAIN + '/bang-hoat-dong-ngay')
            const boxes = page.doc.querySelectorAll('[id^="reward-box-"]')
            let count = 0
            for (let i = 0; i < boxes.length; i++) {
                const box = boxes[i]
                const stage = i + 1
                if (box.classList.contains('claimed')) {
                    count += 1
                } else if (box.classList.contains('unlocked')) {
                    if (await this.claim(stage)) {
                        count += 1
                    }
                }
            }
            this.user.hoatdongngay = Math.min(2, count)
            logger.log(`🟢 [Hoạt Động Ngày] - Đã nhận ${count} rương thưởng.`)
        } catch (error) {
            logger.log(`🔴 [Hoạt Động Ngày] - Lỗi "trigger": ${error.message}`)
        }
    }

    async claim(stage) {
        const result = await postRequest(ADMIN_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'daily_activity_reward', stage: 'stage' + stage })
        })
        const message = result?.success === true
            ? `✅ [Hoạt Động Ngày] - Nhận thành công - Rương ${stage}.`
            : `❌ [Hoạt Động Ngày] - Nhận thất bại - Rương${result?.data?.message || result}.`
        logger.log(message)
        return !!result?.success
    }
}

class LinhThach {
    constructor(codes) {
        this.codes = codes
    }

    async trigger() {
        try {
            for (const code of this.codes) {
                await this.redeemLinhThach(code)
            }
            logger.log(`🟢 [Linh Thạch] - Đã nhập xong`)
        } catch (error) {
            logger.log(`🔴 [Linh Thạch] - Lỗi "trigger": ${error.message}`)
        }
    }

    async redeemLinhThach(code) {
        const page = await loadPage(DOMAIN + '/linh-thach')
        const nonce = page.html.match(/'nonce'\s*:\s*'([a-f0-9]+)'/i)?.[1]
        if (!nonce) return logger.log(`🔴 [Linh Thạch] - Không tìm thấy nonce redeem_linh_thach.`)
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'redeem_linh_thach', code, nonce, hold_timestamp: Math.floor(Date.now() / 1000) })
        })
        const message = result?.success === true
            ? `✅ [Linh Thạch] - ${code} - ${result.data?.message || result.data}`
            : `⚠️ [Linh Thạch] - ${code} - ${result?.data?.message || result}`
        logger.log(message)
    }
}

class BanPhuc {
    async trigger() {
        try {
            const page = await loadPage(DOMAIN + '/thanh-dien-ban-phuc')
            const userData = parseUserData(page)
            let tienngoc = userData.tien_ngoc?.value || 0
            const activeIds = Array.from(page.doc.querySelectorAll('.bless-card'))
                .filter(card => {
                    const button = card.querySelector('.bless-button')
                    return button && !button.classList.contains('disabled')
                })
                .map(card => card.getAttribute('data-id'))
            if (activeIds.length) {
                const requestData = parseRequestData(page.html)
                const security = requestData.find(value => value.action === 'bless_user')?.security
                if (!security) return logger.log(`🔴 [Ban Phúc] - Không tìm thấy security bless_user.`)
                for (const id of activeIds) {
                    if (tienngoc < 20) return logger.log(`🔴 [Ban Phúc] - Hết Tiên Ngọc - Còn lại ${tienngoc}`)
                    if (await this.blessUser(id, security)) tienngoc -= 20
                }
            }
            logger.log(`🟢 [Ban Phúc] - Đã chúc phúc xong.`)
        } catch (error) {
            logger.log(`🔴 [Ban Phúc] - Lỗi "trigger": ${error.message}`)
        }
    }

    async blessUser(blessed_id, security) {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'bless_user', blessed_id, security })
        })
        const message = result?.success === true
            ? `✅ [Ban Phúc] - Chúc phúc thành công cho ${result.data?.blessed_name} - nhận được Ban Phúc ${result.data?.reward} Tu Vi!`
            : `❌ [Ban Phúc] - Chúc phúc thất bại - ${result?.data?.message || result}`
        logger.log(message)
        return !!result?.success
    }
}

class VongQuayPhucVan {
    constructor(user) {
        this.user = user
    }

    async trigger() {
        try {
            const total = this.user.hoatdongngay === 2 ? 4 : 3
            if (this.user.vongquay === total) return logger.log(`🟢 [Vòng Quay Phúc Vận] - Đã hoàn thành.`)
            const page = await loadPage(DOMAIN + '/vong-quay-phuc-van')
            const nonce = page.html.match(/this\.nonce\s*=\s*['"]([a-z0-9]+)['"]/)?.[1]
            const turns = parseInt(page.doc.getElementById('remainingTurns')?.textContent || '0', 10)
            this.user.vongquay = Math.max(0, total - turns)
            for (let i = 0; i < turns; i++) {
                if (await this.spin(nonce)) this.user.vongquay += 1
            }
            logger.log(`🟢 [Vòng Quay Phúc Vận] - Đã quay ${turns > 0 ? turns.toString() : 'hết'} lượt.`)
        } catch (error) {
            logger.log(`🔴 [Vòng Quay Phúc Vận] - Lỗi "trigger": ${error.message}`)
        }
    }

    async spin(nonce) {
        const result = await postRequest(LOTTERY_URL + '/spin', {
            headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce }
        })
        if (result?.success === true) {
            const type = result?.prize?.type
            const specialMessages = {
                loi_kiep: '⚡️ LÔI KIẾP GIÁNG XUỐNG ⚡️',
                hap_thu_loi_kiep: '🎉 SỨC MẠNH BÙNG PHÁT 🎉',
                xu_khoa: '💰 CHÚC MỪNG ĐẠO HỮU 💰'
            }
            const message = specialMessages[type] || '🎊 CHÚC MỪNG ĐẠO HỮU 🎊'
            logger.log(message)
            logger.log(`✅ [Vòng Quay Phúc Vận] - Quay thành công - ${result.message}`)
        } else {
            logger.log(`❌ [Vòng Quay Phúc Vận] - Quay thất bại - ${result?.message || result}`)
        }
        return !!result?.success
    }
}

    class DuaTop {
        constructor(user, page = null) {
            this.user = user
            this.page = page
            this.cooldown = ((6 * 60 + 30) * 60) * 1000
        }

        async trigger({ tab, retries = 5, delay = 10000, timeout = 15000 }) {
            const bank = Object.fromEntries(Object.entries(quizBank).map(([key, value]) => [normalize(key), value]))
            const remainingTime = (doc) => {
                const text = doc.getElementById('countdown-timer')?.textContent?.trim() ?? ''
                const [hh, mm, ss] = text.split(':').map(Number)
                if ([hh, mm, ss].some(isNaN)) return 0
                return (hh * 3600 + mm * 60 + ss) * 1000
            }
            const answerIndex = (value) => {
                const question = normalize(value.question)
                const answer = bank[question] ?? ''
                const options = value.options.map(option => typeof option === 'string' ? option : option.content)
                let bestIndex = bestMatch(options, answer).bestIndex
                return bestIndex
            }
            const retry = async (reason = '') => {
                if (reason) logger.log(`↪️ [Đua Top] - ${reason} ➤ Thử lại còn ${retries - 1} lần...`)
                if (tab && !tab.closed) tab.location.replace('about:blank')
                retries--
                await sleep(delay)
            }

            while (retries > 0) {
                const targetURLString = DOMAIN + '/dua-top-hh3d'
                if (!tab || tab.closed) {
                    this.page = await loadPage(targetURLString)
                    const distance = remainingTime(this.page.doc)
                    if (distance > 0) return this.user.last_duatop = Date.now() + Math.max(0, distance) - this.cooldown
                    const nonce = Better_Messages?.nonce
                    const value = await this.getQuestion(nonce)
                    if (!value.id || !value.options.length) {
                        await retry('Không tải được câu hỏi')
                        continue
                    }
                    let quiz = this.user.quiz || (this.user.quiz = [])
                    quiz.push({ question: value.question, options: value.options })
                    const index = answerIndex(value)
                    if (index < 0) return logger.log('🔴 [Đua Top] - Không tìm thấy câu trả lời - Kiểm tra lại.')
                    const success = await this.submitAnswer(nonce, value.id, index)
                    if (success) {
                        this.user.last_duatop = Date.now()
                    } else {
                        this.user.last_duatop = Date.now() + 5 * 60 * 1000 - this.cooldown
                    }
                    return
                }
                tab.location.replace(targetURLString)
                await sleep(250)
                const navigated = await new Promise(resolve => {
                    const interval = setInterval(() => {
                        if (tab.location.href === targetURLString) {
                            clearInterval(interval)
                            resolve(true)
                        }
                    }, 500)
                    setTimeout(() => {
                        clearInterval(interval)
                        resolve(false)
                    }, timeout)
                })
                if (!navigated) {
                    await retry('Điều hướng thất bại.')
                    continue
                }
                try {
                    const loaded = await this.waitForPage(tab, timeout)
                    if (!loaded) {
                        await retry('Không tải được trang đua top.')
                        continue
                    }
                    const distance = remainingTime(tab.document)
                    if (distance > 0) {
                        this.user.last_duatop = Date.now() + Math.max(0, distance) - this.cooldown
                        return tab.location.replace('about:blank')
                    }
                    const openButton = tab.document.querySelector('.nhan-luot-container .mo-ruong-btn')
                    if (!openButton) {
                        await retry('Không tìm thấy thấy nút Mở rương')
                        continue
                    }
                    openButton.click()
                    const { question, optionButtons } = await this.waitForQuiz(tab, timeout)
                    if (!question || !optionButtons.length) {
                        await retry('Không tải được câu hỏi')
                        continue
                    }
                    const options = optionButtons.map(button => button.innerText.trim())
                    let quiz = this.user.quiz || (this.user.quiz = [])
                    quiz.push({ question: question, options: options })
                    const index = answerIndex({ question, options })
                    if (index < 0) return logger.log('🔴 [Đua Top] - Không tìm thấy câu trả lời - Kiểm tra lại.')
                    optionButtons[index].click()
                    const submitButton = tab.document.getElementById('submit-answer')
                    if (!submitButton) {
                        console.warn('Không tìm thấy nút Trả lời')
                        return false
                    }
                    submitButton.click()
                    this.user.index_duatop = index
                    const success = await this.waitForAnswer(tab, timeout)
                    if (success) {
                        this.user.last_duatop = Date.now()
                    } else {
                        this.user.last_duatop = Date.now() + 5 * 60 * 1000 - this.cooldown
                    }
                    return tab.location.replace('about:blank')
                } catch (error) {
                    await retry(`Lỗi xử lý trang đua top: ${error.message || error}`)
                }
            }
            this.user.last_duatop = Date.now() + 5 * 60 * 1000 - this.cooldown
            logger.log('🔴 [Đua Top] - Mở rương thất bại sau nhiều lần.')
        }

        async waitForPage(tab, timeout = 15000) {
            return new Promise(resolve => {
                const interval = setInterval(() => {
                    try {
                        if (tab.document && tab.document.readyState === 'complete') {
                            clearInterval(interval)
                            resolve(true)
                        }
                    } catch (error) {
                        logger.log(`🔴 [Đua Top] - Lỗi truy cập trang đua top`)
                        clearInterval(interval)
                        resolve(false)
                    }
                }, 500)
                setTimeout(() => {
                    clearInterval(interval)
                    resolve(false)
                }, timeout)
            })
        }

        waitForQuiz(tab, timeout = 15000) {
            return new Promise(resolve => {
                const modalElement = tab.document.getElementById('quiz-modal')
                const questionElement = tab.document.getElementById('quiz-question')
                const optionsElement = tab.document.getElementById('quiz-options')
                if (!modalElement || !questionElement || !optionsElement) return resolve({ question: '', optionButtons: [] })
                const visible = modalElement.style.display === 'block'
                const question = questionElement.innerText?.trim()
                const optionButtons = Array.from(optionsElement.children || [])
                if (visible && question && optionButtons.length) {
                    return resolve({ question, optionButtons })
                }

                const observer = new MutationObserver(() => {
                    const visible = modalElement.style.display === 'block'
                    const question = questionElement.innerText?.trim()
                    const optionButtons = Array.from(optionsElement.children || [])
                    if (visible && question && optionButtons.length) {
                        observer.disconnect()
                        clearTimeout(timer)
                        resolve({ question, optionButtons })
                    }
                })
                observer.observe(modalElement, { attributes: true, childList: true, subtree: true, characterData: true, attributeFilter: ['style'] })
                const timer = setTimeout(() => {
                    observer.disconnect()
                    resolve({ question: '', optionButtons: [] })
                }, timeout)
            })
        }

        waitForAnswer(tab, timeout = 10000) {
            return new Promise(resolve => {
                const container = tab.document.querySelector('#quiz-options')
                if (!container) return resolve(false)
                const observer = new MutationObserver(() => {
                    const correct = container.querySelector('.correct-answer')
                    if (correct) {
                        observer.disconnect()
                        clearTimeout(timer)
                        const wrong = container.querySelector('.wrong-answer')
                        resolve(!wrong)
                    }
                })
                observer.observe(container, { subtree: true, attributes: true, attributeFilter: ['class'] })
                const timer = setTimeout(() => {
                    observer.disconnect()
                    resolve(false)
                }, timeout)
            })
        }

        async getQuestion(nonce) {
            if (!nonce) return logger.log(`🔴 [Đua Top] - Không tìm thấy nonce hh3d_get_question.`)
            const result = await postRequest(ACTION_URL, {
                headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
                body: JSON.stringify({ action: 'hh3d_get_question' })
            })
            if (result?.id && Array.isArray(result.options) && result.options.length) {
                return { id: result.id, question: result.question, options: result.options }
            }
            logger.log('🔴 [Đua Top] - Không lấy được dữ liệu hh3d_get_question.')
            return { id: null, question: null, options: [] }
        }

        async submitAnswer(nonce, question_id, selected_answer) {
            if (!nonce) {
                logger.log(`🔴 [Đua Top] - Không tìm thấy nonce hh3d_submit_answer.`)
                return false
            }
            const result = await postRequest(ACTION_URL, {
                headers: { 'Content-Type': 'application/json', 'X-WP-Nonce': nonce },
                body: JSON.stringify({ action: 'hh3d_submit_answer', question_id, selected_answer })
            })
            if (result?.success === true) {
                logger.log(`🟢 [Đua Top] - Mở rương thành công - Nhận được ${result.points} Tu Vi.`)
                return true
            } else {
                logger.log(`🔴 [Đua Top] - Mở rương thất bại`, result?.message || result)
                return false
            }
        }
    }

class EventGame {
    async trigger() {
        try {
            const page = await loadPage(DOMAIN + '/event-trung-thu-2025')
            const remainingText = page.doc.getElementById('remaining-count')?.textContent || ""
            let remaining = parseInt(remainingText.match(/\d+/)?.[0] || "0", 10)
            const reward = page.doc.getElementById('reward-progress')?.textContent?.trim() || '0/20'
            logger.log(`🟡 [Sự Kiện] - Số lần còn lại: ${remaining} | Nhận quà từ hoạt động: ${reward}`)
            const requestData = parseRequestData(page.html)
            const security = requestData.find(value => value.action === 'xoay_mnq')?.security
            if (!security) return logger.log(`🔴 [Sự Kiện] - Không tìm thấy security xoay_mnq.`)
            while (remaining > 0) {
                const count = remaining >= 5 ? 5 : 1
                remaining = await this.spin(security, count) || 0
            }
        } catch (error) {
            logger.log(`🔴 [Sự Kiện] - Lỗi "trigger": ${error.message}`)
        }
    }

// director: "tuvi" | "phapbao" | "tinhthach"
    async triggerExchange(director = "tuvi") {
        const targetMap = { tuvi: 140, phapbao: 200, tinhthach: 80 }
        if (!this.page) this.page = await loadPage(DOMAIN + '/event-trung-thu-2025')
        const requestData = parseRequestData(this.page.html)
        const security = requestData.find(value => value.action === 'exchange_item')?.security
        const items = await this.fetchGiftItems()
        const today = new Date()
        today.setHours(0, 0, 0, 0)
        const future = new Date("2025-10-08")
        future.setHours(0, 0, 0, 0)
        const days = Math.ceil((future - today) / (1000 * 60 * 60 * 24))
        const exchange_days = days > 2 ? (days + 1) : days
        let den_max_today = days === 2 ? 80 : 40
        let den_current = Number(items.find(value => value.type === 'den_ong_sao')?.quantity || "0")
        let mat_trang = Number(items.find(value => value.type === 'mat_trang')?.quantity || "0")
        let tho_ngoc = Number(items.find(value => value.type === 'tho_ngoc')?.quantity || "0")
        const dau_lan = Number(items.find(value => value.type === 'dau_lan')?.quantity || "0")
        const keo_deo = Number(items.find(value => value.type === 'keo_deo')?.quantity || "0")
        const am_tra = Number(items.find(value => value.type === 'am_tra')?.quantity || "0")
        if ((this.user.hoatdongngay || 0) < 1) return logger.log(`⚠️ [Sự Kiện] - Nhận thêm 1 Mặt Trăng từ Hoạt Động Ngày rồi đổi tiếp nha!`)
        if (mat_trang > 0) {
            const den_mat_trang_exchange = Math.min(4, mat_trang)
            await this.exchangeItem("den_ong_sao", "mat_trang", den_mat_trang_exchange, security)
            den_current += den_mat_trang_exchange * 10
            den_max_today -= den_mat_trang_exchange * 10
            mat_trang -= den_mat_trang_exchange
        }
        den_current += tho_ngoc * 10
        const den_target = targetMap[director] || 0
        const den_future = exchange_days * 30 - mat_trang * 10
        const den_exchange = den_target - den_current - (days + mat_trang) * 10
        let den_min_today = Math.max(0, den_exchange - den_future)
        if (den_min_today > den_max_today) return logger.log(`⚠️ [Sự Kiện] - Không còn khả năng tự đổi - Vào xem lại đi!`)
        logger.log(`🎯 [Sự Kiện] - Đèn Ông Sao: Mục tiêu: ${den_target} | Hiện tại: ${den_current} (Thỏ Ngọc: ${tho_ngoc}) | Cần đổi: ${den_exchange} | Hôm nay: ${den_min_today}`)
        let den_dau_lan = Math.floor(dau_lan / 3)
        let den_keo_deo = Math.floor(keo_deo / 3)
        let den_am_tra = Math.floor(am_tra / 3)
        let den_dau_lan_exchange = 0
        let den_keo_deo_exchange = 0
        let den_am_tra_exchange = 0
        while (den_min_today > 0) {
            if (den_dau_lan > 0 && director != "tinhthach") {
                den_dau_lan_exchange = Math.min(den_dau_lan, den_min_today)
                den_dau_lan = Math.max(0, den_dau_lan - den_dau_lan_exchange)
                den_min_today = Math.max(0, den_min_today - den_dau_lan_exchange)
                continue
            }
            if (den_keo_deo > 0) {
                den_keo_deo_exchange = Math.min(den_keo_deo, den_min_today)
                den_keo_deo = Math.max(0, den_keo_deo - den_keo_deo_exchange)
                den_min_today = Math.max(0, den_min_today - den_keo_deo_exchange)
                continue
            }
            if (den_am_tra > 0) {
                den_am_tra_exchange = Math.min(den_am_tra, den_min_today)
                den_am_tra = Math.max(0, den_am_tra - den_am_tra_exchange)
                den_min_today = Math.max(0, den_min_today - den_am_tra_exchange)
                continue
            }
        }
        logger.log(`〽️ [Sự Kiện] - Đổi Đèn Ông Sao: Đầu Lân: ${den_dau_lan_exchange} | Kẹo: ${den_keo_deo_exchange} | Ấm Trà: ${den_am_tra_exchange}`)
        if (den_dau_lan_exchange > 0) await this.exchangeItem("den_ong_sao", "dau_lan", den_dau_lan_exchange, security)
        if (den_keo_deo_exchange > 0) await this.exchangeItem("den_ong_sao", "keo_deo", den_keo_deo_exchange, security)
        if (den_am_tra_exchange > 0) await this.exchangeItem("den_ong_sao", "am_tra", den_am_tra_exchange, security)
        switch (director) {
            case "tuvi":
                if (days === 0) {
                    const items = await this.fetchGiftItems()
                    const den_ong_sao = Number(items.find(value => value.type === 'den_ong_sao')?.quantity || "0")
                    if (den_ong_sao !== 140) return logger.log(`⚠️ [Sự Kiện] - Số lượng Đèn Ông Sao sai lệch - Vào xem lại đi!`)
                    await this.exchangeItem("khung_vip_trung_thu_1_2025", "den_ong_sao", 1, security)
                    await this.exchangeItem("khung_vip_trung_thu_2_2025", "den_ong_sao", 1, security)
                    await this.exchangeItem("khung_vip_trung_thu_3_2025", "den_ong_sao", 1, security)
                    await this.exchangeItem("phap_bao_2", "den_ong_sao", 1, security)
                    const refineItems = items.filter(value => ["dau_lan", "keo_deo", "am_tra", "banh_dau_xanh", "banh_thap_cam"].includes(value.type))
                    for (const item of refineItems) {
                        await this.refineItem(item.type, item.quantity, security)
                    }
                }
                break
            case "phapbao":
                const tho_ngoc_target = 15
                const tho_ngoc_future = exchange_days * 3
                const tho_ngoc_exchange = tho_ngoc_target - tho_ngoc
                const tho_ngoc_min_today = Math.max(0, tho_ngoc_exchange - tho_ngoc_future)
                const tho_ngoc_max_today = days === 2 ? 6 : 3
                logger.log(`🎯 [Sự Kiện] - Thỏ Ngọc: Mục tiêu: ${tho_ngoc_target} | Hiện tại: ${tho_ngoc}) | Cần đổi: ${tho_ngoc_exchange} | Hôm nay: ${tho_ngoc_min_today}`)
                const tho_ngoc_den_ong_sao = Math.floor(den_current / 10)
                const tho_ngoc_den_ong_sao_exchange = Math.min(tho_ngoc_min_today, tho_ngoc_den_ong_sao)
                if (tho_ngoc_den_ong_sao_exchange > tho_ngoc_max_today) return logger.log(`⚠️ [Sự Kiện] - Không còn khả năng tự đổi - Vào xem lại đi!`)
                logger.log(`〽️ [Sự Kiện] - Đổi Thỏ Ngọc: ${tho_ngoc_den_ong_sao_exchange}`)
                if (tho_ngoc_den_ong_sao_exchange > 0) await this.exchangeItem("tho_ngoc", "den_ong_sao", tho_ngoc_den_ong_sao_exchange, security)
                if (days === 0) {
                    const items = await this.fetchGiftItems()
                    const den_ong_sao = Number(items.find(value => value.type === 'den_ong_sao')?.quantity || "0")
                    const tho_ngoc = Number(items.find(value => value.type === 'tho_ngoc')?.quantity || "0")
                    if (den_ong_sao !== 50 || tho_ngoc !== 15) return logger.log(`⚠️ [Sự Kiện] - Số lượng Đèn Ông Sao | Thỏ Ngọc sai lệch - Vào xem lại đi!`)
                    await this.exchangeItem("phap_bao_1", "tho_ngoc", 1, security)
                    await this.exchangeItem("phap_bao_2", "den_ong_sao", 1, security)
                    const refineItems = items.filter(value => ["dau_lan", "keo_deo", "am_tra", "banh_dau_xanh", "banh_thap_cam"].includes(value.type))
                    for (const item of refineItems) {
                        await this.refineItem(item.type, item.quantity, security)
                    }
                }
                break
            case "tinhthach":
                if (days === 0) {
                    const items = await this.fetchGiftItems()
                    const den_ong_sao = Number(items.find(value => value.type === 'den_ong_sao')?.quantity || "0")
                    if (den_ong_sao !== 80) return logger.log(`⚠️ [Sự Kiện] - Số lượng Đèn Ông Sao sai lệch - Vào xem lại đi!`)
                    logger.log(`⚠️ [Sự Kiện] - Vào đổi Khung Trung Thu đi!`)
                    await this.exchangeItem("phap_bao_2", "den_ong_sao", 1, security)
                    const refineItems = items.filter(value => ["dau_lan", "keo_deo", "am_tra", "banh_dau_xanh", "banh_thap_cam"].includes(value.type))
                    for (const item of refineItems) {
                        await this.refineItem(item.type, item.quantity, security)
                    }
                }
                break
            default:
                break
        }
    }

    async spin(security, count) {
        const result = await postRequest(HH3D_AJAX_URL, {
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams({ action: 'xoay_mnq', shakes: count, security })
        })
        if (result?.success === true) {
            const { rewards = [], remaining = 0 } = result.data || {}
            const rewardLogs = rewards.map(reward => `${reward.name}: ${reward.quantity}`)
            if (rewardLogs.length) logger.log(rewardLogs.join(' | '))
            logger.log(`✅ [Sự Kiện] - Thực hiện thành công - Còn lại: ${remaining} lần.`)
            return remaining
        } else {
            logger.log(`❌ [Sự Kiện] - Thực hiện thất bại - ${result?.data?.message || result?.message || result}`)
            return 0
        }
    }
}

class VIPHH3D {
    constructor(user) {
        this.user = user
    }

    async trigger() {
        try {
            if (typeof this.user.vip === 'boolean') return
            const page = await loadPage(DOMAIN + '/vip-hh3d')
            this.user.vip = this.isVIP(page)
        } catch (error) {
            logger.log(`🔴 [VIP HH3D] - Lỗi "trigger": ${error.message}`)
        }
    }

    isVIP(page) {
        const card = page.doc.querySelector('.vip-membership-card')
        if (!card || card.style.display === 'none') return false
        const text = page.doc.getElementById('vip-expiry-date')?.textContent?.trim()
        if (!text) return false
        const [date, time] = text.split(' ')
        const [dd, mm, yyyy] = date.split('/')
        const isoString = `${yyyy}-${mm}-${dd}T${time || '00:00:00'}`
        const expiry = new Date(isoString)
        const now = new Date()
        return expiry.getTime() > now.getTime()
    }
}


class TaskRunnerUI {
    constructor() {
        if (TaskRunnerUI.instance) {
            TaskRunnerUI.instance.show();
            return TaskRunnerUI.instance;
        }
        this.container = null;
        this.buttonContainer = null;
        this.triggerButton = null;
        this.isCollapsed = false;
        this.footer = null;
        this.createUI();
        this.setupKeyboardShortcut();
        TaskRunnerUI.instance = this;
    }

    show() {
        if (this.container) {
            this.container.style.display = 'flex';
            requestAnimationFrame(() => {
                this.container.style.transform = 'scale(1)';
                this.container.style.opacity = '1';
            });
        }
        if (this.triggerButton) {
            this.triggerButton.style.opacity = '0';
            setTimeout(() => {
                if (this.triggerButton) this.triggerButton.style.display = 'none';
            }, 200);
        }
    }

    hide() {
        if (this.container) {
            this.container.style.transform = 'scale(0.95)';
            this.container.style.opacity = '0';
            setTimeout(() => {
                if (this.container) this.container.style.display = 'none';
            }, 300);
        }
        if (this.triggerButton) {
            this.triggerButton.style.display = 'flex';
            requestAnimationFrame(() => {
                if (this.triggerButton) this.triggerButton.style.opacity = '1';
            });
        }
    }

    createTriggerButton() {
        const trigger = document.createElement('div');
        trigger.id = 'task-runner-trigger';
        trigger.textContent = '🎮';
        Object.assign(trigger.style, {
            position: 'fixed',
            top: '15px',
            left: '16px',
            width: '44px',
            height: '44px',
            backgroundColor: 'rgba(28, 32, 46, 0.9)',
            backdropFilter: 'blur(10px)',
            border: '1px solid rgba(255, 255, 255, 0.2)',
            borderRadius: '50%',
            boxShadow: '0 4px 15px rgba(0, 0, 0, 0.3)',
            color: '#ffffff',
            display: 'none', // Initially hidden
            justifyContent: 'center',
            alignItems: 'center',
            fontSize: '24px',
            cursor: 'pointer',
            zIndex: '9998',
            transition: 'transform 0.2s ease, opacity 0.3s ease',
        });

        trigger.onclick = () => this.show();
        
        document.body.appendChild(trigger);
        this.triggerButton = trigger;
    }

    createUI() {
        if (document.readyState === 'loading') {
              document.addEventListener('DOMContentLoaded', this.createUI.bind(this));
            return;
        }

        const container = document.createElement('div');
        container.id = 'task-runner-ui';
        Object.assign(container.style, {
            position: 'fixed',
            top: '15px',
            left: '16px',
            width: '220px',
            zIndex: '9999',
            backgroundColor: 'rgba(28, 32, 46, 0.88)',
            backdropFilter: 'blur(12px) saturate(180%)',
            border: '1px solid rgba(255, 255, 255, 0.15)',
            borderRadius: '12px',
            boxShadow: '0 8px 32px rgba(0, 0, 0, 0.37)',
            color: '#ffffff',
            fontFamily: '"Poppins", sans-serif',
            display: 'flex',
            flexDirection: 'column',
            maxHeight: 'calc(100vh - 30px)',
            transition: 'transform 0.3s ease, opacity 0.3s ease',
            transform: 'scale(0.95)',
            opacity: '0',
        });
const header = document.createElement('div');
Object.assign(header.style, {
    padding: '12px 14px',
            fontWeight: 'bold',
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'space-between',
            cursor: 'pointer',
            userSelect: 'none',
            borderBottom: '1px solid rgba(255, 255, 255, 0.1)',
        });

        const titleWrapper = document.createElement('div');
        Object.assign(titleWrapper.style, {
            display: 'flex',
            alignItems: 'center',
            gap: '8px',
        });

        const icon = document.createElement('span');
        icon.textContent = '🎮';
        icon.style.fontSize = '18px';

        const title = document.createElement('span');
        title.textContent = 'Bảng Điều Khiển';

        titleWrapper.appendChild(icon);
        titleWrapper.appendChild(title);

        const closeBtn = document.createElement('span');
        closeBtn.innerHTML = '&times;';
        Object.assign(closeBtn.style, {
            cursor: 'pointer',
            fontSize: '22px',
            lineHeight: '1',
            color: '#aaa',
            transition: 'color 0.2s ease, transform 0.2s ease',
        });
        closeBtn.onmouseover = () => {
            closeBtn.style.color = '#ff4d4d';
            closeBtn.style.transform = 'scale(1.2)';
        };
        closeBtn.onmouseout = () => {
            closeBtn.style.color = '#aaa';
            closeBtn.style.transform = 'scale(1)';
        };
        closeBtn.onclick = (e) => {
            e.stopPropagation();
            this.hide();
        };

        header.appendChild(titleWrapper);
        header.appendChild(closeBtn);
        container.appendChild(header);

        const buttonContainer = document.createElement('div');
        this.buttonContainer = buttonContainer;
        Object.assign(buttonContainer.style, {
            padding: '10px',
            display: 'grid',
            gridTemplateColumns: '1fr 1fr',
            gap: '8px',
             overflowY: 'auto',
            transition: 'max-height 0.4s ease-out, padding 0.4s ease-out, opacity 0.3s 0.1s ease-out',
        });

        header.onclick = () => this.toggleCollapse();

        const footer = document.createElement('div');
        this.footer = footer;
        Object.assign(footer.style, {
            padding: '10px 12px',
            fontSize: '12px',
            textAlign: 'center',
            color: 'rgba(255, 255, 255, 0.7)',
            borderTop: '1px solid rgba(255, 255, 255, 0.1)',
            transition: 'display 0.4s ease-out',
            display: 'flex',
            justifyContent: 'center',
            alignItems: 'center',
            gap: '10px'
        });
        // --- THAY ĐỔI: Thêm link liên hệ ---
        footer.innerHTML = `
            <span>© Bốn & Tủn</span>
            <a href="https://discord.gg/JP64pSwybA" target="_blank" style="color: #7289DA; text-decoration: none; font-weight: 600;">| Discord</a>
            <a href="https://hoathinh3d.gg/profile/1/" target="_blank" style="color: #1877F2; text-decoration: none; font-weight: 600;">| HH3D</a>
        `;
        container.appendChild(buttonContainer);
        container.appendChild(footer);
        document.body.appendChild(container);
        this.container = container;
        this.addTasks();
        this.createTriggerButton();

        // Initial animation
        requestAnimationFrame(() => {
            container.style.transform = 'scale(1)';
            container.style.opacity = '1';
            this.buttonContainer.style.maxHeight = '300px';
        });
    }

    addButton(text, onClick) {
        const button = document.createElement('button');
        button.textContent = text;
        Object.assign(button.style, {
            padding: '10px 8px',
            border: '1px solid rgba(255, 255, 255, 0.2)',
            borderRadius: '6px',
            background: 'rgba(255, 255, 255, 0.08)',
            color: '#ffffff',
            cursor: 'pointer',
            fontSize: '12px',
            transition: 'background-color 0.2s ease, transform 0.1s ease, box-shadow 0.2s ease',
            fontFamily: 'inherit'
        });
        button.onmouseover = () => {
            button.style.backgroundColor = 'rgba(255, 255, 255, 0.15)';
            button.style.boxShadow = '0 0 8px rgba(139, 92, 246, 0.5)';
        };
        button.onmouseout = () => {
            button.style.backgroundColor = 'rgba(255, 255, 255, 0.08)';
            button.style.boxShadow = 'none';
        };
        button.onmousedown = () => button.style.transform = 'scale(0.95)';
        button.onmouseup = () => button.style.transform = 'scale(1)';
        button.onclick = onClick;
        this.buttonContainer.appendChild(button);
    }

    toggleCollapse() {
        this.isCollapsed = !this.isCollapsed;
        if (this.isCollapsed) {
            this.buttonContainer.style.maxHeight = '0px';
            this.buttonContainer.style.paddingTop = '0';
            this.buttonContainer.style.paddingBottom = '0';
            this.buttonContainer.style.opacity = '0';
            if (this.footer) {
                this.footer.style.display = 'none';
            }
        } else {
            this.buttonContainer.style.maxHeight = '300px';
            this.buttonContainer.style.paddingTop = '10px';
            this.buttonContainer.style.paddingBottom = '10px';
            this.buttonContainer.style.opacity = '1';
            if (this.footer) {
                this.footer.style.display = 'block';
            }
        }
    }

    addTasks() {
        const taskMap = {
            'Full Action': () => {
                logger.log('▶️ Full Action');
                manager.trigger({ tasks: [Task.DIEM_DANH, Task.VAN_DAP, Task.TE_LE], bets, blessings, codes, battles });
             },
            // 'Điểm Danh': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new DiemDanh(user).trigger();
            // },
            // 'Vấn Đáp': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new VanDap(user).trigger();
            // },
            // 'Tế Lễ': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new TongMon(user).triggerTeLe();
            // },
            // 'TLTM': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new ThiLuyenTongMon(user).trigger();
            // },
            'Đồ Thạch': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                await new DoThach(user).trigger();
            },
            // 'Phúc Lợi': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new PhucLoiDuong(user).trigger();
            // },
            // 'Hoang Vực': async () => {
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     await new HoangVuc(user).trigger();
            // },
            // 'Linh Thạch': async () => { 
            //     const userData = await storage.getUserData();
            //     const { user_id } = Better_Messages || {};
            //     if (!user_id) return logger.log('Không tìm thấy user_id');
            //     const user = userData[user_id] || (userData[user_id] = {});
            //     const codes = user.linhthach_codes || [];
            //     if (codes.length === 0) return logger.log('Không có mã Linh Thạch nào để nhập.');
            //     await new LinhThach(codes).trigger();
            // },
            'VQPV': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                await new VongQuayPhucVan(user).trigger();
            },
            'Bí Cảnh': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                await new TongMon(user).triggerBiCanh();
            },
            'Luận Võ': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                const luanvo = new LuanVo(user);
                await luanvo.triggerReceive(battles.autoOn);
                await luanvo.triggerSend(battles.options);
            },
            'Tiên Duyên': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                await new TienDuyen(user).scanBlessing(null, true);
            },
            'Cầu Nguyện': async () => {
                const userData = await storage.getUserData();
                const { user_id } = Better_Messages || {};
                if (!user_id) return logger.log('Không tìm thấy user_id');
                const user = userData[user_id] || (userData[user_id] = {});
                await new TienDuyen(user).triggerWish();
            }
        };

        for (const [text, action] of Object.entries(taskMap)) {
            this.addButton(text, action);
        }
    }
setupKeyboardShortcut() {
        document.addEventListener('keydown', (event) => {
            // Check for Ctrl+Alt+K
            if (event.ctrlKey && event.altKey && (event.key === 'k' || event.key === 'K')) {
                // Prevent default browser action for this shortcut
                event.preventDefault();

                // Toggle the UI visibility
                if (!this.container || this.container.style.display === 'none') {
                    this.show();
                } else {
                    this.hide();
                }
            }
        });
    }
}

const TaskGroups = {
    "-1": ['BI_CANH'],
    "0": ['TIEN_DUYEN'],
    "1": ['DIEM_DANH', 'VAN_DAP', 'TE_LE', 'VONG_QUAY_PHUC_VAN', 'EVENT'],
    "2": ['DO_THACH'],
    "3": ['THI_LUYEN_TONG_MON'],
    "4": ['PHUC_LOI_DUONG'],
    "5": ['HOANG_VUC'],
    "10": ['LUAN_VO'],
    "26": ['DUA_TOP'],
    "50": ['BAN_PHUC']
}
Object.freeze(TaskGroups)
const Task = {}
for (const list of Object.values(TaskGroups)) {
    for (const key of list) {
        Task[key] = key
    }
}
Task.ALL = Object.values(Task)
Object.freeze(Task)
const getCooldown = (task, vip) => {
    switch (task) {
        case Task.THI_LUYEN_TONG_MON:
        case Task.PHUC_LOI_DUONG:
            return ((vip === true) ? 7.5 : 30) * 60 * 1000
        case Task.HOANG_VUC:
            return ((vip === true) ? 7.5 : 15) * 60 * 1000
        default:
            return 0
    }
}

class TaskManager {
    constructor() {
        this.queue = []
        this.running = false
        this.schedulers = new Map()
        this.repeaters = new Map()
    }

    enqueue(operation) {
        this.queue.push(operation)
        if (!this.running) {
            this.running = true
            this.next()
        }
    }

    schedule({ task = '', times = [], last = null, handler }) {
        this.enqueue(async () => {
            await handler()

            const step = () => {
                const now = Date.now()
                const target = new Date()
                while (times.length > 0) {
                    const time = times[0]
                    const [hour, minute] = time.split(':').map(Number)
                    target.setHours(hour, minute, 0, 0)
                    const interval = target.getTime()
                    const lastInterval = last()
                    if ((lastInterval && interval > lastInterval + 30 * 60 * 1000 && interval > now) || (!lastInterval && interval > now)) {
                        if (this.schedulers.has(task)) {
                            clearTimeout(this.schedulers.get(task))
                        }
                        const delay = interval - now
                        const total = Math.floor(delay / 1000)
                        const hours = String(Math.floor(total / 3600)).padStart(2, '0')
                        const minutes = String(Math.floor((total % 3600) / 60)).padStart(2, '0')
                        const seconds = String(total % 60).padStart(2, '0')
                        const detail = new Date(Date.now() + delay)
                        logger.log(`🕒 [${task}] - Sẽ chạy sau ${hours}:${minutes}:${seconds} (${detail.toLocaleTimeString()})`)
                        const scheduler = setTimeout(() => {
                            this.enqueue(async () => {
                                await handler()
                                times.shift()
                                step()
                            })
                        }, delay)
                        this.schedulers.set(task, scheduler)
                        return
                    }
                    times.shift()
                }
                this.schedulers.delete(task)
            }
            step()
        })
    }

    repeat({ task = '', interval, condition, handler }) {
        const step = () => {
            this.enqueue(async () => {
                await handler()
                if (this.repeaters.has(task)) {
                    clearTimeout(this.repeaters.get(task))
                }
                if (condition()) {
                    const delay = typeof interval === 'function' ? interval() : interval
                    const total = Math.floor(delay / 1000)
                    const hours = String(Math.floor(total / 3600)).padStart(2, '0')
                    const minutes = String(Math.floor((total % 3600) / 60)).padStart(2, '0')
                    const seconds = String(total % 60).padStart(2, '0')
                    const detail = new Date(Date.now() + delay)
                    logger.log(`🕒 [${task}] - Sẽ chạy sau ${hours}:${minutes}:${seconds} (${detail.toLocaleTimeString()})`)
                    const repeater = setTimeout(step, delay)
                    this.repeaters.set(task, repeater)
                } else {
                    this.repeaters.delete(task)
                }
            })
        }
        step()
    }

    cancel(task) {
        const scheduler = this.schedulers.get(task)
        if (scheduler) {
            clearTimeout(scheduler)
            this.schedulers.delete(task)
        }
        const repeater = this.repeaters.get(task)
        if (repeater) {
            clearTimeout(repeater)
            this.repeaters.delete(task)
        }
    }

    async next() {
        while (this.queue.length) {
            const operation = this.queue.shift()
            try {
                await operation()
            } catch (error) {
                logger.log(`🔴 [Task Manager]: ${error}`)
            }
        }
        this.running = false
    }

    async trigger({ codes = [], tasks, blessings = { gift: false, lixi: false }, bets = [1, 2], battles = { autoOn: true, options: { online: true, retries: 3 } }, tab = null }) {
        let targets = Task.ALL
        if (Array.isArray(tasks) && tasks.length > 0) {
            const isArrayString = tasks.every(task => typeof task === 'string')
            const isArrayNumber = tasks.every(task => typeof task === 'number')
            if (isArrayString) {
                targets = [...new Set(tasks.filter(task => Task[task]))]
            } else if (isArrayNumber) {
                targets = [...new Set(tasks.flatMap(id => TaskGroups[id] || []))]
            }
        }

        const userData = await storage.getUserData()
        const { user_id } = Better_Messages || {}
        if (!user_id) return logger.log(`🔴 [HoatHinh3D] - Không tìm thấy user_id.`)
        const user = userData[user_id] || (userData[user_id] = {})

        const viphh3d = new VIPHH3D(user)
        const tienduyen = new TienDuyen(user)
        const luanvo = new LuanVo(user)

        await viphh3d.trigger()
        if (blessings.gift) {
            this.enqueue(() => tienduyen.triggerGift())
            this.enqueue(() => tienduyen.triggerWish())
        }
        if (codes.length) this.enqueue(() => new LinhThach(codes).trigger())
        for (const task of targets) {
            switch (task) {
                case Task.BI_CANH:
                    this.repeat({
                        task: task,
                        interval: () => {
                            const cooldown = 7 * 60 * 1000
                            const last = user.last_bicanh || 0
                            const remaining = last + cooldown - Date.now()
                            return remaining > 0 ? remaining : cooldown
                        },
                        condition: () => user.bicanh < 5,
                        handler: async () => {
                            await new TongMon(user).triggerBiCanh()
                            storage.setUserData(userData)
                        }
                    })
                    break
                case Task.TIEN_DUYEN:
                    this.schedule({
                        task: task,
                        times: [
                            "11:50", "11:55", "11:57", "11:59",   
                            "12:00", "12:02", "12:04", "12:06", "12:08", "12:10", "12:12", "12:14", "12:16", "12:18",
                            "12:20", "12:22", "12:24", "12:26", "12:28", "12:30", "12:32", "12:34", "12:36", "12:38",
                            "12:40", "12:42", "12:44", "12:46", "12:48", "12:50", "12:52", "12:54", "12:56", "12:58",
                            "13:00", "13:02", "13:04", "13:06", "13:08", "13:10", "13:12", "13:14", "13:16", "13:18",
                            "13:20", "13:22", "13:24", "13:26", "13:28", "13:30", "13:32", "13:34", "13:36", "13:38",
                            "13:40", "13:42", "13:44", "13:46", "13:48", "13:50", 
                            "19:00", "19:02", "19:04", "19:06", "19:08", "19:10", "19:12", "19:14", "19:16", "19:18",
                            "19:20", "19:22", "19:24", "19:26", "19:28", "19:30", "19:32", "19:34", "19:36", "19:38",
                            "19:40", "19:42", "19:44", "19:46", "19:48", "19:50", "19:52", "19:54", "19:56", "19:58",
                            "20:00", "20:02", "20:04", "20:06", "20:08", "20:10", "20:12", "20:14", "20:16", "20:18",
                            "20:20", "20:22", "20:24", "20:26", "20:28", "20:30", "20:32", "20:34", "20:36", "20:38",
                            "20:40", "20:42", "20:44", "20:46", "20:48", "20:50"
                        ],
                        last: () => user.last_wedding ? new Date(user.last_wedding).getTime() : null,
                        handler: async () => {
                            await new TienDuyen(user).scanBlessing(null, blessings.lixi)
                            storage.setUserData(userData)
                        }
                    })
                    break
                case Task.DIEM_DANH:
                    this.enqueue(() => new DiemDanh(user).trigger())
                    break
                case Task.VAN_DAP:
                    this.enqueue(() => new VanDap(user).trigger())
                    break
                case Task.TE_LE:
                    this.enqueue(() => new TongMon(user).triggerTeLe())
                    break
                case Task.VONG_QUAY_PHUC_VAN:
                    this.enqueue(() => new VongQuayPhucVan(user).trigger())
                    break
                case Task.EVENT:
                    this.enqueue(() => new EventGame().trigger())
                    break
                case Task.DO_THACH:
                    this.schedule({
                        task: task,
                        times: [
                        "06:30:00", "08:30:00", "10:00:00", "12:00:00", "12:30:00",
                        "16:30:00", "17:30:00", "18:00:00", "19:00:00", "20:00:00",
                    ],
                        last: () => null,
                        handler: async () => {
                            await new DoThach(bets).trigger()
                        }
                    })
                    break
                case Task.THI_LUYEN_TONG_MON:
                    this.repeat({
                        task: task,
                        interval: () => {
                            const cooldown = getCooldown(task, user.vip)
                            const last = user.last_thiluyen || 0
                            const remaining = last + cooldown - Date.now()
                            return remaining > 0 ? remaining : cooldown
                        },
                        condition: () => user.thiluyen < 3,
                        handler: async () => {
                            await new ThiLuyenTongMon(user).trigger()
                            storage.setUserData(userData)
                        }
                    })
                    break
                case Task.PHUC_LOI_DUONG:
                    this.repeat({
                        task: task,
                        interval: () => {
                            const cooldown = getCooldown(task, user.vip)
                            const last = user.last_phucloi || 0
                            const remaining = last + cooldown - Date.now()
                            return remaining > 0 ? remaining : cooldown
                        },
                        condition: () => user.phucloi < 4,
                        handler: async () => {
                            await new PhucLoiDuong(user).trigger()
                            storage.setUserData(userData)
                        }
                    })
                    break
                case Task.HOANG_VUC:
                    this.repeat({
                        task: task,
                        interval: () => {
                            const cooldown = getCooldown(task, user.vip)
                            const last = user.last_hoangvuc || 0
                            const remaining = last + cooldown - Date.now()
                            return remaining > 0 ? remaining : cooldown
                        },
                        condition: () => user.hoangvuc?.attack < 5,
                        handler: async () => {
                            await new HoangVuc(user).trigger()
                            storage.setUserData(userData)
                        }
                    })
                    break
                case Task.LUAN_VO:
                    this.enqueue(() => luanvo.triggerReceive(battles.autoOn))
                    this.enqueue(() => luanvo.triggerSend(battles.options))
                    break
                case Task.DUA_TOP:
                    this.repeat({
                        task: task,
                        interval: () => {
                            const last = user.last_duatop || 0
                            const cooldown = ((6 * 60 + 30) * 60) * 1000
                            const remaining = last + cooldown - Date.now()
                            const delay = Math.floor(Math.random() * 4)
                            return (remaining > 0 ? remaining : (5 * 60 * 1000)) + delay
                        },
                        condition: () => true,
                        handler: async () => {
                            await new DuaTop(user).trigger({ tab })
                            storage.setUserData(userData)
                        }
                    })
                    break
                default:
                    break
            }
        }
        this.enqueue(() => luanvo.triggerReceive(battles.autoOn))
        this.enqueue(async () => {
            await new HoatDongNgay(user).triggerReward()
            if (user.hoatdongngay === 2) await new VongQuayPhucVan(user).trigger()
        })

        this.enqueue(() => {
            storage.setUserData(userData)
            logger.log('🍀🍀🍀🍀🍀🍀🍀🍀🍀🍀')
        })
    }
}

const manager = new TaskManager()

// Danh sách các nhiệm vụ cần thực hiện.
// ➤ Nếu muốn chạy nhiệm vụ nào, chỉ cần thêm ID tương ứng vào mảng `tasks`.
// ➤ Ví dụ: tasks = [1, 4] - Chạy các hoạt động Điểm Danh, Vấn Đáp, Tế Lễ và Phúc Lợi.
// ➤ Ví dụ: tasks = [0, 2] - Chạy các hoạt động Tiên Duyên, Đổ Thạch.
// Danh sách nhiệm vụ:
// -1 - Bí Cảnh
//  0 - Tiên Duyên
//  1 - Điểm Danh - Vấn Đáp - Tế Lễ
//  2 - Đổ Thạch
//  3 - Thí Luyện Tông Môn
//  4 - Phúc Lợi
//  5 - Hoang Vực
// 10 - Luận Võ - Gửi Khiêu Chiến
// 26 - Đua Top
// 50 - Ban Phúc
const tasks = [-1, 0, 1, 2, 3, 4, 5, 10]

// Tuỳ chỉnh trong Tiên Duyên
// `lixi` - Nhận Lì Xì (nếu có) (true hoặc false).
// ➤ lixi: true = Chúc phúc Tiên Duyên + Nhận Lì Xì.
// ➤ lixi: false = Chỉ chúc phúc Tiên Duyên + Không nhận Lì Xì.
const blessings = { gift: true, lixi: true }

// Loại đá bạn muốn cược trong Đổ Thạch - Từ 1 đến 6 (number).
// ➤ Nếu muốn thay đổi loại đá để cược, chỉ cần chỉnh lại các con số trong mảng `bets`.
// ➤ Ví dụ: bets = [1, 4] - Cược vào 2 loại đá có tỉ lệ thưởng cao thứ 1 và thứ 4.
const bets = [1, 2]

// Tuỳ chỉnh trong Luận Võ
// `autoOn` - Tự động nhận khiêu chiến trong Luận Võ (true hoặc false).
// ➤ autoOn: true = Bật tự động nhận khiêu chiến.
// ➤ autoOn: false = Tắt tự động nhận khiêu chiến.
// `options` - Tùy chọn gửi khiêu chiến trong Luận Võ - `online` (true hoặc false) - `retries` (number).
// ➤ online: false = Không tự động tìm đánh người Online khi lượt gửi người Theo dõi chưa đạt tối đa.
// ➤ online: true = Tự động tìm đánh người Online khi lượt gửi người Theo dõi chưa đạt tối đa.
// ➤ retries: 3 = Số lần tải lại danh sách người Online.
const battles = { autoOn: true, options: { online: true, retries: 3 } }

// Danh sách code cần nhập trong Linh Thạch (text).
// ➤ Ví dụ: codes = ["NOTHINGIMPOSSIBLE", "KETTHUCDUATOP"] hoặc codes = ['NOTHINGIMPOSSIBLE', 'KETTHUCDUATOP']
const codes = ["baotri2309"]

async function trigger({ codes, tasks, blessings, bets, battles, tab = null }) {
    let userData = await storage.getUserData()
    const { user_id } = Better_Messages || {}
    if (!user_id) return logger.log(`🔴 [HoatHinh3D] - Không tìm thấy user_id.`)
    let user = userData[user_id] || (userData[user_id] = {})

    const viphh3d = new VIPHH3D(user)
    const tienduyen = new TienDuyen(user)
    const tongmon = new TongMon(user)
    const luanvo = new LuanVo(user)
    const vongquay = new VongQuayPhucVan(user)

    await viphh3d.trigger()
    if (blessings.gift) {
        await tienduyen.triggerGift()
        await tienduyen.triggerWish()
    }
    if (codes.length) await new LinhThach(codes).trigger()
    if (tasks.includes(-1)) await tongmon.triggerBiCanh()
    if (tasks.includes(0)) await tienduyen.scanBlessing(null, blessings.lixi)
    if (tasks.includes(1)) {
        await new DiemDanh(user).trigger()
        await new VanDap(user).trigger()
        await tongmon.triggerTeLe()
        await vongquay.trigger()
        await new EventGame().trigger()
    }
    if (tasks.includes(2)) await new DoThach(bets).trigger()
    if (tasks.includes(3)) await new ThiLuyenTongMon(user).trigger()
    if (tasks.includes(4)) await new PhucLoiDuong(user).trigger()
    if (tasks.includes(5)) await new HoangVuc(user).trigger()
    if (tasks.includes(10)) {
        await luanvo.triggerReceive(battles.autoOn)
        await luanvo.triggerSend(battles.options)
    }
    if (tasks.includes(26)) await new DuaTop(user).trigger({ tab })
    if (tasks.includes(50)) await new BanPhuc().trigger()
    await luanvo.triggerReceive(battles.autoOn)
    await new HoatDongNgay(user).triggerReward()
    if (user.hoatdongngay === 2) await vongquay.trigger()

    storage.setUserData(userData)
    logger.log('🍀🍀🍀🍀🍀🍀🍀🍀🍀🍀')
}
// --- HÀM KHỞI ĐỘNG SCRIPT ---
(async function main() {
    try {
        // Bước 1: Xác thực người dùng trước khi chạy bất kỳ tác vụ nào
        const { userId, name } = await verifyAndReportUser();

        // Bước 2: Nếu xác thực thành công, tiếp tục khởi tạo UI và các tác vụ
        logger.log(`🟢 Xác thực: ID:${userId}(${name}) thành công. Bắt đầu khởi tạo, chạy các tác vụ tự động...`, LoggerMessageType.SUCCESS);
        new TaskRunnerUI;
        // let tab = window.open('about:blank', '_blank');
        manager.trigger({ codes, tasks, blessings, bets, battles});
        // manager.trigger({ tasks: [26], tab }); // Chạy Đua Top (ID 26)
    } catch (error) {
        // Nếu xác thực thất bại, `verifyAndReportUser` sẽ ném lỗi và bị bắt ở đây
        logger.log(`🔴 Script đã dừng do lỗi xác thực: ${error.message}`, 'error');
    }
})();
