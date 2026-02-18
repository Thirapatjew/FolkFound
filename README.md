<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Local Buddy - Premium Design</title>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- RESET & GLOBAL VARIABES --- */
        :root {
            --primary: #FF7043; /* สีส้มอิฐ ดูอบอุ่น เป็นมิตร */
            --secondary: #263238; /* สีเข้มสำหรับ Text */
            --bg-color: #F7F9FC; /* สีพื้นหลังเทาอ่อนๆ ดูคลีน */
            --card-bg: #FFFFFF;
            --shadow: 0 10px 30px rgba(0,0,0,0.06); /* เงาฟุ้งราคาแพง */
            --radius: 24px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Kanit', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: #E0E5EC;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        /* --- IPHONE FRAME (PREMIUM) --- */
        .iphone-frame {
            width: 375px;
            height: 812px;
            background-color: var(--bg-color);
            border-radius: 40px;
            position: relative;
            box-shadow: 0 0 0 10px #222, 0 30px 80px rgba(0,0,0,0.4);
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }

        .notch {
            position: absolute; top: 0; left: 50%; transform: translateX(-50%);
            width: 160px; height: 30px; background-color: #222;
            border-bottom-left-radius: 18px; border-bottom-right-radius: 18px; z-index: 999;
        }

        .status-bar {
            height: 44px; display: flex; justify-content: space-between; padding: 12px 25px 0;
            font-size: 14px; font-weight: 600; color: #333; z-index: 998;
        }

        /* --- SCREEN MANAGEMENT --- */
        .screen {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: var(--bg-color);
            display: flex; flex-direction: column;
            transition: transform 0.3s ease-in-out;
            z-index: 10;
        }
        
        .screen.hidden {
            transform: translateX(100%);
            pointer-events: none;
        }
        .screen.active {
            transform: translateX(0);
        }

        /* --- SCROLLABLE CONTENT --- */
        .content-scroll {
            flex: 1; overflow-y: auto; padding-bottom: 90px;
            -ms-overflow-style: none; scrollbar-width: none;
        }
        .content-scroll::-webkit-scrollbar { display: none; }

        /* ================= SCREEN 1: HOME ================= */
        .header-home {
            padding: 20px 24px;
        }
        .welcome-text { font-size: 14px; color: #888; }
        .app-name { font-size: 26px; font-weight: 700; color: var(--secondary); margin-bottom: 15px; }
        
        /* Search Bar หรูๆ */
        .search-wrapper {
            position: relative;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border-radius: 16px;
        }
        .search-input {
            width: 100%; padding: 16px 20px 16px 50px;
            border: none; border-radius: 16px;
            background: white; color: var(--secondary); font-size: 16px;
            outline: none;
        }
        .search-icon {
            position: absolute; left: 20px; top: 16px; color: #ccc;
        }

        /* Filter Pills */
        .categories {
            display: flex; gap: 12px; padding: 0 24px; margin-bottom: 20px;
            overflow-x: auto; scrollbar-width: none;
        }
        .cat-pill {
            padding: 8px 16px; background: white; border-radius: 20px;
            font-size: 13px; color: #666; white-space: nowrap;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            transition: 0.2s;
        }
        .cat-pill.active { background: var(--primary); color: white; }

        /* LIST CARDS (Premium Style) */
        .card-list { padding: 0 24px; }
        
        .guide-card {
            background: white;
            border-radius: 20px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            display: flex;
            overflow: hidden;
            height: 140px;
            transition: transform 0.1s;
            cursor: pointer;
            position: relative;
        }
        .guide-card:active { transform: scale(0.98); }

        .card-img-box {
            width: 120px;
            position: relative;
        }
        .card-img-box img { width: 100%; height: 100%; object-fit: cover; }
        .badge-verified {
            position: absolute; top: 10px; left: 10px;
            background: rgba(255,255,255,0.9);
            padding: 4px 8px; border-radius: 12px;
            font-size: 10px; font-weight: 600; color: #27ae60;
            display: flex; align-items: center; gap: 3px;
        }

        /* Divider line (Subtle) */
        .card-divider { width: 1px; background: #f0f0f0; margin: 15px 0; }

        .card-details {
            flex: 1; padding: 15px;
            display: flex; flex-direction: column; justify-content: space-between;
        }
        .guide-name { font-size: 18px; font-weight: 700; color: var(--secondary); }
        .guide-loc { font-size: 12px; color: #888; display: flex; align-items: center; gap: 4px; margin-bottom: 8px; }
        .guide-skill { 
            font-size: 11px; color: var(--primary); background: #FFF3E0; 
            padding: 4px 8px; border-radius: 6px; width: fit-content;
        }
        .guide-footer {
            display: flex; justify-content: space-between; align-items: center; margin-top: auto;
        }
        .rating { font-size: 12px; font-weight: 600; color: #333; display: flex; align-items: center; gap: 3px;}
        .price { font-size: 14px; font-weight: 700; color: var(--primary); }

        /* ================= SCREEN 2: DETAIL PROFILE ================= */
        .detail-hero {
            height: 280px; position: relative;
        }
        .detail-hero img { width: 100%; height: 100%; object-fit: cover; }
        .back-btn {
            position: absolute; top: 50px; left: 20px;
            width: 40px; height: 40px; background: rgba(255,255,255,0.3);
            backdrop-filter: blur(5px); border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            color: white; font-size: 18px; cursor: pointer; z-index: 10;
        }

        .detail-content {
            background: white; border-top-left-radius: 30px; border-top-right-radius: 30px;
            margin-top: -40px; padding: 30px 24px 100px; /* Overlap hero */
            position: relative; min-height: 500px;
        }
        
        .detail-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 20px; }
        .detail-title h1 { font-size: 24px; color: var(--secondary); }
        .detail-tag { color: #888; font-size: 14px; margin-top: 5px; }
        .detail-rating { 
            background: #FFF9C4; padding: 6px 12px; border-radius: 12px; 
            font-weight: 700; color: #FBC02D; display: flex; align-items: center; gap: 5px;
        }

        .section-title { font-size: 16px; font-weight: 600; margin: 25px 0 10px; color: #333; }
        .story-text { font-size: 14px; color: #666; line-height: 1.6; }
        
        .gallery-row { display: flex; gap: 10px; overflow-x: auto; padding-bottom: 10px; }
        .gallery-img { width: 100px; height: 100px; border-radius: 12px; object-fit: cover; flex-shrink: 0;}

        /* Floating Booking Bar */
        .bottom-action-bar {
            position: absolute; bottom: 0; left: 0; width: 100%;
            padding: 20px 24px 30px; background: white;
            box-shadow: 0 -5px 20px rgba(0,0,0,0.05);
            display: flex; justify-content: space-between; align-items: center;
        }
        .price-total { font-size: 12px; color: #888; }
        .price-val { font-size: 20px; font-weight: 700; color: var(--secondary); }
        
        .btn-book {
            background: var(--primary); color: white;
            padding: 14px 30px; border-radius: 16px; font-weight: 600;
            border: none; box-shadow: 0 5px 15px rgba(255, 112, 67, 0.4);
            cursor: pointer; transition: 0.2s;
        }
        .btn-book:active { transform: scale(0.95); }

        /* ================= SCREEN 3: CHAT ================= */
        .chat-header {
            padding: 50px 20px 15px; background: white;
            display: flex; align-items: center; gap: 15px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.03);
        }
        .chat-avatar { width: 40px; height: 40px; border-radius: 50%; object-fit: cover; }
        
        .chat-area { flex: 1; padding: 20px; background: #F7F9FC; overflow-y: auto;}
        
        .msg { max-width: 75%; padding: 12px 16px; margin-bottom: 15px; font-size: 14px; line-height: 1.4; position: relative;}
        .msg-left { 
            background: white; border-radius: 16px 16px 16px 2px; 
            color: #333; align-self: flex-start; 
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        .msg-right { 
            background: var(--primary); border-radius: 16px 16px 2px 16px; 
            color: white; margin-left: auto; 
            box-shadow: 0 5px 10px rgba(255, 112, 67, 0.3);
        }

        .chat-input-area {
            padding: 15px 20px 30px; background: white;
            display: flex; gap: 10px; align-items: center; border-top: 1px solid #eee;
        }
        .input-msg {
            flex: 1; background: #f0f2f5; border: none; padding: 12px 15px;
            border-radius: 20px; outline: none;
        }
        .btn-send { color: var(--primary); font-size: 20px; padding: 10px; cursor: pointer; }

        /* ================= BOTTOM NAV (MAIN) ================= */
        .bottom-nav {
            position: absolute; bottom: 0; width: 100%; height: 85px;
            background: white;
            display: flex; justify-content: space-around; align-items: center;
            padding-bottom: 15px; border-top: 1px solid #f5f5f5;
            z-index: 100;
        }
        .nav-item { color: #C0C0C0; font-size: 24px; transition: 0.2s; cursor: pointer;}
        .nav-item.active { color: var(--primary); }
        
        /* Floating Chat Button (Middle) */
        .nav-chat-wrap { position: relative; top: -25px; }
        .nav-chat-btn {
            width: 60px; height: 60px; background: var(--secondary);
            border-radius: 50%; box-shadow: 0 8px 20px rgba(38, 50, 56, 0.4);
            display: flex; align-items: center; justify-content: center;
            color: white; font-size: 22px; cursor: pointer;
            transition: transform 0.2s;
        }
        .nav-chat-btn:active { transform: scale(0.9); }

        .home-indicator {
            position: absolute; bottom: 8px; left: 50%; transform: translateX(-50%);
            width: 135px; height: 5px; background: #000; border-radius: 10px; z-index: 1000; opacity: 0.2;
        }

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
                    <p class="welcome-text">สวัสดี, วันหยุดไปไหนดี?</p>
                    <h1 class="app-name">เที่ยววิถีชุมชน <span style="color:var(--primary)">.</span></h1>
                    
                    <div class="search-wrapper">
                        <i class="fa-solid fa-magnifying-glass search-icon"></i>
                        <input type="text" class="search-input" placeholder="ค้นหาชุมชน, ผู้นำเที่ยว...">
                    </div>
                </div>

                <div class="categories">
                    <div class="cat-pill active">ทั้งหมด</div>
                    <div class="cat-pill">🏔️ เดินป่า</div>
                    <div class="cat-pill">🛶 พายเรือ</div>
                    <div class="cat-pill">🍜 อาหาร</div>
                    <div class="cat-pill">🏺 งานฝีมือ</div>
                </div>

                <div class="card-list">
                    <div class="guide-card" onclick="goToDetail('ป้าเพ็ญ', 'ชุมชนอัมพวา', 'https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', 'ทำขนมไทย / พายเรือชมสวน')">
                        <div class="card-img-box">
                            <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80" alt="">
                            <div class="badge-verified"><i class="fa-solid fa-check-circle"></i> Local</div>
                        </div>
                        <div class="card-divider"></div>
                        <div class="card-details">
                            <div>
                                <h3 class="guide-name">ป้าเพ็ญ (65)</h3>
                                <p class="guide-loc"><i class="fa-solid fa-location-dot" style="color:var(--primary)"></i> ชุมชนอัมพวา</p>
                                <span class="guide-skill">ทำขนมไทยโบราณ</span>
                            </div>
                            <div class="guide-footer">
                                <span class="rating"><i class="fa-solid fa-star" style="color:#FBC02D"></i> 4.9</span>
                                <span class="price">฿500<span style="font-size:10px; color:#888; font-weight:400">/วัน</span></span>
                            </div>
                        </div>
                    </div>

                    <div class="guide-card" onclick="goToDetail('ลุงคำ', 'บ้านแม่กลางหลวง', 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', 'เดินป่า / ชิมกาแฟคั่วมือ')">
                        <div class="card-img-box">
                            <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80" alt="">
                            <div class="badge-verified"><i class="fa-solid fa-medal"></i> Pro</div>
                        </div>
                        <div class="card-divider"></div>
                        <div class="card-details">
                            <div>
                                <h3 class="guide-name">ลุงคำ (58)</h3>
                                <p class="guide-loc"><i class="fa-solid fa-location-dot" style="color:var(--primary)"></i> บ้านแม่กลางหลวง</p>
                                <span class="guide-skill">เดินป่า ดอยอินทนนท์</span>
                            </div>
                            <div class="guide-footer">
                                <span class="rating"><i class="fa-solid fa-star" style="color:#FBC02D"></i> 5.0</span>
                                <span class="price">฿800<span style="font-size:10px; color:#888; font-weight:400">/ทริป</span></span>
                            </div>
                        </div>
                    </div>

                    <div class="guide-card" onclick="goToDetail('น้องฝ้าย', 'ดอยผาฮี้', 'https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80', 'ถ่ายรูป / จุดเช็คอินลับ')">
                        <div class="card-img-box">
                            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=80" alt="">
                            <div class="badge-verified"><i class="fa-solid fa-check-circle"></i> Local</div>
                        </div>
                        <div class="card-divider"></div>
                        <div class="card-details">
                            <div>
                                <h3 class="guide-name">น้องฝ้าย (22)</h3>
                                <p class="guide-loc"><i class="fa-solid fa-location-dot" style="color:var(--primary)"></i> ดอยผาฮี้ เชียงราย</p>
                                <span class="guide-skill">พาถ่ายรูปคาเฟ่</span>
                            </div>
                            <div class="guide-footer">
                                <span class="rating"><i class="fa-solid fa-star" style="color:#FBC02D"></i> 4.7</span>
                                <span class="price">฿350<span style="font-size:10px; color:#888; font-weight:400">/ชม.</span></span>
                            </div>
                        </div>
                    </div>
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
                            <h1 id="detail-name">ชื่อคนนำเที่ยว</h1>
                            <p id="detail-loc" class="detail-tag"><i class="fa-solid fa-location-dot"></i> สถานที่</p>
                        </div>
                        <div class="detail-rating">
                            <i class="fa-solid fa-star"></i> 4.9
                        </div>
                    </div>

                    <div style="display:flex; gap:10px; margin-bottom:20px;">
                        <span id="detail-skill" style="background:#f0f0f0; padding:6px 12px; border-radius:8px; font-size:12px; color:#555;">Skill</span>
                        <span style="background:#E8F5E9; padding:6px 12px; border-radius:8px; font-size:12px; color:#2E7D32;">✅ ยืนยันตัวตนแล้ว</span>
                    </div>

                    <h3 class="section-title">เกี่ยวกับฉัน</h3>
                    <p class="story-text">
                        สวัสดีค่ะ ยินดีต้อนรับสู่ชุมชนของเรา ฉันเกิดและโตที่นี่ รักในการทำอาหารและเล่าเรื่องราวเก่าๆ อยากให้ทุกคนได้สัมผัสวิถีชีวิตจริงๆ ที่หาไม่ได้จากที่อื่น
                        <br><br>
                        "การท่องเที่ยวไม่ใช่แค่การเห็น แต่คือการสัมผัสด้วยหัวใจ"
                    </p>

                    <h3 class="section-title">รูปภาพกิจกรรม</h3>
                    <div class="gallery-row">
                        <img src="https://images.unsplash.com/photo-1504328345606-18bbc8c9d7d1?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" class="gallery-img">
                        <img src="https://images.unsplash.com/photo-1516483638261-f4dbaf036963?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" class="gallery-img">
                        <img src="https://images.unsplash.com/photo-1596422846543-75c6fc197f07?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&q=80" class="gallery-img">
                    </div>

                    <h3 class="section-title">รีวิวจากนักท่องเที่ยว</h3>
                    <div style="background:#f9f9f9; padding:15px; border-radius:12px; margin-bottom:10px;">
                        <div style="font-size:12px; font-weight:bold; margin-bottom:5px;">คุณสมชาย</div>
                        <div style="font-size:12px; color:#666;">"สนุกมากครับ เป็นกันเอง อาหารอร่อยมาก"</div>
                    </div>
                </div>
            </div>

            <div class="bottom-action-bar">
                <div>
                    <div class="price-total">ราคาเริ่มต้น</div>
                    <div class="price-val">฿500</div>
                </div>
                <button class="btn-book" onclick="goToChatFromDetail()">ทักแชท / จอง</button>
            </div>
        </div>

        <div class="screen hidden" id="screen-chat">
            <div class="chat-header">
                <div class="back-btn" style="position:static; background:none; color:#333; margin-right:10px;" onclick="goBack()"><i class="fa-solid fa-arrow-left"></i></div>
                <img id="chat-avatar" src="" class="chat-avatar">
                <div>
                    <h3 id="chat-name" style="font-size:16px;">คู่สนทนา</h3>
                    <div style="font-size:10px; color:#27ae60;">● กำลังใช้งาน</div>
                </div>
            </div>

            <div class="chat-area" id="message-container">
                <div class="msg msg-left">สวัสดีครับ สนใจอยากไปเที่ยวชุมชนครับ</div>
                <div class="msg msg-right">ยินดีเลยค่ะ! ช่วงนี้อากาศดีมากนะคะ</div>
                <div class="msg msg-left">มีโปรแกรมแนะนำไหมครับ?</div>
                <div class="msg msg-right">มีโปรแกรมทำขนมไทยครึ่งวันค่ะ ได้ลงมือทำเองด้วยนะ สนใจไหมคะ?</div>
            </div>

            <div class="chat-input-area">
                <i class="fa-solid fa-plus" style="color:var(--primary); font-size:20px;"></i>
                <input type="text" class="input-msg" placeholder="พิมพ์ข้อความ..." id="msg-input">
                <i class="fa-solid fa-paper-plane btn-send" onclick="sendMessage()"></i>
            </div>
        </div>

        <div class="home-indicator"></div>
    </div>

    <script>
        // Variables to store current guide info
        let currentGuideName = "";
        let currentGuideImg = "";

        function showScreen(screenId) {
            // Hide all screens
            document.querySelectorAll('.screen').forEach(el => {
                el.classList.remove('active');
                el.classList.add('hidden');
            });
            // Show target screen
            const target = document.getElementById(screenId);
            target.classList.remove('hidden');
            target.classList.add('active');
        }

        // 1. Click Card -> Go to Detail
        function goToDetail(name, loc, img, skill) {
            currentGuideName = name;
            currentGuideImg = img;

            // Set Data
            document.getElementById('detail-name').innerText = name;
            document.getElementById('detail-loc').innerHTML = `<i class="fa-solid fa-location-dot"></i> ${loc}`;
            document.getElementById('detail-img').src = img;
            document.getElementById('detail-skill').innerText = skill;

            showScreen('screen-detail');
        }

        // 2. Click Chat Button (from Detail)
        function goToChatFromDetail() {
            goToChat(currentGuideName, currentGuideImg);
        }

        // 3. Click Chat (General)
        function goToChat(name, img) {
            // If called from Nav without specific person
            if(name === 'Support') {
                name = "Local Support";
                img = "https://cdn-icons-png.flaticon.com/512/4712/4712035.png";
            } else if (!img) {
                img = currentGuideImg; 
            }

            document.getElementById('chat-name').innerText = name;
            document.getElementById('chat-avatar').src = img;
            
            showScreen('screen-chat');
        }

        // 4. Back Button
        function goBack() {
            // Check where we are to decide where to go back
            const chatScreen = document.getElementById('screen-chat');
            const detailScreen = document.getElementById('screen-detail');

            if (chatScreen.classList.contains('active')) {
                // If in Chat, go back to Detail (if we came from there) or Home? 
                // Simple logic: Go back to Home if name is Support, else Detail
                if(document.getElementById('chat-name').innerText === "Local Support"){
                    showScreen('screen-home');
                } else {
                    showScreen('screen-detail');
                }
            } else if (detailScreen.classList.contains('active')) {
                showScreen('screen-home');
            }
        }

        // 5. Send Message (Fake)
        function sendMessage() {
            const input = document.getElementById('msg-input');
            const text = input.value;
            if(text.trim() === "") return;

            const container = document.getElementById('message-container');
            
            // Add User Message
            const userMsg = document.createElement('div');
            userMsg.className = 'msg msg-right';
            userMsg.innerText = text;
            container.appendChild(userMsg);

            input.value = "";
            container.scrollTop = container.scrollHeight;

            // Fake Auto Reply
            setTimeout(() => {
                const botMsg = document.createElement('div');
                botMsg.className = 'msg msg-left';
                botMsg.innerText = "รับทราบค่ะ เดี๋ยวจะรีบตรวจสอบให้นะคะ 😊";
                container.appendChild(botMsg);
                container.scrollTop = container.scrollHeight;
            }, 1000);
        }
    </script>
</body>
</html>
