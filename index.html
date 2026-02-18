<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>FolkFound - Premium Experience</title>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- GLOBAL & RESET --- */
        :root {
            --primary: #FF7043; --primary-dark: #E64A19; --secondary: #263238;
            --bg-color: #F7F9FC; --white: #FFFFFF;
            --shadow-card: 0 4px 20px rgba(0,0,0,0.08);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Kanit', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background-color: #E0E5EC; display: flex; justify-content: center; align-items: center; min-height: 100vh; }

        /* --- IPHONE FRAME --- */
        .iphone-frame {
            width: 375px; height: 812px; background-color: var(--bg-color);
            border-radius: 40px; position: relative;
            box-shadow: 0 0 0 12px #222, 0 30px 80px rgba(0,0,0,0.4);
            overflow: hidden; display: flex; flex-direction: column;
        }
        .notch {
            position: absolute; top: 0; left: 50%; transform: translateX(-50%);
            width: 160px; height: 30px; background-color: #222;
            border-bottom-left-radius: 18px; border-bottom-right-radius: 18px; z-index: 1000;
        }
        .status-bar {
            height: 44px; display: flex; justify-content: space-between; padding: 12px 25px 0;
            font-size: 14px; font-weight: 600; color: #333; z-index: 999;
            position: absolute; width: 100%; top: 0; pointer-events: none;
        }

        /* --- SCREENS --- */
        .screen {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: var(--bg-color); display: flex; flex-direction: column;
            transition: transform 0.3s cubic-bezier(0.2, 0.8, 0.2, 1); z-index: 10;
        }
        .screen.hidden { transform: translateX(100%); pointer-events: none; }
        .screen.active { transform: translateX(0); }

        .content-scroll { flex: 1; overflow-y: auto; padding-bottom: 100px; scrollbar-width: none; }
        .content-scroll::-webkit-scrollbar { display: none; }

        /* --- HOME --- */
        .header-home { padding: 70px 24px 20px; }
        .app-name { font-size: 28px; font-weight: 700; color: var(--secondary); margin-bottom: 20px; letter-spacing: -0.5px; }
        
        .search-wrapper { position: relative; box-shadow: 0 4px 15px rgba(0,0,0,0.03); border-radius: 16px; }
        .search-input { width: 100%; padding: 16px 20px 16px 50px; border: none; border-radius: 16px; background: var(--white); font-size: 15px; outline: none; }
        .search-icon { position: absolute; left: 20px; top: 16px; color: #aaa; }

        /* --- CATEGORIES (FIXED SCROLL) --- */
        .categories { 
            display: flex; gap: 12px; padding: 0 24px; margin-bottom: 24px; 
            overflow-x: auto; scrollbar-width: none; cursor: grab; /* เพิ่ม cursor */
        }
        .categories::-webkit-scrollbar { display: none; }
        .categories.active { cursor: grabbing; cursor: -webkit-grabbing; }

        .cat-pill { 
            padding: 8px 18px; background: var(--white); border-radius: 25px; 
            font-size: 13px; color: #666; white-space: nowrap; font-weight: 500; transition: 0.2s;
            flex-shrink: 0; /* !! สำคัญมาก: ห้ามหดตัว !! */
            user-select: none; /* ห้ามคลุมดำเวลาลาก */
        }
        .cat-pill.active { background: var(--primary); color: var(--white); box-shadow: 0 4px 12px rgba(255, 112, 67, 0.3); }

        /* --- CARDS --- */
        .card-list { padding: 0 24px; }
        .guide-card {
            background: var(--white); border-radius: 20px; margin-bottom: 20px;
            box-shadow: var(--shadow-card); display: flex; overflow: hidden;
            height: 140px; transition: transform 0.1s; cursor: pointer; position: relative;
        }
        .guide-card:active { transform: scale(0.98); }
        .card-img-box { width: 120px; position: relative; }
        .card-img-box img { width: 100%; height: 100%; object-fit: cover; }
        .badge-verified {
            position: absolute; top: 10px; left: 10px;
            background: rgba(255, 255, 255, 0.9); color: #27ae60;
            border-radius: 20px; padding: 5px 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            font-size: 11px; font-weight: 600; display: flex; align-items: center; gap: 4px; backdrop-filter: blur(4px);
        }
        .card-details { flex: 1; padding: 16px; display: flex; flex-direction: column; justify-content: space-between; }
        .guide-name { font-size: 18px; font-weight: 700; color: var(--secondary); }
        .guide-loc { font-size: 12px; color: #888; display: flex; align-items: center; gap: 4px; margin-top: 4px; }
        .guide-skill { font-size: 11px; color: var(--primary-dark); background: #FFCCBC; padding: 4px 10px; border-radius: 6px; width: fit-content; margin-top: 8px; font-weight: 500; }
        .guide-footer { display: flex; justify-content: space-between; align-items: center; margin-top: auto; }
        .rating { font-size: 12px; font-weight: 600; color: #333; display: flex; align-items: center; gap: 3px;}
        .price { font-size: 16px; font-weight: 700; color: var(--primary); }
        .price span { font-size: 10px; color: #999; font-weight: 400; }

        /* --- DETAIL --- */
        .detail-hero { height: 300px; position: relative; }
        .detail-hero img { width: 100%; height: 100%; object-fit: cover; }
        .back-btn {
            position: absolute; top: 50px; left: 24px; width: 44px; height: 44px; background: rgba(255,255,255,0.9);
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
            color: #333; font-size: 18px; cursor: pointer; z-index: 10; box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        .detail-content { background: var(--white); border-top-left-radius: 35px; border-top-right-radius: 35px; margin-top: -40px; padding: 35px 24px 120px; position: relative; min-height: 500px; }
        .detail-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 20px; }
        .detail-title h1 { font-size: 26px; color: var(--secondary); line-height: 1.2; }
        .detail-rating { background: #FFF9C4; padding: 6px 12px; border-radius: 12px; font-weight: 700; color: #F9A825; display: flex; align-items: center; gap: 5px; font-size: 14px; }
        .section-title { font-size: 18px; font-weight: 600; margin: 30px 0 12px; color: var(--secondary); }
        .story-text { font-size: 15px; color: #555; line-height: 1.7; }
        .bottom-action-bar {
            position: absolute; bottom: 0; left: 0; width: 100%; padding: 20px 24px 35px; background: var(--white);
            box-shadow: 0 -5px 25px rgba(0,0,0,0.06); display: flex; justify-content: space-between; align-items: center; z-index: 20;
        }
        .price-val { font-size: 22px; font-weight: 700; color: var(--primary); }
        .btn-book { background: var(--primary); color: white; padding: 16px 32px; border-radius: 18px; font-weight: 600; border: none; box-shadow: 0 8px 20px rgba(255, 112, 67, 0.3); cursor: pointer; }

        /* --- CHAT --- */
        .chat-header {
            padding: 60px 20px 15px; background: var(--white); display: flex; align-items: center; gap: 15px;
            box-shadow: 0 2px 15px rgba(0,0,0,0.04); z-index: 20;
        }
        .chat-avatar { width: 42px; height: 42px; border-radius: 50%; object-fit: cover; }
        .chat-area { flex: 1; padding: 20px; background: #F7F9FC; overflow-y: auto; display: flex; flex-direction: column; gap: 15px;}
        .msg { max-width: 75%; padding: 14px 18px; font-size: 15px; line-height: 1.5; position: relative; word-wrap: break-word; transition: all 0.3s;}
        .msg-left { background: var(--white); border-radius: 20px 20px 20px 4px; color: #333; align-self: flex-start; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
        .msg-right { background: var(--primary); border-radius: 20px 20px 4px 20px; color: white; align-self: flex-end; box-shadow: 0 4px 12px rgba(255, 112, 67, 0.2); }
        .typing-indicator { font-size: 12px; color: #888; margin-left: 20px; display: none; font-style: italic;}
        .chat-input-area {
            padding: 15px 20px 35px; background: var(--white); display: flex; gap: 12px; align-items: center; border-top: 1px solid #f0f0f0;
        }
        .input-msg { flex: 1; background: #f5f5f5; border: none; padding: 14px 18px; border-radius: 25px; outline: none; font-size: 15px; color: #333; }
        .btn-send { color: var(--primary); font-size: 22px; padding: 10px; cursor: pointer; }

        /* --- BOTTOM NAV --- */
        .bottom-nav {
            position: absolute; bottom: 0; width: 100%; height: 85px; background: var(--white);
            display: flex; justify-content: space-around; align-items: center; padding-bottom: 15px; border-top: 1px solid #f5f5f5; z-index: 100;
        }
        .nav-item { color: #C0C0C0; font-size: 26px; transition: 0.2s; cursor: pointer;}
        .nav-item.active { color: var(--primary); }
        .nav-chat-wrap { position: relative; top: -25px; }
        .nav-chat-btn {
            width: 64px; height: 64px; background: var(--secondary); border-radius: 50%;
            box-shadow: 0 10px 25px rgba(38, 50, 56, 0.3); display: flex; align-items: center; justify-content: center;
            color: white; font-size: 26px; cursor: pointer; border: 4px solid var(--white);
        }
        .home-indicator { position: absolute; bottom: 8px; left: 50%; transform: translateX(-50%); width: 135px; height: 5px; background: #000; border-radius: 10px; z-index: 1000; opacity: 0.2; }
    </style>
</head>
<body>

    <div class="iphone-frame">
        <div class="notch"></div>
        <div class="status-bar">
            <span>10:30</span>
            <span><i class="fa-solid fa-wifi"></i> 100%</span>
        </div>

        <div class="screen active" id="screen-home">
            <div class="content-scroll">
                <div class="header-home">
                    <h1 class="app-name">FolkFound <span style="color:var(--primary)">.</span></h1>
                    <div class="search-wrapper">
                        <i class="fa-solid fa-magnifying-glass search-icon"></i>
                        <input type="text" class="search-input" placeholder="ค้นหาชุมชน, ผู้นำเที่ยว...">
                    </div>
                </div>

                <div class="categories" id="categories-scroll">
                    <div class="cat-pill active">ทั้งหมด</div>
                    <div class="cat-pill">🏔️ เดินป่า</div>
                    <div class="cat-pill">🛶 พายเรือ</div>
                    <div class="cat-pill">🍜 อาหาร</div>
                    <div class="cat-pill">🏺 งานฝีมือ</div>
                    <div class="cat-pill">📸 ถ่ายรูป</div>
                    <div class="cat-pill">🧘 สปา/นวด</div>
                    <div class="cat-pill">☕ กาแฟ</div>
                </div>

                <div class="card-list" id="guide-list-container">
                    </div>
            </div>
            
            <div class="bottom-nav">
                <i class="fa-solid fa-compass nav-item active"></i>
                <div class="nav-chat-wrap" onclick="goToChat('Support')">
                    <div class="nav-chat-btn"><i class="fa-solid fa-comment-dots"></i></div>
                </div>
                <i class="fa-solid fa-user nav-item"></i>
            </div>
        </div>

        <div class="screen hidden" id="screen-detail">
            <div class="content-scroll">
                <div class="detail-hero">
                    <img id="detail-img" src="" alt="">
                    <div class="back-btn" onclick="goBack()"><i class="fa-solid fa-arrow-left"></i></div>
                </div>
                <div class="detail-content">
                    <div class="detail-header">
                        <div class="detail-title">
                            <h1 id="detail-name">ชื่อ</h1>
                            <p id="detail-loc" class="detail-tag"><i class="fa-solid fa-location-dot"></i> สถานที่</p>
                        </div>
                        <div class="detail-rating"><i class="fa-solid fa-star"></i> 4.9</div>
                    </div>

                    <div style="display:flex; gap:10px; margin-bottom:24px;">
                        <span id="detail-skill" style="background:#f0f0f0; padding:6px 12px; border-radius:8px; font-size:12px; color:#555;">Skill</span>
                        <span style="background:#E8F5E9; padding:6px 12px; border-radius:8px; font-size:12px; color:#2E7D32;">✅ ยืนยันตัวตนแล้ว</span>
                    </div>

                    <h3 class="section-title">เกี่ยวกับฉัน</h3>
                    <p class="story-text" id="detail-desc">...</p>

                    <h3 class="section-title">รูปภาพกิจกรรม</h3>
                    <div class="gallery-row">
                        <img src="https://images.unsplash.com/photo-1504328345606-18bbc8c9d7d1?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" class="gallery-img">
                        <img src="https://images.unsplash.com/photo-1516483638261-f4dbaf036963?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" class="gallery-img">
                    </div>
                </div>
            </div>

            <div class="bottom-action-bar">
                <div>
                    <div class="price-total">ราคาเริ่มต้น</div>
                    <div class="price-val" id="detail-price">฿500</div>
                </div>
                <button class="btn-book" onclick="goToChatFromDetail()">ทักแชท / จอง</button>
            </div>
        </div>

        <div class="screen hidden" id="screen-chat">
            <div class="chat-header">
                <div class="back-btn" style="position:static; width:36px; height:36px; background:#f0f0f0; box-shadow:none; margin-right:10px;" onclick="goBack()"><i class="fa-solid fa-arrow-left"></i></div>
                <img id="chat-avatar" src="" class="chat-avatar">
                <div>
                    <h3 id="chat-name" style="font-size:16px; font-weight:700;">คู่สนทนา</h3>
                    <div style="font-size:11px; color:#27ae60; display:flex; align-items:center; gap:4px;">
                        <div style="width:6px; height:6px; background:#27ae60; border-radius:50%;"></div> ออนไลน์
                    </div>
                </div>
            </div>

            <div class="chat-area" id="message-container">
            </div>
            
            <div class="typing-indicator" id="typing-indicator">กำลังพิมพ์...</div>

            <div class="chat-input-area">
                <i class="fa-solid fa-plus" style="color:var(--primary); font-size:20px;"></i>
                <input type="text" class="input-msg" placeholder="พิมพ์ข้อความ..." id="msg-input" onkeypress="handleEnter(event)">
                <i class="fa-solid fa-paper-plane btn-send" onclick="sendMessage()"></i>
            </div>
        </div>

        <div class="home-indicator"></div>
    </div>

    <script>
        // --- 1. ENABLE DRAG SCROLL (ให้เมาส์ลากได้) ---
        const slider = document.querySelector('.categories');
        let isDown = false;
        let startX;
        let scrollLeft;

        slider.addEventListener('mousedown', (e) => {
            isDown = true;
            slider.classList.add('active');
            startX = e.pageX - slider.offsetLeft;
            scrollLeft = slider.scrollLeft;
        });
        slider.addEventListener('mouseleave', () => { isDown = false; slider.classList.remove('active'); });
        slider.addEventListener('mouseup', () => { isDown = false; slider.classList.remove('active'); });
        slider.addEventListener('mousemove', (e) => {
            if(!isDown) return;
            e.preventDefault();
            const x = e.pageX - slider.offsetLeft;
            const walk = (x - startX) * 2; // Scroll fast
            slider.scrollLeft = scrollLeft - walk;
        });

        // --- 2. DATABASE ---
        const dbGuides = [
            { id: 'g1', name: 'ป้าเพ็ญ (65)', loc: 'ชุมชนอัมพวา', skill: 'ทำขนมไทยโบราณ', price: '฿500', unit: '/วัน', desc: 'สวัสดีจ้ะ ป้าทำขนมไทยมา 40 ปีแล้ว อยากให้เด็กรุ่นใหม่มาลองทำน้ำตาลมะพร้าวแท้ๆ กันนะ', img: 'https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', badge: 'Local', badgeColor: '#27ae60', badgeIcon: 'fa-check-circle' },
            { id: 'g2', name: 'ลุงคำ (58)', loc: 'บ้านแม่กลางหลวง', skill: 'เดินป่า ดอยอินทนนท์', price: '฿800', unit: '/ทริป', desc: 'ผมรู้จักป่าที่นี่ทุกตารางนิ้ว พาไปดูนาขั้นบันไดช่วงที่สวยที่สุด จิบกาแฟคั่วมือที่ผมปลูกเองครับ', img: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', badge: 'Pro', badgeColor: '#2980b9', badgeIcon: 'fa-medal' },
            { id: 'g3', name: 'น้องฝ้าย (22)', loc: 'ดอยผาฮี้ เชียงราย', skill: 'พาถ่ายรูปคาเฟ่', price: '฿350', unit: '/ชม.', desc: 'ใครสายคอนเทนต์มาทางนี้! ฝ้ายรู้มุมลับๆ บนดอยเยอะมาก รับรองได้รูปปังๆ กลับไปแน่นอนค่ะ', img: 'https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', badge: 'Teen', badgeColor: '#8e44ad', badgeIcon: 'fa-camera' }
        ];

        const chatSessions = {
            'g1': [{ sender: 'left', text: 'สวัสดีจ้ะ สนใจมาทำขนมวันไหนจ๊ะ?' }],
            'g2': [{ sender: 'left', text: 'สวัสดีครับ อยากเดินป่าเส้นทางไหนบอกลุงได้เลย' }],
            'g3': [{ sender: 'left', text: 'ฮัลโหลล! อยากได้รูปฟีลไหนบอกฝ้ายได้เลยน้า 📸' }],
            'support': [{ sender: 'left', text: 'สวัสดีครับ มีอะไรให้ทีมงาน FolkFound ช่วยดูแลไหมครับ?' }]
        };

        let currentChatID = null;
        let currentGuide = null;

        function renderGuides() {
            const container = document.getElementById('guide-list-container');
            let html = '';
            dbGuides.forEach(g => {
                html += `
                <div class="guide-card" onclick="goToDetail('${g.id}')">
                    <div class="card-img-box">
                        <img src="${g.img}" alt="">
                        <div class="badge-verified">
                            <i class="fa-solid ${g.badgeIcon}"></i> ${g.badge}
                        </div>
                    </div>
                    <div class="card-details">
                        <div>
                            <h3 class="guide-name">${g.name}</h3>
                            <p class="guide-loc"><i class="fa-solid fa-location-dot" style="color:var(--primary)"></i> ${g.loc}</p>
                            <div class="guide-skill">${g.skill}</div>
                        </div>
                        <div class="guide-footer">
                            <span class="rating"><i class="fa-solid fa-star" style="color:#FBC02D"></i> 4.9</span>
                            <span class="price">${g.price}<span>${g.unit}</span></span>
                        </div>
                    </div>
                </div>`;
            });
            container.innerHTML = html;
        }

        function showScreen(screenId) {
            document.querySelectorAll('.screen').forEach(el => { el.classList.remove('active'); el.classList.add('hidden'); });
            const target = document.getElementById(screenId); target.classList.remove('hidden'); target.classList.add('active');
        }

        function goToDetail(id) {
            currentGuide = dbGuides.find(g => g.id === id);
            document.getElementById('detail-name').innerText = currentGuide.name;
            document.getElementById('detail-loc').innerHTML = `<i class="fa-solid fa-location-dot"></i> ${currentGuide.loc}`;
            document.getElementById('detail-img').src = currentGuide.img;
            document.getElementById('detail-skill').innerText = currentGuide.skill;
            document.getElementById('detail-price').innerText = currentGuide.price;
            document.getElementById('detail-desc').innerText = currentGuide.desc;
            showScreen('screen-detail');
        }

        function goToChatFromDetail() { startChatSession(currentGuide.id, currentGuide.name, currentGuide.img); }
        function goToChat(type) { if(type === 'Support') startChatSession('support', 'Local Support', 'https://cdn-icons-png.flaticon.com/512/4712/4712035.png'); }

        function startChatSession(id, name, img) {
            currentChatID = id;
            document.getElementById('chat-name').innerText = name;
            document.getElementById('chat-avatar').src = img;
            renderMessages();
            showScreen('screen-chat');
        }

        function renderMessages() {
            const container = document.getElementById('message-container');
            container.innerHTML = '';
            const history = chatSessions[currentChatID] || [];
            history.forEach(msg => {
                const div = document.createElement('div');
                div.className = `msg msg-${msg.sender}`;
                div.innerText = msg.text;
                container.appendChild(div);
            });
            container.scrollTop = container.scrollHeight;
        }

        function handleEnter(e) { if(e.key === 'Enter') sendMessage(); }
        function sendMessage() {
            const input = document.getElementById('msg-input');
            const text = input.value.trim();
            if(text === "") return;
            addMessage('right', text);
            input.value = "";
            const typing = document.getElementById('typing-indicator');
            typing.style.display = 'block';
            document.getElementById('message-container').scrollTop = document.getElementById('message-container').scrollHeight;

            setTimeout(() => {
                typing.style.display = 'none';
                const reply = generateSmartReply(text, currentChatID);
                addMessage('left', reply);
            }, 1200);
        }

        function addMessage(sender, text) {
            if(!chatSessions[currentChatID]) chatSessions[currentChatID] = [];
            chatSessions[currentChatID].push({ sender, text });
            const container = document.getElementById('message-container');
            const div = document.createElement('div');
            div.className = `msg msg-${sender}`;
            div.innerText = text;
            container.appendChild(div);
            container.scrollTop = container.scrollHeight;
        }

        function generateSmartReply(input, id) {
            input = input.toLowerCase();
            if(input.includes('ราคา') || input.includes('บาท')) {
                if(id === 'g1') return 'ทำขนมคิดคนละ 500 บาทจ้ะ รวมวัตถุดิบหมดแล้วนะ';
                if(id === 'g2') return 'ค่าพาเดินป่า 800 บาทครับ ราคานี้รวมกาแฟดริปให้ด้วยครับ';
                if(id === 'g3') return 'ค่าจ้างฝ้ายชม.ละ 350 ค่ะ ถ่ายรัวๆ ไม่จำกัดรูปเลย';
                return 'ราคาขึ้นอยู่กับกิจกรรมครับ';
            }
            if(input.includes('ที่ไหน') || input.includes('ไกล')) {
                if(id === 'g1') return 'ป้าอยู่อัมพวานี่เองจ้ะ มาง่าย จอดรถที่วัดแล้วนั่งเรือต่อมาได้เลย';
                if(id === 'g2') return 'บ้านแม่กลางหลวง ดอยอินทนนท์ครับ อากาศกำลังดีเลย';
                return 'อยู่ในชุมชนเลยครับ';
            }
            if(input.includes('ว่าง') || input.includes('จอง')) return 'ช่วงนี้คิวเริ่มแน่นแล้วครับ สนใจจองล็อกวันไว้ก่อนไหมครับ?';
            if(input.includes('ขอบคุณ')) return 'ยินดีครับผม 😊';
            
            if(id === 'g1') return 'จ้ะ เดี๋ยวป้าเตรียมของรอนะ มีอะไรถามเพิ่มได้เลย';
            if(id === 'g2') return 'ครับผม สนใจเส้นทางไหนเป็นพิเศษบอกลุงได้นะ';
            if(id === 'g3') return 'ได้เลยค่าา รีบมาน้า แสงเย็นกำลังสวย!';
            return 'รับทราบครับ เดี๋ยวตรวจสอบข้อมูลให้นะครับ';
        }

        function goBack() {
            const chatScreen = document.getElementById('screen-chat');
            const detailScreen = document.getElementById('screen-detail');
            if (chatScreen.classList.contains('active')) {
                if(currentChatID === 'support') showScreen('screen-home');
                else showScreen('screen-detail');
            } else if (detailScreen.classList.contains('active')) {
                showScreen('screen-home');
            }
        }

        renderGuides();
    </script>
</body>
</html>
