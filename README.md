<html lang="km">
<head>
<meta charset="UTF-8" />
<title>សេវាកម្មម៉ាស្សា និង ក្លៀក សម្បត្តិធូរព្យាបាលមុខ</title>
<style>
  body {
    margin: 0; padding: 0;
    font-family: 'Khmer OS System', Arial, sans-serif;
    background-image: url('"C:\Users\93 Computer\Downloads\dR Testing\photo_2026-01-09_21-49-10.jpg"');
    background-size: cover;
    background-position: center;
    color: white;
    min-height: 100vh;
    position: relative;
  }
  body::before {
    content: "";
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    background-color: rgba(0,0,0,0.5);
    z-index: -1;
  }
  h1 { font-size: 36px; margin-top: 40px; font-family: 'Battambang', serif; text-align: center;}
  .service {
    background: rgba(0,0,0,0.7);
    margin: 15px 0;
    padding: 20px;
    border-radius: 10px;
    width: 320px;
    text-align: left; /* រៀបខាងឆ្វេង */
    margin-left: 20px; /* ចន្លោះខាងឆ្វេង */
    font-size: 18px; /* អក្សរតូចជាង */
  }
  .service h2 { font-size: 20px; margin-bottom: 10px; font-family: 'Battambang', serif;}
  button.selectBtn {
    background-color: #2ecc71; color: white;
    border: none; padding: 8px 16px;
    font-size: 16px; border-radius: 6px;
    cursor: pointer; font-family: 'Khmer OS System', Arial, sans-serif;
  }
  button.selectBtn:hover { background-color: #27ae60; }
  #backButton {
    display: none;
    position: fixed; top: 20px; left: 20px;
    font-size: 28px; font-weight: bold;
    background: rgba(46, 204, 113, 0.9); color: white;
    border: none; padding: 12px 24px; border-radius: 8px;
    cursor: pointer; z-index: 1000;
  }
  #serviceDetails {
    display: none;
    position: fixed; top: 100px; left: 20px;
    background: rgba(0,0,0,0.85); padding: 20px;
    border-radius: 12px; max-width: 450px;
    font-size: 18px; font-weight: bold; color: #fff;
    line-height: 1.8; text-align: left; z-index: 999;
    font-family: 'Battambang', serif;
  }
  #serviceDetails ol { padding-left: 20px; margin: 0; }
</style>
</head>
<body>

<h1>សេវាកម្មម៉ាស្សា និង ក្លៀក សម្បត្តិធូរព្យាបាលមុខ</h1>

<!-- ម៉ាស្សា -->
<div id="massageService">
  <div class="service" data-details="detox">
    <h2>ម៉ាស្សាមុខ 10$</h2>
    <button class="selectBtn">ជ្រើសរើស</button>
  </div>
  <div class="service" data-details="cleanFace">
    <h2>ម៉ាស្សាមុខ 15$</h2>
    <button class="selectBtn">ជ្រើសរើស</button>
  </div>
</div>

<div id="massageService2">
  <div class="service" data-details="cleanFaceExtra">
    <h2>ម៉ាស្សាមុខ 20$</h2>
    <button class="selectBtn">ជ្រើសរើស</button>
  </div>
</div>

<!-- ក្លៀក -->
<div id="bleachService">
  <div class="service" data-details="bleachStandard">
    <h2>សេវាកម្មក្លៀក ស+ម៉ត 15$</h2>
    <button class="selectBtn">ជ្រើសរើស</button>
  </div>
  <div class="service" data-details="bleachBaby">
    <h2>សេវាកម្មក្លៀក Baby 25$</h2>
    <button class="selectBtn">ជ្រើសរើស</button>
  </div>
</div>

<button id="backButton">ថយក្រោយ</button>

<div id="serviceDetails">
  <ol id="detailsList"></ol>
</div>

<script>
const divs = Array.from(document.querySelectorAll('.service'));
const backBtn = document.getElementById('backButton');
const detailsDiv = document.getElementById('serviceDetails');
const detailsList = document.getElementById('detailsList');

const detailsData = {
  detox: [
    "Detox ជាតិពុល ២មុខ",
    "ម៉ាសបិតជាតិពុល ស្តាប់ជាមួយម៉ាស៊ីន",
    "ស្នំមុន ញឹមមុន បូមមុន",
    "ម៉ាស្សាមុខvip 6មុខ",
    "បញ្ចូលសារ៉ាយសមុទ្រ +វិតាមីន",
    "បិទម៉ាសស៊ីម៉ង អាំងម៉ាស៊ីនLED",
    "បញ្ចូលវិតាមីន oxygen +ផងឌីម៉ា",
    "អ៊ុតបញ្ចូលវិតាមីន ម៉ាស៊ីនក្តៅ",
    "បំបាត់ភ្នែកខ្មៅ ស្លក់ ដក់ ខ្លាញ់ ភ្នែកប៉ោង",
    "សេវាកម្មលើកបន្តឹងទំរង់មុខ «កិបមុខ បំបាត់បើកចង្ការ»",
    "ស្ទឹមសែកសុកចៀម អ៊ុតត្រជាក់"
  ],
  cleanFace: [
    "សំអាតមុខដោយទឹកវិតាមីន",
    "ដែលDetoxកោសិកាចាស់ចាស់",
    "ជូតទឹកផ្តាច់ជាតិពុល",
    "បិទម៉ាសបឺតជាតិពុល & ស្ដាប់ម៉ាស៊ីន",
    "ស្អំបើកកោសិកាមុន +បូមមុខច្រមុះ+ញិចសំអាតមុខ",
    "ឈុតគ្លីនិចម៉ាស្សា៦មុខ",
    "បញ្ចូលសារ៉ាយសមុទ្រ +វិតាមីន",
    "បិទម៉ាសស៊ីម៉ងគ្លីនិច+អាំងLED",
    "លាបគ្រីមសំនើម",
    "លាបលេការពារកំដៅថ្ងៃ"
  ],
  cleanFaceExtra: [
    "សំអាតមុខដោយទឹកសំអាតវិតាមីន",
    "Detoxជាតិពុល 2មុខ",
    "បិទម៉ាសបឺតជាតិពុល &ស្រាប់ម៉ាស៊ីនស្ដាប់មុខ",
    "ស្អំបើកកោសិកាមុន +បូមមុនច្រមុះ +ញិចមុន",
    "ម៉ាស្សាផ្តល់សំនើមជាមួយឈុតម៉ាស្សាស្តង់ដារគ្លីនិច6មុខ",
    "បិទម៉ាសសន្លឹកផ្តល់សំនើម 10នាទី",
    "លាបគ្រីមសំនើម",
    "លាបលេការពារកំដៅថ្ងៃ"
  ],
  bleachStandard: [
    "សំអាតក្លៀក",
    "បករោមក្លៀកដោយកាវត្រជាក់",
    "សំអាតរោមក្លៀក ដករំលីងរោមក្លៀក",
    "ជូតសំលីវិតាមីនផ្ចិតរុន្ធរោម",
    "បញ្ចូលវិតាមីន+សារ៉ាយសមុទ្រ",
    "បិទម៉ាសស៊ីម៉ង",
    "អ៊ុតត្រជាក់ផ្ចិតរន្ធរោម"
  ],
  bleachBaby: [
    "សំអាតក្លៀក",
    "សារ៉ាយសមុទ្រ+វិតាមីន",
    "បករោមក្លៀកដោយកាវត្រជាក់",
    "បិទម៉ាសស៊ីម៉ង",
    "សំអាតដករំលីងរោមក្លៀក",
    "ប៊ិច BaBy glow + Dr. Pen",
    "ស្ប៉ាស្តាប់ក្លៀក Facial TREATM",
    "សម្បត្តិ អ៊ុតត្រជាក់ ផ្ចិតរុន្ធរោម"
  ]
};

divs.forEach(btnDiv => {
  const btn = btnDiv.querySelector('.selectBtn');
  btn.addEventListener('click', () => {
    // លាក់ div ទាំងអស់
    divs.forEach(d => d.style.display = 'none');

    // បង្ហាញ details
    const key = btnDiv.dataset.details;
    detailsList.innerHTML = detailsData[key].map((item, idx) => `<li>${item}</li>`).join('');
    detailsDiv.style.display = 'block';

    // បង្ហាញ back button
    backBtn.style.display = 'block';
  });
});

backBtn.addEventListener('click', () => {
  // បង្ហាញ div ទាំងអស់វិញ
  divs.forEach(d => d.style.display = 'block');
  detailsDiv.style.display = 'none';
  backBtn.style.display = 'none';
});
</script>
</body>
</html>
