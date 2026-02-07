<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Виктория & Семён | Наша Свадьба</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@200;300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <!-- AOS Animation Library -->
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <style>
        :root {
            --glass-bg: rgba(30, 30, 30, 0.6);
            --glass-border: rgba(255, 255, 255, 0.1);
            --text-main: #f8f9fa;
            --accent: #d4a373; /* Золотистый акцент */
        }
        
        body {
            font-family: 'Montserrat', sans-serif;
            background-color: #0f0f0f;
            color: var(--text-main);
            overflow-x: hidden;
        }

        .font-serif { font-family: 'Playfair Display', serif; }
        .font-cursive { font-family: 'Great Vibes', cursive; }

        .glass {
            background: var(--glass-bg);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.4);
        }

        .hero-bg {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                        url('https://images.unsplash.com/photo-1511285560929-80b456fea0bc?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        /* Preloader Style */
        #preloader {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: #0f0f0f;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transition: opacity 1s ease-out, visibility 1s;
        }

        .loader-text {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: var(--accent);
            animation: pulse 2s infinite ease-in-out;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.3; transform: scale(0.95); }
            50% { opacity: 1; transform: scale(1); }
        }

        .custom-scroll::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: #1a1a1a;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: var(--accent);
            border-radius: 10px;
        }

        .timeline-dot::after {
            content: '';
            position: absolute;
            width: 12px;
            height: 12px;
            background: var(--accent);
            border-radius: 50%;
            left: -6px;
            top: 10px;
        }

        .designer-tag {
            font-size: 0.65rem;
            letter-spacing: 0.4em;
            color: rgba(255,255,255,0.2);
            transition: color 0.3s;
        }
        .designer-tag:hover {
            color: var(--accent);
        }

        .btn-primary {
            background: var(--accent);
            color: #000;
            transition: all 0.4s;
        }
        .btn-primary:hover {
            background: #fff;
            transform: translateY(-2px);
        }

        input, select, textarea {
            color: white !important;
        }
        input::placeholder, textarea::placeholder {
            color: rgba(255,255,255,0.4) !important;
        }
    </style>
</head>
<body class="custom-scroll">

    <!-- Preloader -->
    <div id="preloader">
        <div class="loader-text">V & S</div>
        <div class="w-12 h-[1px] bg-stone-800 mt-4"></div>
    </div>

    <!-- Hero Section -->
    <section class="relative h-screen flex items-center justify-center text-center text-white hero-bg overflow-hidden">
        <div class="z-10 px-4" data-aos="zoom-out" data-aos-duration="2000">
            <h2 class="text-lg md:text-xl mb-6 tracking-[0.3em] uppercase font-light text-stone-300">Сохраните дату</h2>
            <h1 class="text-7xl md:text-[10rem] font-cursive mb-4 drop-shadow-2xl text-white">Виктория & Сёма</h1>
            <div class="h-[1px] w-24 bg-accent mx-auto my-8 opacity-70"></div>
            <p class="text-2xl md:text-3xl font-serif italic mb-12 text-stone-200">30 мая 2026</p>
            <div class="flex flex-col md:flex-row gap-4 justify-center items-center">
                <a href="#rsvp" class="btn-primary px-10 py-4 rounded-full font-medium tracking-widest uppercase text-sm">Приду!</a>
                <a href="#timing" class="glass px-10 py-4 rounded-full hover:bg-white hover:text-black transition duration-500 font-medium tracking-widest uppercase text-sm">Программа</a>
            </div>
        </div>
        <!-- Декор -->
        <div class="absolute -bottom-20 -left-20 w-96 h-96 bg-accent/10 rounded-full blur-3xl"></div>
    </section>

    <!-- История пары -->
    <section class="relative py-24 bg-[#0a0a0a] overflow-hidden border-b border-white/5">
        <div class="container mx-auto px-4 grid md:grid-cols-2 gap-16 items-center">
            <div data-aos="fade-right">
                <h2 class="text-5xl font-serif mb-8 text-white">Наша история</h2>
                <p class="text-stone-400 leading-relaxed mb-8 text-lg">
                    Мы прошли долгий путь от случайного знакомства до осознанного решения создать свою крепость. 
                    Челябинск подарил нам друг друга, и мы хотим, чтобы в этот весенний вечер вы стали частью нашей новой главы.
                </p>
                <div id="countdown" class="grid grid-cols-4 gap-4">
                    <div class="text-center">
                        <span id="days" class="text-4xl font-light text-accent block">00</span>
                        <span class="text-[10px] uppercase tracking-widest text-stone-500">дней</span>
                    </div>
                    <div class="text-center">
                        <span id="hours" class="text-4xl font-light text-accent block">00</span>
                        <span class="text-[10px] uppercase tracking-widest text-stone-500">часов</span>
                    </div>
                    <div class="text-center">
                        <span id="minutes" class="text-4xl font-light text-accent block">00</span>
                        <span class="text-[10px] uppercase tracking-widest text-stone-500">минут</span>
                    </div>
                    <div class="text-center">
                        <span id="seconds" class="text-4xl font-light text-accent block">00</span>
                        <span class="text-[10px] uppercase tracking-widest text-stone-500">сек</span>
                    </div>
                </div>
            </div>
            <div class="relative" data-aos="fade-left">
                <img src="https://i.pinimg.com/736x/7c/0f/34/7c0f3446d236be50c4cdb4763de7c6e7.jpg" alt="Свадебная пара" class="rounded-2xl shadow-2xl relative z-10 brightness-75">
                <div class="absolute -top-10 -right-10 w-full h-full border-2 border-accent/20 rounded-2xl z-0"></div>
            </div>
        </div>
    </section>

    <!-- Программа дня -->
    <section id="timing" class="py-24 bg-[#0f0f0f]">
        <div class="container mx-auto px-4 max-w-4xl text-center">
            <h2 class="text-4xl font-serif mb-16 uppercase tracking-widest text-white" data-aos="fade-up">Программа дня</h2>
            <div class="relative border-l-2 border-stone-800 ml-6 md:ml-0 md:border-none inline-block text-left w-full">
                
                <div class="mb-12 relative md:flex md:justify-between items-center" data-aos="fade-up">
                    <div class="md:w-[45%] md:text-right mb-4 md:mb-0">
                        <span class="text-accent font-light italic">15:30 — 16:00</span>
                    </div>
                    <div class="timeline-dot hidden md:block"></div>
                    <div class="md:w-[45%] pl-6 md:pl-0">
                        <h4 class="font-bold text-lg uppercase tracking-wider text-stone-200">Welcome-коктейль</h4>
                        <p class="text-stone-500 text-sm">Сбор гостей, легкие закуски и живой джаз</p>
                    </div>
                </div>

                <div class="mb-12 relative md:flex md:justify-between items-center" data-aos="fade-up">
                    <div class="md:w-[45%] md:text-right mb-4 md:mb-0">
                        <span class="text-accent font-light italic">16:00 — 16:30</span>
                    </div>
                    <div class="timeline-dot hidden md:block"></div>
                    <div class="md:w-[45%] pl-6 md:pl-0">
                        <h4 class="font-bold text-lg uppercase tracking-wider text-stone-200">Выездная регистрация</h4>
                        <p class="text-stone-500 text-sm">Трогательный момент обмена клятвами под открытым небом</p>
                    </div>
                </div>

                <div class="mb-12 relative md:flex md:justify-between items-center" data-aos="fade-up">
                    <div class="md:w-[45%] md:text-right mb-4 md:mb-0">
                        <span class="text-accent font-light italic">17:00 — 23:00</span>
                    </div>
                    <div class="timeline-dot hidden md:block"></div>
                    <div class="md:w-[45%] pl-6 md:pl-0">
                        <h4 class="font-bold text-lg uppercase tracking-wider text-stone-200">Свадебный ужин</h4>
                        <p class="text-stone-500 text-sm">Банкет, поздравления и праздничная программа</p>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Местоположение -->
    <section class="py-24 relative overflow-hidden bg-[#0a0a0a]">
        <div class="container mx-auto px-4 max-w-5xl">
            <div class="glass p-12 rounded-[3rem] relative z-10" data-aos="flip-up">
                <div class="grid md:grid-cols-2 gap-12 items-center text-center md:text-left">
                    <div>
                        <h3 class="text-4xl font-serif mb-6 text-white">Место встречи</h3>
                        <p class="text-xl mb-2 font-medium text-accent">Челябинск</p>
                        <p class="text-stone-400 mb-6 italic">улица Победы, 20</p>
                        <p class="text-stone-500 text-sm leading-relaxed mb-8">
                            Банкетный холл "Торжество". Для вашего удобства предусмотрена охраняемая парковка. 
                            Пожалуйста, планируйте маршрут заранее, чтобы не пропустить начало церемонии.
                        </p>
                        <a href="https://yandex.ru/maps" target="_blank" class="inline-block btn-primary px-8 py-3 rounded-full tracking-widest text-xs uppercase font-bold">Открыть карту</a>
                    </div>
                    <div class="rounded-3xl overflow-hidden h-64 shadow-2xl">
                        <img src="https://static.tildacdn.com/tild3562-3630-4162-b337-396132646262/MV5A3444.jpg" alt="Место проведения" class="w-full h-full object-cover grayscale hover:grayscale-0 transition duration-700 brightness-50 hover:brightness-100">
                    </div>
                </div>
            </div>
        </div>
        <div class="absolute top-0 right-0 w-80 h-80 bg-accent/5 rounded-full -mr-40 blur-3xl"></div>
    </section>

    <!-- Дресс-код и FAQ -->
    <section class="py-24 bg-[#0f0f0f]">
        <div class="container mx-auto px-4 max-w-4xl">
            <div class="grid md:grid-cols-2 gap-16">
                <div data-aos="fade-up">
                    <h3 class="text-3xl font-serif mb-8 text-white">Дресс-код</h3>
                    <p class="text-stone-500 mb-8 italic">Мы будем признательны за соблюдение нашей палитры в ваших образах:</p>
                    <div class="flex gap-4">
                        <div class="w-14 h-14 rounded-full bg-[#1a1a1a] shadow-lg border-2 border-accent/30 ring-2 ring-black"></div>
                        <div class="w-14 h-14 rounded-full bg-[#d4a373] shadow-lg border-2 border-black ring-2 ring-stone-900"></div>
                        <div class="w-14 h-14 rounded-full bg-[#4a4a4a] shadow-lg border-2 border-black ring-2 ring-stone-900"></div>
                        <div class="w-14 h-14 rounded-full bg-[#f8f9fa] shadow-lg border-2 border-black ring-2 ring-stone-900"></div>
                    </div>
                </div>
                <div data-aos="fade-up" data-aos-delay="200">
                    <h3 class="text-3xl font-serif mb-8 text-white">Важно знать</h3>
                    <div class="space-y-4">
                        <details class="group cursor-pointer">
                            <summary class="flex justify-between items-center font-medium py-2 border-b border-stone-800 text-stone-300">
                                Можно ли прийти с детьми?
                                <span class="group-open:rotate-180 transition text-accent">↓</span>
                            </summary>
                            <p class="text-sm text-stone-500 py-2">Да, мы будем рады видеть вашу семью в полном составе. Сообщите нам об этом в RSVP форме.</p>
                        </details>
                        <details class="group cursor-pointer">
                            <summary class="flex justify-between items-center font-medium py-2 border-b border-stone-800 text-stone-300">
                                Что дарить?
                                <span class="group-open:rotate-180 transition text-accent">↓</span>
                            </summary>
                            <p class="text-sm text-stone-500 py-2">Ваше присутствие — самый главный подарок. Подарки в конвертах помогут нам осуществить нашу мечту.</p>
                        </details>
                        <details class="group cursor-pointer">
                            <summary class="flex justify-between items-center font-medium py-2 border-b border-stone-800 text-stone-300">
                                Цветы
                                <span class="group-open:rotate-180 transition text-accent">↓</span>
                            </summary>
                            <p class="text-sm text-stone-500 py-2">Вместо живых цветов мы будем рады бутылочке вашего любимого вина для нашей домашней коллекции.</p>
                        </details>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- RSVP Форма -->
    <section id="rsvp" class="py-24 bg-[#0a0a0a] relative">
        <div class="container mx-auto px-4">
            <div class="max-w-2xl mx-auto glass p-10 md:p-16 rounded-[4rem] text-center" data-aos="zoom-in">
                <h2 class="text-5xl font-cursive mb-6 text-white">Ждем вас!</h2>
                <p class="text-accent mb-12 italic uppercase tracking-widest text-[10px]">Пожалуйста, подтвердите участие до 1 мая 2026</p>
                
                <form id="rsvpForm" action="https://api.sheetmonkey.io/form/czR9XJkEHR2KoZa3y1yQnj" method="POST" class="space-y-6 text-left">
                    <div class="relative">
                        <input type="text" name="Name" required placeholder="Ваше Имя и Фамилия" class="w-full bg-black/30 border-b border-stone-700 p-4 outline-none focus:border-accent transition text-white">
                    </div>
                    <div class="relative">
                        <select name="Attendance" class="w-full bg-black/30 border-b border-stone-700 p-4 outline-none focus:border-accent transition cursor-pointer appearance-none text-white">
                            <option value="ДА" class="bg-stone-900">Да, приду!</option>
                            <option value="НЕТ" class="bg-stone-900">К сожалению, не смогу</option>
                            <option value="НЕ ЗНАЮ" class="bg-stone-900">Пока под вопросом</option>
                        </select>
                    </div>
                    <div>
                        <textarea name="Message" rows="3" placeholder="Предпочтения по напиткам или еде" class="w-full bg-black/30 border-b border-stone-700 p-4 outline-none focus:border-accent transition resize-none text-white"></textarea>
                    </div>
                    <button type="submit" class="w-full btn-primary py-5 rounded-2xl hover:scale-[1.02] transition duration-300 font-bold uppercase tracking-[0.2em] shadow-2xl">Отправить ответ</button>
                </form>

                <div id="successMessage" class="hidden animate-pulse mt-8 p-6 bg-accent/10 text-accent rounded-3xl border border-accent/20">
                    <p class="font-serif text-2xl mb-1 italic">До встречи!</p>
                    <p class="text-[10px] uppercase">Ваш ответ бережно сохранен в Google Таблицу</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Подвал -->
    <footer class="py-20 bg-black text-center relative overflow-hidden">
        <p class="text-7xl md:text-[8rem] font-cursive opacity-5 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 select-none text-white">Victoria & Semyon</p>
        <div class="relative z-10">
            <h4 class="text-3xl font-cursive mb-4 text-accent">Виктория & Семён</h4>
            <div class="flex justify-center gap-6 text-stone-500 text-sm tracking-[0.3em] uppercase mb-12">
                <span>30.05.2026</span>
            </div>
            <p class="text-[10px] text-stone-600 uppercase tracking-widest mb-2">&copy; Семья Корж 2026. Ждем встречи!</p>
            <p class="designer-tag uppercase">DESIGN BY SOLOVYEV</p>
        </div>
    </footer>

    <!-- Скрипты -->
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        // Прелоадер
        window.addEventListener('load', () => {
            const preloader = document.getElementById('preloader');
            preloader.style.opacity = '0';
            setTimeout(() => {
                preloader.style.visibility = 'hidden';
                AOS.init({
                    duration: 1200,
                    once: true
                });
            }, 1000);
        });

        // Логика таймера
        const targetDate = new Date("May 30, 2026 15:30:00").getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            const dEl = document.getElementById("days");
            const hEl = document.getElementById("hours");
            const mEl = document.getElementById("minutes");
            const sEl = document.getElementById("seconds");

            if(dEl) dEl.innerText = days < 10 ? "0" + days : days;
            if(hEl) hEl.innerText = hours < 10 ? "0" + hours : hours;
            if(mEl) mEl.innerText = minutes < 10 ? "0" + minutes : minutes;
            if(sEl) sEl.innerText = seconds < 10 ? "0" + seconds : seconds;

            if (distance < 0) {
                const cd = document.getElementById("countdown");
                if(cd) cd.innerHTML = "<p class='text-2xl font-serif italic text-accent'>Счастливы вместе!</p>";
            }
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // Отправка RSVP формы
        document.getElementById('rsvpForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            const form = e.target;
            const button = form.querySelector('button');
            const formData = new FormData(form);

            button.disabled = true;
            button.innerText = "ОБРАБОТКА...";

            try {
                const response = await fetch(form.action, {
                    method: 'POST',
                    body: formData,
                });

                if (response.ok) {
                    form.classList.add('hidden');
                    document.getElementById('successMessage').classList.remove('hidden');
                } else {
                    alert("Ошибка отправки данных. Попробуйте еще раз.");
                    button.disabled = false;
                    button.innerText = "ОТПРАВИТЬ ОТВЕТ";
                }
            } catch (error) {
                console.error('Error!', error);
                button.disabled = false;
                button.innerText = "ОТПРАВИТЬ ОТВЕТ";
            }
        });
    </script>
</body>
</html>
