```markdown
# МІНІСТЕРСТВО ОСВІТИ І НАУКИ УКРАЇНИ
# ХАРКІВСЬКИЙ НАЦІОНАЛЬНИЙ УНІВЕРСИТЕТ РАДІОЕЛЕКТРОНІКИ
## Кафедра програмної інженерії

<br>

### ЗВІТ
### про виконання лабораторної роботи №1
### з дисципліни «Гіпертекст та гіпермедіа»
### Тема: «Розробка структури та кодування вебсайту засобами мови HTML та каскадних таблиць стилів CSS»

<br>

**Виконав:** Студент групи ПЗПІ-25-4  
*Михайліченко Злата Юріївна*
**Перевірили:** *Зибіна К.В., Єрохін А.Л.*
<br>

### Харків — 2026

---

## 1. МЕТА РОБОТИ
Ознайомитися з принципами функціонування мови розмітки гіпертексту HTML та каскадних таблиць стилів CSS. Набути практичних навичок проектирування структури багатосторінкового веб-ресурсу, використання семантичних тегів HTML5, створення логічних блоків, гіперпосилань, навігаційних меню із випадаючими списками, табличних даних та форм зворотного зв'язку на прикладі веб-сайту мережі фітнес-центрів «Iron Force».

---

## 2. ЗАВДАННЯ РОБОТИ
1. Розробити концепцію, структуру та дизайн-систему для інформаційного сайту мережі спортзалів «Iron Force».
2. Створити три взаємопов'язані веб-сторінки (`index.html`, `services.html`, `contact.html`) з використанням семантичної розмітки HTML5.
3. Реалізувати головне навігаційне меню зі складним випадаючим списком (`.dropdown`) для переходу між розділами сайту та якірними посиланнями.
4. Організувати контент за допомогою сучасних елементів: структурованих таблиць (прайс-лист), маркованих списків переваг та інтерактивних форм для введення даних користувача.
5. Розробити файл каскадних таблиць стилів (`style.css`) для забезпечення сучасного, адаптивного візуального оформлення веб-ресурсу у темних тонах.

---

## 3. ТЕОРЕТИЧНІ ВІДОМОСТІ
* **HTML (HyperText Markup Language)** — це стандартизована мова розмітки документів у Всесвітній павутині. Вона керує структурою веб-сторінки за допомогою тегів. Сучасний стандарт HTML5 вводить семантичні теги (`<header>`, `<main>`, `<nav>`, `<section>`), які допомагають браузерам та пошуковим системам краще інтерпретувати логіку інтерфейсу.
* **CSS (Cascading Style Sheets)** — мова стилів, що відповідає за зовнішній вигляд документа. Вона відокремлює структуру (HTML) від дизайну. Використання сучасних властивостей Flexbox та CSS Grid дозволяє будувати адаптивні інтерфейси, а псевдокласи (наприклад, `:hover`) забезпечують інтерактивний відгук на дії користувача.
* **Гіпермедіа** — це розширення поняття гіпертексту, яке включає графіку, аудіо, відео та інтерактивні елементи. Вбудовування сторонніх сервісів (як-от інтерактивні карти) реалізується за допомогою тегу `<iframe>`.

---

## 4. ХІД РОБОТИ ТА ОПИС РЕАЛІЗАЦІЇ
У ході виконання роботи було спроектовано та закодовано веб-сайт «Iron Force». Структура проєкту складається з трьох HTML-сторінок та загального файлу стилів `style.css`. Для візуального оформлення обрано сучасну темну палітру кольорів на основі градієнту (`#0f172a` -> `#1e293b`) та акцентного помаранчевого кольору (`#ff4500`).

1. **Головна сторінка (`index.html`):** Містить секцію привітання (Hero), інформаційні картки про напрямки тренувань, правила клубу та інтерактивну фотогалерею залу (`.photo-grid`), яка реалізована за допомогою Grid Layout.
2. **Сторінка послуг (`services.html`):** Презентує прайс-лист у вигляді таблиці `<table>`. Реалізовано виділення популярного тарифу за допомогою спеціального CSS-класу `.highlight-row` та маркований список переваг залу.
3. **Сторінка контактів (`contact.html`):** Містить форму запису на тренування з текстовими та числовими полями введення (`input`, `textarea`) з атрибутом `required` для базової валідації, а також інтегровану карту через `<iframe>`.

---

## 5. ЛІСТИНГ КОДУ ТА РЕЗУЛЬТАТИ ВІДОБРАЖЕННЯ
```

---

```markdown
### 5.1 Код сторінки `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iron Force — Головна</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="logo">IRON FORCE</div>
        <nav>
            <ul class="main-nav">
                <li><a href="index.html">Головна</a></li>
                <li class="dropdown">
                    <a href="services.html">Послуги ▾</a>
                    <ul class="dropdown-content">
                        <li><a href="services.html#prices">Абонементи</a></li>
                        <li><a href="services.html#benefits">Що є у залі</a></li>
                        <li><a href="index.html#rules">Правила залу</a></li>
                    </ul>
                </li>
                <li><a href="contact.html">Контакти</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero-section">
            <h1>Ласкаво просимо в <span class="accent">Iron Force</span></h1>
            <p class="hero-subtitle">Ми допоможемо вам досягти мети</p>
        </section>
        <section class="card" id="training">
            <h2>Напрямки тренувань</h2>
            <div class="training-grid">
                <div class="training-item">
                    <h3>💪 Силовий тренінг</h3>
                    <p>Зона вільних ваг, професійні тренажери Hammer Strength.</p>
                </div>
                <div class="training-item">
                    <h3>🏃‍♂️ Кардіо зона</h3>
                    <p>Сучасні бігові доріжки, орбітреки та велотренажери Matrix.</p>
                </div>
                <div class="training-item">
                    <h3>🥊 Кросфіт</h3>
                    <p>Спеціалізована зона для функціонального тренінгу та витривалості.</p>
                </div>
            </div>
        </section>
        <section class="card" id="gallery">
            <h2>Наш зал у деталях</h2>
            <div class="photo-grid">
                <img src="1.jpg" alt="Зал 1" class="gallery-img">
                <img src="2.jpg" alt="Зал 2" class="gallery-img">
                <img src="3.jpg" alt="Зал 3" class="gallery-img">
                <img src="4.jpg" alt="Зал 4" class="gallery-img">
                <img src="5.jpg" alt="Зал 5" class="gallery-img">
                <img src="6.jpg" alt="Зал 6" class="gallery-img">
            </div>
        </section>
        <section class="card" id="rules">
            <h2>Правила клубу</h2>
            <div class="rules-grid">
                <div class="rule-item"><h3>👟 Взуття</h3><p>Тільки чисте змінне взуття.</p></div>
                <div class="rule-item"><h3>🧼 Гігієна</h3><p>Використовуйте рушник на тренажерах.</p></div>
                <div class="rule-item"><h3>⚖️ Інвентар</h3><p>Повертайте ваги на місце.</p></div>
                <div class="rule-item"><h3>⏳ Час</h3><p>Не займайте тренажер довше 15 хв.</p></div>
            </div>
        </section>
    </main>
</body>
</html>
```

#### Результат відображення сторінки `index.html`:
<img width="1035" height="855" alt="Снимок экрана 2026-06-16 135414" src="https://github.com/user-attachments/assets/ed8c1c5f-296e-4d71-a4b3-2572461fb68c" />

---

### 5.2 Код сторінки `services.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Послуги — Iron Force</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="logo">IRON FORCE</div>
        <nav>
            <ul class="main-nav">
                <li><a href="index.html">Головна</a></li>
                <li class="dropdown">
                    <a href="services.html">Послуги ▾</a>
                    <ul class="dropdown-content">
                        <li><a href="#prices">Абонементи</a></li>
                        <li><a href="#benefits">Що є у залі</a></li>
                        <li><a href="index.html#rules">Rules клубу</a></li>
                    </ul>
                </li>
                <li><a href="contact.html">Контакти</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero-section">
            <h1>Наші <span class="accent">Послуги та ціни</span></h1>
        </section>
        <section class="card" id="prices">
            <h2>Абонементи</h2>
            <div class="table-container">
                <table class="services-table">
                    <thead>
                        <tr>
                            <th>Тип</th>
                            <th>Час</th>
                            <th>Ціна</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Rank "Light"</td>
                            <td>07:00 — 15:00</td>
                            <td>800 грн</td>
                        </tr>
                        <tr>
                            <td>Rank "Standard"</td>
                            <td>07:00 — 23:00</td>
                            <td>1200 грн</td>
                        </tr>
                        <tr class="highlight-row">
                            <td>Rank "PRO" <span class="tag-popular">(популярне)</span></td>
                            <td>24/7 Безліміт</td>
                            <td>2000 грн</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>
        <section class="card" id="benefits">
            <h2>Що ви отримуєте</h2>
            <ul class="main-list">
                <li>
                    <span class="list-title">Matrix & Hammer Strength</span>
                    <span class="list-text">Найкраще професійне обладнання для ваших результатів.</span>
                </li>
                <li>
                    <span class="list-title">Фінська сауна</span>
                    <span class="list-text">Відновлення м'язів після важкого тренування.</span>
                </li>
                <li>
                    <span class="list-title">Персональний підхід</span>
                    <span class="list-text">Вступне тренування з тренером у подарунок.</span>
                </li>
            </ul>
        </section>
    </main>
</body>
</html>
```

#### Результат відображення сторінки `services.html`:
<img width="1013" height="863" alt="Снимок экрана 2026-06-16 135606" src="https://github.com/user-attachments/assets/a82f663d-0f0f-439a-8923-654102c250b3" />

---

### 5.3 Код сторінки `contact.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Контакти — Iron Force</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="logo">IRON FORCE</div>
        <nav>
            <ul class="main-nav">
                <li><a href="index.html">Головна</a></li>
                <li class="dropdown">
                    <a href="services.html">Послуги ▾</a>
                    <ul class="dropdown-content">
                        <li><a href="services.html#prices">Абонементи</a></li>
                        <li><a href="services.html#benefits">Що є у залі</a></li>
                        <li><a href="index.html#rules">Правила залу</a></li>
                    </ul>
                </li>
                <li><a href="contact.html">Контакти</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero-section">
            <h1>Зворотній <span class="accent">Зв'язок</span></h1>
        </section>
        <div class="contact-container">
            <section class="card contact-form-card">
                <h2>Записатись на тренування</h2>
                <form>
                    <input type="text" placeholder="Ваше ім'я" required>
                    <input type="email" placeholder="Email" required>
                    <input type="tel" placeholder="Номер телефону" required>
                    <textarea placeholder="Ваше повідомлення" rows="4"></textarea>
                    <button type="submit" class="btn">Відправити</button>
                </form>
            </section>
            <section class="card contact-map-card">
                <h2>Ми на карті</h2>
                <div class="map-wrapper">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2564.299317544062!2d36.22530187693539!3d50.01230191839556!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4127a1243b925b41%3A0x77fa747df34a2e26!2z0KXQndCj0KD!5e0!3m2!1suk!2sua!4v1700000000000!5m2!1suk!2sua" width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                </div>
            </section>
        </div>
    </main>
</body>
</html>
```

#### Результат відображення сторінки `contact.html`:
<img width="1014" height="871" alt="Снимок экрана 2026-06-16 135735" src="https://github.com/user-attachments/assets/bd094c8c-6fe9-4814-9716-6df44259e1a9" />

---

### 5.4 Код каскадної таблиці стилів `style.css`
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap');
* { margin: 0; padding: 0; box-sizing: border-box; }
html { height: 100%; scroll-behavior: smooth; }
body {
    font-family: 'Montserrat', sans-serif;
    background: linear-gradient(180deg, #0f172a 0%, #1e293b 100%);
    background-attachment: fixed;
    color: #f1f5f9;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    -webkit-font-smoothing: antialiased;
}
header {
    background: rgba(15, 23, 42, 0.9);
    backdrop-filter: blur(10px);
    padding: 20px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 1px solid #334155;
}
.logo { font-size: 1.5rem; font-weight: 900; letter-spacing: 2px; color: #fff; }
.main-nav { display: flex; list-style: none; gap: 30px; }
.main-nav a { color: #cbd5e1; text-decoration: none; font-weight: 700; font-size: 0.95rem; transition: color 0.3s; }
.main-nav a:hover { color: #ff4500; }
.dropdown { position: relative; }
.dropdown-content {
    display: none; position: absolute; top: 100%; left: 0; background: #1e293b;
    border: 1px solid #334155; list-style: none; border-radius: 8px; padding: 10px 0;
    min-width: 180px; box-shadow: 0 10px 15px -3px rgba(0,0,0,0.5);
}
.dropdown-content a { display: block; padding: 10px 20px; font-weight: 400; }
.dropdown-content a:hover { background: #334155; }
.dropdown:hover .dropdown-content { display: block; }
main { flex: 1; max-width: 1200px; width: 100%; margin: 0 auto; padding: 40px 20px; }
.hero-section { text-align: center; margin-bottom: 60px; padding: 40px 0; }
.hero-section h1 { font-size: 3rem; font-weight: 900; margin-bottom: 15px; }
.accent { color: #ff4500; }
.hero-subtitle { color: #94a3b8; font-size: 1.2rem; }
.card { background: #1e293b; border: 1px solid #334155; border-radius: 16px; padding: 40px; margin-bottom: 40px; }
.card h2 { font-size: 1.8rem; margin-bottom: 30px; border-left: 4px solid #ff4500; padding-left: 15px; }
.training-grid, .rules-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 25px; }
.training-item, .rule-item { background: #0f172a; border: 1px solid #334155; padding: 25px; border-radius: 12px; }
.training-item h3, .rule-item h3 { margin-bottom: 12px; color: #fff; }
.training-item p, .rule-item p { color: #94a3b8; font-size: 0.95rem; line-height: 1.5; }
.photo-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
.gallery-img { width: 100%; height: 200px; object-fit: cover; border-radius: 8px; transition: transform 0.3s; }
.gallery-img:hover { transform: scale(1.03); }
.table-container { overflow-x: auto; }
.services-table { width: 100%; border-collapse: collapse; background: #0f172a; border-radius: 8px; overflow: hidden; }
.services-table th, .services-table td { padding: 16px 20px; text-align: left; }
.services-table th { background: #334155; color: #fff; font-weight: 700; }
.services-table td { border-bottom: 1px solid #334155; color: #cbd5e1; }
.highlight-row { background: rgba(255, 69, 0, 0.1); }
.highlight-row td { color: #fff; font-weight: 700; }
.tag-popular { color: #ff4500; font-size: 0.8rem; margin-left: 10px; }
.main-list { list-style: none; }
.main-list li { background: #0f172a; border: 1px solid #334155; padding: 20px; border-radius: 8px; margin-bottom: 15px; }
.list-title { color: #fff; font-weight: 700; display: block; margin-bottom: 5px; }
.list-text { color: #94a3b8; font-size: 0.9rem; }
.contact-container { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; }
@media (max-width: 800px) { .contact-container { grid-template-columns: 1fr; } }
input, textarea { width: 100%; padding: 14px; margin-bottom: 15px; background: #0f172a; border: 1px solid #334155; color: #fff; border-radius: 8px; font-family: inherit; }
input:focus, textarea:focus { outline: none; border-color: #ff4500; }
.btn { background: #ff4500; color: #fff; padding: 14px 28px; border: none; border-radius: 8px; font-weight: 700; cursor: pointer; transition: background 0.3s; }
.btn:hover { background: #e03e00; }
.map-wrapper { border-radius: 8px; overflo
```

---

## 6. ВИСНОВКИ

Під час виконання лабораторної роботи №1 з навчальної дисципліни **«Гіпертекст та гіпермедіа»** було всебічно опановано теоретичні засади та отримано стійкі практичні навички проектування й кодування багатосторінкових веб-ресурсів засобами мови розмітки HTML5 та каскадних таблиць стилів CSS3.

На прикладі побудованого інформаційного веб-сайту мережі фітнес-центрів **«Iron Force»** успішно розв'язано такі завдання:

* **Реалізовано семантичну структуру документа** відповідно до сучасних стандартів консорціуму W3C за допомогою тегів `<header>`, `<main>`, `<nav>`, `<section>`. Це забезпечує коректну логіку та високий уровень семантичної чистоти коду, що позитивно впливає на SEO-оптимізацію та доступність веб-документа.
* **Організовано взаємопов'язану систему навігації** на основі відносних гіперпосилань між трьома автономними веб-сторінками (`index.html`, `services.html`, `contact.html`). Розроблено багаторівневе меню з випадаючим списком підрозділів (`.dropdown`) та інтегровано внутрішньонавігаційні якірні посилання для швидкого переходу користувача до логічних блоків сторінок (ціни, правила залу, переваги).
* **Структуровано табличні та спискові дані.** Прайс-лист абонементів подано у вигляді інтерактивної кросбраузерної таблиці `<table>`, де завдяки CSS-селекторам та псевдокласам виділено пріоритетні тарифи. Списки переваг та особливостей залу зорганізовано за допомогою маркованих списков `<ul>`.
* **Створено форму зворотного зв'язку** із застосуванням різнотипних елементів введення (`input[type="text"]`, `input[type="email"]`, `input[type="tel"]`, `textarea`). Інтеграція атрибуту `required` дозволила забезпечити базову валідацію клієнтських даних на рівні браузера без залучення сторонніх скриптів.
* **Інтегровано об'єкти гіпермедіа.** За допомогою фрейму `<iframe>` у структуру сторінки контактів вбудовано сторонній інтерактивний сервіс (картографічний модуль Google Maps), що значно покращує користувацький досвід (UX).

> **Загальний підсумок:** Завдяки відокремленню контенту від стильового представлення у зовнішній CSS-файл `style.css` було досягнуто високої гнучкості та перевикористованості коду. Застосування сучасних інструментів верстки, як-от Flexbox та CSS Grid Layout, дозволило побудувати адаптивну сітку карток тренувань та галереї зображень (`.photo-grid`), яка гнучко підлаштовується під роздільну здатність екранів користувачів. Використання псевдокласів (`:hover`, `:focus`) та плавної поведінки прокрутки (`scroll-behavior: smooth`) забезпечило сучасний та інтерактивний відгук інтерфейсу.

Поставлені завдання виконано в повному обсязі, а отримані практичні навички створюють необхідне підґрунтя для подальшого вивчення складніших систем гіпермедіа та адаптивних веб-фреймворків.
