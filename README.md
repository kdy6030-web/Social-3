<!doctype html>
<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>사회계열 관점의 생태·환경 페이지</title>
  <style>
    /* 기본 리셋 */
    * { box-sizing: border-box; margin: 0; padding: 0; }
    html, body { height: 100%; width: 100%; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Noto Sans KR", "Apple SD Gothic Neo", "Malgun Gothic", sans-serif; background: #f5f5f5; color: #111; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; }
    body { overflow: hidden; }

    /* 슬라이더 래퍼 (뷰포트 전용) */
    .slider-viewport {
      position: relative;
      width: 100vw;
      height: 100vh;
      overflow: hidden;
    }

    /* 슬라이드 트랙: translateX으로 이동 */
    .slides {
      display: flex;
      height: 100%;
      width: 600%; /* 6 슬라이드 가정 (각 100%) */
      transition: transform 480ms cubic-bezier(.22,.9,.31,1);
      will-change: transform;
      touch-action: pan-y; /* 세로 스크롤 허용, 가로는 JS 처리 */
    }

    .slide {
      flex: 0 0 100vw;
      height: 100vh;
      padding: 48px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 18px;
      align-items: flex-start;
      position: relative;
    }

    /* 무채색 테마 (각 슬라이드 톤 다르게) */
    .s-1 { background: linear-gradient(180deg,#111,#181818); color: #f3f3f3; }
    .s-2 { background: #f7f7f7; color: #111; }
    .s-3 { background: linear-gradient(180deg,#e8e8e8,#d9d9d9); color:#111; }
    .s-4 { background: #ffffff; color:#111; }
    .s-5 { background: linear-gradient(180deg,#efefef,#e2e2e2); color:#111; }
    .s-6 { background: #f3f3f3; color:#111; }

    /* 타이틀 */
    .hero-title {
      font-size: clamp(26px, 6vw, 56px);
      line-height: 1.02;
      font-weight: 800;
      letter-spacing: -0.02em;
      margin-bottom: 8px;
    }
    .hero-sub {
      font-size: clamp(12px, 1.6vw, 18px);
      opacity: 0.85;
    }

    /* 카드 */
    .card {
      background: rgba(0,0,0,0.05);
      padding: 18px;
      border-radius: 10px;
      max-width: 900px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.06);
    }
    /* 어두운 배경 전용 카드 보정 */
    .s-1 .card { background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.04); }

    h2 { font-size: 20px; margin-bottom: 8px; }
    p, li { font-size: 15px; line-height: 1.6; color: inherit; }
    ul { margin-left: 18px; margin-top: 8px; }

    /* 네비게이션 (도트) */
    .nav-dots {
      position: fixed;
      right: 18px;
      top: 50%;
      transform: translateY(-50%);
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 60;
    }
    .dot {
      width: 10px; height: 10px; border-radius: 50%;
      background: rgba(0,0,0,0.18);
      cursor: pointer;
      transition: transform .18s ease, background .18s ease;
      border: 1px solid rgba(0,0,0,0.06);
    }
    .dot.active { transform: scale(1.5); background: rgba(0,0,0,0.75); }

    /* 좌우 화살표 */
    .arrow {
      position: fixed;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0,0,0,0.06);
      border-radius: 50%;
      width: 44px; height: 44px;
      display: grid; place-items: center;
      cursor: pointer;
      z-index: 70;
      border: 1px solid rgba(0,0,0,0.06);
    }
    .arrow.left { left: 16px; }
    .arrow.right { right: 16px; }
    .arrow svg { width: 20px; height: 20px; color: #111; }

    .arrow:active { transform: translateY(-50%) scale(.98); }

    @media (max-width:720px) {
      .slide { padding: 28px; align-items: center; text-align: center; }
      .nav-dots { right: 8px; }
      .arrow { display: none; } /* 모바일은 스와이프 사용 */
    }

    /* 작은 화면에서 폰트 크기 보정 */
    @media (max-width:400px) {
      .hero-title { font-size: 24px; }
    }
  </style>
</head>
<body>
  <div class="slider-viewport" id="viewport">
    <div class="slides" id="slides" aria-live="polite">
      <!-- 1: 타이틀(요구사항: 첫번째장에 해당 문구) -->
      <section class="slide s-1" aria-label="첫번째 페이지: 사회계열의 관점 제목">
        <div>
          <h1 class="hero-title">사회계열의 관점에서의<br><span style="color:#cfcfcf">생태 환경 문제들</span></h1>
          <p class="hero-sub">사회구조·가치·정책·참여 관점에서 환경 문제의 원인과 의미를 되짚습니다.</p>
        </div>

        <div style="height:20px;"></div>

        <div class="card" role="article" aria-label="핵심 요약">
          <h2>핵심 요약</h2>
          <p>사회계열적 관점은 환경 문제를 단순한 자연 파괴가 아니라 <strong>사회 구조·제도·가치의 결과</strong>로 봅니다. 불평등·과잉소비·정책 불균형·가치결핍·세대 불공정성이 주요 원인입니다.</p>
        </div>
      </section>

      <!-- 2: 문제 목록 -->
      <section class="slide s-2" aria-label="문제 목록">
        <div class="card">
          <h2>사회계열 관점에서 본 주요 문제들</h2>
          <ul>
            <li><strong>환경 불평등</strong> — 오염 시설과 피해가 사회적 약자에게 집중.</li>
            <li><strong>과잉소비와 생산 구조</strong> — 이윤 우선의 소비문화가 자원 고갈 초래.</li>
            <li><strong>정책·제도 불균형</strong> — 개발 우선 정책이 지속가능성 저해.</li>
            <li><strong>가치관 결핍</strong> — 환경을 우선하지 않는 사회 문화.</li>
            <li><strong>세대 간 불공정</strong> — 현재 선택이 미래 세대에 부담으로 전가.</li>
          </ul>
        </div>

        <div style="margin-top:18px;" class="card">
          <h2>사회적 해석</h2>
          <p>환경 문제는 개인 책임만으로는 해결되지 않습니다. 제도·문화·권력 구조를 함께 바꿔야 지속 가능한 변화가 가능합니다.</p>
        </div>
      </section>

      <!-- 3: 해결 아이디어 1-3 -->
      <section class="slide s-3" aria-label="해결 아이디어 1">
        <div class="card">
          <h2>1. 환경 정의 정책 강화</h2>
          <p>오염 취약 지역 우선 지원과 시민 환경감시제 도입으로 환경 불평등을 해소합니다.</p>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>2. 지속 가능한 소비문화 확산</h2>
          <p>제로웨이스트 캠페인, 공공기관의 공정무역 우선 구매 등 제도와 캠페인을 결합합니다.</p>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>3. 참여형 지역 공동체 생태 관리</h2>
          <p>주민 주도의 생태 프로그램과 지역 인센티브로 공동체 기반의 생태관리를 활성화합니다.</p>
        </div>
      </section>

      <!-- 4: 해결 아이디어 4-6 -->
      <section class="slide s-4" aria-label="해결 아이디어 2">
        <div class="card">
          <h2>4. 기업의 사회적 책임과 공공 파트너십</h2>
          <p>기업-지역 협력 프로젝트를 통해 기업을 환경 개선 파트너로 전환합니다.</p>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>5. 생태 시민교육 제도화</h2>
          <p>학교 교육과정에 환경 윤리와 체험형 학습을 포함해 시민 역량을 키웁니다.</p>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>6. 미래세대 기금 조성</h2>
          <p>개발 수익 일부를 환경기금으로 적립해 기후대응 및 생태복원에 사용합니다.</p>
        </div>
      </section>

      <!-- 5: 실행 로드맵 -->
      <section class="slide s-5" aria-label="실행 로드맵">
        <div class="card">
          <h2>실행 로드맵(예시)</h2>
          <ol style="margin-left:18px;">
            <li>단기(1년): 지역 시범사업(시민감시단, 제로웨이스트 캠페인) 운영</li>
            <li>중기(2-4년): 교육과정 개편, 기업 파트너십 확대</li>
            <li>장기(5년+): 법제화 및 전국 확산</li>
          </ol>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>성공 핵심 포인트</h2>
          <ul>
            <li>주민 참여와 투명한 의사결정</li>
            <li>사회적 인센티브(포인트/지역화폐)</li>
            <li>세대·계층 간 형평성 고려</li>
          </ul>
        </div>
      </section>

      <!-- 6: 요약/다음 단계 -->
      <section class="slide s-6" aria-label="요약">
        <div class="card">
          <h2>요약</h2>
          <p>사회계열적 해법은 제도·문화·참여를 바꿔 지속 가능한 변화를 만드는 것입니다. 기술만으로는 부족하며 사회적 구조를 함께 개선해야 합니다.</p>
        </div>

        <div class="card" style="margin-top:12px;">
          <h2>원하시면 제가 더 만들어 드립니다</h2>
          <ul>
            <li>보고서용 1페이지 요약(PDF)</li>
            <li>5슬라이드 PPT 발표 자료</li>
            <li>지역 시범사업 기획안(템플릿)</li>
          </ul>
          <p style="margin-top:8px; font-size:13px; color:#666;">(좌우로 밀거나 ← →키, 도트/화살표로 이동하세요.)</p>
        </div>
      </section>
    </div>

    <!-- 화살표 -->
    <button class="arrow left" id="prev" aria-label="이전 슬라이드">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M15 19l-7-7 7-7" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/></svg>
    </button>
    <button class="arrow right" id="next" aria-label="다음 슬라이드">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor"><path d="M9 5l7 7-7 7" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/></svg>
    </button>

    <!-- 도트 네비 -->
    <div class="nav-dots" id="navDots" role="tablist" aria-label="슬라이드 네비게이션"></div>
  </div>

  <script>
    (function() {
      const slidesEl = document.getElementById('slides');
      const slides = Array.from(document.querySelectorAll('.slide'));
      const prevBtn = document.getElementById('prev');
      const nextBtn = document.getElementById('next');
      const navDots = document.getElementById('navDots');
      let currentIndex = 0;
      const total = slides.length;

      // 도트 생성
      for (let i = 0; i < total; i++) {
        const d = document.createElement('button');
        d.className = 'dot';
        d.setAttribute('aria-label', `페이지 ${i+1}로 이동`);
        d.setAttribute('data-index', i);
        d.addEventListener('click', (e) => {
          goTo(parseInt(e.currentTarget.dataset.index, 10));
        });
        navDots.appendChild(d);
      }
      const dots = Array.from(document.querySelectorAll('.dot'));

      function updateUI() {
        // 슬라이드 이동
        slidesEl.style.transform = `translateX(-${currentIndex * 100}vw)`;
        // 도트 활성화
        dots.forEach((dot, i) => dot.classList.toggle('active', i === currentIndex));
        // 화살표 비활성화 처리 (첫/마지막)
        prevBtn.disabled = currentIndex === 0;
        nextBtn.disabled = currentIndex === total - 1;
        prevBtn.style.opacity = prevBtn.disabled ? '0.45' : '1';
        nextBtn.style.opacity = nextBtn.disabled ? '0.45' : '1';
      }

      function goTo(idx) {
        if (idx < 0) idx = 0;
        if (idx >= total) idx = total - 1;
        currentIndex = idx;
        updateUI();
      }

      prevBtn.addEventListener('click', () => goTo(currentIndex - 1));
      nextBtn.addEventListener('click', () => goTo(currentIndex + 1));

      // 키보드 내비
      window.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowLeft') goTo(currentIndex - 1);
        else if (e.key === 'ArrowRight') goTo(currentIndex + 1);
      });

      // 터치/드래그 지원 (모바일 + 데스크탑 드래그)
      let startX = 0;
      let currentTranslate = 0;
      let isDragging = false;
      let dragStartTime = 0;

      const viewport = document.getElementById('viewport');

      function onDragStart(clientX) {
        isDragging = true;
        startX = clientX;
        currentTranslate = -currentIndex * window.innerWidth;
        dragStartTime = Date.now();
        slidesEl.style.transition = 'none';
      }
      function onDragMove(clientX) {
        if (!isDragging) return;
        const diff = clientX - startX;
        slidesEl.style.transform = `translateX(${currentTranslate + diff}px)`;
      }
      function onDragEnd(clientX) {
        if (!isDragging) return;
        isDragging = false;
        const diff = clientX - startX;
        const abs = Math.abs(diff);
        const dt = Date.now() - dragStartTime;
        slidesEl.style.transition = 'transform 480ms cubic-bezier(.22,.9,.31,1)';
        // 속도 기반 플릭 또는 거리 기반
        const flick = (abs > 15 && dt < 250);
        const threshold = window.innerWidth * 0.18;
        if ((diff < 0 && (abs > threshold || flick)) && currentIndex < total - 1) {
          goTo(currentIndex + 1);
        } else if ((diff > 0 && (abs > threshold || flick)) && currentIndex > 0) {
          goTo(currentIndex - 1);
        } else {
          goTo(currentIndex); // 롤백
        }
      }

      // 터치 이벤트
      viewport.addEventListener('touchstart', (e) => onDragStart(e.touches[0].clientX), {passive:true});
      viewport.addEventListener('touchmove', (e) => onDragMove(e.touches[0].clientX), {passive:true});
      viewport.addEventListener('touchend', (e) => onDragEnd(e.changedTouches[0].clientX));

      // 마우스 드래그 (데스크탑)
      viewport.addEventListener('mousedown', (e) => { e.preventDefault(); onDragStart(e.clientX); });
      window.addEventListener('mousemove', (e) => onDragMove(e.clientX));
      window.addEventListener('mouseup', (e) => onDragEnd(e.clientX));

      // 화면 리사이즈시 다시 위치 맞춤
      window.addEventListener('resize', () => {
        slidesEl.style.transition = 'none';
        slidesEl.style.transform = `translateX(-${currentIndex * 100}vw)`;
        // 작은 지연 후 트랜지션 복원
        setTimeout(() => slidesEl.style.transition = 'transform 480ms cubic-bezier(.22,.9,.31,1)', 50);
      });

      // 초기 UI 설정
      goTo(0);
    })();
  </script>
</body>
</html>
