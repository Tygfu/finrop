<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Finrop</title>
  <script src="https://www.google.com/recaptcha/api.js" async defer></script>
  <style>
    :root {
      --bg-color: #1e1e1e;
      --text-color: #26bbc8;
      --header-color: #2c2c2c;
    }

    body.light-theme {
      --bg-color: #f0f0f0;
      --text-color: #1d82c0;
      --header-color: #ffffff;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: sans-serif;
      background-color: var(--bg-color);
      color: var(--text-color);
      transition: background-color 0.3s, color 0.3s;
      scroll-behavior: smooth;
    }

    html {
      scroll-behavior: smooth;
    }
    #privacy {
      scroll-margin-top: 80px; /* скоригуйте під висоту вашого header */
    }

    header {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      background-color: var(--header-color);
      padding: 10px 20px;
    }

    .logo-container {
      display: flex;
      align-items: center;
    }

    header img {
      height: 50px;
      margin-right: 10px;
    }

    header h1 {
      margin: 0;
      font-size: 24px;
    }

    nav {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 10px;
    }

    nav a {
      color: var(--text-color);
      text-decoration: none;
      font-weight: bold;
    }

    nav a:hover {
      text-decoration: underline;
    }

    .theme-toggle,
    .lang-toggle {
      padding: 5px 10px;
      background-color: transparent;
      color: var(--text-color);
      border: 1px solid var(--text-color);
      border-radius: 5px;
      cursor: pointer;
    }

    main {
      padding: 20px;
    }

    section {
      margin-bottom: 40px;
    }

    footer {
      padding: 10px;
      text-align: center;
      background-color: var(--header-color);
    }

    form {
      margin-top: 20px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      max-width: 400px;
    }

    label {
      font-weight: bold;
    }

    input, textarea {
      padding: 8px;
      border-radius: 5px;
      border: 1px solid #aaa;
      font-size: 16px;
    }

    button[type="submit"] {
      background-color: var(--text-color);
      color: var(--bg-color);
      padding: 10px;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }

    button[type="submit"]:hover {
      opacity: 0.9;
    }

    @media (max-width: 600px) {
      nav {
        flex-direction: column;
        align-items: flex-start;
      }
      header h1 {
        font-size: 20px;
      }
      form {
        width: 100%;
      }
    }
  </style>
</head>
<body>

<header>
  <div class="logo-container">
    <img src="https://iili.io/FHqMkx9.png" alt="Finrop logo">
    <h1>Finrop</h1>
  </div>
  <nav>
    <a href="#about" id="nav-about">Про нас</a>
    <a href="#services" id="nav-services">Послуги</a>
    <a href="#privacy" id="nav-privacy">Політика</a>
    <button class="theme-toggle" onclick="toggleTheme()">☀︎</button>
    <button class="lang-toggle" onclick="toggleLang()">🌐</button>
  </nav>
</header>

<main>
  <section id="about">
    <h2 id="about-title">Про нас</h2>
    <p id="about-text">
      Finrop — молода команда, яка вже сьогодні перетворює довіру на прибуток. Ви інвестуєте — ми працюємо з валютними та фондовими ринками, використовуючи досвідчений підхід до аналізу можливостей.
    </p>
  </section>

  <section id="services">
    <h2 id="services-title">Послуги</h2>
    <ul id="services-list">
      <li>Керування інвестиціями на глобальних ринках</li>
      <li>Фінансова аналітика та консультації</li>
      <li>Індивідуальні інвестиційні плани</li>
    </ul>

    <h3 id="form-title">Залишити заявку</h3>
    <form onsubmit="return validateForm(event)">
      <label for="name" id="label-name">Як вас звати?</label>
      <input type="text" id="name" name="name" required>

      <label for="age" id="label-age">Скільки вам років?</label>
      <input type="number" id="age" name="age" min="18" required>

      <label for="amount" id="label-amount">Скільки ви плануєте вкласти (у $)?</label>
      <input type="number" id="amount" name="amount" min="20" required>

      <label for="contact" id="label-contact">Ваш Telegram або номер телефону:</label>
      <input type="text" id="contact" name="contact" required>

      <label id="label-privacy">
        <input type="checkbox" required>
        Я погоджуюсь з <a href="#privacy">Політикою конфіденційності</a>
      </label>

      <div class="g-recaptcha" data-sitekey="6LcMZ1UrAAAAAFMFSWFuTnItSiaIMejig3LCkGtP"></div>

      <button type="submit" id="submit-button">Надіслати заявку</button>
    </form>
  </section>

  <section id="privacy">
    <h2 data-uk="Політика конфіденційності" data-en="Privacy Policy" id="privacy-title">Політика конфіденційності</h2>
    <p id="privacy-text" data-uk="Ця Політика конфіденційності описує, як Finrop збирає, використовує, зберігає та захищає персональні дані користувачів." data-en="This Privacy Policy describes how Finrop collects, uses, stores, and protects users' personal data.">
      Ця Політика конфіденційності описує, як Finrop збирає, використовує, зберігає та захищає персональні дані користувачів.
    </p>
    <h3 data-uk="1. Збір персональної інформації" data-en="1. Collection of Personal Information">1. Збір персональної інформації</h3>
    <p data-uk="Ми збираємо лише ту інформацію, яку ви добровільно надаєте через форму заявки: ваше ім’я, вік, планована сума інвестиції, контакт для зв’язку." data-en="We collect only the information you voluntarily provide through the application form: your name, age, planned investment amount, and contact details.">
      Ми збираємо лише ту інформацію, яку ви добровільно надаєте через форму заявки: ваше ім’я, вік, планована сума інвестиції, контакт для зв’язку.
    </p>
    <h3 data-uk="2. Мета обробки даних" data-en="2. Purpose of Data Processing">2. Мета обробки даних</h3>
    <p data-uk="Зібрана інформація використовується виключно для:" data-en="Collected information is used solely for:">Зібрана інформація використовується виключно для:</p>
    <ul>
      <li data-uk="обробки вашої заявки;" data-en="processing your application;">обробки вашої заявки;</li>
      <li data-uk="надання зворотного зв’язку;" data-en="providing feedback;">надання зворотного зв’язку;</li>
      <li data-uk="встановлення контакту для подальшої комунікації." data-en="establishing contact for further communication.">встановлення контакту для подальшої комунікації.</li>
    </ul>
    <h3 data-uk="3. Зберігання та захист даних" data-en="3. Data Storage and Protection">3. Зберігання та захист даних</h3>
    <p data-uk="Уся інформація зберігається з дотриманням норм безпеки. Доступ до ваших даних мають лише уповноважені особи Finrop." data-en="All information is stored securely. Only authorized Finrop personnel have access to your data.">
      Уся інформація зберігається з дотриманням норм безпеки. Доступ до ваших даних мають лише уповноважені особи Finrop.
    </p>
    <h3 data-uk="4. Передача третім особам" data-en="4. Sharing with Third Parties">4. Передача третім особам</h3>
    <p data-uk="Ми не передаємо ваші персональні дані третім особам без вашої окремої згоди, за винятком випадків, передбачених законом." data-en="We do not share your personal data with third parties without your explicit consent, except as required by law.">
      Ми не передаємо ваші персональні дані третім особам без вашої окремої згоди, за винятком випадків, передбачених законом.
    </p>
    <h3 data-uk="5. Ваші права" data-en="5. Your Rights">5. Ваші права</h3>
    <p data-uk="Ви маєте право:" data-en="You have the right to:">Ви маєте право:</p>
    <ul>
      <li data-uk="запитати копію ваших персональних даних;" data-en="request a copy of your personal data;">запитати копію ваших персональних даних;</li>
      <li data-uk="вимагати виправлення або видалення інформації;" data-en="request correction or deletion of your data;">вимагати виправлення або видалення інформації;</li>
      <li data-uk="відкликати згоду на обробку персональних даних у будь-який момент." data-en="withdraw your consent to data processing at any time.">відкликати згоду на обробку персональних даних у будь-який момент.</li>
    </ul>
    <p data-uk="Для цього зверніться до нашої адміністрації через контактні дані, вказані на сайті." data-en="To do so, contact our administration via the contact details provided on the site.">
      Для цього зверніться до нашої адміністрації через контактні дані, вказані на сайті.
    </p>
    <h3 data-uk="6. Використання reCAPTCHA" data-en="6. Use of reCAPTCHA">6. Використання reCAPTCHA</h3>
    <p data-uk="На сайті використовується Google reCAPTCHA для захисту від спаму. Ваші дії можуть бути проаналізовані сервісами Google відповідно до їхньої" data-en="Google reCAPTCHA is used on the site to protect against spam. Your activities may be analyzed by Google services according to their">
      На сайті використовується Google reCAPTCHA для захисту від спаму. Ваші дії можуть бути проаналізовані сервісами Google відповідно до їхньої
      <a href="https://policies.google.com/privacy" target="_blank">Політикою конфіденційності</a> та
      <a href="https://policies.google.com/terms" target="_blank">Умовами використання</a>.
    </p>
    <h3 data-uk="7. Зміни до політики" data-en="7. Changes to the Policy">7. Зміни до політики</h3>
    <p data-uk="Ми залишаємо за собою право змінювати цю політику в будь-який момент. Актуальна версія завжди буде доступна на цьому сайті." data-en="We reserve the right to change this policy at any time. The current version will always be available on this site.">
      Ми залишаємо за собою право змінювати цю політику в будь-який момент. Актуальна версія завжди буде доступна на цьому сайті.
    </p>
    <p data-uk="<strong>Дата оновлення:</strong> 1 червня 2025 року" data-en="<strong>Last updated:</strong> June 1, 2025"><strong>Дата оновлення:</strong> 1 червня 2025 року</p>
  </section>
</main>

<footer>
  <p>© 2025 Finrop</p>
</footer>

<script>
  let currentLang = 'uk';

  const translations = {
    uk: {
      nav: ["Про нас", "Послуги", "Політика"],
      aboutTitle: "Про нас",
      aboutText: "Finrop — молода команда, яка вже сьогодні перетворює довіру на прибуток...",
      servicesTitle: "Послуги",
      servicesList: [
        "Керування інвестиціями на глобальних ринках",
        "Фінансова аналітика та консультації",
        "Індивідуальні інвестиційні плани"
      ],
      formTitle: "Залишити заявку",
      form: {
        name: "Як вас звати?",
        age: "Скільки вам років?",
        amount: "Скільки ви плануєте вкласти (у $)?",
        contact: "Ваш Telegram або номер телефону:",
        privacy: 'Я погоджуюсь з <a href="#privacy">Політикою конфіденційності</a>',
        <div class="g-recaptcha" data-sitekey="6LcMZ1UrAAAAAFMFSWuTnItSialMejjg3LCkGtP"></div>
        button: "Надіслати заявку"
      },
      privacyTitle: "Політика конфіденційності",
      privacyText: "Ми поважаємо вашу конфіденційність...",
    },
    en: {
      nav: ["About", "Services", "Policy"],
      aboutTitle: "About Us",
      aboutText: "Finrop is a young team that is already turning trust into profit...",
      servicesTitle: "Services",
      servicesList: [
        "Investment management on global markets",
        "Financial analytics and consulting",
        "Individual investment plans"
      ],
      formTitle: "Submit a Request",
      form: {
        name: "What's your name?",
        age: "How old are you?",
        amount: "How much do you plan to invest (in $)?",
        contact: "Your Telegram or phone number:",
        privacy: 'I agree with the <a href="#privacy">Privacy Policy</a>',
          <div class="g-recaptcha" data-sitekey="6LcMZ1UrAAAAAFMFSWuTnItSialMejjg3LCkGtP"></div>
        button: "Submit"
      },
      privacyTitle: "Privacy Policy",
      privacyText: "Your privacy is important to us...",
    }
  };

  function toggleTheme() {
    document.body.classList.toggle('light-theme');
  }

  function toggleLang() {
    currentLang = currentLang === 'uk' ? 'en' : 'uk';
    const t = translations[currentLang];

    document.getElementById('nav-about').textContent = t.nav[0];
    document.getElementById('nav-services').textContent = t.nav[1];
    document.getElementById('nav-privacy').textContent = t.nav[2];

    document.getElementById('about-title').textContent = t.aboutTitle;
    document.getElementById('about-text').textContent = t.aboutText;

    document.getElementById('services-title').textContent = t.servicesTitle;
    document.getElementById('services-list').innerHTML = t.servicesList.map(item => `<li>${item}</li>`).join('');

    document.getElementById('form-title').textContent = t.formTitle;
    document.getElementById('label-name').textContent = t.form.name;
    document.getElementById('label-age').textContent = t.form.age;
    document.getElementById('label-amount').textContent = t.form.amount;
    document.getElementById('label-contact').textContent = t.form.contact;
    document.getElementById('label-privacy').innerHTML = `<input type="checkbox" required> ${t.form.privacy}`;
    document.getElementById('submit-button').textContent = t.form.button;

    document.getElementById('privacy-title').textContent = t.privacyTitle;
    document.getElementById('privacy-text').textContent = t.privacyText;

    document.documentElement.lang = currentLang;
  }

  function validateForm(event) {
    event.preventDefault();

    const age = parseInt(document.getElementById('age').value, 10);
    const amount = parseFloat(document.getElementById('amount').value);
    const name = document.getElementById("name").value.trim();

    if (age < 18) {
      alert(currentLang === 'uk' ? 'Мінімальний вік — 18 років.' : 'Minimum age is 18 years.');
      return false;
    }
    if (amount < 20) {
      alert(currentLang === 'uk' ? 'Мінімальна сума — 20 доларів.' : 'Minimum amount is $20.');
      return false;
    }

    const message = `📝 Нова заявка:\n👤 Ім'я: ${name}\n📅 Вік: ${age}\n💵 Сума: $${amount}\n📞 Контакт: ${contact}`;

    fetch(`https://api.telegram.org/bot7829423068:AAE4PrTCGQPlTgm24mrfAripeoIfyn5YSqM/sendMessage`, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({
        chat_id: -4978937001,
        text: message,
        parse_mode: "HTML"
      })
    })
    .then(response => {
      if (response.ok) {
        alert(currentLang === 'uk' ? 'Заявка успішно надіслана!' : 'Request submitted successfully!');
        document.querySelector("form").reset();
        grecaptcha.reset();
      } else {
        alert("Помилка надсилання заявки.");
      }
    })
    .catch(error => {
      console.error("Помилка:", error);
      alert("Не вдалося надіслати заявку.");
    });

    return false;
  }
</script>

</body>
</html>
