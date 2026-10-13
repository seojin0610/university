# university
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>대한민국 지역별 대학 알아보기</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Pretendard Font for Korean readability -->
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css" />

    <style>
        body {
            font-family: "Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif;
            font-weight: 400;
            background-color: #061a12;
            background-image: 
                radial-gradient(circle at 15% 20%, rgba(16, 185, 129, 0.15) 0%, transparent 45%),
                radial-gradient(circle at 85% 80%, rgba(5, 150, 105, 0.15) 0%, transparent 45%),
                radial-gradient(circle at 50% 50%, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
            background-size: 100% 100%, 100% 100%, 28px 28px;
            color: #f0fdf4;
            min-height: 100vh;
            line-height: 1.6;
        }

        /* Green Glassmorphism Containers */
        .glass-card {
            background: rgba(11, 38, 27, 0.85);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(52, 211, 153, 0.2);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }

        /* Region Button Styling */
        .region-btn {
            transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
            background: linear-gradient(135deg, rgba(16, 85, 58, 0.8), rgba(6, 45, 30, 0.9));
            border: 1.5px solid rgba(52, 211, 153, 0.3);
        }

        .region-btn:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 24px rgba(16, 185, 129, 0.35);
            border-color: #34d399;
            background: linear-gradient(135deg, rgba(20, 110, 75, 1), rgba(16, 85, 58, 0.9));
        }

        .region-btn:active {
            transform: translateY(-1px);
        }

        /* Speech Bubble */
        .speech-bubble {
            position: relative;
            background: rgba(15, 50, 36, 0.95);
            border: 2px solid #10b981;
            box-shadow: 0 0 20px rgba(16, 185, 129, 0.25);
        }

        .speech-bubble::before {
            content: '';
            position: absolute;
            left: -14px;
            top: 28px;
            border-width: 8px 14px 8px 0;
            border-style: solid;
            border-color: transparent #10b981 transparent transparent;
        }

        .speech-bubble::after {
            content: '';
            position: absolute;
            left: -10px;
            top: 30px;
            border-width: 6px 11px 6px 0;
            border-style: solid;
            border-color: transparent rgba(15, 50, 36, 0.95) transparent transparent;
        }

        @media (max-width: 640px) {
            .speech-bubble::before {
                left: 30px;
                top: -14px;
                border-width: 0 8px 14px 8px;
                border-color: transparent transparent #10b981 transparent;
            }
            .speech-bubble::after {
                left: 32px;
                top: -10px;
                border-width: 0 6px 11px 6px;
                border-color: transparent transparent rgba(15, 50, 36, 0.95) transparent;
            }
        }

        /* Animations */
        .pop-in {
            animation: popIn 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        @keyframes popIn {
            0% { opacity: 0; transform: scale(0.95) translateY(15px); }
            100% { opacity: 1; transform: scale(1) translateY(0); }
        }

        .float-anim {
            animation: float 3.5s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-6px); }
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between p-4 md:p-8">

    <header class="text-center my-3 md:my-6">
        <div class="inline-block relative">
            <span class="inline-block bg-gradient-to-r from-emerald-600 to-teal-600 text-white text-xs font-semibold px-4 py-1.5 rounded-full border border-emerald-400/30 uppercase tracking-wider mb-2.5 shadow-md">
                🎓 KOREA UNIVERSITY GUIDE
            </span>
            <h1 class="text-3xl md:text-5xl font-extrabold tracking-tight text-transparent bg-clip-text bg-gradient-to-r from-emerald-300 via-teal-200 to-green-400">
                대한민국 지역별 대학 알아보기
            </h1>
            <p class="text-emerald-100 text-base md:text-lg mt-2 font-medium">
                지역을 선택하고 대표 대학들의 특징과 장단점을 한눈에 확인해보세요!
            </p>
        </div>
    </header>

    <main class="max-w-5xl mx-auto w-full flex-grow flex flex-col justify-center my-2 md:my-4">

        <!-- ================= PAGE 1: REGION SELECTION PAGE ================= -->
        <div id="selection-page" class="space-y-6 pop-in">
            
            <!-- Guide Avatar & Dialogue -->
            <div class="flex flex-col sm:flex-row items-center justify-center gap-5 p-5 md:p-6 rounded-2xl glass-card">
                
                <!-- Character Avatar -->
                <div class="relative flex-shrink-0 float-anim">
                    <div class="w-28 h-28 md:w-32 md:h-32 rounded-full border-3 border-emerald-400 overflow-hidden shadow-[0_0_25px_rgba(16,185,129,0.35)] bg-emerald-950 flex items-center justify-center p-2">
                        <svg class="w-20 h-20 text-emerald-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 14l9-5-9-5-9 5 9 5z"></path>
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0112 20.055a11.952 11.952 0 01-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"></path>
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 14l9-5-9-5-9 5 9 5zm0 0v6"></path>
                        </svg>
                    </div>
                    <span class="absolute -bottom-2 left-1/2 transform -translate-x-1/2 bg-gradient-to-r from-emerald-600 to-teal-600 text-white text-xs font-semibold px-3 py-0.5 rounded-full border border-white/20 shadow-md whitespace-nowrap">
                        대학 진학 가이드
                    </span>
                </div>

                <!-- Speech Bubble -->
                <div class="speech-bubble rounded-2xl p-5 text-slate-100 flex-grow max-w-xl">
                    <p class="text-xl font-bold text-emerald-300 mb-1 flex items-center gap-2">
                        <span>"원하는 지역권을 선택해 주세요!"</span>
                        <i class="fa-solid fa-compass text-teal-300 text-lg"></i>
                    </p>
                    <p class="text-base text-emerald-100 leading-relaxed font-normal">
                        안녕하세요! 대한민국 주요 권역별 대표 대학 가이드입니다. <br class="hidden sm:inline"/>
                        아래 5개 지역 중 관심 있는 지역을 선택하시면 주요 대학 정보와 장·단점을 친절히 안내해 드릴게요!
                    </p>
                </div>
            </div>

            <!-- Region Selection Grid -->
            <div class="glass-card p-6 md:p-8 rounded-2xl">
                <div class="flex items-center justify-between mb-5">
                    <h2 class="text-xl md:text-2xl font-bold text-white flex items-center gap-2.5">
                        <span class="w-3 h-3 rounded-full bg-emerald-400 inline-block animate-ping"></span>
                        대한민국 지역권 선택
                    </h2>
                    <span class="text-sm text-emerald-300 font-medium">5대 권역</span>
                </div>
                
                <div id="region-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                    <!-- Buttons will be dynamically injected here -->
                </div>
            </div>
        </div>

        <!-- ================= PAGE 2: UNIVERSITY LIST RESULT PAGE ================= -->
        <div id="result-page" class="hidden">
            <div class="pop-in space-y-6">
                
                <!-- Region Title Header Card -->
                <div class="glass-card rounded-2xl p-6 md:p-7 border border-emerald-400/40 flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                    <div>
                        <div class="inline-flex items-center gap-2 bg-emerald-900/80 border border-emerald-400/30 text-emerald-300 text-xs font-semibold px-3 py-1 rounded-full mb-2">
                            <i class="fa-solid fa-map-location-dot"></i> 선택 권역
                        </div>
                        <h2 id="selected-region-title" class="text-3xl md:text-4xl font-extrabold text-white">
                            수도권 주요 대학
                        </h2>
                        <p id="selected-region-desc" class="text-emerald-200 text-sm md:text-base mt-1">
                            해당 지역을 대표하는 주요 5개 대학의 정보입니다.
                        </p>
                    </div>

                    <!-- Retry Button -->
                    <button onclick="resetSelection()" class="w-full md:w-auto bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-500 hover:to-teal-500 text-white font-bold text-base px-6 py-3 rounded-xl border border-emerald-300/40 shadow-lg transition-all transform active:scale-95 flex items-center justify-center gap-2 flex-shrink-0">
                        <i class="fa-solid fa-rotate-left"></i>
                        <span>지역 다시 고르기</span>
                    </button>
                </div>

                <!-- University Cards List -->
                <div id="university-list" class="space-y-6">
                    <!-- University cards will be dynamically injected here -->
                </div>

                <!-- Bottom Back Button -->
                <div class="pt-4 text-center">
                    <button onclick="resetSelection()" class="bg-slate-800/90 hover:bg-slate-700 text-emerald-300 font-bold text-base px-8 py-3.5 rounded-xl border border-emerald-500/30 shadow-lg transition-all inline-flex items-center gap-2">
                        <i class="fa-solid fa-arrow-left"></i>
                        <span>다른 지역 살펴보기</span>
                    </button>
                </div>

            </div>
        </div>

    </main>

    <footer class="text-center text-emerald-400/70 text-sm font-normal mt-8 py-3">
        <p>© 대한민국 지역별 대학 안내 가이드라인 | 초보자용 대학교 입시/특징 참고용 데이터</p>
    </footer>

    <script>
        // 5 Regions & 5 Major Universities Data Structure
        const universityData = {
            "수도권": {
                description: "대한민국의 수도 서울과 인천, 경기도를 포함한 최대 인프라 집중 지역입니다.",
                icon: "fa-city",
                universities: [
                    {
                        name: "서울대학교",
                        location: "서울특별시 관악구",
                        type: "국립 (거점국립대)",
                        specialty: "대한민국 최고 수준의 학문적 명성과 넓은 관악 캠퍼스 인프라",
                        pros: [
                            "국내 최고 수준의 연구 환경과 도서관 및 학술 자원 보유",
                            "압도적인 동문 네트워크와 취업 및 사회 진출 이점",
                            "국립대로서 사립대 대비 상대적으로 저렴한 등록금"
                        ],
                        cons: [
                            "캠퍼스가 매우 넓어 내부 이동 시 순환버스 이용 필수",
                            "학업 경쟁 강도가 높아 학점 관리에 부담이 큼"
                        ]
                    },
                    {
                        name: "연세대학교",
                        location: "서울특별시 서대문구 (신촌)",
                        type: "사립",
                        specialty: "신촌 중심가 위치, 국제화 프로그램 및 뛰어난 대학 문화",
                        pros: [
                            "신촌에 위치하여 활발한 대학가 문화와 편의시설 우수",
                            "국제학부 및 교환학생 프로그램 등 글로벌 네트워크 강력",
                            "의학·경영·인문 분야의 높은 학과 경쟁력"
                        ],
                        cons: [
                            "사립대 특성상 등록금이 높은 편",
                            "1학년 송도 국제캠퍼스 이수로 인한 신촌과의 거리감 존재"
                        ]
                    },
                    {
                        name: "고려대학교",
                        location: "서울특별시 성북구 (안암)",
                        type: "사립",
                        specialty: "끈끈한 선후배 단결력과 전통의 입실렌티 문화",
                        pros: [
                            "강력한 동문 유대감과 끈끈한 네트워크 형성",
                            "이공계 인공지능·IT 및 법학·경영 분야 최상위권",
                            "지하철역(안암역, 고려대역) 직결로 우수한 교통 접근성"
                        ],
                        cons: [
                            "경사지가 많은 캠퍼스 지형 구조",
                            "주변 대학가가 신촌에 비해 상대적으로 소박함"
                        ]
                    },
                    {
                        name: "성균관대학교",
                        location: "인문사회(서울 종로) / 자연과학(경기 수원)",
                        type: "사립",
                        specialty: "삼성재단의 과감한 투자와 계열별 이원화 캠퍼스 운영",
                        pros: [
                            "기업 재단의 든든한 장학금 및 취업 연계 프로그램",
                            "자연과학캠퍼스(수원)의 첨단 연구 시설과 산학협력",
                            "서울 캠퍼스의 대학로 및 혜화 문화권 접근성"
                        ],
                        cons: [
                            "문과(서울)와 이과(수원)의 캠퍼스 이원화로 교류 한계",
                            "수원 캠퍼스의 경우 수도권 외곽에 위치함"
                        ]
                    },
                    {
                        name: "한양대학교",
                        location: "서울특별시 성동구 (왕십리)",
                        type: "사립",
                        specialty: "전통적 명성의 공과대학과 왕십리 교통의 요충지",
                        pros: [
                            "공과대학 분야에서 독보적인 기술력과 인지도 보유",
                            "2호선·5호선·경의중앙선·수인분당선 환승 왕십리역 상권 연결",
                            "실용 학문 위주의 커리큘럼과 높은 취업률"
                        ],
                        cons: [
                            "캠퍼스 내 언덕(행원파크 등)이 높아서 이동 피로도 존재",
                            "인문계열 지원 규모가 공대에 비해 상대적으로 작다는 인식"
                        ]
                    }
                ]
            },
            "충청권": {
                description: "대전, 세종, 충남, 충북을 아우르는 연구 인프라와 교통 중심 지역입니다.",
                icon: "fa-atom",
                universities: [
                    {
                        name: "KAIST (한국과학기술원)",
                        location: "대전광역시 유성구",
                        type: "특별법인 과학기술원",
                        specialty: "대한민국 과학기술 연구와 이공계 교육의 중심지",
                        pros: [
                            "전교생 국비 장학생 혜택 및 수강료·기숙사비 대폭 지원",
                            "대덕연구개발특구 연계로 최고 수준의 연구 시설 보유",
                            "100% 영어 강의 및 자유로운 학과 선택(무학과) 제도"
                        ],
                        cons: [
                            "이공계 전공 위주로 인문·예술 분야 학문 다양성 부족",
                            "높은 학업 난이도로 인한 스트레스 수준이 높음"
                        ]
                    },
                    {
                        name: "충남대학교",
                        location: "대전광역시 유성구 (궁동)",
                        type: "국립 (거점국립대)",
                        specialty: "대덕연구단지 및 대전 중심가와 가까운 거점 국립대",
                        pros: [
                            "넓은 평지 캠퍼스 및 국립대의 저렴한 등록금",
                            "유성구 궁동 대학가 상권과의 우수한 접근성",
                            "충청권 지역인재 채용 제도 혜택 적용"
                        ],
                        cons: [
                            "캠퍼스가 커서 강의실 간 이동 시 유성 타슈(자전거) 필수",
                            "수도권 유입 학생의 경우 주말 교통 편의성 고려 필요"
                        ]
                    },
                    {
                        name: "충북대학교",
                        location: "충청북도 청주시 서원구",
                        type: "국립 (거점국립대)",
                        specialty: "약학·의학·IT 인프라가 강한 충북 지역 거점 국립대",
                        pros: [
                            "청주 중심지에 위치하여 생활 인프라 편리",
                            "오송 바이오캠퍼스 연계 바이오·약학 분야 특화",
                            "저렴한 생활비와 높은 기숙사 수용률"
                        ],
                        cons: [
                            "타 거점 국립대에 비해 대외 인지도 면에서 아쉬움",
                            "수도권 접근 시 대중교통 이용에 시간 다소 소요"
                        ]
                    },
                    {
                        name: "단국대학교 (천안캠퍼스)",
                        location: "충청남도 천안시 동남구",
                        type: "사립",
                        specialty: "의·치·약학 및 생명과학 생태계가 구축된 캠퍼스",
                        pros: [
                            "수도권 전철 1호선 연결로 수도권 등하교 가능",
                            "대학병원 보유로 의학·보건 계열 강세",
                            "단대호수(안서호) 등 수려한 캠퍼스 경관"
                        ],
                        cons: [
                            "죽전(용인) 캠퍼스와의 이원화로 인한 차이점 존재",
                            "천안역/터미널에서 캠퍼스까지 시내버스 이동 필요"
                        ]
                    },
                    {
                        name: "한남대학교",
                        location: "대전광역시 대덕구",
                        type: "사립",
                        specialty: "기독교 사학 전통 및 외국어/국제화 교육 특화",
                        pros: [
                            "외국어 전공 및 글로벌 교환학생 프로그램 활성화",
                            "대전 오정동 위치로 대전역 및 터미널 접근 용이",
                            "아기자기하고 캠퍼스 영화 촬영지로 유명한 경관"
                        ],
                        cons: [
                            "이공계열 연구 인프라가 대형 연구 중심대에 비해 다소 적음",
                            "사립대로서 국립대 대비 높은 등록금"
                        ]
                    }
                ]
            },
            "호남권": {
                description: "광주, 전남, 전북을 포함하는 풍부한 예향과 첨단 과학기술의 조화 지역입니다.",
                icon: "fa-leaf",
                universities: [
                    {
                        name: "전남대학교",
                        location: "광주광역시 북구 (용봉)",
                        type: "국립 (거점국립대)",
                        specialty: "호남권 최대 규모의 학문적 인프라와 전통의 거점국립대",
                        pros: [
                            "넓고 평평한 아름다운 용봉 캠퍼스와 도심 접근성",
                            "광주전남 혁신도시 공공기관 지역인재 채용 우대",
                            "의학·농생대·인문학 등 전 분야 균형 잡힌 학과 구성"
                        ],
                        cons: [
                            "수도권과의 물리적 거리로 이동 비용 및 시간 발생",
                            "일부 노후화된 건물 및 시설 개선 추진 중"
                        ]
                    },
                    {
                        name: "전북대학교",
                        location: "전북특별자치도 전주시 덕진구",
                        type: "국립 (거점국립대)",
                        specialty: "한옥풍 전통 캠퍼스 디자인과 공격적인 대학 혁신 투자",
                        pros: [
                            "한옥 스타일 건물이 조화된 개성 있고 아름다운 캠퍼스",
                            "정부 국책사업 수주가 많아 학생 지원금 혜택 풍부",
                            "전주 덕진공원 부근 우수한 주변 환경과 맛집 문화"
                        ],
                        cons: [
                            "전주 시내 교통 체증 시 접근성 저하",
                            "특정 선호 학과와 비선호 학과 간의 지원 격차"
                        ]
                    },
                    {
                        name: "GIST (광주과학기술원)",
                        location: "광주광역시 북구 (첨단단지)",
                        type: "특별법인 과학기술원",
                        specialty: "소수 정예 융합 과학기술 교육과 최고 수준의 장학 혜택",
                        pros: [
                            "교수 대 학생 비율 최상위권의 밀착 연구 지도",
                            "등록금 지원 및 기숙사 제공 등 압도적인 장학 지원",
                            "첨단과학산업단지 내 위치하여 연구소 연계 우수"
                        ],
                        cons: [
                            "학부생 규모가 작아 대형 종합대학의 동아리/축제 문화 부족",
                            "매우 빡빡한 이공계 커리큘럼 과정"
                        ]
                    },
                    {
                        name: "조선대학교",
                        location: "광주광역시 동구 (서석동)",
                        type: "사립 (민립대학)",
                        specialty: "국내 최초의 민립대학 역사와 광주 도심 속 대형 캠퍼스",
                        pros: [
                            "광주 동구 도심(충장로, 무등산) 인접으로 생활 편의 우수",
                            "의·치·간호 등 보건 의료 계열의 막강한 경쟁력",
                            "장미원 축제 등 지역 사회와 함께하는 활발한 문화"
                        ],
                        cons: [
                            "무등산 자락 경사지에 위치하여 등교 시 경사 완판 필요",
                            "사립대 특성상 국립대 대비 상대적으로 높은 등록금"
                        ]
                    },
                    {
                        name: "원광대학교",
                        location: "전북특별자치도 익산시",
                        type: "사립",
                        specialty: "의학·치학·한의학·약학을 모두 보유한 보건의료 특화대",
                        pros: [
                            "의·치·한·약·간호 분야 완비로 보건의료 인프라 최고 수준",
                            "익산역(KTX) 인접으로 수도권 접근성 양호",
                            "평지의 넓고 쾌적한 박물관 및 수목원 보유 캠퍼스"
                        ],
                        cons: [
                            "보건계열 외 일반 비의료계열 학과의 인지도 격차",
                            "익산 시내 중심가와의 거리감"
                        ]
                    }
                ]
            },
            "영남권": {
                description: "부산, 대구, 울산, 경남, 경북을 아우르는 동남권 산업 및 교육의 중심입니다.",
                icon: "fa-industry",
                universities: [
                    {
                        name: "부산대학교",
                        location: "부산광역시 금정구 (장전)",
                        type: "국립 (거점국립대)",
                        specialty: "영남권 대표 거점 국립대 및 전통의 전통 명문",
                        pros: [
                            "부산 최대 대학가 상권(부산대 정문/장전동) 형성",
                            "동남권 해양·기계·공학 및 인문 사회 전 분야 높은 인지도",
                            "혁신도시 이전 공공기관 및 대기업 지역인재 채용 우대"
                        ],
                        cons: [
                            "금정산 자락에 위치하여 경사가 심한 편",
                            "밀양/양산 캠퍼스 분리로 인한 학과 간 교류 불편"
                        ]
                    },
                    {
                        name: "경북대학교",
                        location: "대구광역시 북구 (산격동)",
                        type: "국립 (거점국립대)",
                        specialty: "대구·경북 거점 국립대 및 전자·IT 분야 특화 전통",
                        pros: [
                            "전자공학부를 필두로 한 IT 및 공학 계열의 강한 전통",
                            "대구 시내 중심부 위치로 대중교통 및 상권 양호",
                            "저렴한 학비와 우수한 대구·경북 인맥 네트워크"
                        ],
                        cons: [
                            "상주캠퍼스 이원화에 따른 캠퍼스 간 거리 존재",
                            "여름철 대구 특유의 더운 기후 환경"
                        ]
                    },
                    {
                        name: "UNIST (울산과학기술원)",
                        location: "울산광역시 울주군",
                        type: "특별법인 과학기술원",
                        specialty: "신소재·에너지·바이오 연구 인프라 중심의 과학기술원",
                        pros: [
                            "울산 첨단 산업단지와 연계된 산학협력 및 연구 과제",
                            "전 과목 100% 영어 강의 및 첨단 연구 시설 완비",
                            "장학금 및 기숙사 혜택 우수"
                        ],
                        cons: [
                            "울산 시가지와 떨어진 울주군 외곽에 위치함",
                            "주변 문화/엔터테인먼트 편의시설 부족"
                        ]
                    },
                    {
                        name: "POSTECH (포항공과대학교)",
                        location: "경상북도 포항시 남구",
                        type: "사립 (연구중심대)",
                        specialty: "세계적 수준의 소수정예 연구 중심 공과대학교",
                        pros: [
                            "학생 1인당 최고 수준의 연구 투자 및 교육 환경",
                            "전교생 등록금 및 생활비 지원 수준 최상위",
                            "포스코 재단의 강력한 지원과 방사광가속기 등 최고 연구 장비"
                        ],
                        cons: [
                            "포항에 위치하여 수도권 및 광역 도시와의 접근성 부족",
                            "매우 엄격한 학업 및 연구 요구량"
                        ]
                    },
                    {
                        name: "동아대학교",
                        location: "부산광역시 서구 / 사하구 / 중구",
                        type: "사립",
                        specialty: "부산 지역 역사가 깊은 전통 사학 및 법학·의학 특화",
                        pros: [
                            "승학, 부민, 구덕 3개 캠퍼스로 부산 주요 도심 위치",
                            "법학전문대학원(로스쿨) 및 동아대병원 보유",
                            "부산·경남 지역 내 넓은 동문 네트워크"
                        ],
                        cons: [
                            "캠퍼스가 3개로 분산되어 있어 교류 제한",
                            "승학캠퍼스의 가파른 108계단 등 언덕 지형"
                        ]
                    }
                ]
            },
            "강원/제주권": {
                description: "청정 자연환경과 독특한 관광·바이오 특화 인프라를 지닌 지역입니다.",
                icon: "fa-mountain-sun",
                universities: [
                    {
                        name: "강원대학교",
                        location: "강원특별자치도 춘천시 (효자)",
                        type: "국립 (거점국립대)",
                        specialty: "ITX-청춘 및 경춘선으로 수도권 접근이 용이한 거점 국립대",
                        pros: [
                            "수도권(청량리/상봉)에서 전철/ITX로 접근 가능",
                            "바이오·의생명·농업 분야 특화 및 저렴한 국립대 등록금",
                            "넓고 평탄한 춘천 캠퍼스 생활 환경"
                        ],
                        cons: [
                            "삼척/도계 캠퍼스 통합에 따른 캠퍼스 간 거리 격차",
                            "겨울철 매우 추운 기후 조건"
                        ]
                    },
                    {
                        name: "한림대학교",
                        location: "강원특별자치도 춘천시 (옥천)",
                        type: "사립",
                        specialty: "일송학원 재단 기반 의학·일송생명과학 및 미디어 특화",
                        pros: [
                            "성심병원 등 5개 부속병원을 바탕으로 한 의학·간호 분야 최고 수준",
                            "소수 정예 맞춤형 교육 및 쾌적한 교육 시설",
                            "춘천 명동 상권과 가까운 위치"
                        ],
                        cons: [
                            "의료/보건계열 외 학과의 인지도 차이",
                            "사립대 특성상 국립대 대비 등록금 부담"
                        ]
                    },
                    {
                        name: "제주대학교",
                        location: "제주특별자치도 제주시 (아라)",
                        type: "국립 (거점국립대)",
                        specialty: "제주도 유일의 거점 국립대 및 해양·수의학·관광 특화",
                        pros: [
                            "수의학과, 해양과학, 관광 관련 특화 학과 경쟁력 우수",
                            "한라산 자락의 아름다운 자연경관과 쾌적한 캠퍼스",
                            "제주 지역 공공기관 및 관광 산업 지역인재 혜택"
                        ],
                        cons: [
                            "육지 이동 시 항공기/선박 이용 필수 (교통비 부담)",
                            "기상 악화 시 이동 제약 발생 가능성"
                        ]
                    },
                    {
                        name: "강릉원주대학교",
                        location: "강원특별자치도 강릉시 / 원주시",
                        type: "국립",
                        specialty: "강릉(해양·치대)과 원주(보건·IT) 이원화 국립 대학",
                        pros: [
                            "국립 치과대학 보유 (강릉캠퍼스)",
                            "KTX-이음 개통으로 서울(청량리/서울역) 접근시간 단축",
                            "동해안 및 원주 혁신도시 인근 위치"
                        ],
                        cons: [
                            "강릉과 원주 캠퍼스 간 거리가 멀어 상호 교류 어려움",
                            "영동 지역 특성상 풍수해 및 제설 영향"
                        ]
                    },
                    {
                        name: "한라대학교",
                        location: "강원특별자치도 원주시",
                        type: "사립",
                        specialty: "HL그룹(구 한라그룹) 지원 기반의 자동차·스마트모빌리티 특화",
                        pros: [
                            "HL그룹 연계 스마트모빌리티, 미래자동차 특화 교육",
                            "원주 위치로 수도권 전철 및 KTX 접근성 양호",
                            "산학협력 위주의 실무 중심 학과 개설"
                        ],
                        cons: [
                            "종합대학에 비해 학과 종류 및 인문계열 규모가 작음",
                            "원주 시내 외곽 위치"
                        ]
                    }
                ]
            }
        };

        // Initialize Region Grid Buttons
        function initRegionButtons() {
            const grid = document.getElementById('region-grid');
            grid.innerHTML = '';

            Object.keys(universityData).forEach(regionKey => {
                const region = universityData[regionKey];
                const btn = document.createElement('button');
                btn.className = 'region-btn p-5 rounded-2xl text-left cursor-pointer flex flex-col justify-between group shadow-md';
                btn.onclick = () => selectRegion(regionKey);

                btn.innerHTML = `
                    <div class="flex items-center justify-between mb-3">
                        <div class="w-12 h-12 rounded-xl bg-emerald-500/20 border border-emerald-400/30 flex items-center justify-center text-emerald-300 text-xl group-hover:scale-110 transition-transform">
                            <i class="fa-solid ${region.icon}"></i>
                        </div>
                        <span class="text-xs bg-emerald-950/80 text-emerald-300 border border-emerald-500/30 px-2.5 py-1 rounded-full font-semibold">5개 대학</span>
                    </div>
                    <div>
                        <h3 class="text-2xl font-bold text-white mb-1 group-hover:text-emerald-300 transition-colors">${regionKey}</h3>
                        <p class="text-xs text-emerald-200/80 line-clamp-2 font-normal">${region.description}</p>
                    </div>
                    <div class="mt-4 pt-3 border-t border-emerald-500/20 flex items-center justify-between text-xs font-semibold text-emerald-300">
                        <span>대학 보기</span>
                        <i class="fa-solid fa-chevron-right group-hover:translate-x-1 transition-transform"></i>
                    </div>
                `;

                grid.appendChild(btn);
            });
        }

        // Handle Region Selection
        function selectRegion(regionKey) {
            const data = universityData[regionKey];
            if (!data) return;

            // Set Title & Description
            document.getElementById('selected-region-title').innerText = `${regionKey} 대표 대학`;
            document.getElementById('selected-region-desc').innerText = data.description;

            // Render University Cards
            const container = document.getElementById('university-list');
            container.innerHTML = '';

            data.universities.forEach((uni, idx) => {
                const card = document.createElement('div');
                card.className = 'glass-card rounded-2xl p-6 md:p-7 border border-emerald-500/30 shadow-xl space-y-4';

                // Pros HTML
                const prosHtml = uni.pros.map(p => `
                    <li class="flex items-start gap-2 text-emerald-100 text-sm md:text-base">
                        <i class="fa-solid fa-circle-check text-emerald-400 mt-1 flex-shrink-0"></i>
                        <span>${p}</span>
                    </li>
                `).join('');

                // Cons HTML
                const consHtml = uni.cons.map(c => `
                    <li class="flex items-start gap-2 text-amber-100/90 text-sm md:text-base">
                        <i class="fa-solid fa-triangle-exclamation text-amber-400 mt-1 flex-shrink-0"></i>
                        <span>${c}</span>
                    </li>
                `).join('');

                card.innerHTML = `
                    <!-- Header -->
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between border-b border-emerald-500/20 pb-4 gap-2">
                        <div class="flex items-center gap-3">
                            <span class="w-8 h-8 rounded-lg bg-emerald-500/20 border border-emerald-400/40 text-emerald-300 font-extrabold flex items-center justify-center text-sm">
                                0${idx + 1}
                            </span>
                            <h3 class="text-2xl md:text-3xl font-extrabold text-white">${uni.name}</h3>
                        </div>
                        <div class="flex items-center gap-2 text-xs md:text-sm">
                            <span class="bg-slate-800 text-emerald-300 px-3 py-1 rounded-full border border-emerald-500/30">
                                <i class="fa-solid fa-location-dot mr-1"></i>${uni.location}
                            </span>
                            <span class="bg-emerald-950 text-teal-300 px-3 py-1 rounded-full border border-teal-500/30 font-medium">
                                ${uni.type}
                            </span>
                        </div>
                    </div>

                    <!-- Specialty / Key Feature -->
                    <div class="bg-emerald-950/60 rounded-xl p-3.5 border border-emerald-500/20 text-emerald-200 text-sm md:text-base flex items-start gap-2.5">
                        <i class="fa-solid fa-star text-amber-300 mt-0.5 text-base flex-shrink-0"></i>
                        <div>
                            <span class="font-bold text-emerald-300">주요 특징: </span>
                            <span>${uni.specialty}</span>
                        </div>
                    </div>

                    <!-- Pros & Cons Grid -->
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4 pt-2">
                        <!-- Advantages (Pros) -->
                        <div class="bg-emerald-950/40 rounded-xl p-4 border border-emerald-500/30">
                            <h4 class="text-base font-bold text-emerald-300 mb-2.5 flex items-center gap-2">
                                <i class="fa-solid fa-thumbs-up"></i> 주요 장점
                            </h4>
                            <ul class="space-y-2">
                                ${prosHtml}
                            </ul>
                        </div>

                        <!-- Disadvantages (Cons) -->
                        <div class="bg-slate-900/60 rounded-xl p-4 border border-amber-500/20">
                            <h4 class="text-base font-bold text-amber-300 mb-2.5 flex items-center gap-2">
                                <i class="fa-solid fa-circle-exclamation"></i> 고려할 점 (단점)
                            </h4>
                            <ul class="space-y-2">
                                ${consHtml}
                            </ul>
                        </div>
                    </div>
                `;

                container.appendChild(card);
            });

            // Switch Screen
            document.getElementById('selection-page').classList.add('hidden');
            document.getElementById('result-page').classList.remove('hidden');

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Reset & Return to Selection Page
        function resetSelection() {
            document.getElementById('result-page').classList.add('hidden');
            document.getElementById('selection-page').classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Run setup on window load
        window.onload = function() {
            initRegionButtons();
        };
    </script>
</body>
</html>
