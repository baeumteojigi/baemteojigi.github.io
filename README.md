<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>배움터지기 | KNOWLEDGE GUARDIAN</title>
    <!-- 고품격 폰트 프리텐다드 적용 -->
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css" />
    <style>
        :root {
            --primary-teal: #005f73;
            --light-teal: #0a9396;
            --silver-bg: #f4f5f7;
            --silver-border: #e2e8f0;
            --dark-text: #111827;
            --gray-text: #6b7280;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, system-ui, Roboto, "Helvetica Neue", "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", "Malgun Gothic", "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", sans-serif;
            letter-spacing: -0.02em;
        }

        body {
            background-color: var(--white);
            color: var(--dark-text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* 1. Header (대기업 스타일의 투명 블러 내비게이션) */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px 10%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }

        .logo {
            font-size: 1.3rem;
            font-weight: 800;
            color: var(--primary-teal);
            text-transform: uppercase;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logo span {
            font-size: 0.85rem;
            font-weight: 400;
            color: var(--gray-text);
        }

        nav a {
            text-decoration: none;
            color: var(--dark-text);
            font-weight: 500;
            margin-left: 35px;
            font-size: 0.95rem;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary-teal);
        }

        /* 2. Hero Section (최고 가치와 가치관을 보여주는 메인 화면) */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 80% 20%, rgba(10, 147, 150, 0.08) 0%, transparent 50%);
        }

        .hero-sub {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--light-teal);
            text-transform: uppercase;
            letter-spacing: 0.15em;
            margin-bottom: 20px;
        }

        .hero-title {
            font-size: 2.8rem;
            font-weight: 800;
            line-height: 1.4;
            margin-bottom: 30px;
            color: var(--dark-text);
        }

        .hero-title span {
            color: var(--primary-teal);
        }

        .hero-desc {
            font-size: 1.2rem;
            color: var(--gray-text);
            max-width: 700px;
            font-weight: 400;
        }

        /* 세션 공통 스타일 */
        section {
            padding: 140px 10%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-header h2 {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--dark-text);
            margin-bottom: 15px;
        }

        .section-header p {
            color: var(--gray-text);
            font-size: 1.05rem;
        }

        /* 3. Protected Value System (수호 · 균형 · 비상 핵심 가치) */
        .values-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
        }

        .value-card {
            background: var(--white);
            padding: 50px 40px;
            border-radius: 16px;
            border: 1px solid var(--silver-border);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .value-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.05);
            border-color: var(--light-teal);
        }

        .value-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--primary-teal);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .value-card:hover::before {
            opacity: 1;
        }

        .value-num {
            font-size: 0.9rem;
            font-weight: 700;
            color: var(--light-teal);
            margin-bottom: 20px;
            display: block;
        }

        .value-card h3 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 15px;
        }

        .value-card p {
            color: var(--gray-text);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        /* 4. Identity System (배움터지기 방패 마크 의미 분석) */
        .identity-section {
            background-color: var(--silver-bg);
        }

        .identity-container {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 60px;
            align-items: center;
        }

        /* 가상의 대기업형 심볼 비주얼 구현 */
        .identity-visual {
            background: linear-gradient(135deg, var(--primary-teal) 0%, #003f4c 100%);
            padding: 80px;
            border-radius: 24px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--white);
            box-shadow: 0 30px 60px rgba(0,63,76, 0.15);
            min-height: 450px;
            text-align: center;
        }

        .visual-emblem {
            border: 4px solid rgba(255,255,255,0.2);
            padding: 40px;
            border-radius: 50% 50% 50% 50% / 15% 15% 85% 85% ; /* 방패 느낌의 곡선 지오메트리 */
            position: relative;
        }

        .visual-emblem h4 {
            font-size: 1.8rem;
            letter-spacing: 0.05em;
            margin-bottom: 5px;
        }

        .visual-emblem p {
            font-size: 0.8rem;
            opacity: 0.7;
            letter-spacing: 0.2em;
        }

        .identity-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 24px;
        }

        .identity-item {
            background: var(--white);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid rgba(0,0,0,0.03);
        }

        .identity-item h4 {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--primary-teal);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .identity-item p {
            font-size: 0.9rem;
            color: var(--gray-text);
            line-height: 1.6;
        }

        /* 5. Footer (하단 기업 정보 영역) */
        footer {
            background-color: #111827;
            color: #9ca3af;
            padding: 80px 10% 40px 10%;
            font-size: 0.9rem;
        }

        .footer-top {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #374151;
            padding-bottom: 40px;
            margin-bottom: 40px;
        }

        .footer-info h3 {
            color: var(--white);
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #9ca3af;
            text-decoration: none;
            margin-left: 20px;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .footer-bottom {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* 반응형 웹 디자인 대응 */
        @media (max-width: 1024px) {
            .values-grid, .identity-container, .identity-grid {
                grid-template-columns: 1fr;
            }
            header { padding: 20px 5%; }
            section { padding: 100px 5%; }
            .hero-title { font-size: 2.2rem; }
        }
    </style>
</head>
<body>

    <!-- 1. HEADER -->
    <header>
        <div class="logo">배움터지기 <span>KNOWLEDGE GUARDIAN</span></div>
        <nav>
            <a href="#values">CORE VALUE</a>
            <a href="#identity">BRAND IDENTITY</a>
        </nav>
    </header>

    <!-- 2. HERO SECTION -->
    <section class="hero" id="home">
        <div class="hero-sub">Knowledge Guardian</div>
        <h1 class="hero-title">
            전통 위에 세운 <span>순수</span>와 <span>지혜</span>
        </h1>
        <p class="hero-desc">
            안정되고 열린 배움터에서 창의의 날개를 달아,<br>
            지속 가능한 최고 가치를 향해 힘차게 도약합니다.
        </p>
    </section>

    <!-- 3. PROTECTED VALUE SYSTEM -->
    <section id="values">
        <div class="section-header">
            <h2>PROTECTED VALUE SYSTEM</h2>
            <p>배움터지기가 수호하고 지향하는 세 가지 핵심 가치입니다.</p>
        </div>
        <div class="values-grid">
            <div class="value-card">
                <span class="value-num">01 / PROTECTION</span>
                <h3>수호 (守護)</h3>
                <p>전통적인 가치와 학문을 온전히 지키며, 인격과 교육적 윤리를 최우선으로 보호하는 견고한 기반이 됩니다.</p>
            </div>
            <div class="value-card">
                <span class="value-num">02 / BALANCE</span>
                <h3>균형 (均衡)</h3>
                <p>지식(Knowledge), 기술(Skill), 태도(Attitude)를 균형 있게 가꾸어 치우침 없는 완전한 성장을 도모합니다.</p>
            </div>
            <div class="value-card">
                <span class="value-num">03 / SOARING</span>
                <h3>비상 (飛翔)</h3>
                <p>안정된 인프라 위에서 창의성의 날개를 펼쳐, 미래 지향적인 최고의 가치를 향해 끊임없이 나아갑니다.</p>
            </div>
        </div>
    </section>

    <!-- 4. IDENTITY SYSTEM -->
    <section class="identity-section" id="identity">
        <div class="section-header">
            <h2>IDENTITY SYSTEM</h2>
            <p>배움터지기의 철학과 상징을 정교하게 담아낸 브랜드 시스템입니다.</p>
        </div>
        <div class="identity-container">
            <!-- 상징 그래픽 비주얼 존 -->
            <div class="identity-visual">
                <div class="visual-emblem">
                    <h4>배움터지기</h4>
                    <p>SHIELD SYSTEM</p>
                </div>
            </div>
            <!-- 상징별 텍스트 그리드 -->
            <div class="identity-grid">
                <div class="identity-item">
                    <h4>청록색 바탕</h4>
                    <p>정서적 안정과 치유를 상징하며, 창의적인 탐구 지향성과 투명하고 청렴한 교육 공간의 가치를 반영합니다.</p>
                </div>
                <div class="identity-item">
                    <h4>월계관</h4>
                    <p>학문과 덕행, 그리고 인격적 탁월함을 추구하며 완전성과 지속적인 성장을 뜻합니다.</p>
                </div>
                <div class="identity-item">
                    <h4>별 3개 (參)</h4>
                    <p>지식·기술·태도의 균형 잡힌 성취를 의미하며, 개개인의 역량이 최고조에 이르는 단계를 보여줍니다.</p>
                </div>
                <div class="identity-item">
                    <h4>책과 리본</h4>
                    <p>전통 위에서 펼쳐지는 열린 탐구의 여정을 뜻하며, 가치와 신념을 담아내는 견고한 기반을 시각화합니다.</p>
                </div>
                <div class="identity-item" style="grid-column: span 2;">
                    <h4>은색 방패 (Silver Shield)</h4>
                    <p>순수와 성실, 평화와 화합을 기반으로 삼아 지혜롭고 통찰력 있게 학문을 추구합니다. 동시에 안전하면서도 혁신적인 학습 공동체의 보호망을 의미합니다.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 5. FOOTER -->
    <footer>
        <div class="footer-top">
            <div class="footer-info">
                <h3>배움터지기</h3>
                <p>학문을 수호하고, 균형을 지키며, 더 높은 가치를 향해 비상합니다.</p>
            </div>
            <div class="footer-links">
                <a href="#home">Top</a>
                <a href="#values">Values</a>
                <a href="#identity">Identity</a>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 BAEM-TEO JIGI. All Rights Reserved.</p>
            <p style="font-size: 0.8rem; color: #4b5563;">KNOWLEDGE GUARDIAN SYSTEM</p>
        </div>
    </footer>

</body>
</html>
