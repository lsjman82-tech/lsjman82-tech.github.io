<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>이세준 영업 전문가 성과 중심 포트폴리오</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Noto+Sans+KR:wght@100..900&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* 1. 기본 글꼴 및 밝은 모드 배경 설정 */
        body {
            font-family: 'Inter', "Noto Sans KR", sans-serif;
            background-color: #f9fafb; /* Very Light Gray - 배경 */
            color: #1f2937; /* Dark Gray 900 - 기본 텍스트 */
            line-height: 1.6;
        }
        
        /* 2. 메인 강조 컬러 (차분한 남색 계열) */
        .text-accent { color: #1e3a8a; } /* Deep Blue / Navy */
        .bg-accent-light { background-color: #eef2ff; } /* Very Light Indigo Background */
        .border-accent { border-color: #1e3a8a; }
        
        /* 3. 카드 스타일: 깔끔하고 정돈된 디자인 + 호버 효과 추가 */
        .card {
            background-color: #ffffff;
            padding: 1.5rem;
            border-radius: 0.75rem; /* 더 둥글게 */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08); /* 조금 더 입체적인 그림자 */
            border: 1px solid #e5e7eb;
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .card:hover {
            transform: translateY(-3px); /* 호버 시 약간 더 띄움 */
            box-shadow: 0 15px 25px -5px rgba(0, 0, 0, 0.1), 0 5px 10px -5px rgba(0, 0, 0, 0.1);
        }

        /* 4. 증명사진 삽입 칸 스타일 (수정됨) */
        .id-photo-placeholder {
            width: 110px; /* 약간 더 키움 */
            height: 140px; /* 약간 더 키움 */
            /* background-color: #f3f4f6; 배경색 제거 (사진이 덮음) */
            border: 2px solid #e5e7eb; /* 점선 대신 깔끔한 실선 테두리로 변경 */
            border-radius: 0.75rem;
            overflow: hidden; /* 이미지가 둥근 모서리를 넘지 않도록 자름 */
            /* 텍스트 정렬 속성 제거 (display: flex 등) */
        }

        /* 5. 메트릭 카드: 핵심 성과 강조 */
        .metric-card {
            min-height: 130px; /* 높이 약간 조정 */
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .metric-value {
            font-size: 2.5rem; /* 더 크게 */
            font-weight: 900; /* Extra Black */
            line-height: 1.1;
            color: #172554;
            letter-spacing: -0.05em; /* 폰트 트래킹 조정 */
        }
        .metric-label {
            color: #374151; /* Darker Gray 700 */
        }
        .metric-icon-square {
            background-color: #c7d2fe;
            color: #3730a3;
            width: 40px; /* 아이콘 크기 키움 */
            height: 40px;
            border-radius: 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            font-weight: bold;
        }

        /* 6. 경력 타임라인 스타일 */
        .timeline-line {
            border-left: 2px solid #d1d5db;
        }
        .timeline-dot {
            background-color: #1e3a8a;
            border: 4px solid #ffffff; /* 테두리 두께 키움 */
            box-shadow: 0 0 0 1px #1e3a8a; /* 외곽선 추가 */
        }
        .job-title {
            color: #111827; /* Near Black */
            font-weight: 700;
        }

        /* 7. 경력 내용 한 줄 스타일 (수정됨: 폰트 축소 및 줄바꿈 방지 노력) */
        .achievement-line {
            margin-bottom: 0.35rem; /* 간격 축소 */
            line-height: 1.3;
            display: block;
            /* text-overflow: ellipsis; 필요시 주석 해제 */
            /* white-space: nowrap; 필요시 주석 해제 (강제로 한줄 만들기, 잘릴 수 있음) */
        }
        .achievement-line strong {
            font-weight: 800; /* 더 굵게 */
            color: #0c4a6e; /* Darker accent for core metric */
        }
        .achievement-icon {
            color: #1e3a8a;
            font-size: 0.8rem; /* 아이콘 크기 축소 */
            line-height: 1;
            vertical-align: middle;
        }
        /* Mobile: 경력 정보 세로 간격 조정 */
        @media (max-width: 640px) {
            .job-info-mobile {
                flex-direction: column;
                align-items: flex-start;
            }
            .job-info-mobile .text-sm {
                margin-top: 0.25rem;
            }
        }

        /* 8. 핵심 역량 배지 스타일 (수정됨: 마진 문제 해결) */
        .skill-badge {
            background-color: #e0e7ff; /* Slightly Darker Indigo Background */
            color: #3730a3;
            font-weight: 600;
            padding: 0.5rem 0.9rem; /* 패딩 약간 축소 */
            border-radius: 9999px; /* Pill shape */
            border: 1px solid #a5b4fc; /* Stronger Indigo Border */
            font-size: 0.8rem; /* 폰트 사이즈 조정 */
            transition: background-color 0.2s, transform 0.1s;
            white-space: nowrap; /* 배지 내부 줄바꿈 방지 */
        }
        .skill-badge:hover {
            background-color: #c7d2fe;
            color: #1e3a8a;
            transform: scale(1.05);
        }

        /* 9. 기타 정보 정렬 스타일 */
        .etc-item-label {
            width: 90px;
            min-width: 90px;
            font-weight: 700;
            color: #1e3a8a;
        }
    </style>
</head>
<body class="p-4 sm:p-10">

    <div class="max-w-7xl mx-auto space-y-12">

        <header class="card p-6 sm:p-10 bg-accent-light border-accent border-l-8"> <div class="flex flex-col sm:flex-row justify-between items-center sm:items-start">
                
                <div class="sm:order-1 sm:w-3/5 md:w-2/3 mb-4 sm:mb-0">
                    <h1 class="text-5xl sm:text-7xl font-extrabold tracking-tight mb-3 text-accent">이세준</h1>
                    <p class="text-xl sm:text-2xl font-light text-gray-700 mb-6 border-l-4 pl-3 border-gray-400/50">B2B 고객 발굴부터 매출 성장까지 실전형 세일즈 리더</p>

                    <address class="mt-4 text-base flex flex-wrap gap-x-8 gap-y-3 text-gray-600 not-italic">
                    <!-- 수정: id="total-career" 추가 -->
                    <p class="flex items-center"><span class="text-accent mr-2 font-extrabold">💼</span> <span id="total-career">총 경력: 계산 중...</span></p>
                    <p class="flex items-center"><span class="text-accent mr-2 font-extrabold">📧</span> 이메일: <a href="mailto:freeman82@naver.com" class="hover:underline hover:text-accent font-medium">freeman82@naver.com</a></p>
                    <p class="flex items-center"><span class="text-accent mr-2 font-extrabold">📞</span> 휴대폰: 010-8780-1847</p>
                    <p class="flex items-center"><span class="text-accent mr-2 font-extrabold">🎂</span> <span id="korean-age">나이(만): 43세</span></p>
                </address>
            </div>

            <!-- 수정된 부분: 구글 드라이브 링크 대신 기본 아이콘으로 대체 -->
            <div class="id-photo-placeholder shrink-0 mt-6 sm:mt-0 sm:order-2 flex items-center justify-center bg-gray-100 text-gray-300">
                <!-- 나중에 실제 사진을 넣으실 때는 아래 svg 태그를 지우고 -->
                <!-- <img src="./내사진파일명.jpg" class="w-full h-full object-cover" alt="프로필 사진"> -->
                <!-- 이렇게 이미지 태그를 넣어주시면 됩니다. -->
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-20 h-20">
                    <path fill-rule="evenodd" d="M7.5 6a4.5 4.5 0 1 1 9 0 4.5 4.5 0 0 1-9 0ZM3.751 20.105a8.25 8.25 0 0 1 16.498 0 .75.75 0 0 1-.437.695A18.683 18.683 0 0 1 12 22.5c-2.786 0-5.433-.608-7.812-1.7a.75.75 0 0 1-.437-.695Z" clip-rule="evenodd" />
                </svg>
            </div>
        </div>
    </header>

    <section id="metrics" class="space-y-6">
            <h2 class="text-2xl font-bold border-l-4 pl-3 border-accent text-gray-800">핵심 성과 대시보드 (Quantitative Performance)</h2>
            <div class="grid grid-cols-2 lg:grid-cols-4 gap-6">
                
                <div class="card metric-card">
                    <div class="flex items-center space-x-3 mb-2">
                        <div class="metric-icon-square">
                            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-trending-up"><polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/></svg>
                        </div>
                        <p class="text-sm font-medium metric-label uppercase">팀 매출 성장</p>
                    </div>
                    <p class="metric-value text-accent">3.25<span class="text-2xl font-bold">배</span></p>
                    <p class="text-xs text-gray-500 font-light mt-1">비에스온 모빌리티팀 (2억 → 6.5억 원)</p>
                </div>

                <div class="card metric-card">
                    <div class="flex items-center space-x-3 mb-2">
                        <div class="metric-icon-square">
                            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-bar-chart-3"><path d="M3 3v18h18"/><path d="M18 17V9"/><path d="M13 17V7"/><path d="M8 17v-3"/></svg>
                        </div>
                        <p class="text-sm font-medium metric-label uppercase">최고 월 매출</p>
                    </div>
                    <p class="metric-value text-accent">11.8<span class="text-2xl font-bold">억</span></p>
                    <p class="text-xs text-gray-500 font-light mt-1">비에스온 모빌리티팀 최고 실적</p>
                </div>

                <div class="card metric-card">
                    <div class="flex items-center space-x-3 mb-2">
                        <div class="metric-icon-square">
                            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-won-sign"><path d="M12 11V2"/><path d="M12 22V13"/><path d="M20 9H4"/><path d="M20 15H4"/><path d="M8 13h8"/></svg>
                        </div>
                        <p class="text-sm font-medium metric-label uppercase">대형 계약 수익</p>
                    </div>
                    <p class="metric-value text-accent">6<span class="text-2xl font-bold">억</span></p>
                    <p class="text-xs text-gray-500 font-light mt-1">마스타동차관리 미쓰비시 A/S 위탁 (연간)</p>
                </div>

                <div class="card metric-card">
                    <div class="flex items-center space-x-3 mb-2">
                        <div class="metric-icon-square">
                            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-users"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                        </div>
                        <p class="text-sm font-medium metric-label uppercase">신규 제휴처</p>
                    </div>
                    <p class="metric-value text-accent">420<span class="text-2xl font-bold">개</span></p>
                    <p class="text-xs text-gray-500 font-light mt-1">아토스터디 스터디카페 지점 체결</p>
                </div>
            </div>
        </section>

        <main class="grid grid-cols-1 lg:grid-cols-12 gap-8">

            <!-- 경력사항: 글자 크기 축소 및 1줄 정렬 적용 -->
            <div class="lg:col-span-8 space-y-8">

                <section id="experience" class="card h-full">
                    <h2 class="text-2xl font-bold mb-8 border-l-4 pl-3 border-accent text-accent">상세 경력 및 성과 (총 9년 8개월)</h2>

                    <div class="relative pl-6 timeline-line pb-8">
                        <div class="absolute w-4 h-4 timeline-dot rounded-full -left-[8px] top-0"></div> <div class="flex justify-between items-start mb-1 flex-wrap job-info-mobile">
                            <h3 class="text-xl font-bold job-title">비에스온 (종합 렌탈 플랫폼)</h3>
                            <!-- 수정: id="current-job-period" 추가 -->
                            <span id="current-job-period" class="text-sm text-gray-500 font-medium mt-1 sm:mt-0">2024. 09 ~ 재직 중</span>
                        </div>
                        <p class="text-base text-gray-600 font-semibold mb-1">영업 1본부 / 모빌리티팀 팀장</p>
                        <p class="text-xs text-gray-500 mb-4">기업개요: 종합 렌탈 플랫폼 | 매출 1,133.9억 원 (2024) | 사원수 122명</p>
                        
                        <!-- 텍스트 크기 xs, 자간 축소, 줄간격 조정 -->
                        <div class="text-gray-700 text-xs tracking-tight space-y-2"> 
                            <p class="achievement-line"><span class="achievement-icon mr-1">📈</span> [매출 성장] 레저용 바이크 장기렌탈 도입 및 파트너사 3곳 유치로 <strong class="text-accent">팀 매출 3.25배 (2억 → 6.5억 원) 성장 달성</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">🏆</span> [KPI/재고 관리] 시장 및 경쟁사 분석 기반 KPI 재정비 및 재고 확대로 <strong class="text-accent">최고 월 매출 11.8억 원 달성</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">📞</span> [B2B 영업] 일평균 15건 콜드콜 기반, 요식업 장비 파트너사 2곳 입점 계약 및 신규 매출 <strong class="text-accent">1.5억 원 창출</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">💡</span> [신규 상품] 중고차 렌탈 상품 기획 및 런칭 <strong class="text-accent">, 신규 매출 1억 원 창출</strong></p> 
                        </div>
                    </div>

                    <div class="relative pl-6 timeline-line pb-8">
                        <div class="absolute w-4 h-4 timeline-dot rounded-full -left-[8px] top-0"></div>
                        <div class="flex justify-between items-start mb-1 flex-wrap job-info-mobile">
                            <h3 class="text-xl font-bold job-title">커넥트앤 (광고 대행업)</h3>
                            <span class="text-sm text-gray-500 font-medium mt-1 sm:mt-0">2024. 04 ~ 2024. 09 (4개월)</span>
                        </div>
                        <p class="text-base text-gray-600 font-semibold mb-1">영업팀 매니저</p>
                        <p class="text-xs text-gray-500 mb-4">기업개요: 광고 대행업 | 매출 10억 원 | 사원수 6명</p>
                        
                        <div class="text-gray-700 text-xs tracking-tight space-y-2">
                            <p class="achievement-line"><span class="achievement-icon mr-1">💰</span> [신규 매출] 보험 GA 및 설계사 대상 마케팅 솔루션 DB 판매 영업으로 <strong class="text-accent">5,500만 원의 신규 매출 달성</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">📋</span> [영업 활동] CRM 기반 고객 리스트 관리 및 일평균 <strong class="text-accent">60건의 상담을 통한 맞춤형 솔루션 제안</strong></p>
                        </div>
                    </div>
                    
                    <div class="relative pl-6 timeline-line pb-8">
                        <div class="absolute w-4 h-4 timeline-dot rounded-full -left-[8px] top-0"></div>
                        <div class="flex justify-between items-start mb-1 flex-wrap job-info-mobile">
                            <h3 class="text-xl font-bold job-title">아토스터디 (교육 서비스업)</h3>
                            <span class="text-sm text-gray-500 font-medium mt-1 sm:mt-0">2022. 11 ~ 2024. 04 (1년 6개월)</span>
                        </div>
                        <p class="text-base text-gray-600 font-semibold mb-1">솔루션 영업팀 팀장</p>
                        <p class="text-xs text-gray-500 mb-4">기업개요: 교육 서비스업 (에듀 테크) | 매출 107.3억 원 | 사원수 72명</p>
                        
                        <div class="text-gray-700 text-xs tracking-tight space-y-2">
                            <p class="achievement-line"><span class="achievement-icon mr-1">🔗</span> [신규 사업] 모바일 교육 앱 제휴 영업 주도, 스터디카페 프랜차이즈 본사 5곳 및 <strong class="text-accent">420개 지점 제휴 체결</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">📣</span> [광고 런칭] 디지털 옥외 광고 신규 사업 런칭 후 초기 광고주 3개사 유치, 총 <strong class="text-accent">2,600만 원 매출 창출</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">🧑‍🏫</span> [팀 코칭] 팀원 대상 콜드콜·콜드메일 교육 체계화로 아웃바운딩 영업력 강화 <strong class="text-accent">기여</strong></p>
                        </div>
                    </div>
                    
                    <div class="relative pl-6 timeline-line pb-8">
                        <div class="absolute w-4 h-4 timeline-dot rounded-full -left-[8px] top-0"></div>
                        <div class="flex justify-between items-start mb-1 flex-wrap job-info-mobile">
                            <h3 class="text-xl font-bold job-title">마스타자동차관리 (자동차 서비스업)</h3>
                            <span class="text-sm text-gray-500 font-medium mt-1 sm:mt-0">2013. 01 ~ 2017. 07 (4년 7개월)</span>
                        </div>
                        <p class="text-base text-gray-600 font-semibold mb-1">네트워크 사업부 대리</p>
                        <p class="text-xs text-gray-500 mb-4">기업개요: 자동차 서비스업 (체인화 사업) | 매출 904억 원 | 사원수 165명</p>
                        
                        <div class="text-gray-700 text-xs tracking-tight space-y-2">
                            <p class="achievement-line"><span class="achievement-icon mr-1">🤝</span> [대형 계약] 수입차 A/S 위탁운영 사업으로 <strong class="text-accent">미쓰비시자동차와 3년 계약 체결, 연간 6억 원 수익 확보</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">⬆️</span> [실적 성장] 전국 80개 가맹점 컨설팅을 통해 본사 PB 부품·용품 구매 실적 <strong class="text-accent">2.5배 성장</strong></p>
                        </div>
                    </div>

                    <div class="relative pl-6">
                        <div class="absolute w-4 h-4 timeline-dot rounded-full -left-[8px] top-0"></div>
                        <div class="flex justify-between items-start mb-1 flex-wrap job-info-mobile">
                            <h3 class="text-xl font-bold job-title">GS리테일 (유통업)</h3>
                            <span class="text-sm text-gray-500 font-medium mt-1 sm:mt-0">2010. 07 ~ 2012. 06 (2년)</span>
                        </div>
                        <p class="text-base text-gray-600 font-semibold mb-1">CVS사업부 사원</p>
                        <p class="text-xs text-gray-500 mb-4">기업개요: 유통업 (체인화 사업) | 매출 10조 5,000억 원</p>
                        
                        <div class="text-gray-700 text-xs tracking-tight space-y-2">
                            <p class="achievement-line"><span class="achievement-icon mr-1">🏪</span> [가맹점 관리] 12개 가맹점 운영 컨설팅 및 매출·재고 분석으로 수익성 <strong class="text-accent">개선</strong></p>
                            <p class="achievement-line"><span class="achievement-icon mr-1">📝</span> [계약 성사] 가맹 재계약 3건, 양수도 2건 <strong class="text-accent">성사</strong></p>
                        </div>
                    </div>
                </section>
            </div>

            <div class="lg:col-span-4 flex flex-col h-full space-y-8">

                <!-- 핵심 역량: Flex Wrap 적용으로 겹침 현상 해결 -->
                <section id="skills" class="card">
                    <h2 class="text-2xl font-bold mb-5 border-l-2 pl-3 border-accent text-accent">핵심 역량</h2>
                    
                    <div class="flex flex-wrap gap-2">
                        <span class="skill-badge">B2B/B2C 전방위 영업</span>
                        <span class="skill-badge">영업 전략 기획/실행</span>
                        <span class="skill-badge">조직 리딩 및 코칭</span>
                        <span class="skill-badge">KPI 기반 성과 관리</span>
                        <span class="skill-badge">콜드콜/아웃바운딩</span>
                        <span class="skill-badge">대내외 커뮤니케이션</span>
                        <span class="skill-badge">신규 사업 런칭/제휴</span>
                        <span class="skill-badge">모빌리티/렌탈 시장 이해</span>
                    </div>
                </section>

                <section id="education" class="card">
                    <h2 class="text-2xl font-bold mb-5 border-l-2 pl-3 border-accent text-accent">학력 사항</h2>
                    
                    <div class="mb-4 pb-4 border-b border-gray-200 last:border-b-0">
                        <p class="text-lg font-semibold text-gray-800">가천대학교(구 경원대학교)</p>
                        <p class="text-gray-600 font-medium">일어일문학과 학사</p>
                        <p class="text-sm text-gray-500 mt-1">2005. 03 - 2009. 08</p>
                    </div>

                    <div>
                        <p class="text-lg font-semibold text-gray-800">서울중산고등학교</p>
                        <p class="text-gray-600 font-medium">졸업</p>
                        <p class="text-sm text-gray-500 mt-1">1998. 03 - 2001. 02</p>
                    </div>
                </section>
                
                <div class="flex-grow"></div> 
                
                <section id="etc" class="card">
                    <h2 class="text-2xl font-bold mb-5 border-l-2 pl-3 border-accent text-accent">기타 정보</h2>
                    
                    <div class="space-y-4 text-base"> <div class="flex items-start p-3 bg-indigo-50/50 rounded-lg border border-indigo-200/50">
                            <span class="etc-item-label shrink-0 mr-4">외국어</span>
                            <span class="text-gray-700 font-medium">일본어 회화 (상)</span>
                        </div>
                        <div class="flex items-start p-3 bg-indigo-50/50 rounded-lg border border-indigo-200/50">
                            <span class="etc-item-label shrink-0 mr-4">자격증</span>
                            <span class="text-gray-700 font-medium">회계 관리 2급 (삼일회계법인), 자동차 운전 면허</span>
                        </div>
                        <div class="flex items-start p-3 bg-indigo-50/50 rounded-lg border border-indigo-200/50">
                            <span class="etc-item-label shrink-0 mr-4">활용 툴</span>
                            <span class="text-gray-700 font-medium">Word, Excel, PPT (상), 구글 스프레드 시트, CRM (핑거세일즈)</span>
                        </div>
                        <div class="flex items-start p-3 bg-indigo-50/50 rounded-lg border border-indigo-200/50">
                            <span class="etc-item-label shrink-0 mr-4">병역</span>
                            <span class="text-gray-700 font-medium">해병대 만기 제대</span>
                        </div>
                    </div>
                </section>
                
            </div>
        </main>

        <footer class="text-center text-gray-400 text-sm pt-12 border-t border-gray-200 mt-12">
            <p>&copy; 2025 이세준. 비즈니스 성과 중심 포트폴리오 | 공식적인 남색 디자인</p>
        </footer>
    </div>

    <!-- JavaScript: 경력 자동 계산 로직 -->
    <script>
        function updateCareerExperience() {
            // 1. 현재 날짜 가져오기
            const now = new Date();
            
            // 2. 현재 직장 입사일 (비에스온: 2024년 9월 1일로 가정)
            const currentJobStart = new Date('2024-09-01');

            // 3. 현재 직장 근무 개월 수 계산
            // (연도 차이 * 12) + 월 차이
            // 입사 당월부터 1개월로 치기 위해 로직 조정 가능하나, 여기선 만으로 계산 후 +1 등을 고려
            // 일반적으로 만 개월수로 표기
            let currentMonthsDiff = (now.getFullYear() - currentJobStart.getFullYear()) * 12 + (now.getMonth() - currentJobStart.getMonth());
            
            // 만약 날짜가 안 지났으면 개월 수 조정 필요할 수 있으나, 보통 월 단위로 계산하므로 이대로 둠.
            // 입사한 달도 1개월로 쳐준다면 +1 (선택사항, 여기선 만 기간으로 계산)
            currentMonthsDiff = Math.max(0, currentMonthsDiff + 1); // 2024.09 입사, 2024.09 조회 시 1개월

            // 4. 과거 확정된 경력의 합 (비에스온 입사 전까지의 총 경력)
            // 기존 총 경력(9년 8개월) - 현재 직장(약 1년 3개월) = 과거 경력 약 8년 5개월로 고정
            // (2025년 11월 기준 1년 3개월이므로, 2024.09 입사시점까지의 과거 경력은 8년 5개월)
            const pastYears = 8;
            const pastMonths = 5;
            const pastTotalMonths = (pastYears * 12) + pastMonths;

            // 5. 총 경력 계산 (과거 + 현재)
            const totalMonths = pastTotalMonths + currentMonthsDiff;
            const totalYearsDisplay = Math.floor(totalMonths / 12);
            const totalMonthsDisplay = totalMonths % 12;

            // 6. 현재 직장 경력 표시용 (년/월)
            const currentJobYears = Math.floor(currentMonthsDiff / 12);
            const currentJobMonths = currentMonthsDiff % 12;
            let currentJobText = `(${currentMonthsDiff}개월)`;
            if (currentJobYears > 0) {
                currentJobText = `(${currentJobYears}년 ${currentJobMonths}개월)`;
            } else {
                 currentJobText = `(${currentJobMonths}개월)`;
            }

            // 7. 화면에 업데이트
            const totalExpElement = document.getElementById('total-career');
            if (totalExpElement) {
                totalExpElement.innerText = `총 경력: ${totalYearsDisplay}년 ${totalMonthsDisplay}개월`;
            }

            const currentJobElement = document.getElementById('current-job-period');
            if (currentJobElement) {
                // 기존 텍스트 "2024. 09 ~ 재직 중" 뒤에 계산된 기간 붙이기
                currentJobElement.innerText = `2024. 09 ~ 재직 중 ${currentJobText}`;
            }

            // (선택사항) 만 나이 자동 계산
            const birthYear = 1982; // 이메일 freeman82 등을 통해 추정, 만약 다르면 수정 필요
            const age = now.getFullYear() - birthYear;
            // 생일이 지났는지 여부는 복잡하므로 단순 연도 계산 혹은 '세'로 표시. '만 나이'이므로 생일 고려 필요.
            // 여기선 기존 43세를 유지하거나, 연도 바뀔 때 +1 되도록 단순 계산
            // 만 나이는 생일이 지나야 하므로 보수적으로 (현재연도 - 1982) - 1 (생일 전이라 가정) 또는 그냥 연나이
            // 기존 텍스트 유지하되, 필요시 아래 주석 해제하여 사용
            /*
            const ageElement = document.getElementById('korean-age');
            if (ageElement) {
                // 단순 계산: 2025년 기준 43세 -> 1982년생
                // 만 나이 계산 로직 (생일 무관하게 연도차-1 or 연도차)
                // 현재 코드에선 생략
            }
            */
        }

        // 페이지 로드 시 실행
        updateCareerExperience();
    </script>
</body>
</html>
