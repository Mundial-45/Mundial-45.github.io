# Mundial-45.github.io
<!DOCTYPE html>
<html lang="ar" dir="rtl" class="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>المسبحة - Misbaha</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = { darkMode: 'class' };
  </script>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Tajawal', 'Inter', sans-serif; }
    .custom-text-size { font-size: var(--app-font-size, 1.125rem); }
  </style>
</head>
<body class="bg-slate-50 dark:bg-slate-900 text-slate-800 dark:text-slate-100 min-h-screen flex flex-col justify-between transition-colors duration-300">

  <!-- Header -->
  <header class="bg-emerald-700 dark:bg-emerald-900 text-white py-4 shadow-lg sticky top-0 z-50">
    <div class="container mx-auto px-4 flex items-center justify-between">
      <div>
        <h1 class="text-xl md:text-2xl font-extrabold tracking-wide cursor-pointer" id="headerTitle" onclick="goHome()">المسبحة</h1>
        <p class="text-emerald-100 text-xs hidden sm:block" id="headerSubtitle">جامع الأذكار والأدعية الكامل</p>
      </div>
      
      <div class="flex items-center space-x-2 space-x-reverse">
        <!-- زر تغيير اللغة -->
        <button type="button" onclick="toggleLanguage()" class="p-2 bg-emerald-800 dark:bg-emerald-950 hover:bg-emerald-600 rounded-xl transition text-xs font-bold flex items-center gap-1 cursor-pointer" title="تغيير اللغة / Cambiar idioma">
          🌐 <span id="langBtnText">ES</span>
        </button>

        <button type="button" onclick="changeFontSize(1)" class="p-1.5 bg-emerald-800 dark:bg-emerald-950 hover:bg-emerald-600 rounded-lg text-xs font-bold transition">A+</button>
        <button type="button" onclick="changeFontSize(-1)" class="p-1.5 bg-emerald-800 dark:bg-emerald-950 hover:bg-emerald-600 rounded-lg text-xs font-bold transition">A-</button>
        
        <button type="button" onclick="toggleDarkMode()" class="p-2 bg-emerald-800 dark:bg-emerald-950 hover:bg-emerald-600 rounded-xl transition" title="تبديل الوضع">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path></svg>
        </button>
      </div>
    </div>
  </header>

  <!-- Main Content Area -->
  <main class="container mx-auto px-4 py-6 max-w-3xl flex-grow">

    <!-- VIEW 1: الرئيسية -->
    <div id="homeView" class="space-y-6 my-auto pt-4">
      <h2 id="homeWelcome" class="text-center text-xl font-bold text-slate-700 dark:text-slate-300 mb-6">اختر القسم للبدء:</h2>
      
      <div class="grid gap-6 md:grid-cols-2">
        <button type="button" onclick="showSection('azkar')" class="bg-gradient-to-br from-emerald-600 to-emerald-800 hover:from-emerald-700 text-white p-6 rounded-3xl shadow-xl transition transform active:scale-95 text-center flex flex-col items-center justify-center space-y-3 cursor-pointer">
          <div class="p-3 bg-white/20 rounded-2xl">
            <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path></svg>
          </div>
          <div>
            <h3 class="text-xl font-bold" id="btnAzkarTitle">الأذكار اليومية</h3>
            <p class="text-emerald-100 text-xs mt-1" id="btnAzkarSub">الصباح، المساء، النوم، الاستيقاظ، أذكار الصلاة</p>
          </div>
        </button>

        <button type="button" onclick="showSection('adya')" class="bg-gradient-to-br from-teal-600 to-teal-800 hover:from-teal-700 text-white p-6 rounded-3xl shadow-xl transition transform active:scale-95 text-center flex flex-col items-center justify-center space-y-3 cursor-pointer">
          <div class="p-3 bg-white/20 rounded-2xl">
            <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>
          </div>
          <div>
            <h3 class="text-xl font-bold" id="btnAdyaTitle">الأدعية المأثورة</h3>
            <p class="text-teal-100 text-xs mt-1" id="btnAdyaSub">أدعية الرزق، الشفاء، الفرج، الحفظ، وقضاء الحوائج</p>
          </div>
        </button>

        <button type="button" onclick="showTasbeeh()" class="bg-gradient-to-br from-amber-600 to-amber-800 hover:from-amber-700 text-white p-6 rounded-3xl shadow-xl transition transform active:scale-95 text-center flex flex-col items-center justify-center space-y-3 cursor-pointer">
          <div class="p-3 bg-white/20 rounded-2xl">
            <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
          </div>
          <div>
            <h3 class="text-xl font-bold" id="btnTasbeehTitle">المسبحة الإلكترونية</h3>
            <p class="text-amber-100 text-xs mt-1" id="btnTasbeehSub">عداد إلكتروني للتسبيح والاستغفار</p>
          </div>
        </button>

        <button type="button" onclick="showFavorites()" class="bg-gradient-to-br from-rose-600 to-rose-800 hover:from-rose-700 text-white p-6 rounded-3xl shadow-xl transition transform active:scale-95 text-center flex flex-col items-center justify-center space-y-3 cursor-pointer">
          <div class="p-3 bg-white/20 rounded-2xl">
            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          </div>
          <div>
            <h3 class="text-xl font-bold" id="btnFavTitle">المفضلة</h3>
            <p class="text-rose-100 text-xs mt-1" id="btnFavSub">الأذكار والأدعية المحفوظة لديك</p>
          </div>
        </button>
      </div>
    </div>

    <!-- VIEW 2: القوائم -->
    <div id="categoryListView" class="hidden space-y-6">
      <div class="flex items-center justify-between pb-3 border-b border-slate-200 dark:border-slate-800">
        <button type="button" onclick="goHome()" class="flex items-center text-sm font-semibold text-emerald-700 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/50 px-3 py-1.5 rounded-xl border border-emerald-200 dark:border-emerald-800">
          <span class="btn-back-label">الرئيسية</span>
        </button>
        <h2 id="sectionTitle" class="text-xl font-bold text-slate-800 dark:text-slate-100"></h2>
        <div class="w-16"></div>
      </div>

      <div class="relative">
        <input type="text" id="searchInput" onkeyup="filterButtons()" placeholder="ابحث عن ذكر أو دعاء..." class="w-full p-3.5 pr-10 rounded-2xl border border-slate-200 dark:border-slate-700 shadow-sm focus:outline-none focus:ring-2 focus:ring-emerald-500 bg-white dark:bg-slate-800 text-sm">
      </div>

      <div id="buttonsGrid" class="grid gap-4 sm:grid-cols-2"></div>
    </div>

    <!-- VIEW 3: تفاصيل القراءة (قائمة جميع أذكار المجموعة) -->
    <div id="detailView" class="hidden space-y-6">
      <div class="flex items-center justify-between pb-3 border-b border-slate-200 dark:border-slate-800 sticky top-16 bg-slate-50 dark:bg-slate-900 py-2 z-40">
        <button type="button" onclick="goBackToSection()" class="flex items-center text-sm font-semibold text-emerald-700 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/50 px-3 py-1.5 rounded-xl border border-emerald-200 dark:border-emerald-800">
          <span class="btn-back-label">رجوع</span>
        </button>
        <h2 id="itemGroupTitle" class="text-lg md:text-xl font-bold text-slate-800 dark:text-slate-100 text-center px-2"></h2>
        
        <button type="button" onclick="resetAllInGroup()" id="resetAllBtn" class="text-xs font-medium text-slate-600 dark:text-slate-400 hover:text-red-600 bg-slate-100 dark:bg-slate-800 px-3 py-1.5 rounded-xl border border-slate-200 dark:border-slate-700">
          إعادة الكل
        </button>
      </div>

      <!-- شريط إنجاز المجموعة -->
      <div id="progressBarContainer" class="bg-white dark:bg-slate-800 p-4 rounded-2xl border border-slate-200 dark:border-slate-700 shadow-sm space-y-2">
        <div class="flex justify-between items-center text-xs font-bold text-slate-600 dark:text-slate-300">
          <span id="progressTextLabel">نسبة الإنجاز الكلية</span>
          <span id="progressPercent">0%</span>
        </div>
        <div class="w-full bg-slate-100 dark:bg-slate-700 h-2.5 rounded-full overflow-hidden">
          <div id="progressBarFill" class="bg-emerald-500 h-full w-0 transition-all duration-300"></div>
        </div>
      </div>

      <!-- حاوية قائمة الأذكار -->
      <div id="itemsContainer" class="space-y-6"></div>
    </div>

    <!-- VIEW 4: المسبحة -->
    <div id="tasbeehView" class="hidden space-y-6 pt-4">
      <div class="flex items-center justify-between pb-3 border-b border-slate-200 dark:border-slate-800">
        <button type="button" onclick="goHome()" class="flex items-center text-sm font-semibold text-emerald-700 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/50 px-3 py-1.5 rounded-xl border border-emerald-200 dark:border-emerald-800">
          <span class="btn-back-label">الرئيسية</span>
        </button>
        <h2 class="text-xl font-bold text-slate-800 dark:text-slate-100" id="tasbeehHeaderTitle">المسبحة الإلكترونية الشاملة</h2>
        <button type="button" onclick="resetAllTasbeehs()" id="resetTasbeehBtn" class="text-xs font-bold text-rose-600 dark:text-rose-400 bg-rose-50 dark:bg-rose-950/50 px-3 py-1.5 rounded-xl border border-rose-200 dark:border-rose-800">
          تصفير الكل
        </button>
      </div>

      <div id="tasbeehGrid" class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3"></div>
    </div>

    <!-- VIEW 5: المفضلة -->
    <div id="favoritesView" class="hidden space-y-6">
      <div class="flex items-center justify-between pb-3 border-b border-slate-200 dark:border-slate-800">
        <button type="button" onclick="goHome()" class="flex items-center text-sm font-semibold text-emerald-700 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/50 px-3 py-1.5 rounded-xl border border-emerald-200 dark:border-emerald-800">
          <span class="btn-back-label">الرئيسية</span>
        </button>
        <h2 class="text-xl font-bold text-slate-800 dark:text-slate-100" id="favHeaderTitle">المفضلة</h2>
        <div class="w-16"></div>
      </div>
      <div id="favoritesContainer" class="space-y-4"></div>
    </div>

  </main>

  <!-- Footer -->
  <footer class="bg-white dark:bg-slate-800 border-t border-slate-200 dark:border-slate-700 py-4 text-center text-xs text-slate-500 dark:text-slate-400">
    <span id="footerText">المسبحة - جامع الأذكار والأدعية الكامل © 2026</span>
  </footer>

  <div id="toast" class="fixed bottom-6 left-1/2 -translate-x-1/2 bg-slate-800 text-white text-xs px-4 py-2.5 rounded-full shadow-2xl opacity-0 pointer-events-none transition duration-300 z-50"></div>

  <script>
    let currentLang = safeGetStorage('app_lang') || 'ar';

    const uiTexts = {
      ar: {
        headerTitle: 'المسبحة',
        headerSubtitle: 'جامع الأذكار والأدعية الكامل',
        homeWelcome: 'اختر القسم للبدء:',
        btnAzkarTitle: 'الأذكار اليومية',
        btnAzkarSub: 'الصباح، المساء، النوم، الاستيقاظ، أذكار الصلاة',
        btnAdyaTitle: 'الأدعية المأثورة',
        btnAdyaSub: 'أدعية الرزق، الشفاء، الفرج، الحفظ، وقضاء الحوائج',
        btnTasbeehTitle: 'المسبحة الإلكترونية',
        btnTasbeehSub: 'عداد إلكتروني للتسبيح والاستغفار',
        btnFavTitle: 'المفضلة',
        btnFavSub: 'الأذكار والأدعية المحفوظة لديك',
        back: 'رجوع',
        home: 'الرئيسية',
        resetAll: 'إعادة الكل',
        reset: 'إعادة ضبط',
        searchPlaceholder: 'ابحث عن ذكر أو دعاء...',
        countLabel: 'التكرار',
        doneLabel: 'تم المتبقي',
        progressLabel: 'نسبة الإنجاز الكلية',
        arabicOriginal: 'النص الأصلي باللغة العربية:',
        azkarSectionTitle: 'الأذكار اليومية',
        adyaSectionTitle: 'الأدعية المأثورة',
        noFavs: 'لا توجد أذكار مضافة للمفضلة حالياً.',
        removeFav: 'إزالة من المفضلة',
        prevBtn: 'السابق',
        nextBtn: 'التالي',
        itemProgress: 'الذكر {current} من {total}',
        completedGroup: '🎉 تم إكمال جميع أذكار هذا القسم',
        pressToCount: 'اضغط للتكرار',
        completedItem: 'تم الإكمال ✓'
      },
      es: {
        headerTitle: 'Misbaha',
        headerSubtitle: 'Colección Completa de Invocaciones y Súplicas',
        homeWelcome: 'Seleccione una categoría:',
        btnAzkarTitle: 'Azkar Diarios',
        btnAzkarSub: 'Mañana, tarde, dormir, despertar y oración',
        btnAdyaTitle: 'Súplicas (Du\'as)',
        btnAdyaSub: 'Sustento, curación, alivio y protección',
        btnTasbeehTitle: 'Rosario Electrónico (Tasbeeh)',
        btnTasbeehSub: 'Contador digital para el recuerdo de Allah',
        btnFavTitle: 'Favoritos',
        btnFavSub: 'Invocaciones guardadas',
        back: 'Volver',
        home: 'Inicio',
        resetAll: 'Reiniciar todo',
        reset: 'Reiniciar',
        searchPlaceholder: 'Buscar suplicación o dhikr...',
        countLabel: 'Repetición',
        doneLabel: 'Completado',
        progressLabel: 'Progreso total',
        arabicOriginal: 'Texto original en árabe:',
        azkarSectionTitle: 'Azkar Diarios',
        adyaSectionTitle: 'Súplicas Seleccionadas',
        noFavs: 'No hay invocaciones guardadas en favoritos.',
        removeFav: 'Eliminar de favoritos',
        prevBtn: 'Anterior',
        nextBtn: 'Siguiente',
        itemProgress: 'Invocación {current} de {total}',
        completedGroup: '¡Has completado todas las invocaciones! 🎉',
        pressToCount: 'Toca para contar',
        completedItem: 'Completado ✓'
      }
    };

    const tasbeehItems = [
      { id: 't1', ar: 'سُبْحَانَ اللَّهِ', latin: 'Subḥān-Allāh', es: 'Glorificado sea Allah' },
      { id: 't2', ar: 'الْحَمْدُ لِلَّهِ', latin: 'Al-ḥamdu lillāh', es: 'Alabado sea Allah' },
      { id: 't3', ar: 'لا إِلَهَ إِلاَّ اللَّهُ', latin: 'Lā ilāha ill-Allāh', es: 'No hay más divinidad que Allah' },
      { id: 't4', ar: 'اللَّهُ أَكْبَرُ', latin: 'Allāhu akbar', es: 'Allah es el más Grande' },
      { id: 't5', ar: 'أَسْتَغْفِرُ اللَّهَ وَأَتُوبُ إِلَيْهِ', latin: 'Astaghfirullāha wa atūbu ilayh', es: 'Pido perdón a Allah y me arrepiento ante Él' },
      { id: 't6', ar: 'لا حَوْلَ وَلا قُوَّةَ إِلاَّ بِاللَّهِ', latin: 'Lā ḥawla wa lā quwwata illā billāh', es: 'No hay poder ni fuerza sino en Allah' },
      { id: 't7', ar: 'اللَّهُمَّ صَلِّ وَسَلِّمْ عَلَى نَبِيِّنَا مُحَمَّدٍ', latin: 'Allāhumma ṣalli wa sallim ‘alā nabiyyinā Muḥammad', es: '¡Oh Allah! Bendice a nuestro Profeta Muhammad' },
      { id: 't8', ar: 'سُبْحَانَ اللَّهِ وَبِحَمْدِهِ ، سُبْحَانَ اللَّهِ الْعَظِيمِ', latin: 'Subḥān-Allāhi wa bi-ḥamdihi, Subḥān-Allāhil-‘aẓīm', es: 'Glorificado sea Allah y con Su alabanza, Glorificado sea Allah el Grandioso' },
      { id: 't9', ar: 'حَسْبُنَا اللَّهُ وَنِعْمَ الْوَكِيلُ', latin: 'Ḥasbun-Allāhu wa ni‘mal-wakīl', es: 'Allah nos basta, y Qué excelente Protector' }
    ];

    const azkarData = [
      {
        id: 'sabah',
        titleAr: 'أذكار الصباح',
        titleEs: 'Azkar de la Mañana',
        items: [
          { 
            text: '﴿اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ الْحَيُّ الْقَيُّومُ لاَ تَأْخُذُهُ سِنَةٌ وَلاَ نَوْمٌ لَّهُ مَا فِي السَّمَوَاتِ وَمَا فِي الأَرْضِ مَن ذَا الَّذِي يَشْفَعُ عِنْدَهُ إِلاَّ بِإِذْنِهِ يَعْلَمُ مَا بَيْنَ أَيْدِيهِمْ وَمَا خَلْفَهُمْ وَلاَ يُحِيطُونَ بِشَيْءٍ مِّنْ عِلْمِهِ إِلاَّ بِمَا شَاء وَسِعَ كُرْسِيُّهُ السَّمَوَاتِ وَالْأَرْضَ وَلاَ يَؤُودُهُ حِفْظُهُمَا وَهُوَ الْعَلِيُّ الْعَظِيمُ﴾', 
            latin: 'Allāhu lā ilāha illā huwal-ḥayyul-qayyūmu, lā ta’khudhuhu sinatun wa lā nawm, lahū mā fis-samāwāti wa mā fil-arḍ, man dhal-ladhī yashfa‘u ‘indahū illā bi-idhnihi, ya‘lamu mā bayna aydīhim wa mā khalfahum, wa lā yuḥīṭūna bi-shay’im-min ‘ilmihī illā bimā shā’a, wasi‘a kursiyyuhus-samāwāti wal-arḍa, wa lā ya’ūduhū ḥifẓuhumā, wa huwal-‘aliyyul-‘aẓīm.', 
            explanationEs: 'Allah! No hay más divinidad que Él, el Viviente, el Subsistente. Ni la somnolencia ni el sueño Le vencen. Suyo es cuanto hay en los cielos y en la tierra. ¿Quién podrá interceder ante Él sin Su permiso? Conoce lo que les antecedió y lo que les sucederá, y ellos no abarcan nada de Su conocimiento excepto lo que Él quiere. Su Trono abarca los cielos y la tierra, y no Le fatiga la custodia de ambos. Él es el Altísimo, el Grandioso. [Al-Baqarah: 255]', 
            count: 1, 
            maxCount: 1, 
            audioUrl: 'https://everyayah.com/data/Alafasy_128kbps/002255.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ هُوَ اللَّهُ أَحَدٌ ۞ اللَّهُ الصَّمَدُ ۞ لَمْ يَلِدْ وَلَمْ يُولَدْ ۞ وَلَمْ يَكُن لَّهُ كُفُوًا أَحَدٌ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul huwal-lāhu aḥad. Allāhuṣ-ṣamad. Lam yalid wa lam yūlad. Wa lam yakul-lahū kufuwan aḥad.', 
            explanationEs: 'Di: Él es Allah, Uno. Allah, el Absoluto. No ha engendrado ni ha sido engendrado, y no hay nadie semejante a Él. (Surah Al-Ikhlas)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/112.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ أَعُوذُ بِرَبِّ الْفَلَقِ ۞ مِن شَرِّ مَا خَلَقَ ۞ وَمِن شَرِّ غَاسِقٍ إِذَا وَقَبَ ۞ وَمِن شَرِّ النَّفَّاثَاتِ فِي الْعُقَدِ ۞ وَمِن شَرِّ حَاسِدٍ إِذَا حَسَدَ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul a‘ūdhu bi-rabbil-falaq. Min sharri mā khalaq. Wa min sharri ghāsiqin idhā waqab. Wa min sharrin-naffāthāti fil-‘uqad. Wa min sharri ḥāsidin idhā ḥasad.', 
            explanationEs: 'Di: Me refugio en el Señor del amanecer, del mal de lo que ha creado, del mal de la oscuridad cuando se extiende, del mal de las que soplan en los nudos, y del mal del envidioso cuando envidia. (Surah Al-Falaq)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/113.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ أَعُوذُ بِرَبِّ النَّاسِ ۞ مَلِكِ النَّاسِ ۞ إِلَهِ النَّاسِ ۞ مِن شَرِّ الْوَسْوَاسِ الْخَنَّاسِ ۞ الَّذِي يُوَسْوِسُ فِي صُدُورِ النَّاسِ ۞ مِنَ الْجِنَّةِ وَالنَّاسِ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul a‘ūdhu bi-rabbin-nās. Malikin-nās. Ilāhin-nās. Min sharril-waswāsil-khannās. Alladhī yuwaswisu fī ṣudūrin-nās. Minal-jinnati wan-nās.', 
            explanationEs: 'Di: Me refugio en el Señor de los hombres, el Rey de los hombres, el Dios de los hombres, del mal del susurrador escurridizo, que susurra en los pechos de los hombres, sea entre los genios o entre los hombres. (Surah An-Nas)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/114.mp3' 
          },
          { 
            text: 'أَصْبَحْنَا وَأَصْبَحَ الْمُلْكُ لِلَّهِ، وَالْحَمْدُ لِلَّهِ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، رَبِّ أَسْأَلُكَ خَيْرَ مَا فِي هَذَا الْيَوْمِ وَخَيْرَ مَا بَعْدَهُ، وَأَعُوذُ بِكَ مِنْ شَرِّ مَا فِي هَذَا الْيَوْمِ وَشَرِّ مَا بَعْدَهُ، رَبِّ أَعُوذُ بِكَ مِنَ الْكَسَلِ، وَسُوءِ الْكِبَرِ، رَبِّ أَعُوذُ بِكَ مِنْ عَذَابٍ فِي النَّارِ وَعَذَابٍ فِي الْقَبْرِ.', 
            latin: 'Aṣbaḥnā wa aṣbaḥal-mulku lillāh, wal-ḥamdu lillāh, lā ilāha ill-Allāhu waḥdahū lā sharīka lah, lahul-mulku wa lahul-ḥamdu wa huwa ‘alā kulli shay’in qadīr. Rabbi as’aluka khayra mā fī hādhal-yawmi wa khayra mā ba‘dah, wa a‘ūdhu bika min sharri mā fī hādhal-yawmi wa sharri mā ba‘dah, Rabbi a‘ūdhu bika minal-kasali wa sū’il-kibar, Rabbi a‘ūdhu bika min ‘adhābin fin-nāri wa ‘adhābin fil-qabr.', 
            explanationEs: 'Hemos llegado a la mañana y el dominio pertenece a Allah, y alabado sea Allah. No hay más divinidad que Allah, Único, sin socios. Suyo es el dominio y Suya es la alabanza, y Él es sobre toda cosa Todopoderoso. Señor mío, Te pido el bien de este día y el bien de lo que le sigue, y me refugio en Ti del mal de este día y del mal de lo que le sigue. Señor mío, me refugio en Ti de la pereza y del mal de la vejez. Señor mío, me refugio en Ti del castigo en el Fuego y del castigo en la tumba.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ بِكَ أَصْبَحْنَا، وَبِكَ أَمْسَيْنَا، وَبِكَ نَحْيَا، وَبِكَ نَمُوتُ وَإِلَيْكَ النُّشُورُ.', 
            latin: 'Allāhumma bika aṣbaḥnā, wa bika amsaynā, wa bika naḥyā, wa bika namūtu wa ilaykan-nushūr.', 
            explanationEs: '¡Oh Allah! Por Ti amanecemos, por Ti anochecemos, por Ti vivimos, por Ti morimos y hacia Ti es la resurrección.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ أَنْتَ رَبِّي لاَ إِلَهَ إِلاَّ أَنْتَ، خَلَقْتَنِي وَأَنَا عَبْدُكَ، وَأَنَا عَلَى عَهْدِكَ وَوَعْدِكَ مَا اسْتَطَعْتُ، أَعُوذُ بِكَ مِنْ شَرِّ مَا صَنَعْتُ، أَبُوءُ لَكَ بِنِعْمَتِكَ عَلَيَّ، وَأَبُوءُ بِذَنْبِي فَاغْفِرْ لِي فَإِنَّهُ لاَ يَغْفِرُ الذُّنُوبَ إِلاَّ أَنْتَ.', 
            latin: 'Allāhumma anta Rabbī lā ilāha illā ant, khalaqtanī wa anā ‘abduk, wa anā ‘alā ‘ahdika wa wa‘dika mas-taṭa‘tu, a‘ūdhu bika min sharri mā ṣana‘tu, abū’u laka bi-ni‘matika ‘alayya, wa abū’u bi-dhanbī faghfir lī fa-innahū lā yaghfirudh-dhunūba illā ant.', 
            explanationEs: '¡Oh Allah! Tú eres mi Señor, no hay más divinidad que Tú. Me creaste y yo soy Tu siervo, y mantengo Tu pacto y Tu promesa en la medida de mis posibilidades. Me refugio en Ti del mal que he cometido. Reconozco ante Ti Tus favores sobre mí y te confieso mis pecados, así que perdóname, pues nadie perdona los pecados excepto Tú.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَصْبَحْتُ أُشْهِدُكَ، وَأُشْهِدُ حَمَلَةَ عَرْشِكَ، وَمَلاَئِكَتَكَ، وَجَمِيعَ خَلْقِكَ، أَنَّكَ أَنْتَ اللَّهُ لاَ إِلَهَ إِلاَّ أَنْتَ وَحْدَكَ لاَ شَرِيكَ لَكَ، وَأَنَّ مُحَمَّدًا عَبْدُكَ وَرَسُولُكَ.', 
            latin: 'Allāhumma innī aṣbaḥtu ushhiduka, wa ushhidu ḥamalata ‘arshika, wa malā’ikataka, wa jamī‘a khalqika, annaka ant-Allāhu lā ilāha illā anta waḥdaka lā sharīka laka, wa anna Muḥammadan ‘abduka wa rasūluk.', 
            explanationEs: '¡Oh Allah! He amanecido tomándote como testigo, y tomando como testigos a los portadores de Tu Trono, a Tus ángeles y a toda Tu creación, de que Tú eres Allah, no hay más divinidad que Tú, Único, sin socios, y que Muhammad es Tu siervo y Tu Mensajero.', 
            count: 4, 
            maxCount: 4 
          },
          { 
            text: 'اللَّهُمَّ مَا أَصْبَحَ بِي مِنْ نِعْمَةٍ أَوْ بِأَحَدٍ مِنْ خَلْقِكَ فَمِنْكَ وَحْدَكَ لاَ شَرِيكَ لَكَ، فَلَكَ الْحَمْدُ وَلَكَ الشُّكْرُ.', 
            latin: 'Allāhumma mā aṣbaḥa bī min ni‘matin aw bi-aḥadin min khalqika fa-minka waḥdaka lā sharīka laka, fa-lakal-ḥamdu wa lakash-shukr.', 
            explanationEs: '¡Oh Allah! Cualquier bendición que amaneciera en mí o en cualquiera de Tus criaturas proviene únicamente de Ti, sin socios. A Ti pertenece la alabanza y a Ti el agradecimiento.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ عَافِنِي فِي بَدَنِي، اللَّهُمَّ عَافِنِي فِي سَمْعِي، اللَّهُمَّ عَافِنِي فِي بَصَرِي، لاَ إِلَهَ إِلاَّ أَنْتَ. اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْكُفْرِ، وَالْفَقْرِ، وَأَعُوذُ بِكَ مِنْ عَذَابِ الْقَبْرِ، لاَ إِلَهَ إِلاَّ أَنْتَ.', 
            latin: 'Allāhumma ‘āfinī fī badanī, Allāhumma ‘āfinī fī sam‘ī, Allāhumma ‘āfinī fī baṣarī, lā ilāha illā ant. Allāhumma innī a‘ūdhu bika minal-kufri wal-faqr, wa a‘ūdhu bika min ‘adhābil-qabr, lā ilāha illā ant.', 
            explanationEs: '¡Oh Allah! Concedeme salud en mi cuerpo. ¡Oh Allah! Concedeme salud en mi oído. ¡Oh Allah! Concedeme salud en mi vista. No hay más divinidad que Tú. ¡Oh Allah! Me refugio en Ti de la incredulidad y de la pobreza, y me refugio en Ti del castigo de la tumba. No hay más divinidad que Tú.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'حَسْبِيَ اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ عَلَيْهِ تَوَكَّلْتُ وَهُوَ رَبُّ الْعَرْشِ الْعَظِيمِ.', 
            latin: 'Ḥasbiy-Allāhu lā ilāha illā huwa ‘alayhi tawakkaltu wa huwa Rabbul-‘arshil-‘aẓīm.', 
            explanationEs: 'Allah me basta; no hay más divinidad que Él. En Él he depositado mi confianza y Él es el Señor del Trono Grandioso.', 
            count: 7, 
            maxCount: 7 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ الْعَفْوَ وَالْعَافِيَةَ فِي الدُّنْيَا وَالآخِرَةِ، اللَّهُمَّ إِنِّي أَسْأَلُكَ الْعَفْوَ وَالْعَافِيَةَ فِي دِينِي وَدُنْيَايَ وَأَهْلِي وَمَالِي، اللَّهُمَّ اسْتُرْ عَوْرَاتِي وَآمِنْ رَوْعَاتِي، اللَّهُمَّ احْفَظْنِي مِنْ بَيْنِ يَدَيَّ وَمِنْ خَلْفِي وَعَنْ يَمِينِي وَعَنْ شِمَالِي وَمِنْ فَوْقِي، وَأَعُوذُ بِعَظَمَتِكَ أَنْ أُغْتَالَ مِنْ تَحْتِي.', 
            latin: 'Allāhumma innī as’alukal-‘afwa wal-‘āfiyata fid-dunyā wal-ākhirah. Allāhumma innī as’alukal-‘afwa wal-‘āfiyata fī dīnī wa dunyāya wa ahlī wa mālī. Allāhummas-tur ‘awrātī wa āmin raw‘ātī. Allāhummaḥ-faẓnī min bayni yadayya wa min khalfī wa ‘an yamīnī wa ‘an shimālī wa min fawqī, wa a‘ūdhu bi-‘aẓamatika an ughtāla min taḥtī.', 
            explanationEs: '¡Oh Allah! Te pido el perdón y la salud en esta vida y en la otra. ¡Oh Allah! Te pido el perdón y la salud en mi religión, mis asuntos mundanales, mi familia y mis bienes. ¡Oh Allah! Cubre mis faltas y calma mis temores. ¡Oh Allah! Protégeme por delante, por detrás, a mi derecha, a mi izquierda y por encima de mí; y me refugio en Tu grandeza de ser tragado por la tierra.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ عَالِمَ الْغَيْبِ وَالشَّهَادَةِ فَاطِرَ السَّمَاوَاتِ وَالأَرْضِ، رَبَّ كُلِّ شَيْءٍ وَمَلِيكَهُ، أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ أَنْتَ، أَعُوذُ بِكَ مِنْ شَرِّ نَفْسِي، وَمِنْ شَرِّ الشَّيْطَانِ وَشِرْكِهِ، وَأَنْ أَقْتَرِفَ عَلَى نَفْسِي سُوءًا أَوْ أَجُرَّهُ إِلَى مُسْلِمٍ.', 
            latin: 'Allāhumma ‘ālimal-ghaybi wash-shahādati fāṭiras-samāwāti wal-arḍ, Rabba kulli shay’in wa malīkah, ash-hadu an lā ilāha illā ant, a‘ūdhu bika min sharri nafsī, wa min sharrish-shayṭāni wa shirkihi, wa an aqtarifa ‘alā nafsī sū’an aw ajurrahū ilā muslim.', 
            explanationEs: '¡Oh Allah! Conocedor de lo oculto y de lo manifiesto, Creador de los cielos y de la tierra, Señor de todas las cosas y su Soberano. Testifico que no hay más divinidad que Tú. Me refugio en Ti del mal de mi alma, del mal del Satán y de su idolatría, y de cometer un mal contra mí mismo o infligírselo a un musulmán.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'بِسْمِ اللَّهِ الَّذِي لاَ يَضُرُّ مَعَ اسْمِهِ شَيْءٌ فِي الأَرْضِ وَلاَ فِي السَّمَاءِ وَهُوَ السَّمِيعُ الْعَلِيمُ.', 
            latin: 'Bismillāhil-ladhī lā yaḍurru ma‘as-mihī shay’un fil-arḍi wa lā fis-samā’i wa huwas-samī‘ul-‘alīm.', 
            explanationEs: 'En el nombre de Allah, con Cuyo nombre nada daña en la tierra ni en el cielo, y Él es el TodoOidor, el AllSabelotodo.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'رَضِيتُ بِاللَّهِ رَبًّا، وَبِالإِسْلاَمِ دِينًا، وَبِمُحَمَّدٍ صَلَّى اللَّهُ عَلَيْهِ وَسَلَّمَ نَبِيًّا.', 
            latin: 'Raḍītu billāhi Rabban, wa bil-Islāmi dīnan, wa bi-Muḥammadin ṣall-Allāhu ‘alayhi wa sallama nabiyyā.', 
            explanationEs: 'Estoy complacido con Allah como Señor, con el Islam como religión y con Muhammad (que la paz y las bendiciones de Allah sean con él) como Profeta.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'يَا حَيُّ يَا قَيُّومُ بِرَحْمَتِكَ أَسْتَغِيثُ أَصْلِحْ لِي شَأْنِي كُلَّهُ وَلاَ تَكِلْنِي إِلَى نَفْسِي طَرْفَةَ عَيْنٍ.', 
            latin: 'Yā Ḥayyu yā Qayyūmu bi-raḥmatika astaghīthu aṣliḥ lī sha’nī kullahu wa lā takilnī ilā nafsī ṭarfata ‘ayn.', 
            explanationEs: '¡Oh Viviente! ¡Oh Subsistente! En Tu misericordia busco auxilio; rectifica todos mis asuntos y no me encomiendes a mí mismo ni por el parpadeo de un ojo.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'أَصْبَحْنَا وَأَصْبَحَ الْمُلْكُ لِلَّهِ رَبِّ الْعَالَمِينَ، اللَّهُمَّ إِنِّي أَسْأَلُكَ خَيْرَ هَذَا الْيَوْمِ: فَتْحَهُ، وَنَصْرَهُ، وَنُورَهُ، وَبَرَكَتَهُ، وَهُدَاهُ، وَأَعُوذُ بِكَ مِنْ شَرِّ مَا فِيهِ وَشَرِّ مَا بَعْدَهُ.', 
            latin: 'Aṣbaḥnā wa aṣbaḥal-mulku lillāhi Rabbil-‘ālamīn, Allāhumma innī as’aluka khayra hādhal-yawmi: fatḥahū, wa naṣrahū, wa nūrahū, wa barakatahū, wa hudāh, wa a‘ūdhu bika min sharri mā fīhi wa sharri mā ba‘dah.', 
            explanationEs: 'Hemos llegado a la mañana y el dominio pertenece a Allah, Señor de los mundos. ¡Oh Allah! Te pido el bien de este día: su conquista, su victoria, su luz, su bendición y su guía; y me refugio en Ti del mal que hay en él y del mal de lo que le sigue.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'أَصْبَحْنَا عَلَى فِطْرَةِ الإِسْلاَمِ، وَعَلَى كَلِمَةِ الإِخْلاَصِ، وَعَلَى دِينِ نَبِيِّنَا مُحَمَّدٍ صَلَّى اللَّهُ عَلَيْهِ وَسَلَّمَ، وَعَلَى مِلَّةِ أَبِينَا إِبْرَاهِيمَ حَنِيفًا مُسْلِمًا وَمَا كَانَ مِنَ الْمُشْرِكِينَ.', 
            latin: 'Aṣbaḥnā ‘alā fiṭratil-Islām, wa ‘alā kalimatil-ikhlāṣ, wa ‘alā dīni nabiyyinā Muḥammadin ṣall-Allāhu ‘alayhi wa sallam, wa ‘alā millati abīnā Ibrāhīma ḥanīfan musliman wa mā kāna minal-mushrikīn.', 
            explanationEs: 'Amanecemos en la naturaleza pura del Islam, en la palabra de la devoción sincera, en la religión de nuestro Profeta Muhammad (que la paz y las bendiciones de Allah sean con él) y en la fe de nuestro padre Abraham, monoteísta puro y musulmán, quien no fue de los asociadores.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'سُبْحَانَ اللَّهِ وَبِحَمْدِهِ: عَدَدَ خَلْقِهِ، وَرِضَا نَفْسِهِ، وَزِنَةَ عَرْشِهِ، وَمِدَادَ كَلِمَاتِهِ.', 
            latin: 'Subḥān-Allāhi wa bi-ḥamdihi: ‘adada khalqihi, wa riḍā nafsihi, wa zinata ‘arshihi, wa midāda kalimātih.', 
            explanationEs: 'Glorificado sea Allah y alabado sea, tantas veces como el número de Su creación, según Su complacencia, el peso de Su Trono y la tinta de Sus palabras.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'أَعُوذُ بِكَلِمَاتِ اللَّهِ التَّامَّاتِ مِنْ شَرِّ مَا خَلَقَ.', 
            latin: 'A‘ūdhu bi-kalimātil-lāhit-tāmmāti min sharri mā khalaq.', 
            explanationEs: 'Me refugio en las palabras perfectas de Allah del mal de lo que ha creado.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ عِلْمًا نَافِعًا، وَرِزْقًا طَيِّبًا، وَعَمَلاً مُتَقَبَّلاً.', 
            latin: 'Allāhumma innī as’aluka ‘ilman nāfi‘an, wa rizqan ṭayyiban, wa ‘amalan mutaqabbalā.', 
            explanationEs: '¡Oh Allah! Te pido un conocimiento beneficioso, un sustento puro y una obra aceptada.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.', 
            latin: 'Lā ilāha ill-Allāhu waḥdahū lā sharīka lah, lahul-mulku wa lahul-ḥamdu, wa huwa ‘alā kulli shay’in qadīr.', 
            explanationEs: 'No hay más divinidad que Allah, Único, sin socios. Suyo es el dominio y Suya es la alabanza, y Él es sobre toda cosa Todopoderoso.', 
            count: 10, 
            maxCount: 10 
          },
          { 
            text: 'سُبْحَانَ اللَّهِ وَبِحَمْدِهِ.', 
            latin: 'Subḥān-Allāhi wa bi-ḥamdih.', 
            explanationEs: 'Glorificado sea Allah y alabado sea.', 
            count: 100, 
            maxCount: 100 
          },
          { 
            text: 'أَسْتَغْفِرُ اللَّهَ وَأَتُوبُ إِلَيْهِ.', 
            latin: 'Astaghfirullāha wa atūbu ilayh.', 
            explanationEs: 'Pido perdón a Allah y me arrepiento ante Él.', 
            count: 100, 
            maxCount: 100 
          },
          { 
            text: 'اللَّهُمَّ صَلِّ وَسَلِّمْ عَلَى نَبِيِّنَا مُحَمَّدٍ.', 
            latin: 'Allāhumma ṣalli wa sallim ‘alā nabiyyinā Muḥammad.', 
            explanationEs: '¡Oh Allah! Bendice y otorga la paz a nuestro Profeta Muhammad.', 
            count: 10, 
            maxCount: 10 
          }
        ]
      },
      {
        id: 'masaa',
        titleAr: 'أذكار المساء',
        titleEs: 'Azkar de la Tarde',
        items: [
          { 
            text: 'أَعُوذُ بِاللَّهِ مِنَ الشَّيْطَانِ الرَّجِيمِ: ﴿اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ الْحَيُّ الْقَيُّومُ لاَ تَأْخُذُهُ سِنَةٌ وَلاَ نَوْمٌ لَّهُ مَا فِي السَّمَاوَاتِ وَمَا فِي الأَرْضِ مَن ذَا الَّذِي يَشْفَعُ عِنْدَهُ إِلاَّ بِإِذْنِهِ يَعْلَمُ مَا بَيْنَ أَيْدِيهِمْ وَمَا خَلْفَهُمْ وَلاَ يُحِيطُونَ بِشَيْءٍ مِّنْ عِلْمِهِ إِلاَّ بِمَا شَاء وَسِعَ كُرْسِيُّهُ السَّمَاوَاتِ وَالأَرْضَ وَلاَ يَؤُودُهُ حِفْظُهُمَا وَهُوَ الْعَلِيُّ الْعَظِيمُ﴾', 
            latin: 'Allāhu lā ilāha illā huwal-ḥayyul-qayyūmu, lā ta’khudhuhu sinatun wa lā nawm, lahū mā fis-samāwāti wa mā fil-arḍ, man dhal-ladhī yashfa‘u ‘indahū illā bi-idhnihi, ya‘lamu mā bayna aydīhim wa mā khalfahum, wa lā yuḥīṭūna bi-shay’im-min ‘ilmihī illā bimā shā’a, wasi‘a kursiyyuhus-samāwāti wal-arḍa, wa lā ya’ūduhū ḥifẓuhumā, wa huwal-‘aliyyul-‘aẓīm.', 
            explanationEs: 'Ayat Al-Kursi para la noche: Protección garantizada de Allah hasta la mañana. [Al-Baqarah: 255]', 
            count: 1, 
            maxCount: 1, 
            audioUrl: 'https://everyayah.com/data/Alafasy_128kbps/002255.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ هُوَ اللَّهُ أَحَدٌ ۞ اللَّهُ الصَّمَدُ ۞ لَمْ يَلِدْ وَلَمْ يُولَدْ ۞ وَلَمْ يَكُن لَّهُ كُفُوًا أَحَدٌ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul huwal-lāhu aḥad. Allāhuṣ-ṣamad. Lam yalid wa lam yūlad. Wa lam yakul-lahū kufuwan aḥad.', 
            explanationEs: 'Di: Él es Allah, Uno. Allah, el Absoluto. No ha engendrado ni ha sido engendrado, y no hay nadie semejante a Él. (Surah Al-Ikhlas)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/112.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ أَعُوذُ بِرَبِّ الْفَلَقِ ۞ مِن شَرِّ مَا خَلَقَ ۞ وَمِن شَرِّ غَاسِقٍ إِذَا وَقَبَ ۞ وَمِن شَرِّ النَّفَّاثَاتِ فِي الْعُقَدِ ۞ وَمِن شَرِّ حَاسِدٍ إِذَا حَسَدَ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul a‘ūdhu bi-rabbil-falaq. Min sharri mā khalaq. Wa min sharri ghāsiqin idhā waqab. Wa min sharrin-naffāthāti fil-‘uqad. Wa min sharri ḥāsidin idhā ḥasad.', 
            explanationEs: 'Di: Me refugio en el Señor del amanecer, del mal de lo que ha creado, del mal de la oscuridad cuando se extiende, del mal de las que soplan en los nudos, y del mal del envidioso cuando envidia. (Surah Al-Falaq)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/113.mp3' 
          },
          { 
            text: 'بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ أَعُوذُ بِرَبِّ النَّاسِ ۞ مَلِكِ النَّاسِ ۞ إِلَهِ النَّاسِ ۞ مِن شَرِّ الْوَسْوَاسِ الْخَنَّاسِ ۞ الَّذِي يُوَسْوِسُ فِي صُدُورِ النَّاسِ ۞ مِنَ الْجِنَّةِ وَالنَّاسِ﴾', 
            latin: 'Bismillāhir-raḥmānir-raḥīm. Qul a‘ūdhu bi-rabbin-nās. Malikin-nās. Ilāhin-nās. Min sharril-waswāsil-khannās. Alladhī yuwaswisu fī ṣudūrin-nās. Minal-jinnati wan-nās.', 
            explanationEs: 'Di: Me refugio en el Señor de los hombres, el Rey de los hombres, el Dios de los hombres, del mal del susurrador escurridizo, que susurra en los pechos de los hombres, sea entre los genios o entre los hombres. (Surah An-Nas)', 
            count: 3, 
            maxCount: 3, 
            audioUrl: 'https://cdn.islamic.network/quran/audio-surah/128/ar.alafasy/114.mp3' 
          },
          { 
            text: 'أَمْسَيْنَا وَأَمْسَى الْمُلْكُ لِلَّهِ، وَالْحَمْدُ لِلَّهِ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، رَبِّ أَسْأَلُكَ خَيْرَ مَا فِي هَذِهِ اللَّيْلَةِ وَخَيْرَ مَا بَعْدَهَا، وَأَعُوذُ بِكَ مِنْ شَرِّ مَا فِي هَذِهِ اللَّيْلَةِ وَشَرِّ مَا بَعْدَهَا، رَبِّ أَعُوذُ بِكَ مِنَ الْكَسَلِ، وَسُوءِ الْكِبَرِ، رَبِّ أَعُوذُ بِكَ مِنْ عَذَابٍ فِي النَّارِ وَعَذَابٍ فِي الْقَبْرِ.', 
            latin: 'Amsaynā wa amsal-mulku lillāh, wal-ḥamdu lillāh, lā ilāha ill-Allāhu waḥdahū lā sharīka lah, lahul-mulku wa lahul-ḥamdu wa huwa ‘alā kulli shay’in qadīr. Rabbi as’aluka khayra mā fī hādhihil-laylati wa khayra mā ba‘dahā, wa a‘ūdhu bika min sharri mā fī hādhihil-laylati wa sharri mā ba‘dahā, Rabbi a‘ūdhu bika minal-kasali wa sū’il-kibar, Rabbi a‘ūdhu bika min ‘adhābin fin-nāri wa ‘adhābin fil-qabr.', 
            explanationEs: 'Hemos llegado a la tarde y el dominio pertenece a Allah, y alabado sea Allah. No hay más divinidad que Allah, Único, sin socios. Suyo es el dominio y Suya es la alabanza, y Él es sobre toda cosa Todopoderoso. Señor mío, Te pido el bien de esta noche y el bien de lo que le sigue, y me refugio en Ti del mal de esta noche y del mal de lo que le sigue. Señor mío, me refugio en Ti de la pereza y del mal de la vejez. Señor mío, me refugio en Ti del castigo en el Fuego y del castigo en la tumba.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ بِكَ أَمْسَيْنَا، وَبِكَ أَصْبَحْنَا، وَبِكَ نَحْيَا، وَبِكَ نَمُوتُ وَإِلَيْكَ الْمَصِيرُ.', 
            latin: 'Allāhumma bika amsaynā, wa bika aṣbaḥnā, wa bika naḥyā, wa bika namūtu wa ilaykal-maṣīr.', 
            explanationEs: '¡Oh Allah! Por Ti anochecemos, por Ti amanecemos, por Ti vivimos, por Ti morimos y hacia Ti es el retorno.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ أَنْتَ رَبِّي لاَ إِلَهَ إِلاَّ أَنْتَ، خَلَقْتَنِي وَأَنَا عَبْدُكَ، وَأَنَا عَلَى عَهْدِكَ وَوَعْدِكَ مَا اسْتَطَعْتُ، أَعُوذُ بِكَ مِنْ شَرِّ مَا صَنَعْتُ، أَبُوءُ لَكَ بِنِعْمَتِكَ عَلَيَّ، وَأَبُوءُ بِذَنْبِي فَاغْفِرْ لِي فَإِنَّهُ لاَ يَغْفِرُ الذُّنُوبَ إِلاَّ أَنْتَ.', 
            latin: 'Allāhumma anta Rabbī lā ilāha illā ant, khalaqtanī wa anā ‘abduk, wa anā ‘alā ‘ahdika wa wa‘dika mas-taṭa‘tu, a‘ūdhu bika min sharri mā ṣana‘tu, abū’u laka bi-ni‘matika ‘alayya, wa abū’u bi-dhanbī faghfir lī fa-innahū lā yaghfirudh-dhunūba illā ant.', 
            explanationEs: '¡Oh Allah! Tú eres mi Señor, no hay más divinidad que Tú. Me creaste y yo soy Tu siervo, y mantengo Tu pacto y Tu promesa en la medida de mis posibilidades. Me refugio en Ti del mal que he cometido. Reconozco ante Ti Tus favores sobre mí y te confieso mis pecados, así que perdóname, pues nadie perdona los pecados excepto Tú.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَمْسَيْتُ أُشْهِدُكَ، وَأُشْهِدُ حَمَلَةَ عَرْشِكَ، وَمَلاَئِكَتَكَ، وَجَمِيعَ خَلْقِكَ، أَنَّكَ أَنْتَ اللَّهُ لاَ إِلَهَ إِلاَّ أَنْتَ وَحْدَكَ لاَ شَرِيكَ لَكَ، وَأَنَّ مُحَمَّدًا عَبْدُكَ وَرَسُولُكَ.', 
            latin: 'Allāhumma innī amsaytu ushhiduka, wa ushhidu ḥamalata ‘arshika, wa malā’ikataka, wa jamī‘a khalqika, annaka ant-Allāhu lā ilāha illā anta waḥdaka lā sharīka laka, wa anna Muḥammadan ‘abduka wa rasūluk.', 
            explanationEs: '¡Oh Allah! He anochecido tomándote como testigo, y tomando como testigos a los portadores de Tu Trono, a Tus ángeles y a toda Tu creación, de que Tú eres Allah, no hay más divinidad que Tú, Único, sin socios, y que Muhammad es Tu siervo y Tu Mensajero.', 
            count: 4, 
            maxCount: 4 
          },
          { 
            text: 'اللَّهُمَّ مَا أَمْسَى بِي مِنْ نِعْمَةٍ أَوْ بِأَحَدٍ مِنْ خَلْقِكَ فَمِنْكَ وَحْدَكَ لاَ شَرِيكَ لَكَ، فَلَكَ الْحَمْدُ وَلَكَ الشُّكْرُ.', 
            latin: 'Allāhumma mā amsā bī min ni‘matin aw bi-aḥadin min khalqika fa-minka waḥdaka lā sharīka laka, fa-lakal-ḥamdu wa lakash-shukr.', 
            explanationEs: '¡Oh Allah! Cualquier bendición que anocheciera en mí o en cualquiera de Tus criaturas proviene únicamente de Ti, sin socios. A Ti pertenece la alabanza y a Ti el agradecimiento.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ عَافِنِي فِي بَدَنِي، اللَّهُمَّ عَافِنِي فِي سَمْعِي، اللَّهُمَّ عَافِنِي فِي بَصَرِي، لاَ إِلَهَ إِلاَّ أَنْتَ. اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْكُفْرِ، وَالْفَقْرِ، وَأَعُوذُ بِكَ مِنْ عَذَابِ الْقَبْرِ، لاَ إِلَهَ إِلاَّ أَنْتَ.', 
            latin: 'Allāhumma ‘āfinī fī badanī, Allāhumma ‘āfinī fī sam‘ī, Allāhumma ‘āfinī fī baṣarī, lā ilāha illā ant. Allāhumma innī a‘ūdhu bika minal-kufri wal-faqr, wa a‘ūdhu bika min ‘adhābil-qabr, lā ilāha illā ant.', 
            explanationEs: '¡Oh Allah! Concedeme salud en mi cuerpo. ¡Oh Allah! Concedeme salud en mi oído. ¡Oh Allah! Concedeme salud en mi vista. No hay más divinidad que Tú. ¡Oh Allah! Me refugio en Ti de la incredulidad y de la pobreza, y me refugio en Ti del castigo de la tumba. No hay más divinidad que Tú.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'حَسْبِيَ اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ عَلَيْهِ تَوَكَّلْتُ وَهُوَ رَبُّ الْعَرْشِ الْعَظِيمِ.', 
            latin: 'Ḥasbiy-Allāhu lā ilāha illā huwa ‘alayhi tawakkaltu wa huwa Rabbul-‘arshil-‘aẓīm.', 
            explanationEs: 'Allah me basta; no hay más divinidad que Él. En Él he depositado mi confianza y Él es el Señor del Trono Grandioso.', 
            count: 7, 
            maxCount: 7 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ الْعَفْوَ وَالْعَافِيَةَ فِي الدُّنْيَا وَالآخِرَةِ، اللَّهُمَّ إِنِّي أَسْأَلُكَ الْعَفْوَ وَالْعَافِيَةَ فِي دِينِي وَدُنْيَايَ وَأَهْلِي وَمَالِي، اللَّهُمَّ اسْتُرْ عَوْرَاتِي وَآمِنْ رَوْعَاتِي، اللَّهُمَّ احْفَظْنِي مِنْ بَيْنِ يَدَيَّ وَمِنْ خَلْفِي وَعَنْ يَمِينِي وَعَنْ شِمَالِي وَمِنْ فَوْقِي، وَأَعُوذُ بِعَظَمَتِكَ أَنْ أُغْتَالَ مِنْ تَحْتِي.', 
            latin: 'Allāhumma innī as’alukal-‘afwa wal-‘āfiyata fid-dunyā wal-ākhirah. Allāhumma innī as’alukal-‘afwa wal-‘āfiyata fī dīnī wa dunyāya wa ahlī wa mālī. Allāhummas-tur ‘awrātī wa āmin raw‘ātī. Allāhummaḥ-faẓnī min bayni yadayya wa min khalfī wa ‘an yamīnī wa ‘an shimālī wa min fawqī, wa a‘ūdhu bi-‘aẓamatika an ughtāla min taḥtī.', 
            explanationEs: '¡Oh Allah! Te pido el perdón y la salud en esta vida y en la otra. ¡Oh Allah! Te pido el perdón y la salud en mi religión, mis asuntos mundanales, mi familia y mis bienes. ¡Oh Allah! Cubre mis faltas y calma mis temores. ¡Oh Allah! Protégeme por delante, por detrás, a mi derecha, a mi izquierda y por encima de mí; y me refugio en Tu grandeza de ser tragado por la tierra.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'اللَّهُمَّ عَالِمَ الْغَيْبِ وَالشَّهَادَةِ فَاطِرَ السَّمَاوَاتِ وَالأَرْضِ، رَبَّ كُلِّ شَيْءٍ وَمَلِيكَهُ، أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ أَنْتَ، أَعُوذُ بِكَ مِنْ شَرِّ نَفْسِي، وَمِنْ شَرِّ الشَّيْطَانِ وَشِرْكِهِ، وَأَنْ أَقْتَرِفَ عَلَى نَفْسِي سُوءًا أَوْ أَجُرَّهُ إِلَى مُسْلِمٍ.', 
            latin: 'Allāhumma ‘ālimal-ghaybi wash-shahādati fāṭiras-samāwāti wal-arḍ, Rabba kulli shay’in wa malīkah, ash-hadu an lā ilāha illā ant, a‘ūdhu bika min sharri nafsī, wa min sharrish-shayṭāni wa shirkihi, wa an aqtarifa ‘alā nafsī sū’an aw ajurrahū ilā muslim.', 
            explanationEs: '¡Oh Allah! Conocedor de lo oculto y de lo manifiesto, Creador de los cielos y de la tierra, Señor de todas las cosas y su Soberano. Testifico que no hay más divinidad que Tú. Me refugio en Ti del mal de mi alma, del mal del Satán y de su idolatría, y de cometer un mal contra mí mismo o infligírselo a un musulmán.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'بِسْمِ اللَّهِ الَّذِي لاَ يَضُرُّ مَعَ اسْمِهِ شَيْءٌ فِي الأَرْضِ وَلاَ فِي السَّمَاءِ وَهُوَ السَّمِيعُ الْعَلِيمُ.', 
            latin: 'Bismillāhil-ladhī lā yaḍurru ma‘as-mihī shay’un fil-arḍi wa lā fis-samā’i wa huwas-samī‘ul-‘alīm.', 
            explanationEs: 'En el nombre de Allah, con Cuyo nombre nada daña en la tierra ni en el cielo, y Él es el TodoOidor, el AllSabelotodo.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'رَضِيتُ بِاللَّهِ رَبًّا، وَبِالإِسْلاَمِ دِينًا، وَبِمُحَمَّدٍ صَلَّى اللَّهُ عَلَيْهِ وَسَلَّمَ نَبِيًّا.', 
            latin: 'Raḍītu billāhi Rabban, wa bil-Islāmi dīnan, wa bi-Muḥammadin ṣall-Allāhu ‘alayhi wa sallama nabiyyā.', 
            explanationEs: 'Estoy complacido con Allah como Señor, con el Islam como religión y con Muhammad (que la paz y las bendiciones de Allah sean con él) como Profeta.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'يَا حَيُّ يَا قَيُّومُ بِرَحْمَتِكَ أَسْتَغِيثُ أَصْلِحْ لِي شَأْنِي كُلَّهُ وَلاَ تَكِلْنِي إِلَى نَفْسِي طَرْفَةَ عَيْنٍ.', 
            latin: 'Yā Ḥayyu yā Qayyūmu bi-raḥmatika astaghīthu aṣliḥ lī sha’nī kullahu wa lā takilnī ilā nafsī ṭarfata ‘ayn.', 
            explanationEs: '¡Oh Viviente! ¡Oh Subsistente! En Tu misericordia busco auxilio; rectifica todos mis asuntos y no me encomiendes a mí mismo ni por el parpadeo de un ojo.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'أَمْسَيْنَا وَأَمْسَى الْمُلْكُ لِلَّهِ رَبِّ الْعَالَمِينَ، اللَّهُمَّ إِنِّي أَسْأَلُكَ خَيْرَ هَذِهِ اللَّيْلَةِ: فَتْحَهَا، وَنَصْرَهَا، وَنُورَهَا، وَبَرَكَتَهَا، وَهُدَاهَا، وَأَعُوذُ بِكَ مِنْ شَرِّ مَا فِيهَا وَشَرِّ مَا بَعْدَهَا.', 
            latin: 'Amsaynā wa amsal-mulku lillāhi Rabbil-‘ālamīn, Allāhumma innī as’aluka khayra hādhihil-laylah: fatḥahā, wa naṣrahā, wa nūrahā, wa barakatahā, wa hudāhā, wa a‘ūdhu bika min sharri mā fīhā wa sharri mā ba‘dahā.', 
            explanationEs: 'Hemos llegado a la tarde y el dominio pertenece a Allah, Señor de los mundos. ¡Oh Allah! Te pido el bien de esta noche: su conquista, su victoria, su luz, su bendición y su guía; y me refugio en Ti del mal que hay en ella y del mal de lo que le sigue.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'أَمْسَيْنَا عَلَى فِطْرَةِ الإِسْلاَمِ، وَعَلَى كَلِمَةِ الإِخْلاَصِ، وَعَلَى دِينِ نَبِيِّنَا مُحَمَّدٍ صَلَّى اللَّهُ عَلَيْهِ وَسَلَّمَ، وَعَلَى مِلَّةِ أَبِينَا إِبْرَاهِيمَ حَنِيفًا مُسْلِمًا وَمَا كَانَ مِنَ الْمُشْرِكِينَ.', 
            latin: 'Amsaynā ‘alā fiṭratil-Islām, wa ‘alā kalimatil-ikhlāṣ, wa ‘alā dīni nabiyyinā Muḥammadin ṣall-Allāhu ‘alayhi wa sallam, wa ‘alā millati abīnā Ibrāhīma ḥanīfan musliman wa mā kāna minal-mushrikīn.', 
            explanationEs: 'Anochecemos en la naturaleza pura del Islam, en la palabra de la devoción sincera, en la religión de nuestro Profeta Muhammad (que la paz y las bendiciones de Allah sean con él) y en la fe de nuestro padre Abraham, monoteísta puro y musulmán, quien no fue de los asociadores.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'سُبْحَانَ اللَّهِ وَبِحَمْدِهِ: عَدَدَ خَلْقِهِ، وَرِضَا نَفْسِهِ، وَزِنَةَ عَرْشِهِ، وَمِدَادَ كَلِمَاتِهِ.', 
            latin: 'Subḥān-Allāhi wa bi-ḥamdihi: ‘adada khalqihi, wa riḍā nafsihi, wa zinata ‘arshihi, wa midāda kalimātih.', 
            explanationEs: 'Glorificado sea Allah y alabado sea, tantas veces como el número de Su creación, según Su complacencia, el peso de Su Trono y la tinta de Sus palabras.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'أَعُوذُ بِكَلِمَاتِ اللَّهِ التَّامَّاتِ مِنْ شَرِّ مَا خَلَقَ.', 
            latin: 'A‘ūdhu bi-kalimātil-lāhit-tāmmāti min sharri mā khalaq.', 
            explanationEs: 'Me refugio en las palabras perfectas de Allah del mal de lo que ha creado.', 
            count: 3, 
            maxCount: 3 
          },
          { 
            text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ عِلْمًا نَافِعًا، وَرِزْقًا طَيِّبًا، وَعَمَلاً مُتَقَبَّلاً.', 
            latin: 'Allāhumma innī as’aluka ‘ilman nāfi‘an, wa rizqan ṭayyiban, wa ‘amalan mutaqabbalā.', 
            explanationEs: '¡Oh Allah! Te pido un conocimiento beneficioso, un sustento puro y una obra aceptada.', 
            count: 1, 
            maxCount: 1 
          },
          { 
            text: 'لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.', 
            latin: 'Lā ilāha ill-Allāhu waḥdahū lā sharīka lah, lahul-mulku wa lahul-ḥamdu, wa huwa ‘alā kulli shay’in qadīr.', 
            explanationEs: 'No hay más divinidad que Allah, Único, sin socios. Suyo es el dominio y Suya es la alabanza, y Él es sobre toda cosa Todopoderoso.', 
            count: 10, 
            maxCount: 10 
          },
          { 
            text: 'سُبْحَانَ اللَّهِ وَبِحَمْدِهِ.', 
            latin: 'Subḥān-Allāhi wa bi-ḥamdih.', 
            explanationEs: 'Glorificado sea Allah y alabado sea.', 
            count: 100, 
            maxCount: 100 
          },
          { 
            text: 'أَسْتَغْفِرُ اللَّهَ وَأَتُوبُ إِلَيْهِ.', 
            latin: 'Astaghfirullāha wa atūbu ilayh.', 
            explanationEs: 'Pido perdón a Allah y me arrepiento ante Él.', 
            count: 100, 
            maxCount: 100 
          },
          { 
            text: 'اللَّهُمَّ صَلِّ وَسَلِّمْ عَلَى نَبِيِّنَا مُحَمَّدٍ.', 
            latin: 'Allāhumma ṣalli wa sallim ‘alā nabiyyinā Muḥammad.', 
            explanationEs: '¡Oh Allah! Bendice y otorga la paz a nuestro Profeta Muhammad.', 
            count: 10, 
            maxCount: 10 
          }
        ]
      },
      {
        id: 'nawm',
        titleAr: 'أذكار النوم',
        titleEs: 'Azkar antes de Dormir',
        items: [
          {
            text: "يَجْمَعُ كَفَّيْهِ ثُمَّ يَنْفُثُ فِيهِمَا فَيَقْرَأُ فِيهِمَا:--﴿قُلْ هُوَ اللَّهُ أَحَدٌ ۞ اللَّهُ الصَّمَدُ ۞ لَمْ يَلِدْ وَلَمْ يُولَدْ ۞ وَلَمْ يَكُن لَّهُ كُفُوًا أَحَدٌ﴾ -- ﴿قُلْ أَعُوذُ بِرَبِّ الْفَلَقِ ۞ مِن شَرِّ مَا خَلَقَ ۞ وَمِن شَرِّ غَاسِقٍ إِذَا وَقَبَ ۞ وَمِن شَرِّ النَّفَّاثَاتِ فِي الْعُقَدِ ۞ وَمِن شَرِّ حَاسِدٍ إِذَا حَسَدَ﴾ -- ﴿قُلْ أَعُوذُ بِرَبِّ النَّاسِ ۞ مَلِكِ النَّاسِ ۞ إِلَهِ النَّاسِ ۞ مِن شَرِّ الْوَسْوَاسِ الْخَنَّاسِ ۞ الَّذِي يُوَسْوِسُ فِي صُدُورِ النَّاسِ ۞ مِنَ الْجِنَّةِ وَالنَّاسِ﴾\n ثُمَّ يَمْسَحُ بِهِمَا مَا اسْتَطَاعَ مِنْ جَسَدِهِ يَبْدَأُ بِهِمَا عَلَى رَأْسِهِ وَوَجْهِهِ وَمَا أَقْبَلَ مِنْ جَسَدِهِ.",
            latin: "Yajma'u kaffayhi thumma yanfuthu fīhimā fayaqra'u fīhimā: {Qul huwa Allāhu aḥad...}, {Qul a'ūdhu birabbi al-falaq...}, {Qul a'ūdhu birabbi an-nās...}, thumma yamsaḥu bihimā mā istaṭā'a min jasadihi, yabda'u bihimā 'alā ra'sihi wa-wajhihi wa-mā aqbala min jasadihi.",
            explanationEs: "Junta sus palmas, sopla suavemente en ellas y recita: Surah Al-Ikhlas, Al-Falaq y An-Nas. Luego pasa sus manos por las partes de su cuerpo que pueda alcanzar, comenzando por la cabeza, la cara y la parte delantera de su cuerpo.",
            count: 3,
            maxCount: 3,
            note: "يفعل ذلك ثلاث مرات"
          },
          {
            text: "﴿اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ الْحَيُّ الْقَيُّومُ لاَ تَأْخُذُهُ سِنَةٌ وَلاَ نَوْمٌ لَّهُ مَا فِي السَّمَوَاتِ وَمَا فِي الأَرْضِ مَن ذَا الَّذِي يَشْفَعُ عِنْدَهُ إِلاَّ بِإِذْنِهِ يَعْلَمُ مَا بَيْنَ أَيْدِيهِمْ وَمَا خَلْفَهُمْ وَلاَ يُحِيطُونَ بِشَيْءٍ مِّنْ عِلْمِهِ إِلاَّ بِمَا شَاء وَسِعَ كُرْسِيُّهُ السَّمَوَاتِ وَالأَرْضَ وَلاَ يَؤُودُهُ حِفْظُهُمَا وَهُوَ الْعَلِيُّ الْعَظِيمُ﴾",
            latin: "Allāhu lā ilāha illā huwa al-ḥayyu al-qayyūm, lā ta'khudhuhu sinatun wa-lā nawm, lahu mā fīs-samāwāti wa-mā fīl-arḍ, man dhāl-ladhī yashfa'u 'indahu illā bi-idhnih, ya'lamu mā bayna aydīhim wa-mā khalfahum, wa-lā yuḥīṭūna bi-shay'in min 'ilmihi illā bimā shā', wasi'a kursiyyuhu as-samāwāti wal-arḍ, wa-lā ya'ūduhu ḥifẓuhumā, wa-huwa al-'aliyyu al-'aẓīm.",
            explanationEs: "¡Allah! No hay más dios que Él, el Viviente, el Sustentador de toda la creación. Ni la somnolencia ni el sueño le vencen. Suyo es cuanto hay en los cielos y en la tierra. ¿Quién podrá interceder ante Él sin Su permiso? Conoce lo que les depara el futuro y lo que dejaron atrás, mientras que ellos no abarcan nada de Su conocimiento, excepto lo que Él quiere. Su Trono se extiende sobre los cielos y la tierra, y no Le fatiga la preservación de ambos. Él es el Altísimo, el Grandioso.",
            count: 1,
            maxCount: 1,
            note: "آية الكرسي"
          },
          {
            text: "﴿آمَنَ الرَّسُولُ بِمَا أُنزِلَ إِلَيْهِ مِن رَّبِّهِ وَالْمُؤْمِنُونَ كُلٌّ آمَنَ بِاللَّهِ وَمَلآئِكَتِهِ وَكُتُبِهِ وَرُسُلِهِ لاَ نُفَرِّقُ بَيْنَ أَحَدٍ مِّن رُّسُلِهِ وَقَالُواْ سَمِعْنَا وَأَطَعْنَا غُفْرَانَكَ رَبَّنَا وَإِلَيْكَ الْمَصِيرُ * لاَ يُكَلِّفُ اللَّهُ نَفْساً إِلاَّ وُسْعَهَا لَهَا مَا كَسَبَتْ وَعَلَيْهَا مَا اكْتَسَبَتْ رَبَّنَا لاَ تُؤَاخِذْنَا إِن نَّسِينَا أَوْ أَخْطَأْنَا رَبَّنَا وَلاَ تَحْمِلْ عَلَيْنَا إِصْراً كَمَا حَمَلْتَهُ عَلَى الَّذِينَ مِن قَبْلِنَا رَبَّنَا وَلاَ تُحَمِّلْنَا مَا لاَ طَاقَةَ لَنَا بِهِ وَاعْفُ عَنَّا وَاغْفِرْ لَنَا وَارْحَمْنَآ أَنتَ مَوْلاَنَا فَانصُرْنَا عَلَى الْقَوْمِ الْكَافِرِينَ﴾",
            latin: "Āmana ar-rasūlu bimā unzila ilayhi min rabbihi wal-mu'minūn, kullun āmana billāhi wa-malā'ikatihi wa-kutubihi wa-rusulih, lā nufarriqu bayna aḥadin min rusulih, wa-qālū sami'nā wa-aṭa'nā ghufrānaka rabbanā wa-ilayka al-maṣīr. Lā yukallifullāhu nafsan illā wus'ahā, lahā mā kasabat wa-'alayhā mak-tasabat, rabbanā lā tu'ākhidhnā in nasīnā aw akhṭa'nā, rabbanā wa-lā taḥmil 'alaynā iṣran kamā ḥamaltahu 'alāl-ladhīna min qablinā, rabbanā wa-lā tuḥammilnā mā lā ṭāqata lanā bih, wa'fu 'annā waghfir lanā war-ḥamnā, anta mawlānā fanṣurnā 'alāl-qawmil-kāfirīn.",
            explanationEs: "El Mensajero cree en lo que le ha sido revelado por su Señor, y los creyentes también. Todos creen en Allah, en Sus ángeles, en Sus Libros y en Sus mensajeros: 'No hacemos distinción entre ninguno de Sus mensajeros'. Y dicen: 'Escuchamos y obedecemos. Pedimos Tu perdón, Señor nuestro, y a Ti es el retorno'. Allah no exige a ninguna alma más allá de sus posibilidades. Obtendrá el bien que haya ganado y sufrirá el mal que haya merecido. '¡Señor nuestro! No nos castigues si olvidamos o cometemos un error. ¡Señor nuestro! No impongas sobre nosotros una carga como la que impusiste sobre los que nos precedieron. ¡Señor nuestro! No nos impongas una carga superior a nuestras fuerzas. Perdónanos, absuélvenos y ten misericordia de nosotros. Tú eres nuestro Protector, concédenos la victoria sobre el pueblo incrédulo'.",
            count: 1,
            maxCount: 1,
            note: "خواتيم سورة البقرة"
          },
          {
            text: "بِاسْمِكَ رَبِّي وَضَعْتُ جَنْبِي، وَبِكَ أَرْفَعُهُ، فَإِن أَمْسَكْتَ نَفْسِي فارْحَمْهَا، وَإِنْ أَرْسَلْتَهَا فَاحْفَظْهَا، بِمَا تَحْفَظُ بِهِ عِبَادَكَ الصَّالِحِينَ.",
            latin: "Bismika rabbī waḍa'tu janbī wa-bika arfa'uh, fa-in amsakta nafsī far-ḥamhā, wa-in arsaltahā faḥ-faẓhā bimā taḥfaẓu bihi 'ibādaka aṣ-ṣāliḥīn.",
            explanationEs: "En Tu nombre, Señor mío, me acuesto y en Tu nombre me levanto. Si tomas mi alma, ten misericordia de ella; y si la devuelves, protégela como proteges a Tus siervos virtuosos.",
            count: 1,
            maxCount: 1
          },
          {
            text: "اللَّهُمَّ إِنَّكَ خَلَقْتَ نَفْسِي وَأَنْتَ تَوَفَّاهَا، لَكَ مَمَاتُهَا وَمَحْياهَا، إِنْ أَحْيَيْتَهَا فَاحْفَظْهَا، وَإِنْ أَمَتَّهَا فَاغْفِرْ لَهَا. اللَّهُمَّ إِنِّي أَسْأَلُكَ العَافِيَةَ.",
            latin: "Allāhumma innaka khalaqta nafsī wa-anta tawaffāhā, laka mamātuhā wa-maḥyāhā, in aḥyaytahā faḥ-faẓhā, wa-in amattahā fagh-fir lahā. Allāhumma innī as'aluka al-'āfiyah.",
            explanationEs: "¡Oh Allah! Tú has creado mi alma y Tú te la llevas. A Ti pertenece su muerte y su vida. Si la mantienes con vida, protégela; y si la haces morir, perdónala. ¡Oh Allah! Te pido bienestar.",
            count: 1,
            maxCount: 1
          },
          {
            text: "اللَّهُمَّ قِنِي عَذَابَكَ يَوْمَ تَبْعَثُ عِبَادَكَ.",
            latin: "Allāhumma qinī 'adhābaka yawma tab'athu 'ibādak.",
            explanationEs: "¡Oh Allah! Protégeme de Tu castigo el Día en que resucites a Tus siervos.",
            count: 3,
            maxCount: 3,
            note: "ثلاث مرات"
          },
          {
            text: "بِاسْمِكَ اللَّهُمَّ أَمُوتُ وَأَحْيَا.",
            latin: "Bismika allāhumma amūtu wa-aḥyā.",
            explanationEs: "En Tu nombre, ¡oh Allah!, muero y vivo.",
            count: 1,
            maxCount: 1
          },
          {
            text: "سُبْحَانَ اللَّهِ (33)، وَالْحَمْدُ لِلَّهِ (33)، وَاللَّهُ أَكْبَرُ (34).",
            latin: "Subḥān-Allāh (33 veces), Wal-ḥamdu lillāh (33 veces), Wa-Allāhu akbar (34 veces).",
            explanationEs: "Glorificado sea Allah (33 veces), la alabanza sea para Allah (33 veces), Allah es el Más Grande (34 veces).",
            count: 1,
            maxCount: 1,
            note: "تسبيح النوم"
          },
          {
            text: "اللَّهُمَّ رَبَّ السَّمَوَاتِ السَّبْعِ وَرَبَّ الأَرْضِ، وَرَبَّ الْعَرْشِ الْعَظِيمِ، رَبَّنَا وَرَبَّ كُلِّ شَيْءٍ، فَالِقَ الْحَبِّ وَالنَّوَى، وَمُنْزِلَ التَّوْرَاةِ وَالْإِنْجِيلِ، وَالْفُرْقَانِ، أَعُوذُ بِكَ مِنْ شَرِّ كُلِّ شَيْءٍ أَنْتَ آخِذٌ بِنَاصِيَتِهِ. اللَّهُمَّ أَنْتَ الأَوَّلُ فَلَيْسَ قَبْلَكَ شَيْءٌ، وَأَنْتَ الآخِرُ فَلَيسَ بَعْدَكَ شَيْءٌ، وَأَنْتَ الظَّاهِرُ فَلَيْسَ فَوْقَكَ شَيْءٌ، وَأَنْتَ الْبَاطِنُ فَلَيْسَ دُونَكَ شَيْءٌ، اقْضِ عَنَّا الدَّيْنَ وَأَغْنِنَا مِنَ الْفَقْرِ.",
            latin: "Allāhumma rabba as-samāwāti as-sab'i wa-rabba al-'arshi al-'aẓīm, rabbanā wa-rabba kulli shay', fāliqa al-ḥabbi wan-nawā, wa-munzila at-tawrāti wal-injīli wal-furqān, a'ūdhu bika min sharri kulli shay'in anta ākhidhun bi-nāṣiyatih. Allāhumma anta al-awwalu fa-laysa qablaka shay', wa-anta al-ākhiru fa-laysa ba'daka shay', wa-anta aẓ-ẓāhiru fa-laysa fawqaka shay', wa-anta al-bāṭinu fa-laysa dūnaka shay', iqḍi 'annā ad-dayna wa-aghninā mina al-faqr.",
            explanationEs: "¡Oh Allah! Señor de los siete cielos, Señor de la Tierra y Señor del Grandioso Trono, Señor nuestro y Señor de todas las cosas, que haces germinar el grano y el hueso, revelador de la Torá, del Evangelio y del Criterio (el Corán). Me refugio en Ti del mal de toda cosa que esté bajo Tu dominio. ¡Oh Allah! Tú eres el Primero y no hay nada antes de Ti; Tú eres el Último y no hay nada después de Ti; Tú eres el Manifiesto y no hay nada por encima de Ti; Tú eres el Oculto y no hay nada más allá de Ti. Salda nuestras deudas y líbranos de la pobreza.",
            count: 1,
            maxCount: 1
          },
          {
            text: "الْحَمْدُ لِلَّهِ الَّذِي أَطْعَمَنَا وَسَقَانَا، وَكَفَانَا، وَآوَانَا، فَكَمْ مِمَّنْ لاَ كَافِيَ لَهُ وَلاَ مُؤْوِيَ.",
            latin: "Al-ḥamdu lillāhi alladhī aṭ'amanā wa-saqānā, wa-kafānā wa-āwānā, fa-kam mimman lā kāfiya lahu wa-lā mu'wī.",
            explanationEs: "Alabado sea Allah, Quien nos ha alimentado, nos ha dado de beber, nos ha provisto de lo suficiente y nos ha dado refugio; ¡cuántos hay que no tienen quien les provea ni les dé refugio!",
            count: 1,
            maxCount: 1
          },
          {
            text: "اللَّهُمَّ عَالِمَ الغَيْبِ وَالشَّهَادَةِ فَاطِرَ السَّمَوَاتِ وَالْأَرْضِ، رَبَّ كُلِّ شَيْءٍ وَمَلِيكَهُ، أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ أَنْتَ، أَعُوذُ بِكَ مِنْ شَرِّ نَفْسِي، وَمِنْ شَرِّ الشَّيْطانِ وَشِرْكِهِ، وَأَنْ أَقْتَرِفَ عَلَى نَفْسِي سُوءاً، أَوْ أَجُرَّهُ إِلَى مُسْلِمٍ.",
            latin: "Allāhumma 'ālima al-ghaybi wash-shahādah, fāṭira as-samāwāti wal-arḍ, rabba kulli shay'in wa-malīkah, ash-hadu an lā ilāha illā ant, a'ūdhu bika min sharri nafsī, wa-min sharri ash-shayṭāni wa-shirkih, wa-an aqtarifa 'alā nafsī sū'an aw ajurrahū ilā muslim.",
            explanationEs: "¡Oh Allah! Conocedor de lo oculto y de lo manifiesto, Creador de los cielos y de la tierra, Señor y Poseedor de todas las cosas. Testifico que no hay más dios que Tú. Me refugio en Ti del mal de mi propia alma, del mal del Satán y de su idolatría, y de cometer cualquier mal contra mí mismo o causárselo a otro musulmán.",
            count: 1,
            maxCount: 1
          },
          {
            text: "يَقْرَأُ ﴿الم﴾ تَنْزِيل ... سورة السجدة، وَ ﴿تَبَارَكَ الَّذِي بِيَدِهِ... سورة الملك﴾.",
            latin: "Yaqra'u {Alif-Lām-Mīm Tanzīl} Sūrat as-Sajdah, wa {Tabāraka alladhī biyadihi al-mulk} Sūrat al-Mulk.",
            explanationEs: "Recitar la Surah As-Sajdah (Capítulo 32) y la Surah Al-Mulk (Capítulo 67).",
            count: 1,
            maxCount: 1,
            note: "قراءة سورتي السجدة والملك"
          },
          {
            text: "اللَّهُمَّ أَسْلَمْتُ نَفْسِي إِلَيْكَ، وَفَوَّضْتُ أَمْرِي إِلَيْكَ، وَوَجَّهْتُ وَجْهِي إِلَيْكَ، وَأَلْجَأْتُ ظَهْرِي إِلَيْكَ، رَغْبَةً وَرَهْبَةً إِلَيْكَ، لاَ مَلْجَأَ وَلاَ مَنْجَا مِنْكَ إِلاَّ إِلَيْكَ، آمَنْتُ بِكِتَابِكَ الَّذِي أَنْزَلْتَ، وَبِنَبِيِّكَ الَّذِي أَرْسَلْتَ.",
            latin: "Allāhumma aslamtu nafsī ilayk, wa-fawwaḍtu amrī ilayk, wa-wajjahtu wajhī ilayk, wa-alja'tu ẓahrī ilayk, raghbatan wa-rahbatan ilayk, lā malja'a wa-lā manjā minka illā ilayk, āmantu bi-kitābika alladhī anzalt, wa-bi-nabiyyika alladhī arsalt.",
            explanationEs: "¡Oh Allah! Me entrego a Ti, encomiendo mi asunto a Ti, vuelvo mi rostro hacia Ti y me apoyo en Ti, por deseo y temor hacia Ti. No hay refugio ni salvación de Ti sino en Ti. Creo en Tu Libro que has revelado y en Tu Profeta que has enviado.",
            count: 1,
            maxCount: 1,
            note: "يُجعل آخر ما يقول قبل النوم"
          }
        ]
      },
      {
        id: 'istiyqadh',
        titleAr: 'أذكار الاستيقاظ',
        titleEs: 'Azkar al Despertar',
        items: [
  { 
    text: 'الْحَمْدُ للَّهِ الَّذِي أَحْيَانَا بَعْدَ مَا أَمَاتَنَا، وَإِلَيْهِ النُّشُورُ', 
    latin: 'Alhamdu lillāhi-lladhī aḥyānā baʿda mā amātanā wa-ilayhi-n-nushūr.', 
    explanationEs: 'Alabado sea Alá, Quien nos devolvió la vida tras habernos hecho morir (dormir), y hacia Él es el retorno.', 
    count: 1, 
    maxCount: 1 
  },
  { 
    text: 'لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَريكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، سُبْحَانَ اللَّهِ، وَالْحَمْدُ للَّهِ، وَلاَ إِلَهَ إِلاَّ اللَّهُ، وَاللَّهُ أَكبَرُ، وَلاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ الْعَلِيِّ الْعَظِيمِ، رَبِّ اغْفرْ لِي ', 
    latin: 'Lā ilāha illa-llāhu waḥdahu lā sharīka lah, lahu-l-mulku wa-lahu-l-ḥamd, wa-huwa ʿalā kulli shayʾin qadīr. Subḥāna-llāhi, wa-l-ḥamdu lillāhi, wa-lā ilāha illa-llāhu, wa-llāhu akbar, wa-lā ḥawla wa-lā quwwata illā billāhi-l-ʿaliyyi-l-ʿaẓīm. Rabbi-ghfir lī.', 
    explanationEs: 'No hay más divinidad digna de adoración excepto Alá, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Todopoderoso. Glorificado sea Alá, alabado sea Alá, no hay más divinidad que Alá, Alá es el Más Grande, y no hay fuerza ni poder excepto en Alá, el Altísimo, el Supremo. ¡Señor mío, perdóname!', 
    count: 1, 
    maxCount: 1 
  },
  { 
    text: 'لْحَمْدُ لِلَّهِ الَّذِي عَافَانِي فِي جَسَدِي، وَرَدَّ عَلَيَّ رُوحِي، وَأَذِنَ لي بِذِكْرِهِ', 
    latin: 'Alhamdu lillāhi-lladhī ʿāfānī fī jasadī, wa-radda ʿalayya rūḥī, wa-adhina lī bi-dhikrih.', 
    explanationEs: 'Alabado sea Alá, Quien sanó mi cuerpo, me devolvió mi alma y me permitió recordarle.', 
    count: 1, 
    maxCount: 1 
  },
  { 
    text: '﴿ إِنَّ فِي خَلْقِ السَّمَوَاتِ وَالأَرْضِ وَاخْتِلاَفِ اللَّيْلِ وَالنَّهَارِ لَآيَاتٍ لأُوْلِي الألْبَابِ * الَّذِينَ يَذْكُرُونَ اللَّهَ قِيَاماً وَقُعُوداً وَعَلَىَ جُنُوبِهِمْ وَيَتَفَكَّرُونَ فِي خَلْقِ السَّمَوَاتِ وَالأَرْضِ رَبَّنَا مَا خَلَقْتَ هَذا بَاطِلاً سُبْحَانَكَ فَقِنَا عَذَابَ النَّارِ* رَبَّنَا إِنَّكَ مَن تُدْخِلِ النَّارَ فَقَدْ أَخْزَيْتَهُ وَمَا لِلظَّالِمِينَ مِنْ أَنصَارٍ* رَّبَّنَا إِنَّنَا سَمِعْنَا مُنَادِياً يُنَادِي Lِلإِيمَانِ أَنْ آمِنُواْ بِرَبِّكُمْ فَآمَنَّا رَبَّنَا فَاغْفِرْ لَنَا ذُنُوبَنَا وَكَفِّرْ عَنَّا سَيِّئَاتِنَا وَتَوَفَّنَا مَعَ الأبْرَارِ* رَبَّنَا وَآتِنَا مَا وَعَدتَّنَا عَلَى رُسُلِكَ وَلاَ تُخْزِنَا يَوْمَ الْقِيَامَةِ إِنَّكَ لاَ تُخْلِفُ الْمِيعَادَ* فَاسْتَجَابَ لَهُمْ رَبُّهُمْ أَنِّي لاَ أُضِيعُ عَمَلَ عَامِلٍ مِّنكُم مِّن ذَكَرٍ أَوْ أُنثَى بَعْضُكُم مِّن بَعْضٍ فَالَّذِينَ هَاجَرُواْ وَأُخْرِجُواْ مِن دِيَارِهِمْ وَأُوذُواْ فِي سَبِيلِي وَقَاتَلُواْ وَقُتِلُواْ لأُكَفِّرَنَّ عَنْهُمْ سَيِّئَاتِهِمْ وَلأُدْخِلَنَّهُمْ جَنَّاتٍ تَجْرِي مِن تَحْتِهَا الأَنْهَارُ ثَوَاباً مِّن عِندِ اللَّهِ وَاللَّهُ عِندَهُ حُسْنُ الثَّوَابِ * لاَ يَغُرَّنَّكَ تَقَلُّبُ الَّذِينَ كَفَرُواْ فِي الْبِلاَدِ * مَتَاعٌ قَلِيلٌ ثُمَّ مَأْوَاهُمْ جَهَنَّمُ وَبِئْسَ الْمِهَادُ * لَكِنِ الَّذِينَ اتَّقَوْاْ رَبَّهُمْ لَهُمْ جَنَّاتٍ تَجْرِي مِنْ تَحْتِهَا الأَنْهَارُ خَالِدِينَ فِيهَا نُزُلاً مِّنْ عِندِ اللَّهِ وَمَا عِندَ اللَّهِ خَيْرٌ لِّلأَبْرَارِ * وَإِنَّ مِنْ أَهْلِ الْكِتَابِ لَمَن يُؤْمِنُ بِاللَّهِ وَمَا أُنزِلَ إِلَيْكُمْ وَمَآ أُنزِلَ إِلَيْهِمْ خَاشِعِينَ لِلَّهِ لاَ يَشْتَرُونَ بِآيَاتِ اللَّهِ ثَمَناً قَلِيلاً أُوْلَئِكَ لَهُمْ أَجْرُهُمْ عِندَ رَبِّهِم| إِنَّ اللَّهَ سَرِيعُ الْحِسَابِ*يَا أَيُّهَا الَّذِينَ آمَنُواْ اصْبِرُواْ وَصَابِرُواْ وَرَابِطُواْ وَاتَّقُواْ اللَّهَ لَعَلَّكُمْ تُفْلِحُونَ ﴾', 
    latin: 'Inna fī khalqi-s-samāwāti wa-l-arḍi wa-khtilāfi-l-layli wa-n-nahāri la-āyātin li-ulī-l-albāb. Alladhīna yadhkurūna-llāha qiyāman wa-quʿūdan wa-ʿalā junūbihim wa-yatafakkarūna fī khalqi-s-samāwāti wa-l-arḍ, Rabbanā mā khalaqta hādhā bāṭilan subḥānaka fa-qinā ʿadhāba-n-nār... [Versículos 190-200 de Al-Imran]', 
    explanationEs: 'En la creación de los cielos y de la tierra y en la sucesión de la noche y el día hay, ciertamente, signos para los dotados de intelecto. Aquellos que recuerdan a Alá de pie, sentados y acostados, y meditan sobre la creación de los cielos y de la tierra: "¡Señor nuestro! No has creado todo esto en vano..." (Corán 3:190-200).', 
    count: 1, 
    maxCount: 1 
  }
]
      },
      {
     id: "hisn_2",
     titleAr: "دعاءُ لُبْسِ الثَّوْبِ",
     titleEs: "Súplica al vestirse",
     items: [
      {
         text: "الْحَمْدُ لِلَّهِ الَّذِي كَسَانِي هَذَا (الثَّوْبَ) وَرَزَقَنِيهِ مِنْ غَيْرِ حَوْلٍ مِنِّي وَلاَ قُوَّةٍ.",
         latin: "Al-ḥamdu lillāhi alladhī kasānī hādhā (ath-thawba) wa razaqanīhi min ghayri ḥawlin minnī wa lā quwwah.",
         explanationEs: "Alabado sea Al-lah, Quien me ha vestido con esta (prenda) y me la ha concedido sin que de mi parte haya habido fuerza ni poder.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_3",
     titleAr: "دعاءُ لُبْسِ الثَّوْبِ الجَدِيدِ",
     titleEs: "Súplica al vestirse con ropa nueva",
     items: [
      {
         text: "اللَّهُمَّ لَكَ الْحَمْدُ أَنْتَ كَسَوْتَنِيهِ، أَسْأَلُكَ مِنْ خَيْرِهِ وَخَيْرِ مَا صُنِعَ لَهُ، وَأَعُوذُ بِكَ مِنْ شَرِّهِ وَشَرِّ مَا صُنِعَ لَهُ.",
         latin: "Allāhumma laka al-ḥamdu anta kasawtanīh, as'aluka min khayrihi wa khayri mā ṣuniʿa lah, wa aʿūdhu bika min sharrihi wa sharri mā ṣuniʿa lah.",
         explanationEs: "¡Oh Al-lah! A Ti pertenecen las alabanzas. Tú me has vestido con ella. Te pido de su bien y del bien para el que fue hecha, y me refugio en Ti de su mal y del mal para el que fue hecha.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_4",
     titleAr: "الدُّعَاءُ لِمَنْ لَبِسَ ثَوْباً جَدِيداً",
     titleEs: "Súplica por alguien que estrena ropa nueva",
     items: [
      {
         text: "تُبْلِي وَيُخْلِفُ اللَّهُ تَعَالَى.",
         latin: "Tublī wa yukhlifu Allāhu taʿālā.",
         explanationEs: "Que la desgastes (con larga vida) y que Al-lah Altísimo te la reemplace.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اِلْبَسْ جَدِيداً وَعِشْ حَمِيداً وَمُتْ شَهِيداً.",
         latin: "Ilbas jadīdan, wa ʿish ḥamīdan, wa mut shahīdā.",
         explanationEs: "Vístete de nuevo, vive de manera elogiable y muere como mártir.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_5",
     titleAr: "مَا يَقُولُ إِذَا وَضَعَ ثَوْبَهُ",
     titleEs: "Lo que se dice al quitarse la ropa",
     items: [
      {
         text: "بِسْمِ اللَّهِ.",
         latin: "Bismillāh.",
         explanationEs: "En el nombre de Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_6",
     titleAr: "دُعَاءُ دُخُولِ الخَلاَءِ",
     titleEs: "Súplica al entrar al baño/sanitario",
     items: [
      {
         text: "[بِسْمِ اللَّهِ] اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْخُبْثِ وَالْخَبَائِثِ.",
         latin: "[Bismillāh] Allāhumma innī aʿūdhu bika mina al-khubthi wal-khabā'ith.",
         explanationEs: "[En el nombre de Al-lah]. ¡Oh Al-lah! Me refugio en Ti de los demonios masculinos y femeninos (del mal y de las impurezas).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_7",
     titleAr: "دُعَاءُ الخُرُوجِ مِنَ الخَلاَءِ",
     titleEs: "Súplica al salir del baño/sanitario",
     items: [
      {
         text: "غُفْرَانَكَ.",
         latin: "Ghufrānak.",
         explanationEs: "Pido Tu perdón.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_8",
     titleAr: "الذِّكْرُ قَبْلَ الوُضُوءِ",
     titleEs: "Súplica antes de realizar las abluciones (Wudu)",
     items: [
      {
         text: "بِسْمِ اللَّهِ.",
         latin: "Bismillāh.",
         explanationEs: "En el nombre de Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_9",
     titleAr: "الذِّكْرُ بَعْدَ الفَرَاغِ مِنَ الوُضُوءِ",
     titleEs: "Súplica al terminar las abluciones (Wudu)",
     items: [
      {
         text: "أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ وَأَشْهَدُ أَنَّ مُحَمَّداً عَبْدُهُ وَرَسُولُهُ.",
         latin: "Ashhadu an lā ilāha illā Allāhu waḥdahu lā sharīka lahu wa ashhadu anna Muḥammadan ʿabduhu wa rasūluh.",
         explanationEs: "Atestiguo que no hay más divinidad que Al-lah, Único, sin asociados, y atestiguo que Muhammad es Su siervo y mensajero.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اجْعَلْنِي مِنَ التَّوَّابِينَ وَاجْعَلْنِي مِنَ الْمُتَطَهِّرِينَ.",
         latin: "Allāhumma ijʿalnī mina at-tawwābīna wa ijʿalnī mina al-mutaṭahhirīn.",
         explanationEs: "¡Oh Al-lah! Hazme de los que se arrepienten y hazme de los que se purifican.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبْحَانَكَ اللَّهُمَّ وَبِحَمْدِكَ، أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ أَنْتَ، أَسْتَغْفِرُكَ وَأَتُوبُ إِلَيْكَ.",
         latin: "Subḥānaka Allāhumma wa bi-ḥamdika, ashhadu an lā ilāha illā anta, astaghfiruka wa atūbu ilayk.",
         explanationEs: "Glorificado seas, ¡oh Al-lah!, y alabado seas. Atestiguo que no hay más divinidad excepto Tú, pido Tu perdón y me arrepiento ante Ti.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_10",
     titleAr: "الذِّكْرُ عِنْدَ الخُرُوجِ مِنَ المَنْزِلِ",
     titleEs: "Súplica al salir de casa",
     items: [
      {
         text: "بِسْمِ اللَّهِ، تَوَكَّلْتُ عَلَى اللَّهِ، وَلاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
         latin: "Bismillāhi, tawakkaltu ʿalā Allāh, wa lā ḥawla wa lā quwwata illā billāh.",
         explanationEs: "En el nombre de Al-lah, me encomiendo a Al-lah; no hay fuerza ni poder sino en Al-lah.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ أَنْ أَضِلَّ، أَوْ أُضَلَّ، أَوْ أَزِلَّ، أَوْ أُزَلَّ، أَوْ أَظْلِمَ، أَوْ أُظْلَمَ، أَوْ أَجْهَلَ، أَوْ يُجْهَلَ عَلَيَّ.",
         latin: "Allāhumma innī aʿūdhu bika an aḍilla, aw uḍalla, aw azilla, aw uzalla, aw aẓlima, aw uẓlama, aw ajhala, aw yujhala ʿalayy.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti para no extraviarme ni ser extraviado, no resbalar (cometer falta) ni ser hecho resbalar, no oprimir ni ser oprimido, y no actuar con ignorancia ni ser tratado con ignorancia.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_11",
     titleAr: "الذِّكْرُ عِنْدَ دُخُولِ المَنْزِلِ",
     titleEs: "Súplica al entrar a casa",
     items: [
      {
         text: "بِسْمِ اللَّهِ وَلَجْنَا، وَبِسْمِ اللَّهِ خَرَجْنَا، وَعَلَى اللَّهِ رَبِّنَا تَوَكَّلْنَا (ثُمَّ لِيُسَلِّمْ عَلَى أَهْلِهِ).",
         latin: "Bismillāhi walajnā, wa bismillāhi kharajnā, wa ʿalā Allāhi rabbinā tawakkalnā (luego saluda a su familia).",
         explanationEs: "En el nombre de Al-lah entramos y en el nombre de Al-lah salimos, y en Al-lah nuestro Señor confiamos. (Luego debe saludar a su familia).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_12",
     titleAr: "دُعَاءُ الذَّهَابِ إِلَى المَسْجِدِ",
     titleEs: "Súplica al ir a la mezquita",
     items: [
      {
         text: "اللَّهُمَّ اجْعَلْ فِي قَلْبِي نُوراً، وَفِي لِسَانِي نُوراً، وَفِي سَمْعِي نُوراً، وَفِي بَصَرِي نُوراً، وَمِنْ فَوْقِي نُوراً، وَمِنْ تَحْتِي نُوراً، وَعَنْ يَمِينِي نُوراً، وَعَنْ شِمَالِي نُوراً، وَمِنْ أَمَامِي نُوراً، وَمِنْ خَلْفِي نُوراً، وَاجْعَلْ فِي نَفْسِي نُوراً، وَأَعْظِمْ لِي نُوراً، وَعَظِّمْ لِي نُوراً، وَاجْعَلْ لِي نُوراً، وَاجْعَلْنِي نُوراً، اللَّهُمَّ أَعْطِنِي نُوراً، وَاجْعَلْ فِي عَصَبِي نُوراً، وَفِي لَحْمِي نُوراً، وَفِي دَمِي نُوراً، وَفِي شَعْرِي نُوراً، وَفِي بَشَرِي نُوراً، اللَّهُمَّ اجْعَلْ لِي نُوراً فِي قَبْرِي... وَنُوراً فِي عِظَامِي، وَزِدْنِي نُوراً، وَزِدْنِي نُوراً، وَزِدْنِي نُوراً، وَهَبْ لِي نُوراً عَلَى نُورٍ.",
     latin: "Allāhumma ijʿal fī qalbī nūrā, wa fī lisānī nūrā, wa fī samʿī nūrā, wa fī baṣarī nūrā, wa min fawqī nūrā, wa min taḥtī nūrā, wa ʿan yamīnī nūrā, wa ʿan shimālī nūrā, wa min amāmī nūrā, wa min khalfī nūrā, wa ijʿal fī nafsī nūrā, wa aʿẓim lī nūrā, wa ʿaẓẓim lī nūrā, wa ijʿal lī nūrā, wa ijʿalnī nūrā, Allāhumma aʿṭinī nūrā, wa ijʿal fī ʿaṣabī nūrā, wa fī laḥmī nūrā, wa fī damī nūrā, wa fī shaʿrī nūrā, wa fī basharī nūrā, Allāhumma ijʿal lī nūrān fī qabrī... wa nūrān fī ʿiẓāmī, wa zidnī nūrā, wa zidnī nūrā, wa zidnī nūrā, wa hab lī nūrān ʿalā nūr.",
     explanationEs: "¡Oh Al-lah! Pon luz en mi corazón, luz en mi lengua, luz en mi oído, luz en mi vista, luz por encima de mí, luz por debajo de mí, luz a mi derecha, luz a mi izquierda, luz delante de mí y luz detrás de mí. Pon luz en mi alma, magnifica para mí la luz, aumenta para mí la luz, haz para mí una luz y hazme luz. ¡Oh Al-lah! Dame luz, pon luz en mis nervios, luz en mi carne, luz en mi sangre, luz en mi cabello y luz en mi piel. ¡Oh Al-lah! Pon para mí luz en mi tumba y luz en mis huesos, auméntame la luz, auméntame la luz, auméntame la luz y concédeme luz sobre luz.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_13",
     titleAr: "دُعَاءُ دُخُولِ المَسْجِدِ",
     titleEs: "Súplica al entrar a la mezquita",
     items: [
      {
         text: "يَبْدَأُ بِرِجْلِهِ الْيُمْنَى، وَيَقُولُ: أَعُوذُ بِاللَّهِ العَظِيمِ، وَبِوَجْهِهِ الْكَرِيمِ، وَسُلْطَانِهِ الْقَدِيمِ، مِنَ الشَّيْطَانِ الرَّجِيمِ، [بِسْمِ اللَّهِ، وَالصَّلَاةُ وَالسَّلَامُ عَلَى رَسُولِ اللَّهِ]، اللَّهُمَّ افْتَحْ لِي أَبْوَابَ رَحْمَتِكَ.",
         latin: "(Empieza con el pie derecho y dice): Aʿūdhu billāhi al-ʿaẓīm, wa bi-wajhihi al-karīm, wa sulṭānihi al-qadīm, mina ash-shayṭāni ar-rajīm. [Bismillāhi, waṣ-ṣalātu was-salāmu ʿalā rasūlillāh], Allāhumma iftaḥ lī abwāba raḥmatik.",
         explanationEs: "Entra con el pie derecho y dice: Me refugio en Al-lah el Grandioso, en Su noble Rostro y en Su poder eterno, del Demonio repudiado. [En el nombre de Al-lah, y que las bendiciones y la paz sean sobre el Mensajero de Al-lah]. ¡Oh Al-lah! Ábreme las puertas de Tu misericordia.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_14",
     titleAr: "دُعَاءُ الخُرُوجِ مِنَ المَسْجِدِ",
     titleEs: "Súplica al salir de la mezquita",
     items: [
      {
         text: "يَبْدَأُ بِرِجْلِهِ الْيُسْرَى وَيَقُولُ: بِسْمِ اللَّهِ وَالصَّلاَةُ وَالسَّلاَمُ عَلَى رَسُولِ اللَّهِ، اللَّهُمَّ إِنِّي أَسْأَلُكَ مِنْ فَضْلِكَ، اللَّهُمَّ اعْصِمْنِي مِنَ الشَّيْطَانِ الرَّجِيمِ.",
         latin: "(Empieza con el pie izquierdo y dice): Bismillāhi waṣ-ṣalātu was-salāmu ʿalā rasūlillāh, Allāhumma innī as'aluka min faḍlik, Allāhumma iʿṣimnī mina ash-shayṭāni ar-rajīm.",
         explanationEs: "Sale con el pie izquierdo y dice: En el nombre de Al-lah, y que las bendiciones y la paz sean sobre el Mensajero de Al-lah. ¡Oh Al-lah! Te pido de Tu favor. ¡Oh Al-lah! Protégeme del Demonio repudiado.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_15",
     titleAr: "أَذْكَارُ الأَذَانِ",
     titleEs: "Súplicas relacionadas con la llamada a la oración (Adhán)",
     items: [
      {
         text: "يَقُولُ مِثْلَ مَا يَقُولُ الْمُؤَذِّنُ إِلاَّ فِي (حَيَّ عَلَى الصَّلاَةِ) وَ(حَيَّ عَلَى الْفَلاَحِ) فَيَقُولُ: لاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
         latin: "Repite lo que dice el muecín, excepto en 'Ḥayya ʿalā ṣ-ṣalāh' y 'Ḥayya ʿalā l-falāḥ', donde dice: Lā ḥawla wa lā quwwata illā billāh.",
         explanationEs: "Repite las mismas palabras que el muecín (llamador a la oración), excepto al escuchar 'Acudid a la oración' y 'Acudid al éxito', donde debe decir: No hay fuerza ni poder sino en Al-lah.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَأَنَا أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ وَأَنَّ مُحَمَّداً عَبْدُهُ وَرَسُولُهُ، رَضِيتُ بِاللَّهِ رَبَّاً، وَبِمُحَمَّدٍ رَسُولاً، وَبِالإِسْلاَمِ دِيناً. (يَقُولُ ذَلِكَ عَقِبَ تَشَهُّدِ الْمُؤَذِّنِ).",
         latin: "Wa anā ashhadu an lā ilāha illā Allāhu waḥdahu lā sharīka lahu wa anna Muḥammadan ʿabduhu wa rasūluh, raḍītu billāhi rabbā, wa bi-Muḥammadin rasūlā, wa bil-islāmi dīnā.",
         explanationEs: "Y yo atestiguo que no hay más divinidad que Al-lah, Único, sin asociados, y que Muhammad es Su siervo y mensajero. Acepto complacido a Al-lah como Señor, a Muhammad como Mensajero y al Islam como religión. (Dice esto tras la atestiguación del muecín).",
         count: 1,
         maxCount: 1
      },
      {
         text: "يُصَلِّي عَلَى النَّبِيِّ صلى الله عليه وسلم بَعْدَ فَرَاغِهِ مِنْ إِجَابَةِ الْمُؤَذِّنِ.",
         latin: "Ṣallā Allāhu ʿalā an-nabiyyi ṣallā Allāhu ʿalayhi wa sallam baʿda farāghihi min ijābati al-mu'adhdhin.",
         explanationEs: "Invoca bendiciones sobre el Profeta (que la paz y las bendiciones de Al-lah sean con él) tras responder a la llamada del muecín.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ رَبَّ هَذِهِ الدَّعْوَةِ التَّامَّةِ، وَالصَّلاَةِ الْقَائِمَةِ، آتِ مُحَمَّداً الْوَسِيلَةَ وَالْفَضِيلَةَ، وَابْعَثْهُ مَقَاماً مَحْمُوداً الَّذِي وَعَدْتَهُ، [إِنَّكَ لاَ تُخْلِفُ الْمِيعَادَ].",
         latin: "Allāhumma rabba hādhihi ad-daʿwati at-tāmmah, waṣ-ṣalāti al-qā'imah, āti Muḥammadan al-wasīlata wal-faḍīlah, wabʿathhu maqāman maḥmūdan alladhī waʿadtah, [innaka lā tukhlifu al-mīʿād].",
         explanationEs: "¡Oh Al-lah, Señor de esta llamada perfecta y de la oración que se va a celebrar! Concede a Muhammad la cercanía (Al-Wasilah) y la excelencia, y resucítalo en la posición honorable que le has prometido. [Ciertamente Tú no faltas a Tu promesa].",
         count: 1,
         maxCount: 1
      },
      {
         text: "يَدْعُو لِنَفْسِهِ بَيْنَ الأَذَانِ وَالإِقَامَةِ فَإِنَّ الدُّعَاءَ حِينَئِذٍ لاَ يُرَدُّ.",
         latin: "Yadʿū li-nafsihi bayna al-adhāni wal-iqāmah, fa-inna ad-duʿā'a ḥīna'idhin lā yuradd.",
         explanationEs: "Súplica por sí mismo entre la llamada a la oración (Adhán) y el inicio de la misma (Iqámah), pues la súplica en ese momento no es rechazada.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_16",
     titleAr: "دعاء استفتاح الصلاة",
     titleEs: "Súplicas de apertura de la oración",
     noteAr: "يقال هذا الدعاء في بداية الصلاة بعد تكبيرة الإحرام وقبل قراءة الفاتحة",
     noteEs: "Esta súplica se dice al comienzo de la oración, después del Takbir inicial y antes de recitar Al-Fatihah",
     items: [
      {
         text: "اللَّهُمَّ بَاعِدْ بَيْنِي وَبَيْنَ خَطَايَايَ كَمَا بَاعَدْتَ بَيْنَ الْمَشْرِقِ وَالْمَغْرِبِ، اللَّهُمَّ نَقِّنِي مِنْ خَطَايَايَ كَمَا يُنَقَّى الثَّوْبُ الْأَبْيَضُ مِنَ الدَّنَسِ، اللَّهُمَّ اغْسِلْني مِنْ خَطَايَايَ، بِالثَّلْجِ وَالْماءِ وَالْبَرَدِ.",
         latin: "Allāhumma bā‘id baynī wa bayna khaṭāyāya kamā bā‘adta baynal-mashriqi wal-maghrib, Allāhumma naqqinī min khaṭāyāya kamā yunaqqath-thawbul-abyaḍu minad-danas, Allāhummag-silnī min khaṭāyāya bith-thalji wal-mā'i wal-barad.",
         explanationEs: "¡Oh Allah! Aléjame de mis pecados tanto como has alejado el Oriente del Occidente. ¡Oh Allah! Purifícame de mis pecados tal como se limpia una vestidura blanca de la suciedad. ¡Oh Allah! Lava mis pecados con nieve, agua y granizo.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبْحانَكَ اللَّهُمَّ وَبِحَمْدِكَ، وَتَبارَكَ اسْمُكَ، وَتَعَالَى جَدُّكَ، وَلاَ إِلَهَ غَيْرُكَ.",
         latin: "Subḥānakallāhumma wa bi-ḥamdika, wa tabārakasmuka, wa ta‘ālā jadduka, wa lā ilāha ghayruka.",
         explanationEs: "Glorificado seas, ¡Oh Allah!, y alabado seas. Bendito sea Tu Nombre, exaltada sea Tu Majestad, y no hay más divinidad con derecho a ser adorada excepto Tú.",
         count: 1,
         maxCount: 1
      },
      {
     text: "وَجَّهْتُ وَجْهِيَ لِلَّذِي فَطَرَ السَّمَوَاتِ وَالأَرْضَ حَنِيفَاً وَمَا أَنَا مِنَ الْمُشْرِكِينَ، إِنَّ صَلاَتِي، وَنُسُكِي، وَمَحْيَايَ، وَمَمَاتِي لِلَّهِ رَبِّ الْعَالَمِينَ، لاَ شَرِيكَ لَهُ وَبِذَلِكَ أُمِرْتُ وَأَنَا مِنَ الْمُسْلِمِينَ. اللَّهُمَّ أَنْتَ المَلِكُ لاَ إِلَهَ إِلاَّ أَنْتَ، أَنْتَ رَبِّي وَأَنَا عَبْدُكَ، ظَلَمْتُ نَفْسِي وَاعْتَرَفْتُ بِذَنْبِي فَاغْفِرْ لِي ذُنُوبي جَمِيعَاً إِنَّهُ لاَ يَغْفِرُ الذُّنوبَ إِلاَّ أَنْتَ. وَاهْدِنِي لِأَحْسَنِ الأَخْلاقِ لاَ يَهْدِي لِأَحْسَنِها إِلاَّ أَنْتَ، وَاصْرِفْ عَنِّي سَيِّئَهَا، لاَ يَصْرِفُ عَنِّي سَيِّئَهَا إِلاَّ أَنْتَ، لَبَّيْكَ وَسَعْدَيْكَ، وَالخَيْرُ كُلُّهُ بِيَدَيْكَ، وَالشَّرُّ لَيْسَ إِلَيْكَ، أَنَا بِكَ وَإِلَيْكَ، تَبارَكْتَ وَتَعَالَيْتَ، أَسْتَغْفِرُكَ وَأَتوبُ إِلَيْكَ.",
     latin: "Wajjahtu wajhiya lilladhī faṭara as-samāwāti wal-arḍa ḥanīfan wa mā anā mina al-mushrikīn. Inna ṣalātī, wa nusukī, wa maḥyāya, wa mamātī lillāhi rabbi al-ʿālamīn, lā sharīka lahu wa bidhālika umirtu wa anā mina al-muslimīn. Allāhumma anta al-maliku lā ilāha illā ant, anta rabbī wa anā ʿabduk, ẓalamtu nafsī waʿtaraftu bidhanbī faghfir lī dhunūbī jamīʿan innahu lā yaghfiru adhdhunūba illā ant. Wahdinī li-aḥsani al-akhlāqi lā yahdī li-aḥsanihā illā ant, waṣrif ʿannī sayyi'ahā lā yaṣrifu ʿannī sayyi'ahā illā ant, labbayka wa saʿdayk, wal-khayru kulluhu bi-yadayk, wash-sharru laysa ilayk, anā bika wa ilayk, tabārakta wa taʿālayt, astaghfiruka wa atūbu ilayk.",
     explanationEs: "He orientado mi rostro francamente hacia Aquel que creó los cielos y la tierra, y no soy de los asociadores. Ciertamente mi oración, mis sacrificios, mi vida y mi muerte pertenecen a Al-lah, Señor de los mundos, Sin asociados. Esto se me ha ordenado y soy de los musulmanes. ¡Oh Al-lah! Tú eres el Rey, no hay más divinidad excepto Tú. Tú eres mi Señor y yo soy Tu siervo. He sido injusto conmigo mismo y reconozco mi pecado, perdóname todos mis pecados, pues nadie perdona los pecados excepto Tú. Guíame hacia el mejor carácter, pues nadie guía hacia él excepto Tú, y aparta de mí el mal carácter, pues nadie lo aparta de mí excepto Tú. Heme aquí a Tu servicio, todo el bien está en Tus manos y el mal no proviene de Ti. Exaltado y Enaltecido seas, pido Tu perdón y me arrepiento ante Ti.",
     count: 1,
     maxCount: 1
  },
  {
     text: "اللَّهُمَّ رَبَّ جِبْرَائِيلَ، وَمِيْكَائِيلَ، وَإِسْرَافِيلَ، فَاطِرَ السَّمَوَاتِ وَالأَرْضِ، عَالِمَ الغَيْبِ وَالشَّهَادَةِ أَنْتَ تَحْكُمُ بَيْنَ عِبَادِكَ فِيمَا كَانُوا فِيهِ يَخْتَلِفُونَ. اهْدِنِي لِمَا اخْتُلِفَ فِيهِ مِنَ الْحَقِّ بِإِذْنِكَ إِنَّكَ تَهْدِي مَنْ تَشَاءُ إِلَى صِرَاطٍ مُسْتَقيمٍ.",
     latin: "Allāhumma rabba Jibrā'īla, wa Mīkā'īla, wa Isrāfīl, fāṭira as-samāwāti wal-arḍ, ʿālima al-ghaybi wash-shahādah, anta taḥkumu bayna ʿibādika fīmā kānū fīhi yakhtalifūn. Ihdinī limākhtulifa fīhi mina al-ḥaqqi bi-idhnik, innaka tahdī man tashā'u ilā ṣirāṭin mustaqīm.",
     explanationEs: "¡Oh Al-lah! Señor de Gabriel, Miguel e Israfil, Creador de los cielos y de la tierra, Conocedor de lo oculto y de lo manifiesto. Tú juzgas entre Tus siervos sobre aquello en lo que diferían. Guíame, con Tu permiso, hacia la verdad en aquello en lo que discrepan, pues Tú guías a quien quieres hacia el camino recto.",
     count: 1,
     maxCount: 1
  },
  {
     text: "اللَّهُ أَكْبَرُ كَبِيرَاً، اللَّهُ أَكْبَرُ كَبِيراً، اللَّهُ أَكْبَرُ كَبِيراً، وَالْحَمْدُ لِلَّهِ كَثيراً، وَالْحَمْدُ لِلَّهِ كَثيراً، وَالْحَمْدُ لِلَّهِ كَثيراً، وَسُبْحَانَ اللَّهِ بُكْرَةً وَأَصِيلاً (ثلاثاً). أَعُوذُ بِاللَّهِ مِنَ الشَّيْطَانِ: مِنْ نَفْخِهِ، وَنَفْثِهِ، وَهَمْزِهِ.",
     latin: "Allāhu akbaru kabīrā, Allāhu akbaru kabīrā, Allāhu akbaru kabīrā, wal-ḥamdu lillāhi kathīrā, wal-ḥamdu lillāhi kathīrā, wal-ḥamdu lillāhi kathīrā, wa subḥāna Allāhi bukratan wa aṣīlā (tres veces). Aʿūdhu billāhi mina ash-shayṭāni: min nafkhihi, wa nafthihi, wa hamzih.",
     explanationEs: "Al-lah es el más Grande en grandeza (x3), y alabado sea Al-lah en abundancia (x3), y glorificado sea Al-lah por la mañana y por la tarde (x3). Me refugio en Al-lah del Demonio: de su orgullo (soplo), de su poesía/hechicería (saliva) y de su locura/susurros.",
     count: 1,
     maxCount: 1
  },
  {
     text: "اللَّهُمَّ لَكَ الْحَمْدُ، أَنْتَ نُورُ السَّمَوَاتِ وَالأَرْضِ وَمَنْ فِيهِنَّ، وَلَكَ الْحَمْدُ أَنْتَ قَيِّمُ السَّمَوَاتِ وَالأَرْضِ وَمَنْ فِيهِنَّ، وَلَكَ الْحَمْدُ أَنْتَ رَبُّ السَّمَواتِ وَالأَرْضِ وَمَنْ فِيهِنَّ، وَلَكَ الْحَمْدُ لَكَ مُلْكُ السَّمَوَاتِ وَالأَرْضِ وَمَنْ فِيهِنَّ، وَلَكَ الْحَمْدُ أَنْتَ مَلِكُ السَّمَوَاتِ وَالأَرْضِ، وَلَكَ الْحَمْدُ، أَنْتَ الْحَقُّ، وَوَعْدُكَ الْحَقُّ، وَقَوْلُكَ الْحَقُّ، وَلِقاؤُكَ الْحَقُّ، وَالْجَنَّةُ حَقٌّ، وَالنَّارُ حَقٌّ، وَالنَّبِيُّونَ حَقٌّ، وَمحَمَّدٌ صلى الله عليه وسلم حَقٌّ، وَالسّاعَةُ حَقٌّ، اللَّهُمَّ لَكَ أَسْلَمتُ، وَعَلَيْكَ تَوَكَّلْتُ، وَبِكَ آمَنْتُ، وَإِلَيْكَ أَنَبْتُ، وَبِكَ خاصَمْتُ، وَإِلَيْكَ حاكَمْتُ. فَاغْفِرْ لِي مَا قَدَّمْتُ، وَمَا أَخَّرْتُ، وَمَا أَسْرَرْتُ، وَمَا أَعْلَنْتُ، وَمَا أَنْتَ أَعْلَمُ بِهِ مِنِّي، أَنْتَ المُقَدِّمُ، وَأَنْتَ المُؤَخِّرُ لاَ إِلَهَ إِلاَّ أَنْتَ، أَنْتَ إِلَهِي لاَ إِلَهَ إِلاَّ أَنْتَ، وَلاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
     latin: "Allāhumma laka al-ḥamd, anta nūru as-samāwāti wal-arḍi wa man fīhin, wa laka al-ḥamdu anta qayyimu as-samāwāti wal-arḍi wa man fīhin, wa laka al-ḥamdu anta rabbu as-samāwāti wal-arḍi wa man fīhin, wa laka al-ḥamdu laka mulku as-samāwāti wal-arḍi wa man fīhin, wa laka al-ḥamdu anta maliku as-samāwāti wal-arḍ, wa laka al-ḥamd, anta al-ḥaqq, wa waʿduka al-ḥaqq, wa qawluka al-ḥaqq, wa liqā'uka al-ḥaqq, wal-jannatu ḥaqq, wan-nāru ḥaqq, wan-nabiyyūna ḥaqq, wa Muḥammadun ṣallā Allāhu ʿalayhi wa sallama ḥaqq, was-sāʿatu ḥaqq. Allāhumma laka aslamtu, wa ʿalayka tawakkaltu, wa bika āmantu, wa ilayka anabtu, wa bika khāṣamtu, wa ilayka ḥākamtu. Faghfir lī mā qaddamtu, wa mā akhkhartu, wa mā asrartu, wa mā aʿlantu, wa mā anta aʿlamu bihi minnī, anta al-muqaddimu wa anta al-mu'akhkhiru lā ilāha illā ant, anta ilāhī lā ilāha illā ant, wa lā ḥawla wa lā quwwata illā billāh.",
     explanationEs: "¡Oh Al-lah! A Ti pertenecen todas las alabanzas, Tú eres la Luz de los cielos y de la tierra y de cuanto hay en ellos. A Ti pertenecen las alabanzas, Tú eres el Sustentador de los cielos y de la tierra y de cuanto hay en ellos. A Ti pertenecen las alabanzas, Tú eres el Señor de los cielos y de la tierra y de cuanto hay en ellos. A Ti pertenecen las alabanzas, Tuyo es el reino de los cielos y de la tierra y de cuanto hay en ellos. A Ti pertenecen las alabanzas, Tú eres el Rey de los cielos y de la tierra. A Ti pertenecen las alabanzas, Tú eres la Verdad, Tu promesa es verdadera, Tu palabra es verdad, el encuentro Contigo es verdad, el Paraíso es verdad, el Infierno es verdad, los Profetas son verdad, Muhammad (que la paz y las bendiciones de Al-lah sean con él) es verdad y la Hora es verdad. ¡Oh Al-lah! A Ti me he sometido, en Ti he confiado, en Ti he creído, a Ti me he vuelto en arrepentimiento, por Ti he disputado y a Tu juicio me he acogido. Perdóname lo que he hecho en el pasado y lo que haga en el futuro, lo que he ocultado y lo que he manifestado, y lo que Tú conoces mejor que yo. Tú eres Quien adelanta y Quien retrasa, no hay más divinidad excepto Tú. Tú eres mi Dios, no hay más divinidad excepto Tú, y no hay fuerza ni poder sino en Al-lah.",
     count: 1,
     maxCount: 1
      }
    ]
  },
  {
     id: "hisn_17",
     titleAr: "دُعَاءُ الرُّكُوعِ",
     titleEs: "Súplica durante la inclinación (Rukūʿ)",
     items: [
      {
         text: "سُبْحَانَ رَبِّيَ الْعَظِيمِ.",
         latin: "Subḥāna rabbiya al-ʿaẓīm.",
         explanationEs: "Glorificado sea mi Señor, el Grandioso. (Se dice tres veces).",
         count: 3,
         maxCount: 3
      },
      {
         text: "سُبْحَانَكَ اللَّهُمَّ رَبَّنَا وَبِحَمْدِكَ، اللَّهُمَّ اغْفِرْ لِي.",
         latin: "Subḥānaka Allāhumma rabbanā wa bi-ḥamdika, Allāhumma ighfir lī.",
         explanationEs: "Glorificado seas, ¡oh Al-lah, Señor nuestro!, y alabado seas. ¡Oh Al-lah! Perdóname.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبُّوحٌ، قُدُّوسٌ، رَبُّ الْمَلاَئِكَةِ وَالرُّوحِ.",
         latin: "Subbūḥun, quddūsun, rabbu al-malā'ikati war-rūḥ.",
         explanationEs: "Glorioso, Santísimo, Señor de los ángeles y del Espíritu (el ángel Gabriel).",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ لَكَ رَكَعْتُ، وَبِكَ آمَنْتُ، وَلَكَ أَسْلَمْتُ، خَشَعَ لَكَ سَمْعِي، وَبَصَرِي، وَمُخِّي، وَعَظْمِي، وَعَصَبِي، وَمَا اسْتَقَلَّتْ بِهِ قَدَمِي.",
         latin: "Allāhumma laka rakaʿtu, wa bika āmantu, wa laka aslamtu, khashaʿa laka samʿī, wa baṣarī, wa mukhkhī, wa ʿaẓmī, wa ʿaṣabī, wa mā istaqallat bihi qadamī.",
         explanationEs: "¡Oh Al-lah! Ante Ti me he inclinado, en Ti he creído y a Ti me he sometido. Se han humillado ante Ti mi oído, mi vista, mi cerebro, mis huesos, mis nervios y lo que sostienen mis pies.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبْحَانَ ذِي الْجَبَرُوتِ، وَالْمَلَكُوتِ، وَالْكِبْرِيَاءِ، وَالْعَظَمَةِ.",
         latin: "Subḥāna dhī al-jabarūti, wal-malakūti, wal-kibriyā'i, wal-ʿaẓamah.",
         explanationEs: "Glorificado sea el Poseedor del poder absoluto, la soberanía, la grandeza y la majestad.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_18",
     titleAr: "دُعَاءُ الرَّفْعِ مِنَ الرُّكُوعِ",
     titleEs: "Súplica al levantarse de la inclinación (Rukūʿ)",
     items: [
      {
         text: "سَمِعَ اللَّهُ لِمَنْ حَمِدَهُ.",
         latin: "Samiʿa Allāhu liman ḥamidah.",
         explanationEs: "Al-lah escucha a quien lo alaba.",
         count: 1,
         maxCount: 1
      },
      {
         text: "رَبَّنَا وَلَكَ الْحَمْدُ، حَمْداً كَثِيراً طَيِّباً مُبَارَكاً فِيهِ.",
         latin: "Rabbanā wa laka al-ḥamdu, ḥamdan kathīran ṭayyiban mubārakan fīh.",
         explanationEs: "¡Señor nuestro! A Ti pertenecen las alabanzas, alabanzas abundantes, puras y benditas.",
         count: 1,
         maxCount: 1
      },
      {
         text: "مِلْءَ السَّمَوَاتِ وَمِلْءَ الأَرْضِ، وَمَا بَيْنَهُمَا، وَمِلْءَ مَا شِئْتَ مِنْ شَيْءٍ بَعْدُ. أَهْلَ الثَّنَاءِ وَالْمَجْدِ، أَحَقُّ مَا قَالَ الْعَبْدُ، وَكُلُّنَا لَكَ عَبْدٌ. اللَّهُمَّ لاَ مَانِعَ لِمَا أَعْطَيْتَ، وَلاَ مُعْطِيَ لِمَا مَنَعْتَ، وَلاَ يَنْفَعُ ذَا الْجَدِّ مِنْكَ الْجَدُّ.",
         latin: "Mil'a as-samāwāti wa mil'a al-arḍi, wa mā baynahumā, wa mil'a mā shi'ta min shay'in baʿd. Ahla ath-thanā'i wal-majd, aḥaqqu mā qāla al-ʿabdu, wa kullunā laka ʿabd. Allāhumma lā māniʿa limā aʿṭayta, wa lā muʿṭiya limā manaʿta, wa lā yanfaʿu dhā al-jaddi minka al-jadd.",
         explanationEs: "[Alabanzas que llenan] los cielos, la tierra, lo que hay entre ambos y cuanto Tú desees después. Digno de alabanza y gloria; es lo más verdadero que dice un siervo, y todos somos Tus siervos. ¡Oh Al-lah! Nadie puede privar lo que Tú concedes, ni nadie puede conceder lo que Tú privas, y la riqueza no beneficia a quien la posee frente a Ti.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_19",
     titleAr: "دُعَاءُ السُّجُودِ",
     titleEs: "Súplica durante la prosternación (Suyūd)",
     items: [
      {
         text: "سُبْحَانَ رَبِّيَ الأَعْلَى.",
         latin: "Subḥāna rabbiya al-aʿlā.",
         explanationEs: "Glorificado sea mi Señor, el Altísimo. (Se dice tres veces).",
         count: 3,
         maxCount: 3
      },
      {
         text: "سُبْحَانَكَ اللَّهُمَّ رَبَّنَا وَبِحَمْدِكَ، اللَّهُمَّ اغْفِرْ لِي.",
         latin: "Subḥānaka Allāhumma rabbanā wa bi-ḥamdika, Allāhumma ighfir lī.",
         explanationEs: "Glorificado seas, ¡oh Al-lah, Señor nuestro!, y alabado seas. ¡Oh Al-lah! Perdóname.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبُّوحٌ، قُدُّوسٌ، رَبُّ الْمَلَائِكَةِ وَالرُّوحِ.",
         latin: "Subbūḥun, quddūsun, rabbu al-malā'ikati war-rūḥ.",
         explanationEs: "Glorioso, Santísimo, Señor de los ángeles y del Espíritu (el ángel Gabriel).",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ لَكَ سَجَدْتُ وَبِكَ آمَنْتُ، وَلَكَ أَسْلَمْتُ، سَجَدَ وَجْهِيَ لِلَّذِي خَلَقَهُ، وَصَوَّرَهُ، وَشَقَّ سَمْعَهُ وَبَصَرَهُ، تَبَارَكَ اللَّهُ أَحْسَنُ الْخَالِقِينَ.",
         latin: "Allāhumma laka sajadtu wa bika āmantu, wa laka aslamtu, sajada wajhiya lilladhī khalaqahu, wa ṣawwarahu, wa shaqqa samʿahu wa baṣarahu, tabāraka Allāhu aḥsanu al-khāliqīn.",
         explanationEs: "¡Oh Al-lah! Ante Ti me he prosternado, en Ti he creído y a Ti me he sometido. Se ha prosternado mi rostro ante Aquel que lo creó, le dio forma y abrió su oído y su vista. Bendito sea Al-lah, el mejor de los creadores.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبْحَانَ ذِي الْجَبَرُوتِ، وَالْمَلَكُوتِ، وَالْكِبْرِيَاءِ، وَالْعَظَمَةِ.",
         latin: "Subḥāna dhī al-jabarūti, wal-malakūti, wal-kibriyā'i, wal-ʿaẓamah.",
         explanationEs: "Glorificado sea el Poseedor del poder absoluto, la soberanía, la grandeza y la majestad.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اغْفِرْ لِي ذَنْبِي كُلَّهُ: دِقَّهُ وَجِلَّهُ، وَأَوَّلَهُ وَآخِرَهُ، وَعَلاَنِيَّتَهُ وَسِرَّهُ.",
         latin: "Allāhumma ighfir lī dhanbī kullah: diqqahu wa jillahu, wa awwalahu wa ākhirahu, wa ʿalāniyatahu wa sirrah.",
         explanationEs: "¡Oh Al-lah! Perdóname todos mis pecados: los pequeños y los grandes, los primeros y los últimos, los públicos y los secretos.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِرِضَاكَ مِنْ سَخَطِكَ، وَبِمُعَافَاتِكَ مِنْ عُقُوبَتِكَ، وَأَعُوذُ بِكَ مِنْكَ، لاَ أُحْصِي ثَنَاءً عَلَيْكَ، أَنْتَ كَمَا أَثْنَيْتَ عَلَى نَفْسِكَ.",
         latin: "Allāhumma innī aʿūdhu bi-riḍāka min sakhaṭika, wa bi-muʿāfātika min ʿuqūbatika, wa aʿūdhu bika minka, lā uḥṣī thanā'an ʿalayka, anta kamā athnayta ʿalā nafsik.",
         explanationEs: "¡Oh Al-lah! Me refugio en Tu complacencia de Tu enojo, en Tu perdón de Tu castigo, y me refugio en Ti de Ti. No puedo enumerar Tus alabanzas; Tú eres tal como Te has alabado a Ti mismo.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_20",
     titleAr: "دُعَاءُ الجَلْسَةِ بَيْنَ السَّجْدَتَيْنِ",
     titleEs: "Súplica en la sentada entre las dos prosternaciones",
     items: [
      {
         text: "رَبِّ اغْفِرْ لِي، رَبِّ اغْفِرْ لِي.",
         latin: "Rabbi ighfir lī, Rabbi ighfir lī.",
         explanationEs: "Señor mío perdóname, Señor mío perdóname.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اغْفِرْ لِي، وَارْحَمْنِي، وَاهْدِنِي، وَاجْبُرْنِي، وَعَافِنِي، وَارْزُقْنِي، وَارْفَعْنِي.",
         latin: "Allāhumma ighfir lī, warḥamnī, wahdinī, wajburnī, wa ʿāfinī, warzuqnī, warfaʿnī.",
         explanationEs: "¡Oh Al-lah! Perdóname, ten misericordia de mí, guíame, reconforta mis carencias, dame salud, susténtame y elévame.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_21",
     titleAr: "دُعَاءُ سُجُودِ التِّلاَوَةِ",
     titleEs: "Súplica para la prosternación por lectura (Suyuud At-Tilawa)",
     items: [
      {
         text: "سَجَدَ وَجْهِيَ لِلَّذِي خَلَقَهُ، وَشَقَّ سَمْعَهُ وَبَصَرَهُ بِحَوْلِهِ وَقُوَّتِهِ، ﴿فَتَبَارَكَ اللَّهُ أَحْسَنُ الْخَالِقِينَ﴾.",
         latin: "Sajada wajhiya lilladhī khalaqahu, wa shaqqa samʿahu wa baṣarahu bi-ḥawlihi wa quwwatih, ﴿fa-tabāraka Allāhu aḥsanu al-khāliqīn﴾.",
         explanationEs: "Se ha prosternado mi rostro ante Aquel que lo creó y le dio oído y vista con Su poder y fuerza. Bendito sea Al-lah, el mejor de los creadores.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اكْتُبْ لِي بِهَا عِنْدَكَ أَجْراً، وَضَعْ عَنِّي بِهَا وِزْراً، وَاجْعَلْهَا لِي عِنْدَكَ ذُخْراً، وَتَقَبَّلْهَا مِنِّي كَمَا تَقَبَّلْتَهَا مِنْ عَبْدِكَ دَاوُدَ.",
         latin: "Allāhumma iktub lī bihā ʿindaka ajrā, wa ḍaʿ ʿannī bihā wizrā, wa ijʿalhā lī ʿindaka dhukhrā, wa taqabbalhā minnī kamā taqabbaltahā min ʿabdika Dāwūd.",
         explanationEs: "¡Oh Al-lah! Anota para mí por ella (esta prosternación) una recompensa ante Ti, quítame con ella una carga, hazla para mí un tesoro ante Ti y acéptala de mí como la aceptaste de Tu siervo David.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_22",
     titleAr: "التَّشَهُّدُ",
     titleEs: "El Tashahhud",
     items: [
      {
         text: "التَّحِيَّاتُ لِلَّهِ، وَالصَّلَوَاتُ، وَالطَّيِّبَاتُ، السَّلاَمُ عَلَيْكَ أَيُّهَا النَّبِيُّ وَرَحْمَةُ اللَّهِ وَبَرَكَاتُهُ، السَّلاَمُ عَلَيْنَا وَعَلَى عِبَادِ اللَّهِ الصَّالِحِينَ. أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ اللَّهُ وَأَشْهَدُ أَنَّ مُحَمَّداً عَبْدُهُ وَرَسُولُهُ.",
         latin: "At-taḥiyyātu lillāhi, waṣ-ṣalawātu, waṭ-ṭayyibāt. As-salāmu ʿalayka ayyuhā an-nabiyyu wa raḥmatu Allāhi wa barakātuh, as-salāmu ʿalaynā wa ʿalā ʿibādillāhi aṣ-ṣāliḥīn. Ashhadu an lā ilāha illā Allāhu wa ashhadu anna Muḥammadan ʿabduhu wa rasūluh.",
         explanationEs: "Todas las veneraciones, oraciones y buenas palabras pertenecen a Al-lah. La paz sea contigo, ¡oh Profeta!, así como la misericordia de Al-lah y Sus bendiciones. La paz sea con nosotros y con los siervos piadosos de Al-lah. Atestiguo que no hay más divinidad que Al-lah y atestiguo que Muhammad es Su siervo y mensajero.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_23",
     titleAr: "الصَّلاَةُ عَلَى النَّبِيِّ بَعْدَ التَّشَهُّدِ",
     titleEs: "Súplica por el Profeta tras el Tashahhud",
     items: [
      {
         text: "اللَّهُمَّ صَلِّ عَلَى مُحَمَّدٍ، وَعَلَى آلِ مُحَمَّدٍ، كَمَا صَلَّيْتَ عَلَى إِبْرَاهِيمَ، وَعَلَى آلِ إِبْرَاهِيمَ، إِنَّكَ حَمِيدٌ مَجِيدٌ، اللَّهُمَّ بَارِكْ عَلَى مُحَمَّدٍ وَعَلَى آلِ مُحَمَّدٍ، كَمَا بَارَكْتَ عَلَى إِبْرَاهِيمَ وَعَلَى آلِ إِبْرَاهِيمَ، إِنَّكَ حَمِيدٌ مَجِيدٌ.",
         latin: "Allāhumma ṣalli ʿalā Muḥammadin, wa ʿalā āli Muḥammad, kamā ṣallayta ʿalā Ibrāhīma, wa ʿalā āli Ibrāhīm, innaka ḥamīdun majīd. Allāhumma bārik ʿalā Muḥammadin wa ʿalā āli Muḥammad, kamā bārakta ʿalā Ibrāhīma wa ʿalā āli Ibrāhīm, innaka ḥamīdun majīd.",
         explanationEs: "¡Oh Al-lah! Bendice a Muhammad y a la familia de Muhammad, como bendijiste a Abraham y a la familia de Abraham, ciertamente Tú eres Loable, Glorioso. ¡Oh Al-lah! Prospera a Muhammad y a la familia de Muhammad, como prosperaste a Abraham y a la familia de Abraham, ciertamente Tú eres Loable, Glorioso.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ صَلِّ عَلَى مُحَمَّدٍ وَعَلَى أَزْوَاجِهِ وَذُرِّيَّتِهِ، كَمَا صَلَّيْتَ عَلَى آلِ إِبْرَاهِيمَ. وَبَارِكْ عَلَى مُحَمَّدٍ وَعَلَى أَزْوَاجِهِ وَذُرِّيَّتِهِ، كَمَا بَارَكْتَ عَلَى آلِ إِبْرَاهِيمَ. إِنَّكَ حَمِيدٌ مَجِيدٌ.",
         latin: "Allāhumma ṣalli ʿalā Muḥammadin wa ʿalā azwājihi wa dhurriyyatih, kamā ṣallayta ʿalā āli Ibrāhīm. Wa bārik ʿalā Muḥammadin wa ʿalā azwājihi wa dhurriyyatih, kamā bārakta ʿalā āli Ibrāhīm. Innaka ḥamīdun majīd.",
         explanationEs: "¡Oh Al-lah! Bendice a Muhammad, a sus esposas y a su descendencia, como bendijiste a la familia de Abraham. Y prospera a Muhammad, a sus esposas y a su descendencia, como prosperaste a la familia de Abraham. Ciertamente Tú eres Loable, Glorioso.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_24",
     titleAr: "الدَّعَاءُ بَعْدَ التَّشَهُّدِ الأَخِيرِ قَبْلَ السَّلاَمِ",
     titleEs: "Súplicas tras el último Tashahhud antes del saludo final",
     items: [
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنْ عَذَابِ الْقَبْرِ، وَمِنْ عَذَابِ جَهَنَّمَ، وَمِنْ فِتْنَةِ الْمَحْيَا وَالْمَمَاتِ، وَمِنْ شَرِّ فِتْنَةِ الْمَسِيحِ الدَّجَّالِ.",
         latin: "Allāhumma innī aʿūdhu bika min ʿadhābi al-qabr, wa min ʿadhābi jahannam, wa min fitnati al-maḥyā wal-mamāt, wa min sharri fitnati al-masīḥi ad-dajjāl.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti del castigo de la tumba, del castigo del Infierno, de las pruebas de la vida y de la muerte, y del mal de la prueba del Falso Mesías (Anticristo).",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنْ عَذَابِ الْقَبْرِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْمَسِيحِ الدَّجَّالِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الْمَحْيَا وَالْمَمَاتِ. اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْمَأْثَمِ وَالْمَغْرَمِ.",
         latin: "Allāhumma innī aʿūdhu bika min ʿadhābi al-qabr, wa aʿūdhu bika min fitnati al-masīḥi ad-dajjāl, wa aʿūdhu bika min fitnati al-maḥyā wal-mamāt. Allāhumma innī aʿūdhu bika mina al-ma'thami wal-maghram.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti del castigo de la tumba, del juicio del Falso Mesías, y de las pruebas de la vida y de la muerte. ¡Oh Al-lah! Me refugio en Ti del pecado y de las deudas agobiantes.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي ظَلَمْتُ نَفْسِي ظُلْماً كَثِيراً، وَلاَ يَغْفِرُ الذُّنُوبَ إِلاَّ أَنْتَ، فَاغْفِرْ لِي مَغْفِرَةً مِنْ عِنْدِكَ وَارْحَمْنِي، إِنَّكَ أَنْتَ الْغَفُورُ الرَّحِيمُ.",
         latin: "Allāhumma innī ẓalamtu nafsī ẓulman kathīrā, wa lā yaghfiru adhdhunūba illā ant, faghfir lī maghfiratan min ʿindika warḥamnī, innaka anta al-ghafūru ar-raḥīm.",
         explanationEs: "¡Oh Al-lah! Ciertamente me he oprimido a mí mismo en gran manera y nadie perdona los pecados excepto Tú, concedeme pues un perdón de Tu parte y ten misericordia de mí, ciertamente Tú eres el Absolvedor, el Misericordioso.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اغْفِرْ لِي مَا قَدَّمْتُ، وَمَا أَخَّرْتُ، وَمَا أَسْرَرْتُ، وَمَا أَعْلَنْتُ، وَمَا أَسْرَفْتُ، وَمَا أَنْتَ أَعْلَمُ بِهِ مِنِّي. أَنْتَ الْمُقَدِّمُ، وَأَنْتَ الْمُؤَخِّرُ لاَ إِلَهَ إِلاَّ أَنْتَ.",
         latin: "Allāhumma ighfir lī mā qaddamtu, wa mā akhkhartu, wa mā asrartu, wa mā aʿlantu, wa mā asraftu, wa mā anta aʿlamu bihi minnī. Anta al-muqaddimu, wa anta al-mu'akhkhiru lā ilāha illā ant.",
         explanationEs: "¡Oh Al-lah! Perdóname lo que he hecho en el pasado y lo que haga en el futuro, lo que he ocultado, lo que he manifestado, mis excesos y lo que Tú conoces mejor que yo. Tú eres Quien adelanta y Quien retrasa, no hay más divinidad excepto Tú.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ أَعِنِّي عَلَى ذِكْرِكَ، وَشُكْرِكَ، وَحُسْنِ عِبَادَتِكَ.",
         latin: "Allāhumma aʿinnī ʿalā dhikrika, wa shukrika, wa ḥusni ʿibādatik.",
         explanationEs: "¡Oh Al-lah! Ayúdame a recordarte, agradecerte y adorarte de la mejor manera.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْبُخْلِ، وَأَعُوذُ بِكَ مِنَ الْجُبْنِ، وَأَعُوذُ بِكَ مِنْ أَنْ أُرَدَّ إِلَى أَرْذَلِ الْعُمُرِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الدُّنْيَا وَعَذَابِ الْقَبْرِ.",
         latin: "Allāhumma innī aʿūdhu bika mina al-bukhl, wa aʿūdhu bika mina al-jubn, wa aʿūdhu bika min an uradda ilā ardhali al-ʿumur, wa aʿūdhu bika min fitnati ad-dunyā wa ʿadhābi al-qabr.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti de la tacañería, la cobardía, la decrepitud en la vejez, las pruebas de este mundo y el castigo de la tumba.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ الْجَنَّةَ وَأَعُوذُ بِكَ مِنَ النَّارِ.",
         latin: "Allāhumma innī as'aluka al-jannata wa aʿūdhu bika mina an-nār.",
         explanationEs: "¡Oh Al-lah! Te pido el Paraíso y me refugio en Ti del Fuego.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ بِعِلْمِكَ الْغَيْبَ وَقُدْرَتِكَ عَلَى الْخَلْقِ أَحْيِنِي مَا عَلِمْتَ الْحَيَاةَ خَيْراً لِي، وَتَوَفَّنِي إِذَا عَلِمْتَ الْوَفَاةَ خَيْراً لِي، اللَّهُمَّ إِنِّي أَسْأَلُكَ خَشْيَتَكَ فِي الْغَيْبِ وَالشَّهَادَةِ، وَأَسْأَلُكَ كَلِمَةَ الْحَقِّ فِي الرِّضَا وَالْغَضَبِ، وَأَسْأَلُكَ الْقَصْدَ فِي الْغِنَى وَالْفَقْرِ، وَأَسْأَلُكَ نَعِيماً لاَ يَنْفَدُ، وَأَسْأَلُكَ قُرَّةَ عَيْنٍ لاَ تَنْقَطِعُ، وَأَسْأَلُكَ الرِّضَا بَعْدَ الْقَضَاءِ، وَأَسْأَلُكَ بَرْدَ الْعَيْشِ بَعْدَ الْمَوْتِ، وَأَسْأَلُكَ لَذَّةَ النَّظَرِ إِلَى وَجْهِكَ، وَالشَّوْقَ إِلَى لِقَائِكَ فِي غَيْرِ ضَرَّاءَ مُضِرَّةٍ، وَلاَ فِتْنَةٍ مُضِلَّةٍ، اللَّهُمَّ زَيِّنَّا بِزِينَةِ الإِيمَانِ، وَاجْعَلْنَا هُدَاةً مُهْتَدِينَ.",
         latin: "Allāhumma bi-ʿilmika al-ghayba wa qudratika ʿalā al-khalqi aḥyinī mā ʿalimta al-ḥayāta khayran lī, wa tawaffanī idhā ʿalimta al-wafāta khayran lī. Allāhumma innī as'aluka khashyataka fī al-ghaybi wash-shahādah, wa as'aluka kalimata al-ḥaqqi fī ar-riḍā wal-ghaḍab, wa as'aluka al-qaṣda fī al-ghinā wal-faqr, wa as'aluka naʿīman lā yanfad, wa as'aluka qurrata ʿaynin lā tanqaṭiʿ, wa as'aluka ar-riḍā baʿda al-qaḍā', wa as'aluka barda al-ʿayshi baʿda al-mawt, wa as'aluka ladhdhata an-naẓari ilā wajhika, wash-shawqa ilā liqā'ika fī ghayri ḍarrā'a muḍirrah, wa lā fitnatin muḍillatın, Allāhumma zayyinnā bi-zīnati al-īmān, wa ijʿalnā hudātan muhtadīn.",
         explanationEs: "¡Oh Al-lah! Con Tu conocimiento de lo oculto y Tu poder sobre la creación, manténme con vida mientras sepas que la vida es buena para mí, y hazme morir cuando sepas que la muerte es buena para mí. ¡Oh Al-lah! Te pido Tu temor en lo oculto y en lo manifiesto, la palabra de verdad en la complacencia y en la ira, la moderación en la riqueza y en la pobreza, una gracia inagotable, una alegría constante, la aceptación tras Tu decreto, el consuelo de la vida tras la muerte, el deleite de contemplar Tu Rostro y el anhelo de encontrarte sin sufrir un perjuicio dañino ni una prueba extraviadora. ¡Oh Al-lah! Adórnanos con el adorno de la fe y haznos guías bien guiados.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ يَا أَللَّهُ بِأَنَّكَ الْوَاحِدُ الأَحَدُ الصَّمَدُ الَّذِي لَمْ يَلِدْ وَلَمْ يُولَدْ، وَلَمْ يَكُنْ لَهُ كُفُواً أَحَدٌ، أَنْ تَغْفِرَ لِي ذُنُوبِي إِنَّكَ أَنْتَ الْغَفُورُ الرَّحِيمُ.",
         latin: "Allāhumma innī as'aluka yā Allāhu bi-annaka al-wāḥidu al-aḥadu aṣ-ṣamadu alladhī lam yalid wa lam yūlad, wa lam yakun lahu kufuwan aḥad, an taghfira lī dhunūbī innaka anta al-ghafūru ar-raḥīm.",
         explanationEs: "¡Oh Al-lah! Te pido, ¡oh Al-lah!, porque Tú eres el Único, el Absoluto, Quien no engendró ni fue engendrado y no hay nadie semejante a Él, que perdones mis pecados. Ciertamente Tú eres el Absolvedor, el Misericordioso.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ بِأَنَّ لَكَ الْحَمْدَ لاَ إِلَهَ إِلاَّ أَنْتَ وَحْدَكَ لاَ شَرِيكَ لَكَ، الْمَنَّانُ، يَا بَدِيعَ السَّمَوَاتِ وَالأَرْضِ يَا ذَا الْجَلاَلِ وَالإِكْرَامِ، يَا حَيُّ يَا قَيُّومُ إِنِّي أَسْأَلُكَ الْجَنَّةَ وَأَعُوذُ بِكَ مِنَ النَّارِ.",
         latin: "Allāhumma innī as'aluka bi-anna laka al-ḥamda lā ilāha illā anta waḥdaka lā sharīka lak, al-mannān, yā badīʿa as-samāwāti wal-arḍ, yā dhā al-jalāli wal-ikrām, yā ḥayyu yā qayyūmu innī as'aluka al-jannata wa aʿūdhu bika mina an-nār.",
         explanationEs: "¡Oh Al-lah! Te pido porque a Ti pertenecen las alabanzas, no hay más divinidad excepto Tú, Único, sin asociados, el Sempiterno Concededor, ¡oh Creador originario de los cielos y de la tierra!, ¡oh Poseedor de la majestad y del honor!, ¡oh Viviente, oh Sustentador de todo! Te pido el Paraíso y me refugio en Ti del Fuego.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ بِأَنِّي أَشْهَدُ أَنَّكَ أَنْتَ اللَّهُ لاَ إِلَهَ إِلاَّ أَنْتَ الأَحَدُ الصَّمَدُ الَّذِي لَمْ يَلِدْ وَلَمْ يُولَدْ وَلَمْ يَكُنْ لَهُ كُفُواً أَحَدٌ.",
         latin: "Allāhumma innī as'aluka bi-annī ashhadu annaka anta Allāhu lā ilāha illā anta al-aḥadu aṣ-ṣamadu alladhī lam yalid wa lam yūlad wa lam yakun lahu kufuwan aḥad.",
         explanationEs: "¡Oh Al-lah! Te pido pues atestiguo que Tú eres Al-lah, no hay más divinidad excepto Tú, el Único, el Absoluto, Quien no engendró ni fue engendrado y no hay nadie semejante a Él.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_25",
     titleAr: "الأَذْكَارُ بَعْدَ السَّلاَمِ مِنَ الصَّلاَةِ",
     titleEs: "Súplicas y alabanzas después de la oración",
     items: [
      {
         text: "أَسْتَغْفِرُ اللَّهَ (ثَلاَثاً)، اللَّهُمَّ أَنْتَ السَّلاَمُ، وَمِنْكَ السَّلاَمُ، تَبَارَكْتَ يَا ذَا الْجَلاَلِ وَالإِكْرَامِ.",
         latin: "Astaghfiru Allāh (tres veces). Allāhumma anta as-salām, wa minka as-salām, tabārakta yā dhā al-jalāli wal-ikrām.",
         explanationEs: "Pido perdón a Al-lah (tres veces). ¡Oh Al-lah! Tú eres la Paz y de Ti procede la paz. Bendito seas, ¡oh Poseedor de la majestad y del honor!",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، اللَّهُمَّ لاَ مَانِعَ لِمَا أَعْطَيْتَ، وَلاَ مُعْطِيَ لِمَا مَنَعْتَ، وَلاَ يَنْفَعُ ذَا الْجَدِّ مِنْكَ الْجَدُّ.",
         latin: "Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku wa lahu al-ḥamd, wa huwa ʿalā kulli shay'in qadīr. Allāhumma lā māniʿa limā aʿṭayt, wa lā muʿṭiya limā manaʿt, wa lā yanfaʿu dhā al-jaddi minka al-jadd.",
         explanationEs: "No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Omnipotente sobre todas las cosas. ¡Oh Al-lah! Nadie puede privar lo que Tú concedes, ni nadie puede conceder lo que Tú privas, y la riqueza no beneficia a quien la posee frente a Ti.",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ، وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ. لاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ، لاَ إِلَهَ إِلاَّ اللَّهُ، وَلاَ نَعْبُدُ إِلاَّ إِيَّاهُ، لَهُ النِّعْمَةُ وَلَهُ الْفَضْلُ وَلَهُ الثَّنَاءُ الْحَسَنُ، لاَ إِلَهَ إِلاَّ اللَّهُ مُخْلِصِينَ لَهُ الدِّينَ وَلَوْ كَرِهَ الْكَافِرُونَ.",
         latin: "Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku, wa lahu al-ḥamdu, wa huwa ʿalā kulli shay'in qadīr. Lā ḥawla wa lā quwwata illā billāh, lā ilāha illā Allāhu, wa lā naʿbudu illā iyyāh, lahu an-niʿmatu wa lahu al-faḍlu wa lahu ath-thanā'u al-ḥasan, lā ilāha illā Allāhu mukhliṣīna lahu ad-dīna wa law kariha al-kāfirūn.",
         explanationEs: "No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Omnipotente sobre todas las cosas. No hay fuerza ni poder sino en Al-lah. No hay más divinidad que Al-lah y no adoramos sino a Él. De Él procede la gracia, el favor y la hermosa alabanza. No hay más divinidad que Al-lah, profesándole la religión de manera sincera aunque esto disguste a los incrédulos.",
         count: 1,
         maxCount: 1
      },
      {
         text: "سُبْحَانَ اللَّهِ، وَالْحَمْدُ لِلَّهِ، وَاللَّهُ أَكْبَرُ.",
         latin: "Subḥānallāh, wal-ḥamdu lillāh, wallāhu akbar.",
         explanationEs: "Glorificado sea Al-lah, alabado sea Al-lah, Al-lah es el más Grande. (33 veces cada uno).",
         count: 33,
         maxCount: 33
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.",
         latin: "Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku wa lahu al-ḥamdu wa huwa ʿalā kulli shay'in qadīr.",
         explanationEs: "No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Omnipotente sobre todas las cosas. (Se completa con esto el número 100 en el dhikr).",
         count: 1,
         maxCount: 1
      },
      {
         text: "بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ ﴿قُلْ هُوَ اللَّهُ أَحَدٌ...﴾، ﴿قُلْ أَعُوذُ بِرَبِّ الْفَلَقِ...﴾، ﴿قُلْ أَعُوذُ بِرَبِّ النَّاسِ...﴾",
         latin: "Bismillāhi ar-raḥmāni ar-raḥīm ﴿Qul huwa Allāhu aḥad...﴾, ﴿Qul aʿūdhu bi-rabbi al-falaq...﴾, ﴿Qul aʿūdhu bi-rabbi an-nās...﴾",
         explanationEs: "Lectura de las suras Al-Ikhlas, Al-Falaq y An-Nas tras cada oración (se repiten tres veces tras el Fajr y el Maghrib).",
         count: 1,
         maxCount: 1
      },
      {
         text: "﴿اللَّهُ لاَ إِلَهَ إِلاَّ هُوَ الْحَيُّ الْقَيُّومُ لاَ تَأْخُذُهُ سِنَةٌ وَلاَ نَوْمٌ لَّهُ مَا فِي السَّمَوَاتِ وَمَا فِي الأَرْضِ مَن ذَا الَّذِي يَشْفَعُ عِنْدَهُ إِلاَّ بِإِذْنِهِ يَعْلَمُ مَا بَيْنَ أَيْدِيهِمْ وَمَا خَلْفَهُمْ وَلاَ يُحِيطُونَ بِشَيْءٍ مِّنْ عِلْمِهِ إِلاَّ بِمَا شَاءَ وَسِعَ كُرْسِيُّهُ السَّمَوَاتِ وَالأَرْضَ وَلاَ يَؤُودُهُ حِفْظُهُمَا وَهُوَ الْعَلِيُّ الْعَظِيمُ﴾",
         latin: "Allāhu lā ilāha illā huwa al-ḥayyu al-qayyūm, lā ta'khudhuhu sinatun wa lā nawm, lahu mā fī as-samāwāti wa mā fī al-arḍ, man dhā alladhī Yashfaʿu ʿindahu illā bi-idhnih, yaʿlamu mā bayna aydīhim wa mā khalfahum, wa lā yuḥīṭūna bi-shay'in min ʿilmihi illā bi-mā shā', wasiʿa kursiyyuhu as-samāwāti wal-arḍ, wa lā ya'ūduhu ḥifẓuhumā wa huwa al-ʿaliyyu al-ʿaẓīm.",
         explanationEs: "Lectura del Versículo del Cincel/Trono (Ayat al-Kursi) tras cada oración obligatoria.",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ يُحْيِي وَيُمِيتُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.",
         latin: "Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku wa lahu al-ḥamdu yuḥyī wa yumītu wa huwa ʿalā kulli shay'in qadīr.",
         explanationEs: "No hay más divinidad que Al-lah, Único, sin asociados, Suyo es el reino y Suya es la alabanza, Él da la vida y da la muerte, y Él es Omnipotente sobre todas las cosas (diez veces tras el Maghrib y el Fajr).",
         count: 10,
         maxCount: 10
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ عِلْماً نَافِعاً، وَرِزْقاً طَيِّباً، وَعَمَلاً مُتَقَبَّلاً.",
         latin: "Allāhumma innī as'aluka ʿilman nāfiʿā, wa rizqan ṭayyibā, wa ʿamalan mutaqabbalā.",
         explanationEs: "¡Oh Al-lah! Te pido un conocimiento útil, un sustento puro y lícito, y obras aceptables (se dice tras el saludo final de la oración del Fajr).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_26",
     titleAr: "دُعَاءُ صَلاَةِ الإِسْتِخَارَةِ",
     titleEs: "Súplica de la oración de la orientación o consulta (Al-Istijárah)",
     items: [
      {
         text: "اللَّهُمَّ إِنِّي أَسْتَخِيرُكَ بِعِلْمِكَ، وَأَسْتَقْدِرُكَ بِقُدْرَتِكَ، وَأَسْأَلُكَ مِنْ فَضْلِكَ الْعَظِيمِ؛ فَإِنَّكَ تَقْدِرُ وَلاَ أَقْدِرُ، وَتَعْلَمُ وَلاَ أَعْلَمُ، وَأَنْتَ عَلاَّمُ الْغُيُوبِ، اللَّهُمَّ إِنْ كُنْتَ تَعْلَمُ أَنَّ هَذَا الأَمْرَ - وَيُسَمِّي حَاجَتَهُ - خَيْرٌ لِي فِي دِينِي وَمَعَاشِي وَعَاقِبَةِ أَمْرِي (أَوْ قَالَ: عَاجِلِهِ وَآجِلِهِ) فَاقْدُرْهُ لِي وَيَسِّرْهُ لِي ثُمَّ بَارِكْ لِي فِيهِ، وَإِنْ كُنْتَ تَعْلَمُ أَنَّ هَذَا الأَمْرَ شَرٌّ لِي فِي دِينِي وَمَعَاشِي وَعَاقِبَةِ أَمْرِي (أَوْ قَالَ: عَاجِلِهِ وَآجِلِهِ) فَاصْرِفْهُ عَنِّي وَاصْرِفْنِي عَنْهُ وَاقْدُرْ لِيَ الْخَيْرَ حَيْثُ كَانَ ثُمَّ أَرْضِنِي بِهِ.",
         latin: "Allāhumma innī astakhīruka bi-ʿilmika, wa astaqdiruka bi-qudratika, wa as'aluka min faḍlika al-ʿaẓīm; fa-innaka taqdiru wa lā aqdir, wa taʿlamu wa lā aʿlam, wa anta ʿallāmu al-ghuyūb. Allāhumma in kunta taʿlamu anna hādhā al-amra (y nombra su asunto) khayrun lī fī dīnī wa maʿāshī wa ʿāqibati amrī (aw qāla: ʿājilihi wa ājilih) faqdurhu lī wa yassirhu lī thumma bārik lī fīh, wa in kunta taʿlamu anna hādhā al-amra sharrun lī fī dīnī wa maʿāshī wa ʿāqibati amrī (aw qāla: ʿājilihi wa ājilih) faṣrifhu ʿannī waṣrifnī ʿanhu waqdur lī al-khayra ḥaythu kāna thumma arḍinī bih.",
         explanationEs: "¡Oh Al-lah! Te pido orientación mediante Tu conocimiento, te pido capacidad mediante Tu poder y Te pido de Tu gran favor; pues Tú puedes y yo no puedo, Tú sabes y yo no sé, y Tú eres el Conocedor de lo oculto. ¡Oh Al-lah! Si sabes que este asunto (nombra su necesidad) es bueno para mí en mi religión, mi vida y mi destino final, me lo decretas, me lo facilitas y me lo bendices. Y si sabes que este asunto es malo para mí en mi religión, mi vida y mi destino final, apártalo de mí y apártame de él, decreta para mí el bien dondequiera que esté y haz que me sienta complacido con ello.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_29",
     titleAr: "الدُّعَاءُ عِنْدَ التَّقَلُّبِ فِي الفِرَاشِ لَيْلاً",
     titleEs: "Súplica al darse la vuelta en la cama por la noche",
     items: [
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ الْوَاحِدُ الْقَهَّارُ، رَبُّ السَّمَوَاتِ وَالأَرْضِ وَمَا بَيْنَهُمَا الْعَزِيزُ الْغَفَّارُ.",
         latin: "Lā ilāha illā Allāhu al-wāḥidu al-qahhār, rabbu as-samāwāti wal-arḍi wa mā baynahumā al-ʿazīzu al-ghaffār.",
         explanationEs: "No hay más divinidad que Al-lah, el Único, el Dominador, Señor de los cielos y de la tierra y de lo que hay entre ambos, el Poderoso, el Absolvedor.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_30",
     titleAr: "دُعَاءُ الفَزَعِ فِي النَّوْمِ وَمَنْ بُلِيَ بِالوَحْشَةِ",
     titleEs: "Súplica ante el sobresalto al dormir o la sensación de angustia",
     items: [
      {
         text: "أَعُوذُ بِكَلِمَاتِ اللَّهِ التَّامَّاتِ مِنْ غَضَبِهِ وَعِقَابِهِ، وَشَرِّ عِبَادِهِ، وَمِنْ هَمَزَاتِ الشَّيَاطِينِ وَأَنْ يَحْضُرُونِ.",
         latin: "Aʿūdhu bi-kalimāti Allāhi at-tāmmāti min ghaḍabihi wa ʿiqābih, wa sharri ʿibādih, wa min hamazāti ash-shayāṭīni wa an yaḥḍurūn.",
         explanationEs: "Me refugio en las palabras perfectas de Al-lah de Su ira, de Su castigo, del mal de Sus siervos y de las incitaciones de los demonios y de que se presenten ante mí.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_31",
     titleAr: "مَا يَفْعَلُ مَنْ رَأَى الرُّؤْيَا أَوْ الحُلْمَ",
     titleEs: "Lo que debe hacer quien tiene una visión o un sueño",
     items: [
      {
         text: "يَنْفُثُ عَنْ يَسَارِهِ (ثَلاَثاً)، وَيَسْتَعِيذُ بِاللَّهِ مِنَ الشَّيْطَانِ وَمِنْ شَرِّ مَا رَأَى (ثَلاَثَ مَرَّاتٍ)، وَلاَ يُحَدِّثْ بِهَا أَحَداً، وَيَتَحَوَّلُ عَنْ جَنْبِهِ الَّذِي كَانَ عَلَيْهِ.",
         latin: "Yanfuthu ʿan yasārihi (thalāthan), wa yastaʿīdhu billāhi mina ash-shayṭāni wa min sharri mā ra'ā (thalātha marrāt), wa lā yuḥaddith bihā aḥadā, wa yataḥawwalu ʿan janbihi alladhī kāna ʿalayh.",
         explanationEs: "Sopla suavemente a su izquierda tres veces, busca refugio en Al-lah del Demonio y del mal de lo que vio (tres veces), no se lo cuenta a nadie y cambia del costado sobre el que estaba recostado.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَيَقُومُ يُصَلِّي إِنْ أَرَادَ ذَلِكَ.",
         latin: "Wa yaqūmu yuṣallī in arāda dhālik.",
         explanationEs: "Y se levanta a orar si así lo desea.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_32",
     titleAr: "دُعَاءُ قُنُوتِ الوِتْرِ",
     titleEs: "Súplica del Qunūt en la oración del Witr",
     items: [
      {
         text: "اللَّهُمَّ اهْدِنِي فِيمَنْ هَدَيْتَ، وَعَافِنِي فِيمَنْ عَافَيْتَ، وَتَوَلَّنِي فِيمَنْ تَوَلَّيْتَ، وَبَارِكْ لِي فِيمَا أَعْطَيْتَ، وَقِنِي شَرَّ مَا قَضَيْتَ؛ فَإِنَّكَ تَقْضِي وَلاَ يُقْضَى عَلَيْكَ، إِنَّهُ لاَ يَذِلُّ مَنْ وَالَيْتَ، [وَلاَ يَعِزُّ مَنْ عَادَيْتَ]، تَبَارَكْتَ رَبَّنَا وَتَعَالَيْتَ.",
         latin: "Allāhumma ihdinī fīman hadayt, wa ʿāfinī fīman ʿāfayt, wa tawallanī fīman tawallayt, wa bārik lī fīmā aʿṭayt, wa qinī sharra mā qaḍayt; fa-innaka taqḍī wa lā yuqḍā ʿalayk, innahu lā yadhillu man wālayt, [wa lā yaʿizzu man ʿādayt], tabārakta rabbanā wa taʿālayt.",
         explanationEs: "¡Oh Al-lah! Guíame junto a quienes has guiado, dame salud junto a quienes has sanado, protégeme junto a quienes has protegido, bendice para mí lo que me has concedido y líbrame del mal de lo que has decretado. Ciertamente Tú decretas y nadie decreta contra Ti; no será humillado a quien Tú proteges [ni será enaltecido a quien Tú tomas por enemigo]. Bendito y Enaltecido seas, Señor nuestro.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِرِضَاكَ مِنْ سَخَطِكَ، وَبِمُعَافَاتِكَ مِنْ عُقُوبَتِكَ، وَأَعُوذُ بِكَ مِنْكَ، لاَ أُحْصِي ثَنَاءً عَلَيْكَ، أَنْتَ كَمَا أَثْنَيْتَ عَلَى نَفْسِكَ.",
         latin: "Allāhumma innī aʿūdhu bi-riḍāka min sakhaṭika, wa bi-muʿāfātika min ʿuqūbatika, wa aʿūdhu bika minka, lā uḥṣī thanā'an ʿalayka, anta kamā athnayta ʿalā nafsik.",
         explanationEs: "¡Oh Al-lah! Me refugio en Tu complacencia de Tu enojo, en Tu perdón de Tu castigo, y me refugio en Ti de Ti. No puedo enumerar Tus alabanzas; Tú eres tal como Te has alabado a Ti mismo.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِيَّاكَ نَعْبُدُ، وَلَكَ نُصَلِّي وَنَسْجُدُ، وَإِلَيْكَ نَسْعَى وَنَحْفِدُ، نَرْجُو رَحْمَتَكَ، وَنَخْشَى عَذَابَكَ، إِنَّ عَذَابَكَ بِالْكَافِرِينَ مُلْحَقٌ. اللَّهُمَّ إِنَّا نَسْتَعِينُكَ، وَنَسْتَغْفِرُكَ، وَنُثْنِي عَلَيْكَ الْخَيْرَ، وَلاَ نَكْفُرُكَ، وَنُؤْمِنُ بِكَ، وَنَخْضَعُ لَكَ، وَنَخْلَعُ مَنْ يَكْفُرُكَ.",
         latin: "Allāhumma iyyāka naʿbudu, wa laka nuṣallī wa nasjudu, wa ilayka nasʿā wa naḥfid, narjū raḥmataka, wa nakhshā ʿadhābak, inna ʿadhābaka bil-kāfirīna mulḥaq. Allāhumma innā nastaʿīnuka, wa nastaghfiruka, wa nuthnī ʿalayka al-khayra, wa lā nakfuruka, wa nu'minu bika, wa nakhḍaʿu laka, wa nakhlaʿu man yakfuruk.",
         explanationEs: "¡Oh Al-lah! A Ti solo adoramos, por Ti oramos y nos prosternamos, hacia Ti nos esmeramos y apresuramos. Esperamos Tu misericordia y tememos Tu castigo; ciertamente Tu castigo alcanzará a los incrédulos. ¡Oh Al-lah! A Ti pedimos ayuda, a Ti pedimos perdón, Te alabamos con todo bien, no somos ingratos Contigo, creemos en Ti, nos sometemos a Ti y nos apartamos de quien Te niega.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_33",
     titleAr: "الذِّكْرُ عَقِبَ السَّلاَمِ مِنَ الوِتْرِ",
     titleEs: "Súplica tras el saludo final en la oración del Witr",
     items: [
      {
         text: "سُبْحَانَ الْمَلِكِ الْقُدُّوسِ (ثَلاَثَ مَرَّاتٍ)، وَالثَّالِثَةُ يَجْهَرُ بِهَا وَيَمُدُّ بِهَا صَوْتَهُ يَقُولُ: [رَبِّ الْمَلاَئِكَةِ وَالرُّوحِ].",
         latin: "Subḥāna al-maliki al-quddūs (tres veces, alzando y alargando la voz en la tercera diciendo): [Rabbi al-malā'ikati war-rūḥ].",
         explanationEs: "Glorificado sea el Rey, el Santísimo (tres veces, elevando y alargando la voz en la tercera oportunidad diciendo: [Señor de los ángeles y del Espíritu]).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_34",
     titleAr: "دُعَاءُ الهَمِّ وَالحَزَنِ",
     titleEs: "Súplica ante la preocupación y la tristeza",
     items: [
      {
         text: "اللَّهُمَّ إِنِّي عَبْدُكَ، ابْنُ عَبْدِكَ، ابْنُ أَمَتِكَ، نَاصِيَتِي بِيَدِكَ، مَاضٍ فِيَّ حُكْمُكَ، عَدْلٌ فِيَّ قَضَاؤُكَ، أَسْأَلُكَ بِكُلِّ اسْمٍ هُوَ لَكَ، سَمَّيْتَ بِهِ نَفْسَكَ، أَوْ أَنْزَلْتَهُ فِي كِتَابِكَ، أَوْ عَلَّمْتَهُ أَحَداً مِنْ خَلْقِكَ، أَوِ اسْتَأْثَرْتَ بِهِ فِي عِلْمِ الْغَيْبِ عِنْدَكَ، أَنْ تَجْعَلَ الْقُرْآنَ رَبِيعَ قَلْبِي، وَنُورَ صَدْرِي، وَجَلاَءَ حُزْنِي، وَذَهَابَ هَمِّي.",
         latin: "Allāhumma innī ʿabduka, ibnu ʿabdika, ibnu amatika, nāṣiyatī bi-yadik, māḍin fiyya ḥukmuk, ʿadlun fiyya qaḍā'uk, as'aluka bi-kulli ismin huwa lak, sammayta bihi nafsak, aw anzaltahu fī kitābik, aw ʿallamtahu aḥadan min khalqik, aw ista'tharta bihi fī ʿilmi al-ghaybi ʿindak, an tajʿala al-qur'āna rabīʿa qalbī, wa nūra ṣadrī, wa jalā'a ḥuznī, wa dhahāba hammī.",
         explanationEs: "¡Oh Al-lah! Ciertamente soy Tu siervo, hijo de Tu siervo, hijo de Tu sierva. Mi frente está en Tu mano, Tu juicio sobre mí es ejecutable y Tu decreto sobre mí es justo. Te pido por cada nombre que Te pertenece, con el que Te has nombrado a Ti mismo, o has revelado en Tu Libro, o has enseñado a alguno de Tus seres creados, o te has reservado en el conocimiento de lo oculto junto a Ti, que hagas del Corán la primavera de mi corazón, la luz de mi pecho, el alivio de mi tristeza y la liberación de mi preocupación.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْهَمِّ وَالْحَزَنِ، وَالْعَجْزِ وَالْكَسَلِ، وَالْبُخْلِ وَالْجُبْنِ، وَضَلَعِ الدَّيْنِ وَغَلَبَةِ الرِّجَالِ.",
         latin: "Allāhumma innī aʿūdhu bika mina al-hammi wal-ḥazan, wal-ʿajzi wal-kasal, wal-bukhli wal-jubn, wa ḍalaʿi ad-dayni wa ghalabati ar-rijāl.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti de la ansiedad y de la tristeza, de la incapacidad y de la pereza, de la tacañería y de la cobardía, del peso de las deudas y de la opresión de los hombres.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_35",
     titleAr: "دُعَاءُ الكَرْبِ",
     titleEs: "Súplica ante la aflicción o angustia severa",
     items: [
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ الْعَظِيمُ الْحَلِيمُ، لاَ إِلَهَ إِلاَّ اللَّهُ رَبُّ الْعَرْشِ الْعَظِيمِ، لاَ إِلَهَ إِلاَّ اللَّهُ رَبُّ السَّمَوَاتِ وَرَبُّ الأَرْضِ وَرَبُّ الْعَرْشِ الْكَرِيمِ.",
         latin: "Lā ilāha illā Allāhu al-ʿaẓīmu al-ḥalīm, lā ilāha illā Allāhu rabbu al-ʿarshi al-ʿaẓīm, lā ilāha illā Allāhu rabbu as-samāwāti wa rabbu al-arḍi wa rabbu al-ʿarshi al-karīm.",
         explanationEs: "No hay más divinidad que Al-lah, el Grandioso, el Tolerante. No hay más divinidad que Al-lah, Señor del Trono grandioso. No hay más divinidad que Al-lah, Señor de los cielos, Señor de la tierra y Señor del Trono noble.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ رَحْمَتَكَ أَرْجُو، فَلاَ تَكِلْنِي إِلَى نَفْسِي طَرْفَةَ عَيْنٍ، وَأَصْلِحْ لِي شَأْنِي كُلَّهُ، لاَ إِلَهَ إِلاَّ أَنْتَ.",
         latin: "Allāhumma raḥmataka arjū, fa-lā takilnī ilā nafsī ṭarfata ʿayn, wa aṣliḥ lī sha'nī kullah, lā ilāha illā ant.",
         explanationEs: "¡Oh Al-lah! Tu misericordia espero, no me abandones a mí mismo ni por el parpadeo de un ojo, y arregla todos mis asuntos. No hay más divinidad excepto Tú.",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ أَنْتَ سُبْحَانَكَ إِنِّي كُنْتُ مِنَ الظَّالِمِينَ.",
         latin: "Lā ilāha illā anta subḥānaka innī kuntu mina aẓ-ẓālimīn.",
         explanationEs: "No hay más divinidad excepto Tú, ¡glorificado seas! Ciertamente he sido de los injustos.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُ اللَّهُ رَبِّي لاَ أُشْرِكُ بِهِ شَيْئاً.",
         latin: "Allāhu Allāhu rabbī lā ushriku bihi shay'ā.",
         explanationEs: "Al-lah, Al-lah es mi Señor, no le asocio absolutamente nada.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_36",
     titleAr: "دُعَاءُ لِقَاءِ العَدُوِّ وَذِي السُّلْطَانِ",
     titleEs: "Súplica al enfrentarse al enemigo o a un gobernante/autoridad",
     items: [
      {
         text: "اللَّهُمَّ إِنَّا نَجْعَلُكَ فِي نُحُورِهِمْ، وَنَعُوذُ بِكَ مِنْ شُرُورِهِمْ.",
         latin: "Allāhumma innā najʿaluka fī nuḥūrihim, wa naʿūdhu bika min shurūrihim.",
         explanationEs: "¡Oh Al-lah! Te ponemos al frente contra ellos y nos refugiamo en Ti de sus males.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ أَنْتَ عَضُدِي، وَأَنْتَ نَصِيرِي، بِكَ أَحُولُ وَبِكَ أَصُولُ، وَبِكَ أُقَاتِلُ.",
         latin: "Allāhumma anta ʿaḍudī, wa anta naṣīrī, bika aḥūlu wa bika aṣūlu, wa bika uqātil.",
         explanationEs: "¡Oh Al-lah! Tú eres mi apoyo y Tú eres mi socorredor. Por Ti me muevo, por Ti me defiendo y por Ti combato.",
         count: 1,
         maxCount: 1
      },
      {
         text: "حَسْبُنَا اللَّهُ وَنِعْمَ الْوَكِيلُ.",
         latin: "Ḥasbunā Allāhu wa niʿma al-wakīl.",
         explanationEs: "Suficiente para nosotros es Al-lah, y ¡qué excelente Protector!",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_37",
     titleAr: "دُعَاءُ مَنْ خَافَ ظُلْمَ السُّلْطَانِ",
     titleEs: "Súplica de quien teme la opresión de un gobernante",
     items: [
      {
         text: "اللَّهُمَّ ربَّ السَّمَوَاتِ السَّبْعِ، وَرَبَّ الْعَرْشِ الْعَظِيمِ، كُنْ لِي جَاراً مِنْ فُلاَنِ بْنِ فُلاَنٍ، وَأَحْزَابِهِ مِنْ خَلاَئِقِكَ، أَنْ يَفْرُطَ عَلَيَّ أَحَدٌ مِنْهُمْ أَوْ يَطْغَى، عَزَّ جَارُكَ، وَجَلَّ ثَنَاؤُكَ، وَلاَ إِلَهَ إِلاَّ أَنْتَ.",
         latin: "Allāhumma rabba as-samāwāti as-sabʿi, wa rabba al-ʿarshi al-ʿaẓīm, kun lī jāran min fulāni ibni fulān, wa aḥzābihi min khalā'iqika, an yafruṭa ʿalayya aḥadun minhum aw yaṭghā, ʿazza jāruka, wa jalla thanā'uka, wa lā ilāha illā ant.",
         explanationEs: "¡Oh Al-lah, Señor de los siete cielos y Señor del Trono grandioso! Sé para mí un protector contra (Fulano, hijo de Fulano) y sus aliados de Tu creación, para que ninguno de ellos se me adelante en agresión ni se extralimite contra mí. Poderoso es Tu protegido, gloriosa es Tu alabanza y no hay más divinidad excepto Tú.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُ أَكْبَرُ، اللَّهُ أَعَزُّ مِنْ خَلْقِهِ جَمِيعاً، اللَّهُ أَعَزُّ مِمَّا أَخَافُ وَأَحْذَرُ، أَعُوذُ بِاللَّهِ الَّذِي لاَ إِلَهَ إِلاَّ هُوَ، الْمُمْسِكِ السَّمَوَاتِ السَّبْعِ أَنْ يَقَعْنَ عَلَى الأَرْضِ إِلاَّ بِإِذْنِهِ، مِنْ شَرِّ عَبْدِكَ فُلاَنٍ، وَجُنُودِهِ وَأَتْبَاعِهِ وَأَشْيَاعِهِ، مِنَ الْجِنِّ وَالإِنْسِ، اللَّهُمَّ كُنْ لِي جَاراً مِنْ شَرِّهِمْ، جَلَّ ثَنَاؤُكَ وَعَزَّ جَارُكَ، وَتَبَارَكَ اسْمُكَ، وَلاَ إِلَهَ غَيْرُكَ.",
         latin: "Allāhu akbaru, Allāhu aʿazzu min khalqihi jamīʿā, Allāhu aʿazzu mimmā akhāfu wa aḥdhar, aʿūdhu billāhi alladhī lā ilāha illā huwa, al-mumsiki as-samāwāti as-sabʿi an yaqaʿna ʿalā al-arḍi illā bi-idhnih, min sharri ʿabdika fulān, wa junūdihi wa atbāʿihi wa ashyāʿih, mina al-jinni wal-ins, Allāhumma kun lī jāran min sharrihim, jalla thanā'uka wa ʿazza jāruk, wa tabāraka ismuk, wa lā ilāha ghayruk (tres veces).",
         explanationEs: "Al-lah es el más Grande, Al-lah es más poderoso que toda Su creación, Al-lah es más poderoso que lo que temo y precavo. Me refugio en Al-lah, no hay más divinidad excepto Él, Quien sostiene los siete cielos para que no caigan sobre la tierra sino por Su permiso, del mal de Tu siervo (Fulano), de sus ejércitos, sus seguidores y sus partidarios, de entre los genios y los humanos. ¡Oh Al-lah! Sé para mí un protector contra sus males. Gloriosa es Tu alabanza, poderoso es Tu protegido, bendito es Tu nombre y no hay más divinidad que Tú. (Se dice tres veces).",
         count: 3,
         maxCount: 3
      }
    ]
  },
  {
     id: "hisn_38",
     titleAr: "الدُّعَاءُ عَلَى العَدُوِّ",
     titleEs: "Súplica contra el enemigo",
     items: [
      {
         text: "اللَّهُمَّ مُنْزِلَ الْكِتَابِ، سَرِيعَ الْحِسَابِ، اهْزِمِ الأَحْزَابَ، اللَّهُمَّ اهْزِمْهُمْ وَزَلْزِلْهُمْ.",
         latin: "Allāhumma munzila al-kitāb, sarīʿa al-ḥisāb, ihzimi al-aḥzāb, Allāhumma ihzimhum wa zalzilhum.",
         explanationEs: "¡Oh Al-lah! Revelador del Libro, Rápido en el cómputo, derrota a las facciones enemigas. ¡Oh Al-lah! Derrótalos y hazlos temblar.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_39",
     titleAr: "مَا يَقُولُ مَنْ خَافَ قَوْماً",
     titleEs: "Lo que dice quien teme a un grupo de personas",
     items: [
      {
         text: "اللَّهُمَّ اكْفِنِيهِمْ بِمَا شِئْتَ.",
         latin: "Allāhumma ikfinīhim bi-mā shi't.",
         explanationEs: "¡Oh Al-lah! Protégeme de ellos como Tú quieras.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_40",
     titleAr: "دُعَاءُ مَنْ أَصَابَهُ وَسْوَسَةٌ فِي الإِيمَانِ",
     titleEs: "Súplica para quien sufre de susurros/dudas sobre la fe",
     items: [
      {
         text: "يَسْتَعِيذُ بِاللَّهِ وَيَنْتَهِي عَمَّا شَكَّ فِيهِ.",
         latin: "Yastaʿīdhu billāhi wa yantahī ʿammā shakka fīh.",
         explanationEs: "Busca refugio en Al-lah y se abstiene de dar curso a las dudas que le surgen.",
         count: 1,
         maxCount: 1
      },
      {
         text: "آمَنْتُ بِاللَّهِ وَرُسُلِهِ.",
         latin: "Āmantu billāhi wa rusulih.",
         explanationEs: "Dice: Creo en Al-lah y en Sus mensajeros.",
         count: 1,
         maxCount: 1
      },
      {
         text: "﴿هُوَ الأَوَّلُ وَالآخِرُ وَالظَّاهِرُ وَالْبَاطِنُ وَهُوَ بِكُلِّ شَيْءٍ عَلِيمٌ﴾.",
         latin: "﴿Huwa al-awwalu wal-ākhiru waẓ-ẓāhiru wal-bāṭinu wa huwa bi-kulli shay'in ʿalīm﴾.",
         explanationEs: "Lee las palabras del Altísimo: ﴿Él es el Primero y el Último, el Evidente y el Oculto, y Él es Conocedor de todas las cosas﴾.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_41",
     titleAr: "دُعَاءُ قَضَاءِ الدَّيْنِ",
     titleEs: "Súplica para el pago de las deudas",
     items: [
      {
         text: "اللَّهُمَّ اكْفِنِي بِحَلاَلِكَ عَنْ حَرَامِكَ، وَأَغْنِنِي بِفَضْلِكَ عَمَّنْ سِوَاكَ.",
         latin: "Allāhumma ikfinī bi-ḥalālika ʿan ḥarāmik, wa aghninī bi-faḍlika ʿamman siwāk.",
         explanationEs: "¡Oh Al-lah! Haz que lo lícito me sea suficiente frente a lo ilícito, y enriquéceme con Tu favor prescindiendo de cualquier otro fuera de Ti.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْهَمِّ وَالْحَزَنِ، وَالْعَجْزِ وَالْكَسَلِ، وَالْبُخْلِ وَالْجُبْنِ، وَضَلَعِ الدَّيْنِ وَغَلَبَةِ الرِّجَالِ.",
         latin: "Allāhumma innī aʿūdhu bika mina al-hammi wal-ḥazan, wal-ʿajzi wal-kasal, wal-bukhli wal-jubn, wa ḍalaʿi ad-dayni wa ghalabati ar-rijāl.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti de la ansiedad y de la tristeza, de la incapacidad y de la pereza, de la tacañería y de la cobardía, del peso de las deudas y de la opresión de los hombres.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_42",
     titleAr: "دُعَاءُ الوَسْوَسَةِ فِي الصَّلاَةِ وَالقِرَاءَةِ",
     titleEs: "Súplica contra las distracciones y susurros en la oración y la lectura",
     items: [
      {
         text: "أَعُوذُ بِاللَّهِ مِنَ الشَّيْطَانِ الرَّجِيمِ، وَاتْفُلْ عَلَى يَسَارِكَ (ثَلاَثاً).",
         latin: "Aʿūdhu billāhi mina ash-shayṭāni ar-rajīm (y escupe suavemente a la izquierda tres veces).",
         explanationEs: "Dice: Me refugio en Al-lah del Demonio repudiado, y sopla suavemente hacia su izquierda tres veces.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_43",
     titleAr: "دُعَاءُ مَنِ اسْتَصْعَبَ عَلَيْهِ أَمْرٌ",
     titleEs: "Súplica para quien se le dificulta un asunto",
     items: [
      {
         text: "اللَّهُمَّ لاَ سَهْلَ إِلاَّ مَا جَعَلْتَهُ سَهْلاً، وَأَنْتَ تَجْعَلُ الْحَزْنَ إِذَا شِئْتَ سَهْلاً.",
         latin: "Allāhumma lā sahla illā mā jaʿaltahu sahlā, wa anta tajʿalu al-ḥazna idhā shi'ta sahlā.",
         explanationEs: "¡Oh Al-lah! No hay nada fácil salvo lo que Tú haces fácil, y Tú haces que la dificultad, si quieres, sea fácil.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_44",
     titleAr: "مَا يَقُولُ وَيَفْعَلُ مَنْ أَذْنَبَ ذَنْباً",
     titleEs: "Lo que dice y hace quien comete un pecado",
     items: [
      {
         text: "مَا مِنْ عَبْدٍ يُذْنِبُ ذَنْباً فَيُحْسِنُ الطُّهُورَ، ثُمَّ يَقُومُ فَيُصَلِّي رَكْعَتَيْنِ، ثُمَّ يَسْتَغْفِرُ اللَّهَ إِلاَّ غَفَرَ اللَّهُ لَهُ.",
         latin: "Mā min ʿabdin yudhnibu dhanban fa-yuḥsinu aṭ-ṭuhūra, thumma yaqūmu fa-yuṣallī rakʿatayni, thumma yastaghfiru Allāha illā ghafara Allāhu lah.",
         explanationEs: "No hay siervo que cometa un pecado, se purifique minuciosamente, luego se levante y realice dos unidades de oración (raka'at), e pida perdón a Al-lah, sin que Al-lah lo perdone.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_45",
     titleAr: "دُعَاءُ طَرْدِ الشَّيْطَانِ وَوَسَاوِسِهِ",
     titleEs: "Acciones para ahuyentar al Demonio y sus susurros",
     items: [
      {
         text: "الاسْتِعَاذَةُ بِاللَّهِ مِنْهُ.",
         latin: "Al-istiʿādhatu billāhi minh.",
         explanationEs: "Buscar refugio en Al-lah de él (diciendo: A'udhu billahi mina ash-shaytan ar-rajim).",
         count: 1,
         maxCount: 1
      },
      {
         text: "الأَذَانُ.",
         latin: "Al-adhān.",
         explanationEs: "La llamada a la oración (el Adhán ahuyenta al Demonio).",
         count: 1,
         maxCount: 1
      },
      {
         text: "الأَذْكَارُ وَقِرَاءَةُ الْقُرْآنِ.",
         latin: "Al-adhkāru wa qirā'atu al-qur'ān.",
         explanationEs: "Las súplicas de recuerdo y la lectura del Corán.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_46",
     titleAr: "الدَّعَاءُ حِينَمَا يَقَعُ مَا لاَ يَرْضَاهُ أَوْ غُلِبَ عَلَى أَمْرِهِ",
     titleEs: "Súplica cuando ocurre algo Indeseado o se es superado por las circunstancias",
     items: [
      {
         text: "قَدَرُ اللَّهِ وَمَا شَاءَ فَعَلَ.",
         latin: "Qadaru Allāhi wa mā shā'a faʿal.",
         explanationEs: "Es el decreto de Al-lah, y Él hace lo que quiere.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_47",
     titleAr: "تَهْنِئَةُ المَوْلُودِ لَهُ وَجَوَابُهُ",
     titleEs: "Felicitación por el nacimiento de un bebé y su respuesta",
     items: [
      {
         text: "بَارَكَ اللَّهُ لَكَ فِي الْمَوْهُوبِ لَكَ، وَشَكَرْتَ الْوَاهِبَ، وَبَلَغَ أَشُدَّهُ، وَرُزِقْتَ بِرَّهُ. وَيَرُدُّ عَلَيْهِ الْمُهَنَّأُ فَيَقُولُ: بَارَكَ اللَّهُ لَكَ وَبَارَكَ عَلَيْكَ، وَجَزَاكَ اللَّهُ خَيْراً، وَرَزَقَكَ اللَّهُ مِثْلَهُ، وَأَجْزَلَ ثَوَابَكَ.",
         latin: "Bāraka Allāhu laka fī al-mawhūbi lak, wa shakarta al-wāhib, wa balagha ashuddah, wa ruziqta birrah. Wa yaruddu ʿalayhi al-muhannā'u fa-yaqūl: Bāraka Allāhu laka wa bāraka ʿalayk, wa jazāka Allāhu khayrā, wa razaqaka Allāhu mithlah, wa ajzala thawābak.",
         explanationEs: "Que Al-lah bendiga para ti lo que te ha concedido, agradezcas al Otorgante, llegue a su madurez y seas agraciado con su piedad filial. Y quien recibe la felicitación responde: Que Al-lah te bendiga y derrame Sus bendiciones sobre ti, te recompense con el bien, te conceda algo semejante y multiplique tu recompensa.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_48",
     titleAr: "مَا يُعَوَّذُ بِهِ الأَوْلاَدُ",
     titleEs: "Súplica de protección para los niños",
     items: [
      {
         text: "أُعِيذُكُمَا بِكَلِمَاتِ اللَّهِ التَّامَّةِ مِنْ كُلِّ شَيْطَانٍ وَهَامَّةٍ، وَمِنْ كُلِّ عَيْنٍ لاَمَّةٍ.",
         latin: "Uʿīdhukumā bi-kalimāti Allāhi at-tāmmati min kulli shayṭānin wa hāmmah, wa min kulli ʿaynin lāmmah.",
         explanationEs: "Los pongo bajo la protección de las palabras perfectas de Al-lah de todo demonio, de todo animal venenoso y de todo ojo dañino.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_49",
     titleAr: "الدَّعَاءُ لِلْمَرِيضِ فِي عِيَادَتِهِ",
     titleEs: "Súplica por el enfermo al visitarlo",
     items: [
      {
         text: "لاَ بَأْسَ طَهُورٌ إِنْ شَاءَ اللَّهُ.",
         latin: "Lā ba'sa ṭahūrun in shā'a Allāh.",
         explanationEs: "No hay mal alguno, esto es una purificación, si Al-lah quiere.",
         count: 1,
         maxCount: 1
      },
      {
         text: "أَسْأَلُ اللَّهَ الْعَظِيمَ رَبَّ الْعَرْشِ الْعَظِيمِ أَنْ يَشْفِيَكَ.",
         latin: "As'alu Allāha al-ʿaẓīma rabba al-ʿarshi al-ʿaẓīmi an yashfiyak.",
         explanationEs: "Ruego a Al-lah el Grandioso, Señor del Trono grandioso, que te sane. (Siete veces).",
         count: 7,
         maxCount: 7
      }
    ]
  },
  {
     id: "hisn_50",
     titleAr: "فَضْلُ عِيَادَةِ المَرِيضِ",
     titleEs: "Mérito de visitar al enfermo",
     items: [
      {
         text: "قَالَ النَّبِيُّ صلى الله عليه وسلم: إِذَا عَادَ الرَّجُلُ أَخَاهُ الْمُسْلِمَ مَشَى فِي خِرَافَةِ الْجَنَّةِ حَتَّى يَجْلِسَ، فَإِذَا جَلَسَ غَمَرَتْهُ الرَّحْمَةُ، فَإِنْ كَانَ غُدْوَةً صَلَّى عَلَيْهِ سَبْعُونَ أَلْفَ مَلَكٍ حَتَّى يُمْسِيَ، وَإِنْ كَانَ مَسَاءً صَلَّى عَلَيْهِ سَبْعُونَ أَلْفَ مَلَكٍ حَتَّى يُصْبِحَ.",
         latin: "Qāla an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam: Idhā ʿāda ar-rajulu akhāhu al-muslima mashā fī khirāfati al-jannati ḥattā yajlis, fa-idhā jalasa ghamarathuhu ar-raḥmah, fa-in kāna ghudwatan ṣallā ʿalayhi sabʿūna alfa malakin ḥattā yumsiya, wa in kāna masā'an ṣallā ʿalayhi sabʿūna alfa malakin ḥattā yuṣbiḥ.",
         explanationEs: "Dijo el Profeta (que la paz y las bendiciones de Al-lah sean con él): Cuando un musulmán visita a su hermano musulmán enfermo, camina recolectando los frutos del Paraíso hasta que se sienta; y cuando se sienta, la misericordia lo envuelve. Si es por la mañana, setenta mil ángeles piden por él hasta la tarde; y si es por la tarde, setenta mil ángeles piden por él hasta la mañana.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_51",
     titleAr: "دُعَاءُ المَرِيضِ الَّذِي يَئِسَ مِنْ حَيَاتِهِ",
     titleEs: "Súplica del enfermo terminal o que pierde la esperanza de vida",
     items: [
      {
         text: "اللَّهُمَّ اغْفِرْ لِي، وَارْحَمْنِي، وَأَلْحِقْنِي بِالرَّفِيقِ الأَعْلَى.",
         latin: "Allāhumma ighfir lī, warḥamnī, wa al-ḥiqnī bir-rafīqi al-aʿlā.",
         explanationEs: "¡Oh Al-lah! Perdóname, ten misericordia de mí y únete a mí con el Compañero Supremo (Al-lah en el nivel más alto del Paraíso).",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ إِنَّ لِلْمَوْتِ سَكَرَاتٍ.",
         latin: "Lā ilāha illā Allāhu inna lil-mawti sakarāt.",
         explanationEs: "No hay más divinidad que Al-lah; ciertamente la muerte tiene sus agonías.",
         count: 1,
         maxCount: 1
      },
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَاللَّهُ أَكْبَرُ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لاَ إِلَهَ إِلاَّ اللَّهُ لَهُ المُلْكُ وَلَهُ الْحَمْدُ، لاَ إِلَهَ إِلاَّ اللَّهُ وَلاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
         latin: "Lā ilāha illā Allāhu wallāhu akbar, lā ilāha illā Allāhu waḥdah, lā ilāha illā Allāhu waḥdahu lā sharīka lah, lā ilāha illā Allāhu lahu al-mulku wa lahu al-ḥamd, lā ilāha illā Allāhu wa lā ḥawla wa lā quwwata illā billāh.",
         explanationEs: "No hay más divinidad que Al-lah y Al-lah es el más Grande. No hay más divinidad que Al-lah, Único. No hay más divinidad que Al-lah, Único, sin asociados. No hay más divinidad que Al-lah, Suyo es el reino y Suya es la alabanza. No hay más divinidad que Al-lah y no hay fuerza ni poder sino en Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_52",
     titleAr: "تَلْقِينُ المُحْتَضَرِ",
     titleEs: "Inculcar el testimonio al moribundo",
     items: [
      {
         text: "مَنْ كَانَ آخِرُ كَلاَمِهِ لاَ إِلَهَ إِلاَّ اللَّهُ دَخَلَ الْجَنَّةَ.",
         latin: "Man kāna ākhiru kalāmihi lā ilāha illā Allāhu dakhala al-jannah.",
         explanationEs: "Aquel cuyas últimas palabras sean 'no hay más divinidad que Al-lah', entrará al Paraíso.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_53",
     titleAr: "دُعَاءُ مَنْ أَصَابَهُ مُصِيبَةٌ",
     titleEs: "Súplica de quien sufre una desgracia o calamidad",
     items: [
      {
         text: "إِنَّا لِلَّهِ وَإِنَّا إِلَيْهِ رَاجِعُونَ، اللَّهُمَّ أْجُرْنِي فِي مُصِيبَتِي، وَأَخْلِفْ لِي خَيْراً مِنْهَا.",
         latin: "Innā lillāhi wa innā ilayhi rājiʿūn, Allāhumma'-jurnī fī muṣībatī, wa akhlif lī khayran minhā.",
         explanationEs: "Ciertamente pertenecemos a Al-lah y a Él hemos de retornar. ¡Oh Al-lah! Recompénsame en mi desgracia y reemplázamela por algo mejor.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_54",
     titleAr: "الدُّعَاءُ عِنْدَ إِغْمَاضِ المَيِّتِ",
     titleEs: "Súplica al cerrar los ojos al difunto",
     items: [
      {
         text: "اللَّهُمَّ اغْفِرْ لِفُلاَنٍ (بِاسْمِهِ) وَارْفَعْ دَرَجَتَهُ فِي الْمَهْدِيِّينَ، وَاخْلُفْهُ فِي عَقِبِهِ فِي الْغَابِرِينَ، وَاغْفِرْ لَنَا وَلَهُ يَا رَبَّ الْعَالَمِينَ، وَافْسَحْ لَهُ فِي قَبْرِهِ، وَنَوِّرْ لَهُ فِيهِ.",
         latin: "Allāhumma ighfir li-fulān (por su nombre) warfaʿ darajatahu fī al-mahdiyyīn, wakhlufhu fī ʿaqibihi fī al-ghābirīn, waghfir lanā wa lahu yā rabba al-ʿālamīn, wafsaḥ lahu fī qabrih, wa nawwir lahu fīh.",
         explanationEs: "¡Oh Al-lah! Perdona a (menciona su nombre) y eleva su rango entre los bien guiados, sé Su sustituto para sus descendientes que quedan atrás, perdónanos a nosotros y a él, ¡oh Señor de los mundos!, ensancha para él su tumba e ilumínasela.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_55",
     titleAr: "الدُّعَاءُ لِلْمَيِّتِ فِي الصَّلاَةِ عَلَيْهِ",
     titleEs: "Súplica por el difunto en la oración fúnebre (Janazah)",
     items: [
      {
         text: "اللَّهُمَّ اغْفِرْ لَهُ وَارْحَمْهُ، وَعَافِهِ، وَاعْفُ عَنْهُ، وَأَكْرِمْ نُزُلَهُ، وَوَسِّعْ مُدْخَلَهُ، وَاغْسِلْهُ بِالْمَاءِ وَالثَّلْجِ وَالْبَرَدِ، وَنَقِّهِ مِنَ الْخَطَايَا كَمَا نَقَّيْتَ الثَّوْبَ الأَبْيَضَ مِنَ الدَّنَسِ، وَأَبْدِلْهُ دَاراً خَيْراً مِنْ دَارِهِ، وَأَهْلاً خَيْراً مِنْ أَهْلِهِ، وَزَوْجاً خَيْراً مِنْ زَوْجِهِ، وَأَدْخِلْهُ الْجَنَّةَ، وَأَعِذْهُ مِنْ عَذَابِ القَبْرِ [وَعَذَابِ النَّارِ].",
         latin: "Allāhumma ighfir lahu warḥamhu, wa ʿāfihi, waʿfu ʿanhu, wa akrim nuzulahu, wa wassiʿ mudkhalahu, waghsilhu bil-mā'i wath-thalji wal-barad, wa naqqihi mina al-khaṭāyā kamā naqqayta ath-thawba al-abyaḍa mina ad-danas, wa abdilhu dāran khayran min dārih, wa ahlan khayran min ahlih, wa zawjan khayran min zawjih, wa adkhilhu al-jannah, wa aʿidhhu min ʿadhābi al-qabr [wa ʿadhābi an-nār].",
         explanationEs: "¡Oh Al-lah! Perdónalo y ten misericordia de él, dale bienestar y perdónalo, honra su morada y ensancha su entrada; lávalo con agua, nieve y granizo, y purifícalo de los pecados como purificas el vestido blanco de la impureza. Concédele una morada mejor que su morada, una familia mejor que su familia, un cónyuge mejor que su cónyuge, introdúcelo en el Paraíso y protégelo del castigo de la tumba [y del castigo del Fuego].",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اغْفِرْ لِحَيِّنَا وَمَيِّتِنَا، وَشَاهِدِنَا وَغَائِبِنَا، وَصَغِيرِنَا وَكَبِيرِنَا، وَذَكَرِنَا وَأُنْثَانَا. اللَّهُمَّ مَنْ أَحْيَيْتَهُ مِنَّا فَأَحْيِهِ عَلَى الإِسْلاَمِ، وَمَنْ تَوَفَّيْتَهُ مِنَّا فَتَوَفَّهُ عَلَى الإِيمَانِ، اللَّهُمَّ لاَ تَحْرِمْنَا أَجْرَهُ، وَلاَ تُضِلَّنَا بَعْدَهُ.",
         latin: "Allāhumma ighfir li-ḥayyinā wa mayyitinā, wa shāhidinā wa ghā'ibinā, wa ṣaghīrinā wa kabīrinā, wa dhakarinā wa unthānā. Allāhumma man aḥyaytahu minnā fa-aḥyihi ʿalā al-islām, wa man tawaffaytahu minnā fa-tawaffahu ʿalā al-īmān. Allāhumma lā taḥrimnā ajrah, wa lā tuḍillanā baʿdah.",
         explanationEs: "¡Oh Al-lah! Perdona a nuestros vivos y a nuestros muertos, a los presentes y a los ausentes, a nuestros pequeños y a nuestros grandes, a nuestros hombres y a nuestras mujeres. ¡Oh Al-lah! A quien de nosotros mantengas con vida, hazlo vivir en el Islam, y a quien hagas morir, hazlo morir en la fe. ¡Oh Al-lah! No nos prives de su recompensa ni nos extravíes después de él.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنَّ فُلاَنَ بْنَ فُلاَنٍ فِي ذِمَّتِكَ، وَحَبْلِ جِوَارِكَ، فَقِهِ مِنْ فِتْنَةِ الْقَبْرِ، وَعَذَابِ النَّارِ، وَأَنْتَ أَهْلُ الْوَفَاءِ وَالْحَقِّ، فَاغْفِرْ لَهُ وَارْحَمْهُ إِنَّكَ أَنْتَ الْغَفُورُ الرَّحِيمُ.",
         latin: "Allāhumma inna fulāna ibna fulān fī dhimmatika, wa ḥabli jiwārik, fa-qihi min fitnati al-qabr, wa ʿadhābi an-nār, wa anta ahlu al-wafā'i wal-ḥaqq, faghfir lahu warḥamhu innaka anta al-ghafūru ar-raḥīm.",
         explanationEs: "¡Oh Al-lah! Ciertamente (Fulano hijo de Fulano) está bajo Tu protección y Tu amparo; protégelo de la prueba de la tumba y del castigo del Fuego. Tú eres el Dueño del cumplimiento y de la Verdad, perdónalo y ten misericordia de él, ciertamente Tú eres el Absolvedor, el Misericordioso.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ عَبْدُكَ وَابْنُ أَمَتِكَ احْتَاجَ إِلَى رَحْمَتِكَ، وَأَنْتَ غَنِيٌّ عَنْ عَذَابِهِ، إِنْ كَانَ مُحْسِناً فَزِدْ فِي حَسَنَاتِهِ، وَإِنْ كَانَ مُسِيئاً فَتَجَاوَزْ عَنْهُ.",
         latin: "Allāhumma ʿabduka wabnu amatika iḥtāja ilā raḥmatik, wa anta ghaniyyun ʿan ʿadhābih, in kāna muḥsinan fa-zid fī ḥasanātih, wa in kāna musī'an fa-tajāwaz ʿanh.",
         explanationEs: "¡Oh Al-lah! Tu siervo e hijo de Tu sierva está necesitado de Tu misericordia, y Tú no necesitas de su castigo. Si fue benefactor, aumenta sus buenas obras; y si fue pecador, pasa por alto sus faltas.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_56",
     titleAr: "الدُّعَاءُ لِلْفَرَطِ فِي الصَّلاَةِ عَلَيْهِ",
     titleEs: "Súplica en la oración fúnebre por un niño fallecido (Farat)",
     items: [
      {
         text: "اللَّهُمَّ أَعِذْهُ مِنْ عَذَابِ الْقَبْرِ. [اللَّهُمَّ اجْعَلْهُ فَرَطاً وَذُخْراً لِوَالِدَيْهِ، وَشَفِيعاً مُجَاباً، اللَّهُمَّ ثَقِّلْ بِهِ مَوَازِينَهُمَا، وَأَعْظِمْ بِهِ أُجُورَهُمَا، وَأَلْحِقْهُ بِصَالِحِ الْمُؤْمِنِينَ، وَاجْعَلْهُ فِي كَفَالَةِ إِبْرَاهِيمَ، وَقِهِ بِرَحْمَتِكَ عَذَابَ الْجَحِيمِ، وَأَبْدِلْهُ دَاراً خَيْراً مِنْ دَارِهِ، وَأَهْلاً خَيْراً مِنْ أَهْلِهِ، اللَّهُمَّ اغْفِرْ لِأَسْلاَفِنَا، وَأَفْرَاطِنَا، وَمَنْ سَبَقَنَا بِالإِيمَانِ].",
         latin: "Allāhumma aʿidhhu min ʿadhābi al-qabr. [Allāhumma ijʿalhu faraṭan wa dhukhran li-wālidayh, wa shafīʿan mujābā, Allāhumma thaqqil bihi mawāzīnahumā, wa aʿẓim bihi ujūrahumā, wa al-ḥiqhu bi-ṣāliḥi al-mu'minīn, wa ijʿalhu fī kafālati Ibrāhīm, wa qihi bi-raḥmatika ʿadhāba al-jaḥīm, wa abdilhu dāran khayran min dārih, wa ahlan khayran min ahlih, Allāhumma ighfir li-aslāfinā, wa afrāṭinā, wa man sabaqanā bil-īmān].",
         explanationEs: "¡Oh Al-lah! Protégelo del castigo de la tumba. [¡Oh Al-lah! Hazlo un precursor y un tesoro para sus padres, y un intercesor cuya intercesión sea aceptada. ¡Oh Al-lah! Haz pesada con él la balanza de sus padres, engrandece con él sus recompensas, únelo a los creyentes piadosos, ponlo bajo el cuidado de Abraham y líbralo con Tu misericordia del castigo del Infierno. Concédele una morada mejor que su morada y una familia mejor que su familia. ¡Oh Al-lah! Perdona a nuestros antepasados, a nuestros niños fallecidos y a quienes nos precedieron en la fe].",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اجْعَلْهُ لَنَا فَرَطاً، وَسَلَفاً، وَأَجْراً.",
         latin: "Allāhumma ijʿalhu lanā faraṭā, wa salafā, wa ajrā.",
         explanationEs: "¡Oh Al-lah! Hazlo para nosotros un precursor, un antecesor y una recompensa.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_57",
     titleAr: "دُعَاءُ التَّعْزِيَةِ",
     titleEs: "Súplica de pésame o condolencia",
     items: [
      {
         text: "إِنَّ لِلَّهِ مَا أَخَذَ، وَلَهُ مَا أَعْطَى، وَكُلُّ شَيْءٍ عِنْدَهُ بِأَجَلٍ مُسَمًّى... فَلْتَصْبِرْ وَلْتَحْتَسِبْ. [أَعْظَمَ اللَّهُ أَجْرَكَ، وَأَحْسَنَ عَزَاءَكَ، وَغَفَرَ لِمَيِّتِكَ].",
         latin: "Inna lillāhi mā akhadha, wa lahu mā aʿṭā, wa kullu shay'in ʿindahu bi-ajalin musammā... fal-taṣbir wal-taḥtasib. [Aʿẓama Allāhu ajrak, wa aḥsana ʿazā'ak, wa ghafara li-mayyitik].",
         explanationEs: "Ciertamente a Al-lah pertenece lo que toma y lo que da, y todo para Él tiene un plazo fijado... Ten paciencia y busca la recompensa divina. [Que Al-lah engrandezca tu recompensa, consolide tu consuelo y perdone a tu difunto].",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_58",
     titleAr: "الدُّعَاءُ عِنْدَ إِدْخَالِ المَيِّتِ القَبْرَ",
     titleEs: "Súplica al introducir al difunto en la tumba",
     items: [
      {
         text: "بِسْمِ اللَّهِ وَعَلَى سُنَّةِ رَسُولِ اللَّهِ.",
         latin: "Bismillāhi wa ʿalā sunnati rasūlillāh.",
         explanationEs: "En el nombre de Al-lah y siguiendo la Sunnah (tradición) del Mensajero de Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_59",
     titleAr: "الدُّعَاءُ بَعْدَ دَفْنِ المَيِّتِ",
     titleEs: "Súplica después de sepultar al difunto",
     items: [
      {
         text: "اللَّهُمَّ اغْفِرْ لَهُ، اللَّهُمَّ ثَبِّتْهُ.",
         latin: "Allāhumma ighfir lah, Allāhumma thabbith.",
         explanationEs: "¡Oh Al-lah! Perdónalo. ¡Oh Al-lah! Manténlo firme (ante las preguntas de los ángeles).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_60",
     titleAr: "دُعَاءُ زِيَارَةِ القُبُورِ",
     titleEs: "Súplica al visitar los cementerios",
     items: [
      {
         text: "السَّلاَمُ عَلَيْكُمْ أَهْلَ الدِّيَارِ، مِنَ الْمُؤْمِنِينَ وَالْمُسْلِمِينَ، وَإِنَّا إِنْ شَاءَ اللَّهُ بِكُمْ لاَحِقُونَ، [وَيَرْحَمُ اللَّهُ الْمُسْتَقْدِمِينَ مِنَّا وَالْمُسْتَأْخِرِينَ]، أَسْأَلُ اللَّهَ لَنَا وَلَكُمُ الْعَافِيَةَ.",
         latin: "As-salāmu ʿalaykum ahla ad-diyār, mina al-mu'minīna wal-muslimīn, wa innā in shā'a Allāhu bikum lāḥiqūn, [wa yarḥamu Allāhu al-mustaqdimīna minnā wal-musta'khirīn], as'alu Allāha lanā wa lakumu al-ʿāfiyah.",
         explanationEs: "La paz sea con vosotros, habitantes de las moradas, de entre los creyentes y los musulmanes. Ciertamente nosotros, si Al-lah quiere, nos uniremos a vosotros. [Que Al-lah tenga misericordia de los primeros y de los últimos de entre nosotros]. Pido a Al-lah el bienestar para nosotros y para vosotros.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_61",
     titleAr: "دُعَاءُ الرِّيحِ",
     titleEs: "Súplica cuando sopla el viento",
     items: [
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ خَيْرَهَا، وَأَعُوذُ بِكَ مِنْ شَرِّهَا.",
         latin: "Allāhumma innī as'aluka khayrahā, wa aʿūdhu bika min sharrihā.",
         explanationEs: "¡Oh Al-lah! Te pido su bien y me refugio en Ti de su mal.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ خَيْرَهَا، وَخَيْرَ مَا فِيهَا، وَخَيْرَ مَا أُرْسِلَتْ بِهِ، وَأَعُوذُ بِكَ مِنْ شَرِّهَا، وَشَرِّ مَا فِيهَا، وَشَرِّ مَا أُرْسِلَتْ بِهِ.",
         latin: "Allāhumma innī as'aluka khayrahā, wa khayra mā fīhā, wa khayra mā ursilat bih, wa aʿūdhu bika min sharrihā, wa sharri mā fīhā, wa sharri mā ursilat bih.",
         explanationEs: "¡Oh Al-lah! Te pido su bien, el bien de lo que hay en él y el bien con el que ha sido enviado; y me refugio en Ti de su mal, del mal de lo que hay en él y del mal con el que ha sido enviado.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_62",
     titleAr: "دُعَاءُ الرَّعْدِ",
     titleEs: "Súplica al escuchar el trueno",
     items: [
      {
         text: "سُبْحَانَ الَّذِي يُسَبِّحُ الرَّعْدُ بِحَمْدِهِ وَالْمَلاَئِكَةُ مِنْ خِيفَتِهِ.",
         latin: "Subḥāna alladhī yusabbiḥu ar-raʿdu bi-ḥamdihi wal-malā'ikatu min khīfatih.",
         explanationEs: "Glorificado sea Aquel a Quien el trueno alaba con Sus elogios y los ángeles por el temor a Él.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_63",
     titleAr: "مِنْ أَدْعِيَةِ الاسْتِسْقَاءِ",
     titleEs: "Súplicas para pedir la lluvia (Istisqa')",
     items: [
      {
         text: "اللَّهُمَّ اسْقِنَا غَيْثاً مُغِيثاً مَرِيئاً مَرِيعاً، نَافِعاً غَيْرَ ضَارٍّ، عَاجِلاً غَيْرَ آجِلٍ.",
         latin: "Allāhumma isqinā ghaythan mughīthan marī'an marīʿā, nāfiʿan ghayra ḍārr, ʿājilan ghayra ājil.",
         explanationEs: "¡Oh Al-lah! Envíanos una lluvia socorredora, provechosa, fértil, beneficiosa y no perjudicial, pronta y no demorada.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ أَغِثْنَا، اللَّهُمَّ أَغِثْنَا، اللَّهُمَّ أَغِثْنَا.",
         latin: "Allāhumma aghithnā, Allāhumma aghithnā, Allāhumma aghithnā.",
         explanationEs: "¡Oh Al-lah! Socórrenos con lluvia, ¡oh Al-lah! Socórrenos con lluvia, ¡oh Al-lah! Socórrenos con lluvia.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ اسْقِ عِبَادَكَ، وَبَهَائِمَكَ، وَانْشُرْ رَحْمَتَكَ، وَأَحْيِي بَلَدَكَ الْمَيِّتَ.",
         latin: "Allāhumma isqi ʿibādaka, wa bahā'imaka, wan-shur raḥmataka, wa aḥyi baladaka al-mayyit.",
         explanationEs: "¡Oh Al-lah! Da de beber a Tus siervos y a Tus animales, extiende Tu misericordia y da vida a Tu tierra muerta.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_64",
     titleAr: "الدُّعَاءُ إِذَا نَزَلَ المَطَرُ",
     titleEs: "Súplica cuando comienza a llover",
     items: [
      {
         text: "اللَّهُمَّ صَيِّباً نَافِعاً.",
         latin: "Allāhumma ṣayyiban nāfiʿā.",
         explanationEs: "¡Oh Al-lah! Haz que sea una lluvia abundante y beneficiosa.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_65",
     titleAr: "الذِّكْرُ بَعْدَ نُزُولِ المَطَرِ",
     titleEs: "Súplica después de la lluvia",
     items: [
      {
         text: "مُطِرْنَا بِفَضْلِ اللَّهِ وَرَحْمَتِهِ.",
         latin: "Muṭirnā bi-faḍli Allāhi wa raḥmatih.",
         explanationEs: "Ha llovido sobre nosotros por la gracia de Al-lah y Su misericordia.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_66",
     titleAr: "مِنْ أَدْعِيَةِ الاسْتِصْحَاءِ",
     titleEs: "Súplica para detener el exceso de lluvia (Istishā')",
     items: [
      {
         text: "اللَّهُمَّ حَوَالَيْنَا وَلاَ عَلَيْنَا، اللَّهُمَّ عَلَى الآكَامِ وَالظِّرَابِ، وَبُطُونِ الأَوْدِيَةِ، وَمَنَابِتِ الشَّجَرِ.",
         latin: "Allāhumma ḥawālaynā wa lā ʿalaynā, Allāhumma ʿalā al-ākāmi waẓ-ẓirāb, wa buṭūni al-awdiyah, wa manābiti ash-shajar.",
         explanationEs: "¡Oh Al-lah! Que llueva a nuestro alrededor y no sobre nosotros; ¡oh Al-lah! Sobre las colinas, las montañas, los lechos de los valles y donde crecen los árboles.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_67",
     titleAr: "دُعَاءُ رُؤْيَةِ الهِلاَلِ",
     titleEs: "Súplica al avistar la luna creciente (Creciente lunar)",
     items: [
      {
         text: "اللَّهُ أَكْبَرُ، اللَّهُمَّ أَهِلَّهُ عَلَيْنَا بِالأَمْنِ وَالإِيمَانِ، وَالسَّلاَمَةِ وَالإِسْلاَمِ، وَالتَّوْفِيقِ لِمَا تُحِبُّ رَبَّنَا وَتَرْضَى، رَبُّنَا وَرَبُّكَ اللَّهُ.",
         latin: "Allāhu akbar, Allāhumma ahillahu ʿalaynā bil-amni wal-īmān, was-salāmati wal-islām, wat-tawfīqi limā tuḥibbu rabbanā wa tarḍā, rabbunā wa rabbuka Allāh.",
         explanationEs: "Al-lah es el más Grande. ¡Oh Al-lah! Haz que este creciente surja sobre nosotros con seguridad y fe, paz e Islam, y con éxito en lo que Tú amas, Señor nuestro, y te complace. Nuestro Señor y tu Señor (¡oh luna!) es Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_68",
     titleAr: "الدُّعَاءُ عِنْدَ إِفْطَارِ الصَّائِمِ",
     titleEs: "Súplica al romper el ayuno",
     items: [
      {
         text: "ذَهَبَ الظَّمَأُ وَابْتَلَّتِ العُرُوقُ، وَثَبَتَ الأَجْرُ إِنْ شَاءَ اللَّهُ.",
         latin: "Dhahaba aẓ-ẓama'u wabtallati al-ʿurūq, wa thabata al-ajru in shā'a Allāh.",
         explanationEs: "La sed se ha ido, las venas se han humedecido y la recompensa se ha confirmado, si Al-lah quiere.",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ بِرَحْمَتِكَ الَّتِي وَسِعَتْ كُلَّ شَيْءٍ أَنْ تَغْفِرَ لِي.",
         latin: "Allāhumma innī as'aluka bi-raḥmatika allatī wasiʿat kulla shay'in an taghfira lī.",
         explanationEs: "¡Oh Al-lah! Te pido por Tu misericordia, que abarca todas las cosas, que me perdones.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_69",
     titleAr: "الدُّعَاءُ قَبْلَ الطَّعَامِ",
     titleEs: "Súplica antes de comer",
     items: [
      {
         text: "إِذَا أَكَلَ أَحَدُكُمْ طَعَاماً فَلْيَقُلْ: بِسْمِ اللَّهِ، فَإِنْ نَسِيَ فِي أَوَّلِهِ فَلْيَقُلْ: بِسْمِ اللَّهِ فِي أَوَّلِهِ وَآخِرِهِ.",
         latin: "Idhā akala aḥadukum ṭaʿāman fal-yaqul: Bismillāh, fa-in nasiya fī awwalihi fal-yaqul: Bismillāhi fī awwalihi wa ākhirih.",
         explanationEs: "Cuando uno de vosotros vaya a comer, que diga 'Bismillah' (En el nombre de Al-lah). Si lo olvida al principio, que diga 'Bismillahi fi awwalihi wa akhirih' (En el nombre de Al-lah al principio y al final).",
         count: 1,
         maxCount: 1
      },
      {
         text: "مَنْ أَطْعَمَهُ اللَّهُ الطَّعَامَ فَلْيَقُلْ: اللَّهُمَّ بَارِكْ لَنَا فِيهِ وَأَطْعِمْنَا خَيْراً مِنْهُ، وَمَنْ سَقَاهُ اللَّهُ لَبَناً فَلْيَقُلْ: اللَّهُمَّ بَارِكْ لَنَا فِيهِ وَزِدْنَا مِنْهُ.",
         latin: "Man aṭʿamahu Allāhu aṭ-ṭaʿāma fal-yaqul: Allāhumma bārik lanā fīhi wa aṭʿimnā khayran minh. Wa man saqāhu Allāhu labanan fal-yaqul: Allāhumma bārik lanā fīhi wa zidnā minh.",
         explanationEs: "A quien Al-lah le proporcione comida, que diga: '¡Oh Al-lah! Bendícenosla y danos de comer algo mejor que ella'. Y a quien Al-lah le dé de beber leche, que diga: '¡Oh Al-lah! Bendísenosla y auméntanosla'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_70",
     titleAr: "الدُّعَاءُ عِنْدَ الفَرَاغِ مِنَ الطَّعَامِ",
     titleEs: "Súplica al terminar de comer",
     items: [
      {
         text: "الْحَمْدُ لِلَّهِ الَّذِي أَطْعَمَنِي هَذَا، وَرَزَقَنِيهِ، مِنْ غَيْرِ حَوْلٍ مِنِّي وَلاَ قُوَّةٍ.",
         latin: "Al-ḥamdu lillāhi alladhī aṭʿamanī hādhā, wa razaqanīhi, min ghayri ḥawlin minnī wa lā quwwah.",
         explanationEs: "Alabado sea Al-lah, Quien me ha alimentado con esto y me lo ha concedido sin que de mi parte haya habido fuerza ni poder.",
         count: 1,
         maxCount: 1
      },
      {
         text: "الْحَمْدُ لِلَّهِ حَمْداً كَثِيراً طَيِّباً مُبَارَكاً فِيهِ، غَيْرَ مَكْفِيٍّ وَلاَ مُوَدَّعٍ، وَلاَ مُسْتَغْنَىً عَنْهُ رَبَّنَا.",
         latin: "Al-ḥamdu lillāhi ḥamdan kathīran ṭayyiban mubārakan fīh, ghayra makfiyyin wa lā muwaddaʿin, wa lā mustaghnan ʿanhu rabbanā.",
         explanationEs: "Alabado sea Al-lah con alabanzas abundantes, puras y benditas; una alabanza continua, jamás suficiente, incesante e indispensable, ¡oh Señor nuestro!",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_71",
     titleAr: "دُعَاءُ الضَّيْفِ لِصَاحِبِ الطَّعَامِ",
     titleEs: "Súplica del invitado para el anfitrión que ofrece la comida",
     items: [
      {
         text: "اللَّهُمَّ بَارِكْ لَهُمْ فِيمَا رَزَقْتَهُمْ، وَاغْفِرْ لَهُمْ وَارْحَمْهُمْ.",
         latin: "Allāhumma bārik lahum fīmā razaqtahum, waghfir lahum warḥamhum.",
         explanationEs: "¡Oh Al-lah! Bendíceles el sustento que les has concedido, perdónales y ten misericordia de ellos.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_72",
     titleAr: "التَّعْرِيضُ بِالدُّعَاءِ لِطَلَبِ الطَّعَامِ أَوْ الشَّرَابِ",
     titleEs: "Súplica para quien da de comer o de beber",
     items: [
      {
         text: "اللَّهُمَّ أَطْعِمْ مَنْ أَطْعَمَنِي، وَاسْقِ مَنْ سَقَانِي.",
         latin: "Allāhumma aṭʿim man aṭʿamanī, wasqi man saqānī.",
         explanationEs: "¡Oh Al-lah! Alimenta a quien me alimentó y da de beber a quien me dio de beber.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_73",
     titleAr: "الدُّعَاءُ إِذَا أَفْطَرَب عِنْدَ أَهْلِ بَيْتٍ",
     titleEs: "Súplica al romper el ayuno en casa de alguien",
     items: [
      {
         text: "أَفْطَرَ عِنْدَكُمُ الصَّائِمُونَ، وَأَكَلَ طَعَامَكُمُ الأَبْرَارُ، وَصَلَّتْ عَلَيْكُمُ المَلاَئِكَةُ.",
         latin: "Afṭara ʿindakumu aṣ-ṣā'imūn, wa akala ṭaʿāmakumu al-abrār, wa ṣallat ʿalaykumu al-malā'ikah.",
         explanationEs: "Que rompan el ayuno en vuestra casa los ayunantes, coman de vuestra comida los piadosos y roguen por vosotros los ángeles.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_74",
     titleAr: "دُعَاءُ الصَّائِمِ إِذَا حَضَرَ الطَّعَامُ وَلَمْ يُفْطِرْ",
     titleEs: "Qué debe hacer el ayunante si le invitan a comer y no rompe su ayuno",
     items: [
      {
         text: "إِذَا دُعِيَ أَحَدُكُمْ فَلْيُجِبْ، فَإِنْ كَانَ صَائِماً فَلْيُصَلِّ، وَإِنْ كَانَ مُفْطِراً فَلْيَطْعَمْ (وَمَعْنَى فَلْيُصَلِّ أَيْ فَلْيَدْعُ).",
         latin: "Idhā duʿiya aḥadukum fal-yujib, fa-in kāna ṣā'iman fal-yuṣalli, wa in kāna mufṭiran fal-yaṭʿam (wa maʿnā fal-yuṣalli ay fal-yadʿu).",
         explanationEs: "Si uno de vosotros es invitado a comer, que acepte. Si está ayunando, que suplique por los anfitriones; y si no está ayunando, que coma.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_75",
     titleAr: "مَا يَقُولُ الصَّائِمُ إِذَا سَابَّهُ أَحَدٌ",
     titleEs: "Lo que dice el ayunante si alguien lo insulta o provoca",
     items: [
      {
         text: "إِنِّي صَائِمٌ، إِنِّي صَائِمٌ.",
         latin: "Innī ṣā'im, innī ṣā'im.",
         explanationEs: "Estoy ayunando, estoy ayunando.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_76",
     titleAr: "الدُّعَاءُ عِنْدَ رُؤْيَةِ بَاكُورَةِ الثَّمَرِ",
     titleEs: "Súplica al ver los primeros frutos de la temporada",
     items: [
      {
         text: "اللَّهُمَّ بَارِكْ لَنَا فِي ثَمَرِنَا، وَبَارِكْ لَنَا فِي مَدِينَتِنَا، وَبَارِكْ لَنَا فِي صَاعِنَا، وَبَارِكْ لَنَا فِي مُدِّنَا.",
         latin: "Allāhumma bārik lanā fī thamarinā, wa bārik lanā fī madīnatinā, wa bārik lanā fī ṣāʿinā, wa bārik lanā fī muddinā.",
         explanationEs: "¡Oh Al-lah! Bendícenos en nuestros frutos, bendícenos en nuestra ciudad, bendícenos en nuestros recipientes de medida (Sa' y Mudd).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_77",
     titleAr: "دُعَاءُ العَطَاسِ",
     titleEs: "Etiqueta y súplica al estornudar",
     items: [
      {
         text: "إِذَا عَطَسَ أَحَدُكُمْ فَلْيَقُلْ: الْحَمْدُ لِلَّهِ، وَلْيَقُلْ لَهُ أَخُوهُ أَوْ صَاحِبُهُ: يَرْحَمُكَ اللَّهُ، فَإِذَا قَالَ لَهُ: يَرْحَمُكَ اللَّهُ، فَلْيَقُلْ: يَهْدِيكُمُ اللَّهُ وَيُصْلِحُ بَالَكُمْ.",
         latin: "Idhā ʿaṭaṣa aḥadukum fal-yaqul: Al-ḥamdu lillāh, wa l-yaqul lahu akhūhu aw ṣāḥibuh: Yarḥamuka Allāh, fa-idhā qāla lah: Yarḥamuka Allāh, fal-yaqul: Yahdīkumu Allāhu wa yuṣliḥu bālakum.",
         explanationEs: "Cuando alguno de vosotros estornude, que diga 'Alabado sea Al-lah'. Su hermano o compañero debe responderle 'Que Al-lah tenga misericordia de ti'. Y cuando le responda esto, el que estornudó debe decir 'Que Al-lah os guíe y mejore vuestra situación'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_78",
     titleAr: "مَا يُقَالُ لِلْكَافِرِ إِذَا عَطَسَ فَحَمِدَ اللَّهَ",
     titleEs: "Lo que se responde a un no musulmán cuando estornuda y alaba a Dios",
     items: [
      {
         text: "يَهْدِيكُمُ اللَّهُ وَيُصْلِحُ بَالَكُمْ.",
         latin: "Yahdīkumu Allāhu wa yuṣliḥu bālakum.",
         explanationEs: "Que Al-lah os guíe y mejore vuestra situación.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_79",
     titleAr: "الدُّعَاءُ لِلْمُتَزَوِّجِ",
     titleEs: "Súplica de felicitación al recién casado",
     items: [
      {
         text: "بَارَكَ اللَّهُ لَكَ، وَبَارَكَ عَلَيْكَ، وَجَمَعَ بَيْنَكُمَا فِي خَيْرٍ.",
         latin: "Bāraka Allāhu laka, wa bāraka ʿalayka, wa jamaʿa baynakumā fī khayr.",
         explanationEs: "Que Al-lah te bendiga, derrame Su bendición sobre ti y os una a ambos en el bien.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_80",
     titleAr: "دُعَاءُ المُتَزَوِّجِ وَشِرَاءِ الدَّابَّةِ",
     titleEs: "Súplica del recién casado o al adquirir una montura/vehículo",
     items: [
      {
         text: "إِذَا تَزَوَّجَ أَحَدُكُمُ امْرَأَةً، أَوْ إِذَا اشْتَرَى خَادِماً فَلْيَقُلْ: اللَّهُمَّ إِنِّي أَسْأَلُكَ خَيْرَهَا، وَخَيْرَ مَا جَبَلْتَهَا عَلَيْهِ، وَأَعُوذُ بِكَ مِنْ شَرِّهَا، وَشَرِّ مَا جَبَلْتَهَا عَلَيْهِ. وَإِذَا اشْتَرَى بَعِيراً فَلْيَأْخُذْ بِذِرْوَةِ سَنَامِهِ وَلْيَقُلْ مِثْلَ ذَلِكَ.",
         latin: "Idhā tazawwaja aḥadukumu imra'atan, aw idhā ishtarā khādiman fal-yaqul: Allāhumma innī as'aluka khayrahā, wa khayra mā jabaltahā ʿalayh, wa aʿūdhu bika min sharrihā, wa sharri mā jabaltahā ʿalayh. Wa idhā ishtarā baʿīran fal-ya'khudh bi-dhirwati sanāmihi wa l-yaqul mithla dhālik.",
         explanationEs: "Cuando alguno de vosotros se case con una mujer o compre un sirviente, que diga: '¡Oh Al-lah! Te pido de su bien y del bien de la naturaleza con que la creaste, y me refugio en Ti de su mal y del mal de la naturaleza con que la creaste'. Y si compra un camello (o vehículo), que tome la parte superior de su joroba y diga lo mismo.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_81",
     titleAr: "الدُّعَاءُ قَبْلَ إِتْيَانِ الزَّوْجَةِ",
     titleEs: "Súplica antes de la intimidad con la esposa",
     items: [
      {
         text: "بِسْمِ اللَّهِ، اللَّهُمَّ جَنِّبْنَا الشَّيْطَانَ، وَجَنِّبِ الشَّيْطَانَ مَا رَزَقْتَنَا.",
         latin: "Bismillāh, Allāhumma jannibnā ash-shayṭān, wa jannibi ash-shayṭāna mā razaqtanā.",
         explanationEs: "En el nombre de Al-lah. ¡Oh Al-lah! Aleja de nosotros al Demonio y aleja al Demonio de la descendencia que nos concedas.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_82",
     titleAr: "دُعَاءُ الغَضَبِ",
     titleEs: "Súplica cuando se siente ira o enojo",
     items: [
      {
         text: "أَعُوذُ بِاللَّهِ مِنَ الشَّيْطَانِ الرَّجِيمِ.",
         latin: "Aʿūdhu billāhi mina ash-shayṭāni ar-rajīm.",
         explanationEs: "Me refugio en Al-lah del Demonio repudiado.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_83",
     titleAr: "دُعَاءُ مَنْ رَأَى مُبْتَلًى",
     titleEs: "Súplica al ver a una persona afligida o con alguna prueba",
     items: [
      {
         text: "الْحَمْدُ لِلَّهِ الَّذِي عَافَانِي مِمَّا ابْتَلاَكَ بِهِ، وَفَضَّلَنِي عَلَى كَثِيرٍ مِمَّنْ خَلَقَ تَفْضِيلاً.",
         latin: "Al-ḥamdu lillāhi alladhī ʿāfānī mimmā ibtalāka bih, wa faḍḍalanī ʿalā kathīrin mimman khalaqa tafḍīlā.",
         explanationEs: "Alabado sea Al-lah, Quien me ha librado de la prueba con la que te ha probado a ti, y me ha favorecido notablemente por encima de gran parte de Su creación.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_84",
     titleAr: "مَا يُقَالُ فِي المَجْلِسِ",
     titleEs: "Lo que se dice durante una reunión o asamblea",
     items: [
      {
         text: "رَبِّ اغْفِرْ لِي، وَتُبْ عَلَيَّ، إِنَّكَ أَنْتَ التَّوَّابُ الْغَفُورُ.",
         latin: "Rabbi ighfir lī, wa tub ʿalayya, innaka anta at-tawwābu al-ghafūr.",
         explanationEs: "Se contaba que el Mensajero de Al-lah decía cien veces en una misma reunión antes de levantarse: 'Señor mío perdóname y acepta mi arrepentimiento, ciertamente Tú eres el Indulgente, el Absolvedor'.",
         count: 100,
         maxCount: 100
      }
    ]
  },
  {
     id: "hisn_85",
     titleAr: "كَفَّارَةُ المَجْلِسِ",
     titleEs: "Súplica de expiación al concluir una reunión",
     items: [
      {
         text: "سُبْحَانَكَ اللَّهُمَّ وَبِحَمْدِكَ، أَشْهَدُ أَنْ لاَ إِلَهَ إِلاَّ أَنْتَ، أَسْتَغْفِرُكَ وَأَتُوبُ إِلَيْكَ.",
         latin: "Subḥānaka Allāhumma wa bi-ḥamdika, ashhadu an lā ilāha illā anta, astaghfiruka wa atūbu ilayk.",
         explanationEs: "Glorificado seas, ¡oh Al-lah!, y alabado seas. Atestiguo que no hay más divinidad excepto Tú, pido Tu perdón y me arrepiento ante Ti.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_86",
     titleAr: "الدُّعَاءُ لِمَنْ قَالَ: غَفَرَ اللَّهُ لَكَ",
     titleEs: "Súplica para quien te dice 'Que Al-lah te perdone'",
     items: [
      {
         text: "وَلَكَ.",
         latin: "Wa lak.",
         explanationEs: "Y a ti también.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_87",
     titleAr: "الدُّعَاءُ لِمَنْ صَنَعَ إِلَيْكَ مَعْرُوفاً",
     titleEs: "Súplica para quien te hace un favor o buena acción",
     items: [
      {
         text: "جَزَاكَ اللَّهُ خَيْراً.",
         latin: "Jazāka Allāhu khayrā.",
         explanationEs: "Que Al-lah te recompense con el bien.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_88",
     titleAr: "مَا يَعْصِمُ اللَّهُ بِهِ مِنَ الدَّجَّالِ",
     titleEs: "Protección contra la prueba del Falso Mesías (Anticristo)",
     items: [
      {
         text: "مَنْ حَفِظَ عَشْرَ آيَاتٍ مِنْ أَوَّلِ سُورَةِ الْكَهْفِ عُصِمَ مِنَ الدَّجَّالِ، وَالاسْتِعَاذَةُ بِاللَّهِ مِنْ فِتْنَتِهِ عَقِبَ التَّشَهُّدِ الأَخِيرِ مِنْ كُلِّ صَلاَةٍ.",
         latin: "Man ḥafiẓa ʿashra āyātin min awwali sūrati al-kahfi ʿuṣima mina ad-dajjāl, wal-istiʿādhatu billāhi min fitnatihi ʿaqiba at-tashahhudi al-ākhiri min kulli ṣalāh.",
         explanationEs: "Quien memorice los primeros diez versículos de la sura Al-Kahf estará protegido del Falso Mesías, así como quien busque refugio en Al-lah de su prueba tras el último Tashahhud en cada oración.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_89",
     titleAr: "الدُّعَاءُ لِمَنْ قَالَ: إِنِّي أُحِبُّكَ فِي اللَّهِ",
     titleEs: "Súplica para quien te dice 'Te amo por la causa de Al-lah'",
     items: [
      {
         text: "أَحَبَّكَ الَّذِي أَحْبَبْتَنِي لَهُ.",
         latin: "Aḥabbaka alladhī aḥbabtanī lah.",
         explanationEs: "Que Te ame Aquel por Quien me has amado.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_90",
     titleAr: "الدُّعَاءُ لِمَنْ عَرَضَ عَلَيْكَ مَالَهُ",
     titleEs: "Súplica para quien te ofrece compartir su dinero",
     items: [
      {
         text: "بَارَكَ اللَّهُ لَكَ فِي أَهْلِكَ وَمَالِكَ.",
         latin: "Bāraka Allāhu laka fī ahlika wa mālik.",
         explanationEs: "Que Al-lah bendiga para ti a tu familia y tus bienes.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_91",
     titleAr: "الدُّعَاءُ لِمَنْ أَقْرَضَ عِنْدَ القَضَاءِ",
     titleEs: "Súplica para el prestamista al saldar la deuda",
     items: [
      {
         text: "بَارَكَ اللَّهُ لَكَ فِي أَهْلِكَ وَمَالِكَ، إِنَّمَا جَزَاءُ السَّلَفِ الْحَمْدُ وَالأَدَاءُ.",
         latin: "Bāraka Allāhu laka fī ahlika wa mālik, innamā jazā'u as-salafi al-ḥamdu wal-adā'.",
         explanationEs: "Que Al-lah bendiga para ti a tu familia y tus bienes. La verdadera recompensa por un préstamo es el agradecimiento y la devolución puntual.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_92",
     titleAr: "دُعَاءُ الخَوْفِ مِنَ الشِّرْكِ",
     titleEs: "Súplica para prevenir el Shirk (asociar socios a Al-lah)",
     items: [
      {
         text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ أَنْ أُشْرِكَ بِكَ وَأَنَا أَعْلَمُ، وَأَسْتَغْفِرُكَ لِمَا لاَ أَعْلَمُ.",
         latin: "Allāhumma innī aʿūdhu bika an ushrika bika wa anā aʿlam, wa astaghfiruka limā lā aʿlam.",
         explanationEs: "¡Oh Al-lah! Me refugio en Ti de asociarte algo a sabiendas, y Te pido perdón por lo que desconozco.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_93",
     titleAr: "الدُّعَاءُ لِمَنْ قَالَ: بَارَكَ اللَّهُ فِيكَ",
     titleEs: "Súplica para quien te dice 'Que Al-lah te bendiga'",
     items: [
      {
         text: "وَفِيكَ بَارَكَ اللَّهُ.",
         latin: "Wa fīka bāraka Allāh.",
         explanationEs: "Y que Al-lah te bendiga a ti también.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_94",
     titleAr: "دُعَاءُ كَرَاهِيَةِ الطِّيَرَةِ",
     titleEs: "Súplica contra la superstición o el mal augurio (Tiyarah)",
     items: [
      {
         text: "اللَّهُمَّ لاَ طَيْرَ إِلاَّ طَيْرُكَ، وَلاَ خَيْرَ إِلاَّ خَيْرُكَ، وَلاَ إِلَهَ غَيْرُكَ.",
         latin: "Allāhumma lā ṭayra illā ṭayruk, wa lā khayra illā khayruk, wa lā ilāha ghayruk.",
         explanationEs: "¡Oh Al-lah! No hay augurio sino Tu decreto, no hay bien sino Tu bien, y no hay más divinidad aparte de Ti.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_95",
     titleAr: "دُعَاءُ الرُّكُوبِ",
     titleEs: "Súplica al montar un medio de transporte",
     items: [
      {
         text: "بِسْمِ اللَّهِ، وَالْحَمْدُ لِلَّهِ ﴿سُبْحَانَ الَّذِي سَخَّرَ لَنَا هَذَا وَمَا كُنَّا لَهُ مُقْرِنِينَ * وَإِنَّا إِلَى رَبِّنَا لَمُنْقَلِبُونَ﴾، الْحَمْدُ لِلَّهِ، الْحَمْدُ لِلَّهِ، الْحَمْدُ لِلَّهِ، اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، سُبْحَانَكَ اللَّهُمَّ إِنِّي ظَلَمْتُ نَفْسِي فَاغْفِرْ لِي؛ فَإِنَّهُ لاَ يَغْفِرُ الذُّنُوبَ إِلاَّ أَنْتَ.",
         latin: "Bismillāh, wal-ḥamdu lillāh ﴿Subḥāna alladhī sakhkhara lanā hādhā wa mā kunnā lahu muqrinīn, wa innā ilā rabbinā la-munqalibūn﴾, Al-ḥamdu lillāh, Al-ḥamdu lillāh, Al-ḥamdu lillāh, Allāhu akbar, Allāhu akbar, Allāhu akbar, Subḥānaka Allāhumma innī ẓalamtu nafsī faghfir lī; fa-innahu lā yaghfiru adhdhunūba illā ant.",
         explanationEs: "En el nombre de Al-lah, y alabado sea Al-lah. ﴿Glorificado sea Aquel que ha sometido esto para nosotros cuando no éramos capaces de hacerlo, y ciertamente a nuestro Señor hemos de retornar﴾. Alabado sea Al-lah (x3), Al-lah es el más Grande (x3). Glorificado seas, ¡oh Al-lah! Ciertamente me he oprimido a mí mismo, perdóname pues nadie perdona los pecados excepto Tú.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_96",
     titleAr: "دُعَاءُ السَّفَرِ",
     titleEs: "Súplica de viaje",
     items: [
      {
         text: "اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، ﴿سُبْحَانَ الَّذِي سَخَّرَ لَنَا هَذَا وَمَا كُنَّا لَهُ مُقْرِنِينَ * وَإِنَّا إِلَى رَبِّنَا لَمُنْقَلِبُونَ﴾. اللَّهُمَّ إِنَّا نَسْأَلُكَ فِي سَفَرِنَا هَذَا البِرَّ وَالتَّقْوَى، وَمِنَ الْعَمَلِ مَا تَرْضَى، اللَّهُمَّ هَوِّنْ عَلَيْنَا سَفَرَنَا هَذَا وَاطْوِ عَنَّا بُعْدَهُ، اللَّهُمَّ أَنْتَ الصَّاحِبُ فِي السَّفَرِ، وَالْخَلِيفَةُ فِي الأَهْلِ، اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنْ وَعْثَاءِ السَّفَرِ، وَكَآبَةِ المَنْظَرِ، وَسُوءِ المُنْقَلَبِ فِي المَالِ وَالأَهْلِ. (وَإِذَا رَجَعَ قَالَهُنَّ وَزَادَ فِيهِنَّ: آيِبُونَ، تَائِبُونَ، عَابِدُونَ، لِرَبِّنَا حَامِدُونَ).",
         latin: "Allāhu akbar, Allāhu akbar, Allāhu akbar, ﴿Subḥāna alladhī sakhkhara lanā hādhā wa mā kunnā lahu muqrinīn, wa innā ilā rabbinā la-munqalibūn﴾. Allāhumma innā nas'aluka fī safarinā hādhā al-birra wat-taqwā, wa mina al-ʿamali mā tarḍā, Allāhumma hawwin ʿalaynā safaranā hādhā waṭwi ʿannā buʿdah, Allāhumma anta aṣ-ṣāḥibu fī as-safar, wal-khalīfatu fī al-ahl, Allāhumma innī aʿūdhu bika min waʿthā'i as-safar, wa ka'ābati al-manẓar, wa sū'i al-munqalabi fī al-māli wal-ahl. (Wa idhā rajaʿa qālahunna wa zāda fīhinna: Āyibūna, tā'ibūna, ʿābidūna, li-rabbinā ḥāmidūn).",
         explanationEs: "Al-lah es el más Grande (x3). ﴿Glorificado sea Aquel que ha sometido esto para nosotros...﴾ ¡Oh Al-lah! Te pedimos en este viaje la piedad, el temor de Ti y las obras que Te complacen. ¡Oh Al-lah! Haznos fácil este viaje y acorta su distancia. ¡Oh Al-lah! Tú eres el Compañero en el viaje y el Protector de la familia. ¡Oh Al-lah! Me refugio en Ti de las dificultades del viaje, de la tristeza de las vistas y de un mal regreso a mis bienes y mi familia. (Al regresar repite lo mismo y añade: 'Regresamos arrepentidos, adorando y alabando a nuestro Señor').",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_97",
     titleAr: "دُعَاءُ دُخُولِ القَرْيَةِ أَوْ البَلْدَةِ",
     titleEs: "Súplica al entrar a un pueblo o ciudad",
     items: [
      {
         text: "اللَّهُمَّ رَبَّ السَّمَوَاتِ السَّبْعِ وَمَا أَظْلَلْنَ، وَرَبَّ الأَرَضِينَ السَّبْعِ وَمَا أَقْلَلْنَ، وَرَبَّ الشَّيَاطِينِ وَمَا أَضْلَلْنَ، وَرَبَّ الرِّيَاحِ وَمَا ذَرَيْنَ، أَسْأَلُكَ خَيْرَ هَذِهِ الْقَرْيَةِ، وَخَيْرَ أَهْلِهَا، وَخَيْرَ مَا فِيهَا، وَأَعُوذُ بِكَ مِنْ شَرِّهَا، وَشَرِّ أَهْلِهَا، وَشَرِّ مَا فِيهَا.",
         latin: "Allāhumma rabba as-samāwāti as-sabʿi wa mā aẓlaln, wa rabba al-araḍīna as-sabʿi wa mā aqlaln, wa rabba ash-shayāṭīni wa mā aḍlaln, wa rabba ar-riyāḥi wa mā dharayn, as'aluka khayra hādhihi al-qaryah, wa khayra ahlihā, wa khayra mā fīhā, wa aʿūdhu bika min sharrihā, wa sharri ahlihā, wa sharri mā fīhā.",
         explanationEs: "¡Oh Al-lah! Señor de los siete cielos y de lo que cubren, Señor de las siete tierras y de lo que sostienen, Señor de los demonios y de a quienes extravían, Señor de los vientos y de lo que dispersan. Te pido el bien de este pueblo, el bien de sus habitantes y el bien de lo que hay en él; y me refugio en Ti de su mal, del mal de sus habitantes y del mal de lo que hay en él.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_98",
     titleAr: "دُعَاءُ دُخُولِ السُّوقِ",
     titleEs: "Súplica al entrar al mercado",
     items: [
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ، وَلَهُ الْحَمْدُ، يُحْيِي وَيُمِيتُ، وَهُوَ حَيٌّ لاَ يَمُوتُ، بِيَدِهِ الْخَيْرُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.",
         latin: "Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku, wa lahu al-ḥamd, yuḥyī wa yumīt, wa huwa ḥayyun lā yamūt, bi-yadihi al-khayr, wa huwa ʿalā kulli shay'in qadīr.",
         explanationEs: "No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, da la vida y da la muerte, y Él es Inmortal. En Su mano está el bien y Él es Omnipotente sobre todas las cosas.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_99",
     titleAr: "الدُّعَاءُ إِذَا تَعِسَ المَرْكُوبُ",
     titleEs: "Súplica si tropieza la montura o el vehículo sufre un percance",
     items: [
      {
         text: "بِسْمِ اللَّهِ.",
         latin: "Bismillāh.",
         explanationEs: "En el nombre de Al-lah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_100",
     titleAr: "دُعَاءُ المُسَافِرِ لِلْمُقِيمِ",
     titleEs: "Súplica del viajero para el residente al despedirse",
     items: [
      {
         text: "أَسْتَوْدِعُكُمُ اللَّهَ الَّذِي لاَ تَضِيعُ وَدَائِعُهُ.",
         latin: "Astawdiʿukumu Allāha alladhī lā taḍīʿu wadā'iʿuh.",
         explanationEs: "Os encomiendo a Al-lah, Aquel ante Quien los depósitos encomendados nunca se pierden.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_101",
     titleAr: "دُعَاءُ المُقِيمِ لِلْمُسَافِرِ",
     titleEs: "Súplica del residente para el viajero",
     items: [
      {
         text: "أَسْتَوْدِعُ اللَّهَ دِينَكَ، وَأَمَانَتَكَ، وَخَوَاتِيمَ عَمَلِكَ.",
         latin: "Astawdiʿu Allāha dīnaka, wa amānataka, wa khawātīma ʿamalik.",
         explanationEs: "Encomiendo a Al-lah tu religión, tu fidelidad y las últimas de tus obras.",
         count: 1,
         maxCount: 1
      },
      {
         text: "زَوَّدَكَ اللَّهُ التَّقْوَى، وَغَفَرَ ذَنْبَكَ، وَيَسَّرَ لَكَ الخَيْرَ حَيْثُ مَا كُنْتَ.",
         latin: "Zawwadaka Allāhu at-taqwā, wa ghafara dhanbaka, wa yassara laka al-khayra ḥaythu mā kunt.",
         explanationEs: "Que Al-lah te provenga de piedad, perdone tu pecado y te facilite el bien dondequiera que estés.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_102",
     titleAr: "التَّكْبِيرُ وَالتَّسْبِيحُ فِي سَيْرِ السَّفَرِ",
     titleEs: "Proclamar la grandeza de Dios y glorificarlo durante el viaje",
     items: [
      {
         text: "قَالَ جَابِرٌ رضي الله عنه: كُنَّا إِذَا صَعَدْنَا كَبَّرْنَا، وَإِذَا نَزَلْنَا سَبَّحْنَا.",
         latin: "Qāla Jābirun raḍiya Allāhu ʿanh: Kunnā idhā ṣaʿidnā kabbarnā, wa idhā nazalnā sabbaḥnā.",
         explanationEs: "Dijo Jabir (que Al-lah esté complacido con él): Cuando subíamos (una cuesta o montaña) decíamos 'Allahu Akbar' (Al-lah es el más Grande), y cuando bajábamos decíamos 'Subhanallah' (Glorificado sea Al-lah).",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_103",
     titleAr: "دُعَاءُ المُسَافِرِ إِذَا أَسْحَرَ",
     titleEs: "Súplica del viajero al amanecer (al rayar el alba)",
     items: [
      {
         text: "سَمَّعَ سَامِعٌ بِحَمْدِ اللَّهِ، وَحُسْنِ بَلاَئِهِ عَلَيْنَا، رَبَّنَا صَاحِبْنَا، وَأَفْضِلْ عَلَيْنَا، عَائِذاً بِاللَّهِ مِنَ النَّارِ.",
         latin: "Sammaʿa sāmiʿun bi-ḥamdi Allāhi, wa ḥusni balā'ihi ʿalaynā, rabbanā ṣāḥibnā, wa afḍil ʿalaynā, ʿā'idhan billāhi mina an-nār.",
         explanationEs: "Que un testigo atestigüe nuestra alabanza a Al-lah y Sus buenas pruebas sobre nosotros. Señor nuestro, acompáñanos y agrácianos con Tu favor; nos refugiamos en Al-lah del Fuego.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_104",
     titleAr: "الدُّعَاءُ إِذَا نَزَلَ مَنْزِلاً فِي سَفَرٍ أَوْ غَيْرِهِ",
     titleEs: "Súplica al hacer una parada o alojarse en un lugar",
     items: [
      {
         text: "أَعُوذُ بِكَلِمَاتِ اللَّهِ التَّامَّاتِ مِنْ شَرِّ مَا خَلَقَ.",
         latin: "Aʿūdhu bi-kalimāti Allāhi at-tāmmāti min sharri mā khalaq.",
         explanationEs: "Me refugio en las palabras perfectas de Al-lah del mal de lo que ha creado.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_105",
     titleAr: "ذِكْرُ الرُّجُوعِ مِنَ السَّفَرِ",
     titleEs: "Súplica al regresar de un viaje",
     items: [
      {
         text: "اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، اللَّهُ أَكْبَرُ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ، وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، آيِبُونَ، تَائِبُونَ، عَابِدُونَ، لِرَبِّنَا حَامِدُونَ، صَدَقَ اللَّهُ وَعْدَهُ، وَنَصَرَ عَبْدَهُ، وَهَزَمَ الأَحْزَابَ وَحْدَهُ.",
         latin: "Allāhu akbar, Allāhu akbar, Allāhu akbar, lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku, wa lahu al-ḥamd, wa huwa ʿalā kulli shay'in qadīr, āyibūna, tā'ibūna, ʿābidūna, li-rabbinā ḥāmidūn, ṣadaqa Allāhu waʿdah, wa naṣara ʿabdah, wa hazama al-aḥzāba waḥdah.",
         explanationEs: "Al-lah es el más Grande (x3). No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Omnipotente sobre todas las cosas. Regresamos arrepentidos, adorando y alabando a nuestro Señor. Al-lah ha cumplido Su promesa, ha socorrido a Su siervo y ha derrotado Él solo a las facciones enemigas.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_106",
     titleAr: "مَا يَقُولُ مَنْ أَتَاهُ أَمْرٌ يَسُرُّهُ أَوْ يَكْرَهُهُ",
     titleEs: "Lo que se dice ante un acontecimiento agradable o desagradable",
     items: [
      {
         text: "كَانَ النَّبِيُّ صلى الله عليه وسلم إِذَا أَتَاهُ الأَمْرُ يَسُرُّهُ قَالَ: الْحَمْدُ لِلَّهِ الَّذِي بِنِعْمَتِهِ تَتِمُّ الصَّالِحَاتُ، وَإِذَا أَتَاهُ الأَمْرُ يَكْرَهُهُ قَالَ: الْحَمْدُ لِلَّهِ عَلَى كُلِّ حَالٍ.",
         latin: "Kāna an-nabiyyu ṣallā Allāhu ʿalayhi wa sallama idhā atāhu al-amru yasurruhu qāl: Al-ḥamdu lillāhi alladhī bi-niʿmatihi tatimmu aṣ-ṣāliḥāt, wa idhā atāhu al-amru yakrahuhu qāl: Al-ḥamdu lillāhi ʿalā kulli ḥāl.",
         explanationEs: "Cuando al Profeta (paz y bendiciones de Al-lah sean con él) le llegaba algo alegre, decía: 'Alabado sea Al-lah, con Cuyo favor se completan las buenas obras'. Y cuando le acontecía algo indeseado, decía: 'Alabado sea Al-lah en toda circunstancia'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_107",
     titleAr: "فَضْلُ الصَّلاَةِ عَلَى النَّبِيِّ صَلَّى اللَّهُ عَلَيْهِ وَ سَلَّمَ",
     titleEs: "Virtud de pedir bendiciones por el Profeta",
     items: [
      {
         text: "قَالَ النَّبِيُّ صلى الله عليه وسلم: مَنْ صَلَّى عَلَيَّ صَلاَةً صَلَّى اللَّهُ عَلَيْهِ بِهَا عَشْراً.",
         latin: "Qāla an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam: Man ṣallā ʿalayya ṣalātan ṣallā Allāhu ʿalayhi bihā ʿashrā.",
         explanationEs: "Dijo el Profeta (paz y bendiciones sean con él): Quien pida para mí una bendición, Al-lah lo bendecirá diez veces por ella.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: لاَ تَجْعَلُوا قَبْرِي عِيداً وَصَلُّوا عَلَيَّ؛ فَإِنَّ صَلاَتَكُمْ تَبْلُغُنِي حَيْثُ كُنْتُمْ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Lā tajʿalū qabrī ʿīdā, wa ṣallū ʿalayya; fa-inna ṣalātakum tablughunī ḥaythu kuntum.",
         explanationEs: "Y dijo: No hagáis de mi tumba un lugar de festividad recurrente, y pedid bendiciones por mí; pues vuestra oración me llega dondequiera que estéis.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: الْبَخِيلُ مَنْ ذُكِرْتُ عِنْدَهُ فَلَمْ يُصَلِّ عَلَيَّ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Al-bakhīlu man dhukirtu ʿindahu falam yuṣalli ʿalayy.",
         explanationEs: "Y dijo: El tacaño es aquel ante quien soy mencionado y no pide bendiciones por mí.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: إِنَّ لِلَّهِ مَلاَئِكَةً سَيَّاحِينَ فِي الأَرْضِ يُبَلِّغُونِي مِنْ أُمَّتِي السَّلاَمَ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Inna lillāhi malā'ikatan sayyāḥīna fī al-arḍi yuballighūnī min ummatī as-salām.",
         explanationEs: "Y dijo: Al-lah tiene ángeles que recorren la tierra para hacerme llegar el saludo de paz de mi comunidad.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: مَا مِنْ أَحَدٍ يُسَلِّمُ عَلَيَّ إِلاَّ رَدَّ اللَّهُ عَلَيَّ رُوحِيَ حَتَّى أَرُدَّ عَلَيْهِ السَّلاَمَ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Mā min aḥadin yusallimu ʿalayya illā radda Allāhu ʿalayya rūḥī ḥattā arudda ʿalayhi as-salām.",
         explanationEs: "Y dijo: No hay nadie que me salude con la paz sin que Al-lah me devuelva el alma para que yo le devuelva el saludo.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_108",
     titleAr: "إِفْشَاءُ السَّلاَمِ",
     titleEs: "Difundir el saludo de paz (Salam)",
     items: [
      {
         text: "قَالَ رَسُولُ اللَّهِ صلى الله عليه وسلم: لاَ تَدْخُلُوا الْجَنَّةَ حَتَّى تُؤْمِنُوا، وَلاَ تُؤْمِنُوا حَتَّى تَحَابُّوا، أَوَلاَ أَدُلُّكُمْ عَلَى شَيْءٍ إِذَا فَعَلْتُمُوهُ تَحَابَبْتُمْ، أَفْشُوا السَّلاَمَ بَيْنَكُمْ.",
         latin: "Qāla rasūlu Allāhi ṣallā Allāhu ʿalayhi wa sallam: Lā tadkhulū al-jannata ḥattā tu'minū, wa lā tu'minū ḥattā taḥābbū, awalā adullukum ʿalā shay'in idhā faʿaltumūhu taḥābabtum, afshū as-salāma baynakum.",
         explanationEs: "Dijo el Mensajero de Al-lah (paz y bendiciones de Al-lah sean con él): No entraréis al Paraíso hasta que creáis, y no creeréis (plenamente) hasta que os améis unos a otros. ¿Acaso no os indicaré algo que si lo hacéis os amaréis? Difundid el saludo de paz entre vosotros.",
         count: 1,
         maxCount: 1
      },
      {
         text: "ثَلاَثٌ مَنْ جَمَعَهُنَّ فَقَدْ جَمَعَ الإِيمَانَ: الإِنْصَافُ مِنْ نَفْسِكَ، وَبَذْلُ السَّلاَمِ لِلْعَالَمِ، وَالإِنْفَاقُ مِنَ الإِقْتَارِ.",
         latin: "Thalāthun man jamaʿahunna faqad jamaʿa al-īmān: Al-inṣāfu min nafsik, wa badhlu as-salāmi lil-ʿālam, wal-infāqu mina al-iqtār.",
         explanationEs: "Tres cosas, quien las reúna habrá reunido la fe completa: la equidad con uno mismo, saludar con la paz a todo el mundo y dar en caridad aun en la escasez.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَعَنْ عَبْدِ اللَّهِ بْنِ عُمَرَ رَضِيَ اللَّهُ عَنْهُمَا: أَنَّ رَجُلاً سَأَلَ النَّبِيَّ صلى الله عليه وسلم أَيُّ الإِسْلاَمِ خَيْرٌ؟ قَالَ: تُطْعِمُ الطَّعَامَ، وَتَقْرَأُ السَّلاَمَ عَلَى مَنْ عَرَفْتَ وَمَنْ لَمْ تَعْرِفْ.",
         latin: "Wa ʿan ʿAbdillāhi ibni ʿUmara raḍiya Allāhu ʿanhumā: Anna rajulan sa'ala an-nabiyya ṣallā Allāhu ʿalayhi wa sallama ayyu al-islāmi khayr? Qāl: Tuṭʿimu aṭ-ṭaʿām, wa taqra'u as-salāma ʿalā man ʿarafta wa man lam taʿrif.",
         explanationEs: "Un hombre preguntó al Profeta (paz y bendiciones sean con él): ¿Qué acción del Islam es la mejor? Respondió: Dar de comer y saludar con la paz a quien conoces y a quien no conoces.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_109",
     titleAr: "كَيْفَ يَرُدُّ السَّلاَمَ عَلَى الكَافِرِ إِذَا سَلَّمَ",
     titleEs: "Cómo responder el saludo a un no musulmán",
     items: [
      {
         text: "إِذَا سَلَّمَ عَلَيْكُمْ أَهْلُ الْكِتَابِ فَقُولُوا: وَعَلَيْكُمْ.",
         latin: "Idhā sallama ʿalaykum ahlu al-kitābi fa-qūlū: Wa ʿalaykum.",
         explanationEs: "Cuando os saluden la Gente del Libro (cristianos o judíos), decid: 'Y sobre vosotros'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_110",
     titleAr: "الدُّعَاءُ عِنْدَ سَمَاعِ صِيَاحِ الدِّيكِ وَنَهِيقِ الحِمَارِ",
     titleEs: "Súplica al escuchar el canto del gallo o el rebuzno del asno",
     items: [
      {
         text: "إِذَا سَمِعْتُمْ صِيَاحَ الدِّيَكَةِ فَاسْأَلُوا اللَّهَ مِنْ فَضْلِهِ؛ فَإِنَّهَا رَأَتْ مَلَكاً، وَإِذَا سَمِعْتُمْ نَهِيقَ الْحِمَارِ فَتَعَوَّذُوا بِاللَّهِ مِنَ الشَّيْطَانِ؛ فَإِنَّهُ رَأَى شَيْطَاناً.",
         latin: "Idhā samiʿtum ṣiyāḥa ad-diyakati fas'alū Allāha min faḍlihi; fa-innahā ra'at malakā, wa idhā samiʿtum nahīqa al-ḥimāri fa-taʿawwadhū billāhi mina ash-shayṭāni; fa-innahu ra'ā shayṭānā.",
         explanationEs: "Cuando escuchéis el canto de los gallos, pedid a Al-lah de Su favor, pues han visto a un ángel; y cuando escuchéis el rebuzno del asno, refugiaos en Al-lah del Demonio, pues ha visto a un demonio.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_111",
     titleAr: "دُعَاءُ نُبَاحِ الكِلاَبِ بِاللَّيْلِ",
     titleEs: "Súplica al escuchar el ladrido de los perros por la noche",
     items: [
      {
         text: "إِذَا سَمِعْتُمْ نُبَاحَ الْكِلاَبِ وَنَهِيقَ الْحَمِيرِ بِاللَّيْلِ فَتَعَوَّذُوا بِاللَّهِ مِنْهُنَّ؛ فَإِنَّهُنَّ يَرَيْنَ مَا لاَ تَرَوْنَ.",
         latin: "Idhā samiʿtum nubāḥa al-kilābi wa nahīqa al-ḥamīri bil-layli fa-taʿawwadhū billāhi minhunna; fa-innahunna yarayna mā lā tarawn.",
         explanationEs: "Cuando escuchéis el ladrido de los perros o el rebuzno de los asnos por la noche, refugiaos en Al-lah de ellos, pues ven lo que vosotros no veis.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_112",
     titleAr: "الدُّعَاءُ لِمَنْ سَبَبْتَهُ",
     titleEs: "Súplica por alguien a quien hayas insultado o injuriado",
     items: [
      {
         text: "اللَّهُمَّ فَأَيُّمَا مُؤْمِنٍ سَبَبْتُهُ فَاجْعَلْ ذَلِك لَهُ قُرْبَةً إِلَيْكَ يَوْمَ الْقِيَامَةِ.",
         latin: "Allāhumma fa-ayyumā mu'minin sababtuhu fajʿal dhālika lahu qurbatan ilayka yawma al-qiyāmah.",
         explanationEs: "Dijo el Profeta (paz y bendiciones sean con él): ¡Oh Al-lah! A cualquier creyente al que haya insultado, haz que eso sea para él un motivo de cercanía a Ti en el Día de la Resurrección.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_113",
     titleAr: "مَا يَقُولُ المُسْلِمُ إِذَا مَدَحَ المُسْلِمَ",
     titleEs: "Lo que se dice al elogiar a otro creyente",
     items: [
      {
         text: "إِذَا كَانَ أَحَدُكُمْ مَادِحاً صَاحِبَهُ لاَ مَحَالَةَ فَلْيَقُلْ: أَحْسِبُ فُلاَناً وَاللَّهُ حَسِيبُهُ، وَلاَ أُزَكِّي عَلَى اللَّهِ أَحَداً، أَحْسِبُهُ (إِنْ كَانَ يَعْلَمُ ذَاكَ) كَذَا وَكَذَا.",
         latin: "Idhā kāna aḥadukum mādiḥan ṣāḥibahu lā maḥālata fal-yaqul: Aḥsibu fulānan wallāhu ḥasībuh, wa lā uzakkī ʿalā Allāhi aḥadā, aḥsibuhu (in kāna yaʿlamu dhāk) kadhā wa kadhā.",
         explanationEs: "Si alguno de vosotros debe elogiar inequívocamente a su hermano, que diga: 'Considero a Fulano —y Al-lah es su Juez, y no purifico a nadie por encima de Al-lah— que es así y así', si conoce eso de él.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_114",
     titleAr: "مَا يَقُولُ المُسْلِمُ إِذَا زُكِّيَ",
     titleEs: "Lo que dice el musulmán cuando es elogiado",
     items: [
      {
         text: "اللَّهُمَّ لاَ تُؤَاخِذْنِي بِمَا يَقُولُونَ، وَاغْفِرْ لِي مَا لاَ يَعْلَمُونَ، [وَاجْعَلْنِي خَيْراً مِمَّا يَظُنُّونَ].",
         latin: "Allāhumma lā tu'ākhidhnī bi-mā yaqūlūn, waghfir lī mā lā yaʿlamūn, [wajʿalnī khayran mimmā yaẓunnūn].",
         explanationEs: "¡Oh Al-lah! No me juzgues por lo que dicen, perdóname lo que ignoran de mí y [hazme mejor de lo que ellos piensan].",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_115",
     titleAr: "كَيْفَ يُلَبِّي المُحْرِمُ فِي الحَجِّ أَوْ العُمْرَةِ؟",
     titleEs: "La Talbiyah durante el Hajj o la Umrah",
     items: [
      {
         text: "لَبَّيْكَ اللَّهُمَّ لَبَّيْكَ، لَبَّيْكَ لاَ شَرِيكَ لَكَ لَبَّيْكَ، إِنَّ الْحَمْدَ، وَالنِّعْمَةَ، لَكَ وَالْمُلْكُ، لاَ شَرِيكَ لَكَ.",
         latin: "Labbayka Allāhumma labbayk, labbayka lā sharīka laka labbayk, inna al-ḥamda, wan-niʿmata, laka wal-mulk, lā sharīka lak.",
         explanationEs: "Heme aquí, ¡oh Al-lah!, a Tu servicio. Heme aquí, no tienes asociados, heme aquí. Ciertamente la alabanza, las bendiciones y la soberanía Te pertenecen, no tienes asociados.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_116",
     titleAr: "التَّكْبِيرُ إِذَا أَتَى الرُّكْنَ الأَسْوَدَ",
     titleEs: "Proclamar la grandeza de Dios al llegar a la Piedra Negra",
     items: [
      {
         text: "طَافَ النَّبِيُّ صلى الله عليه وسلم بِالْبَيْتِ عَلَى بَعِيرٍ كُلَّمَا أَتَى الرُّكْنَي أَشَارَ إِلَيْهِ بِشَيْءٍ عِنْدَهُ وَكَبَّرَ.",
         latin: "Ṭāfa an-nabiyyu ṣallā Allāhu ʿalayhi wa sallama bil-bayti ʿalā baʿīrin kullamā atā ar-rukna ashāra ilayhi bi-shay'in ʿindahu wa kabbar.",
         explanationEs: "El Profeta (paz y bendiciones sean con él) realizó el Tawaf alrededor de la Kaaba sobre un camello; cada vez que llegaba a la esquina de la Piedra Negra, la señalaba con lo que tenía en la mano y decía 'Allahu Akbar'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_117",
     titleAr: "الدُّعَاءُ بَيْنَ الرُّكْنِ اليَمَانِي وَالحَجَرِ الأَسْوَدِ",
     titleEs: "Súplica entre la Esquina Yamani y la Piedra Negra",
     items: [
      {
         text: "﴿رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً وَفِي الآخِرَةِ حَسَنَةً وَقِنَا عَذَابَ النَّارِ﴾.",
         latin: "﴿Rabbanā ātinā fī ad-dunyā ḥasanatan wa fī al-ākhirati ḥasanatan wa qinā ʿadhāba an-nār﴾.",
         explanationEs: "﴿Señor nuestro, concédenos lo bueno en este mundo y lo bueno en la otra vida, y líbranos del castigo del Fuego﴾.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_118",
     titleAr: "دُعَاءُ الوُقُوفِ عَلَى الصَّفَا وَالمَرْوَةِ",
     titleEs: "Súplica al subir a las colinas de As-Safa y Al-Marwah",
     items: [
      {
         text: "قَرَأَ: ﴿إِنَّ الصَّفَا وَالْمَرْوَةَ مِنْ شَعَائِرِ اللَّهِ﴾، أَبْدَأُ بِمَا بَدَأَ اللَّهُ بِهِ، فَبَدَأَ بِالصَّفَا فَرَقِيَ عَلَيْهِ حَتَّى رَأَى الْبَيْتَ، فَاسْتَقْبَلَ الْقِبْلَةَ، فَوَحَّدَ اللَّهَ وَكَبَّرَهُ وَقَالَ: لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ، لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ، أَنْجَزَ وَعْدَهُ، وَنَصَرَ عَبْدَهُ، وَهَزَمَ الأَحْزَابَ وَحْدَهُ، ثُمَّ دَعَا بَيْنَ ذَلِكَ (ثَلاَثَ مَرَّاتٍ).",
         latin: "Qara'a: ﴿Inna aṣ-ṣafā wal-marwata min shaʿā'irillāh﴾, abda'u bi-mā bada'a Allāhu bih, fa-bada'a biṣ-ṣafā fa-raqiya ʿalayhi ḥattā ra'ā al-bayt, fas-taqbala al-qiblata, fa-waḥḥada Allāha wa kabbarah, wa qāl: Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku wa lahu al-ḥamdu wa huwa ʿalā kulli shay'in qadīr, lā ilāha illā Allāhu waḥdah, anjaza waʿdah, wa naṣara ʿabdah, wa hazama al-aḥzāba waḥdah, thumma daʿā bayna dhālik (thalātha marrāt).",
         explanationEs: "Leyó: ﴿Ciertamente As-Safa y Al-Marwah son símbolos de Al-lah﴾, empiezo con lo que Al-lah empezó. Empezó por As-Safa, subió hasta ver la Casa (Kaaba), se orientó hacia la Qibla, proclamó la unicidad de Dios y Su grandeza diciendo: 'No hay más divinidad que Al-lah, Único, sin asociados...' y suplicó entre medio (repitiéndolo tres veces). E hizo en Al-Marwah lo mismo que en As-Safa.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_119",
     titleAr: "الدُّعَاءُ يَوْمَ عَرَفَةَ",
     titleEs: "Súplica en el día de Arafah",
     items: [
      {
         text: "قَالَ النَّبِيُّ صلى الله عليه وسلم: خَيْرُ الدُّعَاءِ دُعَاءُ يَوْمِ عَرَفَةَ، وَخَيْرُ مَا قُلْتُ أَنَا وَالنَّبِيُّونَ مِنْ قَبْلِي: لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.",
         latin: "Qāla an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam: Khayru ad-duʿā'i duʿā'u yawmi ʿarafah, wa khayru mā qultu anā wan-nabiyyūna min qablī: Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku wa lahu al-ḥamd, wa huwa ʿalā kulli shay'in qadīr.",
         explanationEs: "Dijo el Profeta (paz y bendiciones sean con él): La mejor súplica es la del día de Arafah, y lo mejor que he dicho yo y los profetas anteriores a mí es: 'No hay más divinidad que Al-lah, Único, sin asociados. Suyo es el reino y Suya es la alabanza, y Él es Omnipotente sobre todas las cosas'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_120",
     titleAr: "الذِّكْرُ عِنْدَ المَشْعَرِ الحَرَامِ",
     titleEs: "Recuerdo en Al-Mash'ar Al-Haram (Muzdalifah)",
     items: [
      {
         text: "رَكِبَ النَّبِيُّ صلى الله عليه وسلم الْقَصْوَاءَ حَتَّى أَتَى الْمَشْعَرَ الْحَرَامَ فَاسْتَقْبَلَ الْقِبْلَةَ (فَدَعَاهُ، وَكَبَّرَهُ، وَهَلَّلَهُ، وَوَحَّدَهُ) فَلَمْ يَزَلْ وَاقِفاً حَتَّى أَسْفَرَ جِدّاً فَدَفَعَ قَبْلَ أَنْ تَطْلُعَ الشَّمْسُ.",
         latin: "Rakiba an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam al-qaṣwā'a ḥattā atā al-mashʿara al-ḥarāma fas-taqbala al-qiblah (fa-daʿāh, wa kabbarah, wa hallalah, wa waḥḥadah) fa-lam yazal wāqifan ḥattā asfara jiddān fa-dafaʿa qabla an taṭluʿa ash-shams.",
         explanationEs: "El Profeta (paz y bendiciones sean con él) montó su camella Al-Qaswa hasta llegar a Al-Mash'ar Al-Haram, se orientó a la Qibla, suplicó a Al-lah, enalteció Su grandeza, proclamó Su unicidad y permaneció allí hasta que aclaró bien el día, partiendo antes de que saliera el sol.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_121",
     titleAr: "التَّكْبِيرُ عِنْدَ رَمْيِ الجِمَارِ مَعَ كُلِّ حَصَاةٍ",
     titleEs: "Proclamar la grandeza de Dios al lanzar las piedras en los Jamarat",
     items: [
      {
         text: "يُكَبِّرُ كُلَّمَا رَمَى بِحَصَاةٍ عِنْدَ الْجِمَارِ الثَّلاَثِ، ثُمَّ يَتَقَدَّمُ، وَيَقِفُ يَدْعُو مُسْتَقْبِلَ الْقِبْلَةِ، رَافِعاً يَدَيْهِ بَعْدَ الْجَمْرَةِ الأُولَى وَالثَّانِيَةِ. أَمَّا جَمْرَةُ الْعَقَبَةِ فَيَرْمِيهَا وَيُكَبِّرُ عِنْدَ كُلِّ حَصَاةٍ وَيَنْصَرِفُ وَلاَ يَقِفُ عِنْدَهَا.",
         latin: "Yukabbiru kullamā ramā bi-ḥaṣātin ʿinda al-jimāri ath-thalāth, thumma yataqaddamu, wa yaqifu yadʿū mustaqbila al-qiblati, rāfiʿan yadayhi baʿda al-jamrati al-ūlā wath-thāniyah. Ammā jamratu al-ʿaqabati fa-yarmīhā wa yukabbiru ʿinda kulli ḥaṣātin wa yanṣarif wa lā yaqifu ʿindahā.",
         explanationEs: "Dice 'Allahu Akbar' con cada guijarro que lanza en los tres pilares (Jamarat). Tras el primero y el segundo, avanza, se orienta a la Qibla con las manos levantadas y suplica. En cuanto al pilar grande (Jamrat Al-Aqabah), lanza las piedras diciendo 'Allahu Akbar' en cada una y se retira sin detenerse a suplicar.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_122",
     titleAr: "دُعَاءُ التَّعَجُّبِ وَالأَمْرِ السَّارِّ",
     titleEs: "Exclamaciones ante el asombro o una noticia grata",
     items: [
      {
         text: "سُبْحَانَ اللَّهِ!",
         latin: "Subḥānallāh!",
         explanationEs: "¡Glorificado sea Al-lah!",
         count: 1,
         maxCount: 1
      },
      {
         text: "اللَّهُ أَكْبَرُ!",
         latin: "Allāhu akbar!",
         explanationEs: "¡Al-lah es el más Grande!",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_123",
     titleAr: "مَا يَفْعَلُ مَنْ أَتَاهُ أَمْرٌ يَسُرُّهُ",
     titleEs: "Lo que hace quien recibe un acontecimiento feliz",
     items: [
      {
         text: "كَانَ النَّبِيُّ صلى الله عليه وسلم إِذَا أَتَاهُ أَمْرٌ يَسُرُّهُ أَوْ يُسَرُّ بِهِ خَرَّ سَاجِداً شُكْراً لِلَّهِ تَبَارَكَ وَتَعَالَى.",
         latin: "Kāna an-nabiyyu ṣallā Allāhu ʿalayhi wa sallama idhā atāhu amrun yasurruhu aw yusarru bihi kharra sājidan shukran lillāhi tabāraka wa taʿālā.",
         explanationEs: "Cuando al Profeta (paz y bendiciones sean con él) le llegaba algo que le alegraba, se prosternaba inmediatamente en agradecimiento a Al-lah, Bendito y Enaltecido sea.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_124",
     titleAr: "مَا يَقُولُ مَنْ أَحَسَّ وَجَعاً فِي جَسَدِهِ",
     titleEs: "Lo que dice quien siente un dolor en el cuerpo",
     items: [
      {
         text: "ضَعْ يَدَكَ عَلَى الَّذِي تَأَلَّمَ مِنْ جَسَدِكَ وَقُلْ: بِسْمِ اللَّهِ (ثَلاَثاً)، وَقُلْ (سَبْعَ مَرَّاتٍ): أَعُوذُ بِاللَّهِ وَقُدْرَتِهِ مِنْ شَرِّ مَا أَجِدُ وَأُحَاذِرُ.",
         latin: "Ḍaʿ yadaka ʿalā alladhī ta'allama min jasadika wa qul: Bismillāh (tres veces), wa qul (siete veces): Aʿūdhu billāhi wa qudratihi min sharri mā ajidu wa uḥādhir.",
         explanationEs: "Coloca tu mano sobre el lugar donde sientes dolor en tu cuerpo y di 'Bismillah' (En el nombre de Al-lah) tres veces, y luego di siete veces: 'Me refugio en Al-lah y en Su poder del mal que siento y al que temo'.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_125",
     titleAr: "دُعَاءُ مَنْ خَشِيَ أَنْ يُصِيبَ شَيْئاً بِعَيْنِهِ",
     titleEs: "Súplica para evitar causar mal de ojo inadvertidamente",
     items: [
      {
         text: "إِذَا رَأَى أَحَدُكُمْ مِنْ أَخِيهِ، أَوْ مِنْ نَفْسِهِ، أَوْ مِنْ مَالِهِ مَا يُعْجِبُهُ فَلْيَدْعُ لَهُ بِالْبَرَكَةِ فَإِنَّ الْعَيْنَ حَقٌّ.",
         latin: "Idhā ra'ā aḥadukum min akhīhi, aw min nafsihi, aw min mālihi mā yuʿjibuhu fal-yadʿu lahu bil-barakah, fa-inna al-ʿayna ḥaqq.",
         explanationEs: "Si alguno de vosotros ve algo que le admire en su hermano, en sí mismo o en sus bienes, que invoque la bendición de Dios para ello, pues el mal de ojo es una realidad.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_126",
     titleAr: "مَا يُقَالُ عِنْدَ الفَزَعِ",
     titleEs: "Lo que se exclama al sentir susto o pánico",
     items: [
      {
         text: "لاَ إِلَهَ إِلاَّ اللَّهُ!",
         latin: "Lā ilāha illā Allāh!",
         explanationEs: "¡No hay más divinidad que Al-lah!",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_127",
     titleAr: "مَا يَقُولُ عِنْدَ الذَّبْحِ أَوْ النَّحْرِ",
     titleEs: "Lo que se dice al sacrificar un animal",
     items: [
      {
         text: "بِسْمِ اللَّهِ وَاللَّهُ أَكْبَرُ [اللَّهُمَّ مِنْكَ وَلَكَ] اللَّهُمَّ تَقَبَّلْ مِنِّي.",
         latin: "Bismillāhi wallāhu akbar [Allāhumma minka wa lak] Allāhumma taqabbal minnī.",
         explanationEs: "En el nombre de Al-lah, y Al-lah es el más Grande. [¡Oh Al-lah! De Ti proviene y a Ti se ofrece]. ¡Oh Al-lah! Acepta de mí.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_128",
     titleAr: "مَا يَقُولُ لِرَدِّ كَيْدِ مَرَدَةِ الشَّيَاطِينِ",
     titleEs: "Súplica para repeler la trama de los demonios rebeldes",
     items: [
      {
         text: "أَعُوذُ بِكَلِمَاتِ اللَّهِ التَّامَّاتِ الَّتِي لاَ يُجَاوِزُهُنَّ بَرٌّ وَلاَ فَاجِرٌ: مِنْ شَرِّ مَا خَلَقَ، وَبَرَأَ وَذَرَأَ، وَمِنْ شَرِّ مَا يَنْزِلُ مِنَ السَّمَاءِ، وَمِنْ شَرِّ مَا يَعْرُجُ فِيهَا، وَمِنْ شَرِّ مَا ذَرَأَ فِي الأَرْضِ، وَمِنْ شَرِّ مَا يَخْرُجُ مِنْهَا، وَمِنْ شَرِّ فِتَنِ اللَّيْلِ وَالنَّهَارِ، وَمِنْ شَرِّ كُلِّ طَارِقٍ إِلاَّ طَارِقاً يَطْرُقُ بِخَيْرٍ يَا رَحْمَنُ.",
         latin: "Aʿūdhu bi-kalimāti Allāhi at-tāmmāti allatī lā yujāwizuhunna barrun wa lā fājir: min sharri mā khalaqa, wa bara'a wa dhara'a, wa min sharri mā yanzilu mina as-samā'i, wa min sharri mā yaʿruju fīhā, wa min sharri mā dhara'a fī al-arḍi, wa min sharri mā yakhruju minhā, wa min sharri fitani al-layli wan-nahār, wa min sharri kulli ṭāriqin illā ṭāriqan yaṭruqu bi-khayrin yā raḥmān.",
         explanationEs: "Me refugio en las palabras perfectas de Al-lah, que ningún piadoso ni perverso puede traspasar: del mal de lo que creó, concibió y multiplicó; del mal de lo que desciende del cielo y de lo que asciende a él; del mal de lo que se multiplica en la tierra y de lo que sale de ella; del mal de las pruebas de la noche y del día; y del mal de todo visitante nocturno, excepto aquel que trae el bien, ¡oh Misericordioso!",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_129",
     titleAr: "الاسْتِغْفَارُ وَالتَّوْبَةُ",
     titleEs: "El pedido de perdón (Istighfar) y el arrepentimiento (Tawbah)",
     items: [
      {
         text: "قَالَ رَسُولُ اللَّهِ صلى الله عليه وسلم: وَاللَّهِ إِنِّي لأَسْتَغْفِرُ اللَّهَ وَأَتُوبُ إِلَيْهِ فِي الْيَوْمِ أَكْثَرَ مِنْ سَبْعِينَ مَرَّةً.",
         latin: "Qāla rasūlu Allāhi ṣallā Allāhu ʿalayhi wa sallam: Wallāhi innī la-astaghfiru Allāha wa atūbu ilayhi fī al-yawmi akthara min sabʿīna marrah.",
         explanationEs: "Dijo el Mensajero de Al-lah (paz y bendiciones sean con él): ¡Por Al-lah! Pido perdón a Al-lah y me arrepiento ante Él en el día más de setenta veces.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: يَا أَيُّهَا النَّاسُ تُوبُوا إِلَى اللَّهِ فَإِنِّي أَتُوبُ فِي الْيَوْمِ إِلَيْهِ مِائَةَ مَرَّةٍ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Yā ayyuhā an-nāsu tūbū ilā Allāhi fa-innī atūbu fī al-yawmi ilayhi mi'ata marrah.",
         explanationEs: "Y dijo: ¡Oh gente! Arrepentíos ante Al-lah, pues yo me arrepiento ante Él cien veces al día.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: مَنْ قَالَ أَسْتَغْفِرُ اللَّهَ الْعَظِيمَ الَّذِي لاَ إِلَهَ إِلاَّ هُوَ الْحَيُّ القَيُّومُ وَأَتُوبُ إِلَيْهِ، غَفَرَ اللَّهُ لَهُ وَإِنْ كَانَ فَرَّ مِنَ الزَّحْفِ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Man qāla astaghfiru Allāha al-ʿaẓīma alladhī lā ilāha illā huwa al-ḥayyu al-qayyūmu wa atūbu ilayh, ghafara Allāhu lahu wa in kāna farra mina az-zaḥf.",
         explanationEs: "Y dijo: Quien diga 'Pido perdón a Al-lah el Grandioso, no hay más divinidad excepto Él, el Viviente, el Sustentador de todo, y me arrepiento ante Él', Al-lah lo perdonará aunque haya huido del combate.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: أَقْرَبُ مَا يَكُونُ الرَّبُّ مِنَ الْعَبْدِ فِي جَوْفِ اللَّيْلِ الآخِرِ، فَإِنِ اسْتَطَعْتَ أَنْ تَكُونَ مِمَّنْ يَذْكُرُ اللَّهَ فِي تِلْكَ السَّاعَةِ فَكُنْ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Aqrabu mā yakūnu ar-rabbu mina al-ʿabdi fī jawfi al-layli al-ākhir, fa-inis-taṭaʿta an takūna mimman yadhkuru Allāha fī tilka as-sāʿati fa-kun.",
         explanationEs: "Y dijo: Lo más cerca que está el Señor de Su siervo es en lo profundo de la última parte de la noche. Si puedes ser de los que recuerdan a Al-lah en esa hora, sélo.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: أَقْرَبُ مَا يَكُونُ الْعَبْدُ مِنْ رَبِّهِ وَهُوَ سَاجِدٌ فَأَكْثِرُوا الدُّعَاءَ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Aqrabu mā yakūnu al-ʿabdu min rabbihi wa huwa sājidun fa-akthirū ad-duʿā'.",
         explanationEs: "Y dijo: Lo más cerca que está el siervo de su Señor es cuando está prosternado; por tanto, abundad en las súplicas.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: إِنَّهُ لَيُغَانُ عَلَى قَلْبِي وَإِنِّي لأَسْتَغْفِرُ اللَّهَ فِي الْيَوْمِ مِائَةَ مَرَّةٍ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Innahu la-yughānu ʿalā qalbī wa innī la-astaghfiru Allāha fī al-yawmi mi'ata marrah.",
         explanationEs: "Y dijo: Ciertamente ocurre que mi corazón se distrae levemente y pido perdón a Al-lah cien veces al día.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_130",
     titleAr: "فَضْلُ التَّسْبِيحِ وَالتَّحْمِيدِ، وَالتَّهْلِيلِ، وَالتَّكْبِيرِ",
     titleEs: "Las virtudes del Tasbih, Tahmid, Tahlil y Takbir",
     items: [
      {
         text: "قَالَ صلى الله عليه وسلم: مَنْ قَالَ سُبْحَانَ اللَّهِ وَبِحَمْدِهِ فِي يَوْمٍ مِائَةَ مَرَّةٍ حُطَّتْ خَطَايَاهُ وَلَوْ كَانَتْ مِثْلَ زَبَدِ الْبَحْرِ.",
         latin: "Qāla ṣallā Allāhu ʿalayhi wa sallam: Man qāla Subḥānallāhi wa bi-ḥamdihi fī yawmin mi'ata marrah ḥuṭṭat khaṭāyāhu wa law kānat mithla zabadi al-baḥr.",
         explanationEs: "Dijo el Profeta (paz y bendiciones sean con él): Quien diga 'Glorificado sea Al-lah y alabado sea' cien veces al día, sus pecados serán borrados aunque sean como la espuma del mar.",
         count: 100,
         maxCount: 100
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: مَنْ قَالَ لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، لَهُ الْمُلْكُ، وَلَهُ الْحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ عَشْرَ مِرَارٍ، كَانَ كَمَنْ أَعْتَقَ أَرْبَعَةَ أَنْفُسٍ مِنْ وَلَدِ إِسْمَاعِيلَ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Man qāla Lā ilāha illā Allāhu waḥdahu lā sharīka lah, lahu al-mulku, wa lahu al-ḥamd, wa huwa ʿalā kulli shay'in qadīr ʿashra mirār, kāna ka-man aʿtaqa arbaʿata anfusin min waladi Ismāʿīl.",
         explanationEs: "Y dijo: Quien diga diez veces 'No hay más divinidad que Al-lah, Único, sin asociados...', será como quien haya liberado a cuatro personas de los descendientes de Ismael.",
         count: 10,
         maxCount: 10
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: كَلِمَتَانِ خَفِيفَتَانِ عَلَى اللِّسَانِ، ثَقِيلَتَانِ فِي الْمِيزَانِ، حَبِيبَتَانِ إِلَى الرَّحْمَنِ: سُبْحَانَ اللَّهِ وَبِحَمْدِهِ، سُبْحَانَ اللَّهِ الْعَظِيمِ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Kalimatāni khafīfatāni ʿalā al-lisān, thaqīlatāni fī al-mīzān, ḥabībatāni ilā ar-raḥmān: Subḥānallāhi wa bi-ḥamdih, Subḥānallāhi al-ʿaẓīm.",
         explanationEs: "Y dijo: Dos palabras son livianas para la lengua, pesadas en la balanza y amadas por el Misericordioso: 'Subhanallahi wa bihamdih, Subhanallahil-'Azim' (Glorificado sea Al-lah y alabado sea, Glorificado sea Al-lah el Grandioso).",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: لَأَنْ أَقُولَ سُبْحَانَ اللَّهِ، وَالْحَمْدُ لِلَّهِ، وَلاَ إِلَهَ إِلاَّ اللَّهُ، وَاللَّهُ أَكْبَرُ، أَحَبُّ إِلَيَّ مِمَّا طَلَعَتْ عَلَيْهِ الشَّمْسُ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: La-an aqūla Subḥānallāh, wal-ḥamdu lillāh, wa lā ilāha illā Allāh, wallāhu akbar, aḥabbu ilayya mimmā ṭalaʿat ʿalayhi ash-shams.",
         explanationEs: "Y dijo: Decir 'Subhanallah, wal-hamdulillah, wa la ilaha illallah, wallahu akbar' me es más querido que todo aquello sobre lo que sale el sol.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: أَيَعْجِزُ أَحَدُكُمْ أَنْ يَكْسِبَ كُلَّ يَوْمٍ أَلْفَ حَسَنَةٍ؟ يُسَبِّحُ مِائَةَ تَسْبِيحَةٍ، فَيُكْتَبُ لَهُ أَلْفُ حَسَنَةٍ أَوْ يُحَطُّ عَنْهُ أَلْفُ خَطِيئَةٍ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: A-yaʿjizu aḥadukum an yaksiba kulla yawmin alfa ḥasanah? Yusabbiḥu mi'ata tasbīḥah, fa-yuktabu lahu alfu ḥasanatin aw yuḥaṭṭu ʿanhu alfu khaṭī'ah.",
         explanationEs: "Y dijo: ¿Acaso es incapaz alguno de vosotros de ganar mil buenas acciones cada día? Glorifica a Dios (diciendo Subhanallah) cien veces, y se le anotarán mil buenas acciones o se le borrarán mil pecados.",
         count: 100,
         maxCount: 100
      },
      {
         text: "مَنْ قَالَ: سُبْحَانَ اللَّهِ الْعَظِيمِ وَبِحَمْدِهِ غُرِسَتْ لَهُ نَخْلَةٌ فِي الْجَنَّةِ.",
         latin: "Man qāla: Subḥānallāhi al-ʿaẓīmi wa bi-ḥamdihi ghurisat lahu nakhlatun fī al-jannah.",
         explanationEs: "Quien diga 'Subhanallahil-'Azimi wa bihamdih' (Glorificado sea Al-lah el Grandioso y alabado sea), se le plantará una palmera en el Paraíso.",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: يَا عَبْدَ اللَّهِ بْنَ قَيْسٍ أَلاَ أَدُلُّكَ عَلَى كَنْزٍ مِنْ كُنُوزِ الْجَنَّةِ؟ قُلْ: لاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Yā ʿAbdallāhi ibna Qaysin alā adulluka ʿalā kanzin min kunūzi al-jannah? Qul: Lā ḥawla wa lā quwwata illā billāh.",
         explanationEs: "Y dijo: ¡Oh Abdullah bin Qais! ¿Acaso no te indicaré un tesoro de los tesoros del Paraíso? Di: 'La hawla wa la quwwata illa billah' (No hay fuerza ni poder sino en Al-lah).",
         count: 1,
         maxCount: 1
      },
      {
         text: "وَقَالَ صلى الله عليه وسلم: أَحَبُّ الْكَلاَمِ إِلَى اللَّهِ أَرْبَعٌ: سُبْحَانَ اللَّهِ، وَالْحَمْدُ لِلَّهِ، وَلاَ إِلَهَ إِلاَّ اللَّهُ، وَاللَّهُ أَكْبَرُ، لاَ يَضُرُّكَ بِأَيِّهِنَّ بَدَأْتَ.",
         latin: "Wa qāla ṣallā Allāhu ʿalayhi wa sallam: Aḥabbu al-kalāmi ilā Allāhi arbaʿ: Subḥānallāh, wal-ḥamdu lillāh, wa lā ilāha illā Allāh, wallāhu akbar, lā yaḍurruka bi-ayyihinna bada't.",
         explanationEs: "Y dijo: Las palabras más amadas por Al-lah son cuatro: Subhanallah, Al-hamdulillah, La ilaha illallah y Allahu Akbar; no importa con cuál de ellas comiences.",
         count: 1,
         maxCount: 1
      },
      {
         text: "جَاءَ أَعْرَابِيٌّ إِلَى رَسُولِ اللَّهِ صلى الله عليه وسلم فَقَالَ: عَلِّمْنِي كَلاَماً أَقُولُهُ، قَالَ: قُلْ: لاَ إِلَهَ إِلاَّ اللَّهُ وَحْدَهُ لاَ شَرِيكَ لَهُ، اللَّهُ أَكْبَرُ كَبِيراً، وَالْحَمْدُ لِلَّهِ كَثِيراً، سُبْحَانَ اللَّهِ رَبِّ الْعَالَمِينَ، لاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ الْعَزِيزِ الْحَكِيمِ. قَالَ: فَهَؤُلاَءِ لِرَبِّي، فَمَا لِي؟ قَالَ: قُلْ: اللَّهُمَّ اغْفِرْ لِي، وَارْحَمْنِي، وَاهْدِنِي، وَارْزُقْنِي.",
         latin: "Jā'a aʿrābiyyun ilā rasūli Allāhi ṣallā Allāhu ʿalayhi wa sallam fa-qāl: ʿAllimnī kalāman aqūluh, qāl: Qul: Lā ilāha illā Allāhu waḥdahu lā sharīka lah, Allāhu akbaru kabīrā, wal-ḥamdu lillāhi kathīrā, Subḥānallāhi rabbi al-ʿālamīn, lā ḥawla wa lā quwwata illā billāhi al-ʿazīzi al-ḥakīm. Qāl: Fa-hā'ulā'i li-rabbī, fa-mā lī? Qāl: Qul: Allāhumma ighfir lī, warḥamnī, wahdinī, warzuqnī.",
         explanationEs: "Un beduino vino al Mensajero de Al-lah (paz y bendiciones sean con él) y dijo: Enséñame unas palabras que decir. Dijo: Di 'No hay más divinidad que Al-lah, Único, sin asociados; Al-lah es el más Grande en grandeza, alabado sea Al-lah en abundancia, glorificado sea Al-lah, Señor de los mundos, no hay fuerza ni poder sino en Al-lah el Poderoso, el Sabio'. El hombre dijo: Esas son para mi Señor, ¿y para mí? Dijo: Di '¡Oh Al-lah! Perdóname, ten misericordia de mí, guíame y susténtame'.",
         count: 1,
         maxCount: 1
      },
      {
         text: "كَانَ الرَّجُلُ إِذَا أَسْلَمَ عَلَّمَهُ النَّبِيُّ صلى الله عليه وسلم الصَّلاَةَ ثُمَّ أَمَرَهُ أَنْ يَدْعُوَ بِهَؤُلاَءِ الْكَلِمَاتِ: اللَّهُمَّ اغْفِرْ لِي، وَارْحَمْنِي، وَاهْدِنِي، وَعَافِنِي، وَارْزُقْنِي.",
         latin: "Kāna ar-rajulu idhā aslama ʿallamahu an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam aṣ-ṣalāta thumma amarahu an yadʿuwa bi-hā'ulā'i al-kalimāt: Allāhumma ighfir lī, warḥamnī, wahdinī, wa ʿāfinī, warzuqnī.",
         explanationEs: "Cuando una persona abrazaba el Islam, el Profeta (paz y bendiciones sean con él) le enseñaba la oración y luego le ordenaba suplicar con estas palabras: '¡Oh Al-lah! Perdóname, ten misericordia de mí, guíame, dame salud y susténtame'.",
         count: 1,
         maxCount: 1
      },
      {
         text: "إِنَّ أَفْضَلَ الدُّعَاءِ الْحَمْدُ لِلَّهِ، وَأَفْضَلَ الذِّكْرِ لاَ إِلَهَ إِلاَّ اللَّهُ.",
         latin: "Inna afḍala ad-duʿā'i Al-ḥamdu lillāh, wa afḍala adh-dhikri Lā ilāha illā Allāh.",
         explanationEs: "La mejor súplica es 'Al-hamdulillah' (Alabado sea Al-lah), y el mejor recuerdo es 'La ilaha illallah' (No hay más divinidad que Al-lah).",
         count: 1,
         maxCount: 1
      },
      {
         text: "الْبَاقِيَاتُ الصَّالِحَاتُ: سُبْحَانَ اللَّهِ، وَالْحَمْدُ لِلَّهِ، وَلاَ إِلَهَ إِلاَّ اللَّهُ، وَاللَّهُ أَكْبَرُ، وَلاَ حَوْلَ وَلاَ قُوَّةَ إِلاَّ بِاللَّهِ.",
         latin: "Al-bāqiyātu aṣ-ṣāliḥāt: Subḥānallāh, wal-ḥamdu lillāh, wa lā ilāha illā Allāh, wallāhu akbar, wa lā ḥawla wa lā quwwata illā billāh.",
         explanationEs: "Las obras perdurables y piadosas son: Subhanallah, Al-hamdulillah, La ilaha illallah, Allahu Akbar, wa La hawla wa la quwwata illa billah.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_131",
     titleAr: "كَيْفَ كَانَ النَّبِيُّ يُسَبِّحُ؟",
     titleEs: "Cómo realizaba el Profeta el conteo de las glorificaciones",
     items: [
      {
         text: "عَنْ عَبْدِ اللَّهِ بْنِ عَمْرٍو رضي الله عنه قَالَ: رَأَيْتُ النَّبِيَّ صلى الله عليه وسلم يَعْقِدُ التَّسْبِيحَ بِيَمِينِهِ.",
         latin: "ʿAn ʿAbdillāhi ibni ʿAmrin raḍiya Allāhu ʿanhumā qāl: Ra'aytu an-nabiyya ṣallā Allāhu ʿalayhi wa sallama yaʿqidu at-tasbīḥa bi-yamīnih.",
         explanationEs: "De Abdullah bin Amr (que Al-lah esté complacido con ambos), dijo: Vi al Profeta (paz y bendiciones de Al-lah sean con él) contar las glorificaciones con los dedos de su mano derecha.",
         count: 1,
         maxCount: 1
      }
    ]
  },
  {
     id: "hisn_132",
     titleAr: "مِنْ أَنْوَاعِ الخَيْرِ وَالأَدَابِ الجَامِعَةِ",
     titleEs: "Normas de comportamiento y protección al anochecer",
     items: [
      {
         text: "قَالَ النَّبِيُّ صلى الله عليه وسلم: إِذَا كَانَ جُنْحُ اللَّيْلِ (أَوْ أَمْسَيْتُمْ) فَكُفُّوا صِبْيَانَكُمْ، فَإِنَّ الشَّيَاطِينَ تَنْتَشِرُ حِينَئِذٍ، فَإِذَا ذَهَبَ سَاعَةٌ مِنَ اللَّيْلِ فَخَلُّوهُمْ، وَأَغْلِقُوا الأَبْوَابَ وَاذْكُرُوا اسْمَ اللَّهِ؛ فَإِنَّ الشَّيْطَانَ لاَ يَفْتَحُ بَاباً مُغْلَقاً، وَأَوْكُوا قِرَبَكُمْ وَاذْكُرُوا اسْمَ اللَّهِ، وَخَمِّرُوا آنِيَتَكُمْ وَاذْكُرُوا اسْمَ اللَّهِ وَلَوْ أَنْ تَعْرُضُوا عَلَيْهَا شَيْئاً، وَأَطْفِئُوا مَصَابِيحَكُمْ.",
         latin: "Qāla an-nabiyyu ṣallā Allāhu ʿalayhi wa sallam: Idhā kāna junḥu al-layl (aw amsaytum) fa-kuffū ṣibyānakum, fa-inna ash-shayāṭīna tantashiru ḥīna'idhin, fa-idhā dhahaba sāʿatun mina al-layli fa-khallūhum, wa aghliqū al-abwāba wadhkurū isma Allāh; fa-inna ash-shayṭāna lā yaftaḥu bāban mughlaqā, wa awkū qirabakum wadhkurū isma Allāh, wa khammirū āniyatakum wadhkurū isma Allāh wa law an taʿriḍū ʿalayhā shay'ā, wa aṭfi'ū maṣābīḥakum.",
         explanationEs: "Dijo el Profeta (paz y bendiciones sean con él): Al anochecer (o entrada la tarde), mantened a vuestros niños dentro de casa, pues los demonios se dispersan en ese momento. Transcurrida una hora de la noche, dejadlos; cerrad las puertas mencionando el nombre de Al-lah, pues el Demonio no abre una puerta cerrada; atad los odres mencionando el nombre de Al-lah; cubrid vuestros recipientes mencionando el nombre de Al-lah aunque sea atravesando algo sobre ellos, y apagad vuestras lámparas.",
         count: 1,
         maxCount: 1
      }
    ]
      }
    ];

    const adyaData = [
      {
        id: 'rizq',
        titleAr: 'دعاء الرزق والبركة',
        titleEs: 'Súplica para el Sustento y Bendición',
        items: [
          { text: 'اللَّهُمَّ اكْفِنِي بِحَلالِكَ عَنْ حَرَامِكَ وَأَغْنِنِي بِفَضْلِكَ عَمَّنْ سِوَاكَ.', latin: 'Allāhummak-finī bi-ḥalālika ‘an ḥarāmika wa aghninī bi-faḍlika ‘amman siwāk.', explanationEs: '¡Oh Allah! Haz que Tu sustento lícito me sea suficiente frente a lo ilícito.', count: 1, maxCount: 1 },
          { text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ عِلْمًا نَافِعًا، وَرِزْقًا طَيِّبًا، وَعَمَلاً مُتَقَبَّلاً.', latin: 'Allāhumma innī as’aluka ‘ilman nāfi‘an, wa rizqan ṭayyiban...', explanationEs: 'Petición de conocimiento beneficioso y sustento puro.', count: 1, maxCount: 1 }
        ]
      },
      {
        id: 'shifa',
        titleAr: 'دعاء الشفاء والعافية',
        titleEs: 'Súplica para la Curación y Salud',
        items: [
          { text: 'اللَّهُمَّ رَبَّ النَّاسِ أَذْهِبِ الْبَاسَ، اشْفِ وَأَنْتَ الشَّافِي، لاَ شِفَاءَ إِلاَّ شِفَاؤُكَ...', latin: 'Allāhumma rabban-nāsi adh-hibil-ba’sa ishfi antash-shāfī...', explanationEs: 'Invocación para la curación de enfermedades.', count: 1, maxCount: 1 },
          { text: 'بِسْمِ اللَّهِ (3 مَرَّاتٍ)، أَعُوذُ بِاللَّهِ وَقُدْرَتِهِ مِنْ شَرِّ مَا أَجِدُ وَأُحَاذِرُ (7 مَرَّاتٍ).', latin: 'Bismillāh (3v), A‘ūdhu billāhi wa qudratihi min sharri mā ajidu wa uḥādhir (7v).', explanationEs: 'Poner la mano en el lugar del dolor y recitar para alivio.', count: 7, maxCount: 7 }
        ]
      },
      {
        id: 'faraj',
        titleAr: 'دعاء الفرج وزوال الهم',
        titleEs: 'Súplica para el Alivio de las Penas',
        items: [
          { text: 'لا إِلَهَ إِلاَّ أَنْتَ سُبْحَانَكَ إِنِّي كُنْتُ مِنَ الظَّالِمِينَ.', latin: 'Lā ilāha illā anta subḥānaka innī kuntu minaẓ-ẓālimīn.', explanationEs: 'La súplica de Junus (Jonás) en el vientre de la ballena. Alivia toda angstia.', count: 1, maxCount: 1 },
          { text: 'اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الْهَمِّ وَالْحَزَنِ، وَالْعَجْزِ وَالْكَسَلِ...', latin: 'Allāhumma innī a‘ūdhu bika minal-hammi wal-ḥazan...', explanationEs: 'Refugio contra la ansiedad, la tristeza y la cobardía.', count: 1, maxCount: 1 }
        ]
      },
      {
        id: 'hifz',
        titleAr: 'دعاء الحفظ والوقاية',
        titleEs: 'Súplica de Protección',
        items: [
          { text: 'بِسْمِ اللَّهِ الَّذِي لاَ يَضُرُّ مَعَ اسْمِهِ شَيْءٌ فِي الأَرْضِ وَلاَ فِي السَّمَاءِ...', latin: 'Bismillāhilladhī lā yaḍurru ma‘asmihi shay’un...', explanationEs: 'Protección general contra peligros.', count: 3, maxCount: 3 }
        ]
      },
      {
        id: 'quran',
        titleAr: 'أدعية من القرآن الكريم',
        titleEs: 'Súplicas del Sagrado Corán',
        items: [
          { text: 'رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً وَفِي الْآخِرَةِ حَسَنَةً وَقِنَا عَذَابَ النَّارِ.', latin: 'Rabbanā ātinā fid-dunyā ḥasanatan wa fil-ākhirati ḥasanatan wa qinā ‘adhāban-nār.', explanationEs: 'Señor nuestro, concédenos lo bueno en este mundo y en el otro.', count: 1, maxCount: 1 },
          { text: 'رَبِّ زِدْنِي عِلْمًا.', latin: 'Rabbi zidnī ‘ilmā.', explanationEs: '¡Señor mío! Aumenta mi conocimiento.', count: 1, maxCount: 1 }
        ]
      },
      {
        id: 'jami',
        titleAr: 'جوامع الدعاء',
        titleEs: 'Súplicas Comprensivas de la Sunnah',
        items: [
          { text: 'اللَّهُمَّ إِنِّي أَسْأَلُكَ الْهُدَى، وَالتُّقَى، وَالْعَفَافَ، وَالْغِنَى.', latin: 'Allāhumma innī as’alukal-hudā wat-tuqā wal-‘afāfa wal-ghinā.', explanationEs: 'Petición de guía, piedad, castidad y autosuficiencia.', count: 1, maxCount: 1 }
        ]
      },
      {
        id: 'parents',
        titleAr: 'الدعاء للوالدين',
        titleEs: 'Súplica por los Padres',
        items: [
          { text: 'رَبِّ ارْحَمْهُمَا كَمَا رَبَّيَانِي صَغِيرًا.', latin: 'Rabbir-ḥamhumā kamā rabbayānī ṣaghīrā.', explanationEs: '¡Señor mío! Ten misericordia de ellos tal como me criaron de pequeño.', count: 1, maxCount: 1 }
        ]
      }
    ];

    let currentSection = null;
    let currentGroup = null;
    let favorites = [];
    let fontSize = 18;
    let currentAudio = null;

    const STORAGE_KEY = 'azkar_adya_progress_v5';
    const FAV_KEY = 'azkar_favorites_v5';
    const THEME_KEY = 'azkar_theme_v5';

    function safeGetStorage(key) {
      try { return localStorage.getItem(key); } catch (e) { return null; }
    }
    function safeSetStorage(key, val) {
      try { localStorage.setItem(key, val); } catch (e) {}
    }

    function toggleLanguage() {
      currentLang = currentLang === 'ar' ? 'es' : 'ar';
      safeSetStorage('app_lang', currentLang);
      applyLanguageUI();
    }

    function applyLanguageUI() {
      const isEs = currentLang === 'es';
      const t = uiTexts[currentLang];

      document.documentElement.dir = isEs ? 'ltr' : 'rtl';
      document.documentElement.lang = currentLang;

      document.getElementById('langBtnText').innerText = isEs ? 'AR' : 'ES';
      document.getElementById('headerTitle').innerText = t.headerTitle;
      document.getElementById('headerSubtitle').innerText = t.headerSubtitle;
      document.getElementById('homeWelcome').innerText = t.homeWelcome;
      
      document.getElementById('btnAzkarTitle').innerText = t.btnAzkarTitle;
      document.getElementById('btnAzkarSub').innerText = t.btnAzkarSub;
      document.getElementById('btnAdyaTitle').innerText = t.btnAdyaTitle;
      document.getElementById('btnAdyaSub').innerText = t.btnAdyaSub;
      document.getElementById('btnTasbeehTitle').innerText = t.btnTasbeehTitle;
      document.getElementById('btnTasbeehSub').innerText = t.btnTasbeehSub;
      document.getElementById('btnFavTitle').innerText = t.btnFavTitle;
      document.getElementById('btnFavSub').innerText = t.btnFavSub;
      
      document.getElementById('searchInput').placeholder = t.searchPlaceholder;
      document.getElementById('resetAllBtn').innerText = t.resetAll;
      document.getElementById('progressTextLabel').innerText = t.progressLabel;
      document.getElementById('tasbeehHeaderTitle').innerText = t.btnTasbeehTitle;
      document.getElementById('resetTasbeehBtn').innerText = t.resetAll;
      document.getElementById('favHeaderTitle').innerText = t.btnFavTitle;
      document.getElementById('footerText').innerText = isEs ? 'Misbaha © 2026' : 'المسبحة - جامع الأذكار والأدعية الكامل © 2026';

      document.querySelectorAll('.btn-back-label').forEach(el => el.innerText = t.back);

      if (currentGroup) {
        document.getElementById('itemGroupTitle').innerText = isEs ? currentGroup.titleEs : currentGroup.titleAr;
        renderGroupItems();
      }
      if (!document.getElementById('categoryListView').classList.contains('hidden')) {
        document.getElementById('sectionTitle').innerText = currentSection === 'azkar' ? t.azkarSectionTitle : t.adyaSectionTitle;
        renderButtonsGrid();
      }
      if (!document.getElementById('tasbeehView').classList.contains('hidden')) renderTasbeehGrid();
      if (!document.getElementById('favoritesView').classList.contains('hidden')) showFavorites();
    }

    function showToast(msg) {
      const toast = document.getElementById('toast');
      if (!toast) return;
      toast.innerText = msg;
      toast.classList.remove('opacity-0', 'pointer-events-none');
      setTimeout(() => { toast.classList.add('opacity-0', 'pointer-events-none'); }, 2000);
    }

    function toggleDarkMode() {
      const html = document.documentElement;
      if (html.classList.contains('dark')) {
        html.classList.remove('dark');
        safeSetStorage(THEME_KEY, 'light');
      } else {
        html.classList.add('dark');
        safeSetStorage(THEME_KEY, 'dark');
      }
    }

    function loadSavedTheme() {
      const savedTheme = safeGetStorage(THEME_KEY);
      if (savedTheme === 'dark' || (!savedTheme && window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        document.documentElement.classList.add('dark');
      }
    }

    function changeFontSize(delta) {
      fontSize = Math.min(Math.max(14, fontSize + delta * 2), 28);
      document.documentElement.style.setProperty('--app-font-size', `${fontSize}px`);
    }

    function playAudio(audioUrl) {
      if (!audioUrl) return;
      if (currentAudio) { 
        currentAudio.pause(); 
        currentAudio = null; 
      }
      showToast(currentLang === 'es' ? 'Reproduciendo audio...' : 'جاري تشغيل التلاوة...');
      currentAudio = new Audio(audioUrl);
      currentAudio.play().catch(err => {
        showToast(currentLang === 'es' ? 'Error al reproducir audio' : 'تعذر تشغيل الصوت');
      });
    }

    function escapeJsStr(str) {
      if (!str) return '';
      return str.replace(/\\/g, '\\\\').replace(/'/g, "\\'").replace(/"/g, '&quot;').replace(/\n/g, ' ');
    }

    function copyText(text) {
      if (navigator.clipboard) {
        navigator.clipboard.writeText(text).then(() => showToast(currentLang === 'es' ? 'Copiado al portapapeles' : 'تم نسخ النص بنجاح'));
      }
    }

    function shareText(text) {
      if (navigator.share) navigator.share({ title: 'Misbaha', text: text }).catch(() => {});
      else copyText(text);
    }

    function loadFavorites() {
      const saved = safeGetStorage(FAV_KEY);
      favorites = saved ? JSON.parse(saved) : [];
    }

    function toggleFavorite(text) {
      const index = favorites.indexOf(text);
      if (index > -1) {
        favorites.splice(index, 1);
        showToast(currentLang === 'es' ? 'Eliminado de favoritos' : 'تم الإزالة من المفضلة');
      } else {
        favorites.push(text);
        showToast(currentLang === 'es' ? 'Añadido a favoritos' : 'تم الإضافة إلى المفضلة');
      }
      safeSetStorage(FAV_KEY, JSON.stringify(favorites));
      if (currentGroup) renderGroupItems();
    }

    function hideAllViews() {
      ['homeView', 'categoryListView', 'detailView', 'tasbeehView', 'favoritesView'].forEach(id => {
        document.getElementById(id)?.classList.add('hidden');
      });
    }

    function goHome() {
      hideAllViews();
      document.getElementById('homeView')?.classList.remove('hidden');
      currentSection = null;
      currentGroup = null;
    }

    function showSection(sec) {
      currentSection = sec;
      hideAllViews();
      document.getElementById('categoryListView')?.classList.remove('hidden');
      const t = uiTexts[currentLang];
      document.getElementById('sectionTitle').innerText = sec === 'azkar' ? t.azkarSectionTitle : t.adyaSectionTitle;
      document.getElementById('searchInput').value = '';
      renderButtonsGrid();
    }

    function goBackToSection() {
      hideAllViews();
      if (currentSection) {
        document.getElementById('categoryListView')?.classList.remove('hidden');
      } else {
        goHome();
      }
    }

    function filterButtons() {
      const query = document.getElementById('searchInput').value.toLowerCase().trim();
      const grid = document.getElementById('buttonsGrid');
      if (!grid) return;
      const buttons = grid.querySelectorAll('button');
      buttons.forEach(btn => {
        const text = btn.innerText.toLowerCase();
        btn.style.display = text.includes(query) ? 'flex' : 'none';
      });
    }

    function renderButtonsGrid() {
      const grid = document.getElementById('buttonsGrid');
      if (!grid) return;
      grid.innerHTML = '';
      const data = currentSection === 'azkar' ? azkarData : adyaData;
      const isEs = currentLang === 'es';

      data.forEach(group => {
        const title = isEs ? group.titleEs : group.titleAr;
        const count = group.items.length;
        const btn = document.createElement('button');
        btn.type = 'button';
        btn.onclick = () => openGroup(group.id);
        btn.className = 'p-5 bg-white dark:bg-slate-800 hover:bg-slate-100 dark:hover:bg-slate-700/50 rounded-2xl border border-slate-200 dark:border-slate-700 shadow-sm transition flex justify-between items-center cursor-pointer text-right';
        btn.innerHTML = `
          <div class="flex items-center space-x-3 space-x-reverse">
            <div class="p-3 bg-emerald-100 dark:bg-emerald-950 text-emerald-700 dark:text-emerald-400 rounded-xl">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path></svg>
            </div>
            <div>
              <h3 class="font-bold text-slate-800 dark:text-slate-100 text-base">${title}</h3>
              <p class="text-xs text-slate-500 dark:text-slate-400 mt-1">${count} ${isEs ? 'invocaciones' : 'أذكار/أدعية'}</p>
            </div>
          </div>
          <span class="text-slate-400 dark:text-slate-500 font-bold text-lg">${isEs ? '→' : '←'}</span>
        `;
        grid.appendChild(btn);
      });
    }

    function openGroup(groupId) {
      const data = currentSection === 'azkar' ? azkarData : adyaData;
      currentGroup = data.find(g => g.id === groupId);
      if (!currentGroup) return;

      hideAllViews();
      document.getElementById('detailView')?.classList.remove('hidden');

      const isEs = currentLang === 'es';
      document.getElementById('itemGroupTitle').innerText = isEs ? currentGroup.titleEs : currentGroup.titleAr;

      renderGroupItems();
    }

    function getSavedCount(groupId, itemIndex, defaultCount) {
      const progress = JSON.parse(safeGetStorage(STORAGE_KEY) || '{}');
      if (progress[groupId] && progress[groupId][itemIndex] !== undefined) {
        return progress[groupId][itemIndex];
      }
      return defaultCount;
    }

    function setSavedCount(groupId, itemIndex, count) {
      const progress = JSON.parse(safeGetStorage(STORAGE_KEY) || '{}');
      if (!progress[groupId]) progress[groupId] = {};
      progress[groupId][itemIndex] = count;
      safeSetStorage(STORAGE_KEY, JSON.stringify(progress));
    }

    function resetGroupProgress(groupId) {
      const progress = JSON.parse(safeGetStorage(STORAGE_KEY) || '{}');
      delete progress[groupId];
      safeSetStorage(STORAGE_KEY, JSON.stringify(progress));
    }

    function decrementCounter(index) {
      if (!currentGroup || !currentGroup.items[index]) return;
      const item = currentGroup.items[index];
      let currentCount = getSavedCount(currentGroup.id, index, item.count);

      if (currentCount > 0) {
        currentCount--;
        setSavedCount(currentGroup.id, index, currentCount);
        renderGroupItems();

        if (currentCount === 0) {
          const nextIndex = index + 1;
          if (nextIndex < currentGroup.items.length) {
            setTimeout(() => {
              const nextElem = document.getElementById(`zikr-card-${nextIndex}`);
              if (nextElem) {
                nextElem.scrollIntoView({ behavior: 'smooth', block: 'center' });
              }
            }, 250);
          } else {
            showToast(uiTexts[currentLang].completedGroup);
          }
        }
      }
    }

    function resetSingleItem(index) {
      if (currentGroup && currentGroup.items[index]) {
        setSavedCount(currentGroup.id, index, currentGroup.items[index].count);
        renderGroupItems();
        showToast(currentLang === 'es' ? 'Contador reiniciado' : 'تم إعادة ضبط الذكر الحالي');
      }
    }

    function resetAllInGroup() {
      if (currentGroup) {
        resetGroupProgress(currentGroup.id);
        renderGroupItems();
        window.scrollTo({ top: 0, behavior: 'smooth' });
        showToast(currentLang === 'es' ? 'Se han reiniciado todos los contadores' : 'تم إعادة تصفير كافة أذكار المجموعة');
      }
    }

    // عرض جميع الأذكار كقائمة واحدة متتالية
    function renderGroupItems() {
      const container = document.getElementById('itemsContainer');
      if (!container || !currentGroup || !currentGroup.items.length) return;

      const totalItems = currentGroup.items.length;
      const isEs = currentLang === 'es';
      const t = uiTexts[currentLang];

      let totalCompletedInGroup = 0;
      currentGroup.items.forEach((it, idx) => {
        const cnt = getSavedCount(currentGroup.id, idx, it.count);
        if (cnt === 0) totalCompletedInGroup++;
      });
      const overallPercent = Math.round((totalCompletedInGroup / totalItems) * 100);

      document.getElementById('progressPercent').innerText = `${overallPercent}%`;
      document.getElementById('progressBarFill').style.width = `${overallPercent}%`;

      container.innerHTML = '';

      currentGroup.items.forEach((item, index) => {
        const currentCount = getSavedCount(currentGroup.id, index, item.count);
        const initialMax = item.maxCount || item.count;
        const isFav = favorites.includes(item.text);
        const isDone = currentCount === 0;
        const itemProgressStr = t.itemProgress.replace('{current}', index + 1).replace('{total}', totalItems);

        const card = document.createElement('div');
        card.id = `zikr-card-${index}`;
        card.className = 'bg-white dark:bg-slate-800 rounded-3xl p-6 shadow-md border border-slate-200 dark:border-slate-700 space-y-5 transition-all duration-300';

        card.innerHTML = `
          <!-- شريط المعرف والمؤشر -->
          <div class="flex items-center justify-between text-xs font-bold border-b border-slate-100 dark:border-slate-700/60 pb-3">
            <span class="text-emerald-700 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3 py-1 rounded-full border border-emerald-200 dark:border-emerald-800">
              ${itemProgressStr}
            </span>
            ${item.note ? `<span class="bg-amber-50 dark:bg-amber-950/50 text-amber-700 dark:text-amber-300 px-3 py-1 rounded-full border border-amber-200 dark:border-amber-800">${item.note}</span>` : ''}
          </div>

          <!-- الأذكار بالعربية -->
          ${!isEs ? `
            <div class="leading-relaxed custom-text-size font-medium text-slate-900 dark:text-slate-50 text-center tracking-wide py-2">
              ${item.text}
            </div>
          ` : ''}

          <!-- الأذكار باللغة الإسبانية والنص اللاتيني -->
          ${isEs ? `
            <div class="space-y-3">
              ${item.latin ? `<div class="text-sm text-slate-500 dark:text-slate-400 italic text-center font-semibold">${item.latin}</div>` : ''}
              ${item.explanationEs ? `<div class="text-sm text-slate-700 dark:text-slate-200 bg-slate-50 dark:bg-slate-900/60 p-4 rounded-2xl border border-slate-100 dark:border-slate-800 leading-relaxed text-center">${item.explanationEs}</div>` : ''}
            </div>
          ` : ''}

          <!-- العداد التفاعلي -->
          <div class="flex flex-col items-center justify-center pt-2">
            <button type="button" onclick="decrementCounter(${index})" class="w-32 h-32 rounded-full flex flex-col items-center justify-center transition transform active:scale-90 cursor-pointer shadow-xl border-4 ${isDone ? 'bg-emerald-600 text-white border-emerald-400 hover:bg-emerald-700' : 'bg-gradient-to-br from-emerald-500 to-teal-700 text-white border-emerald-300 hover:from-emerald-600 hover:to-teal-800'}">
              <span class="text-3xl font-extrabold">${isDone ? '✓' : currentCount}</span>
              <span class="text-[11px] font-semibold mt-1 opacity-90">${isDone ? t.completedItem : t.pressToCount}</span>
              ${!isDone ? `<span class="text-[10px] opacity-75 mt-0.5">${currentCount} /${initialMax}</span>` : ''}
            </button>
          </div>

          <!-- أدوات التفاعل -->
          <div class="flex items-center justify-center space-x-2 space-x-reverse pt-2 border-t border-slate-100 dark:border-slate-700">
            ${item.audioUrl ? `
              <button type="button" onclick="playAudio('${item.audioUrl}')" class="p-2.5 rounded-xl bg-slate-100 dark:bg-slate-700 hover:bg-emerald-100 dark:hover:bg-emerald-900 text-slate-700 dark:text-slate-200 transition cursor-pointer" title="استماع">
                🔊
              </button>
            ` : ''}
            <button type="button" onclick="copyText('${escapeJsStr(isEs ? (item.explanationEs || item.text) : item.text)}')" class="p-2.5 rounded-xl bg-slate-100 dark:bg-slate-700 hover:bg-emerald-100 dark:hover:bg-emerald-900 text-slate-700 dark:text-slate-200 transition cursor-pointer" title="نسخ">
              📋
            </button>
            <button type="button" onclick="shareText('${escapeJsStr(isEs ? (item.explanationEs || item.text) : item.text)}')" class="p-2.5 rounded-xl bg-slate-100 dark:bg-slate-700 hover:bg-emerald-100 dark:hover:bg-emerald-900 text-slate-700 dark:text-slate-200 transition cursor-pointer" title="مشاركة">
              🔗
            </button>
            <button type="button" onclick="toggleFavorite('${escapeJsStr(item.text)}')" class="p-2.5 rounded-xl ${isFav ? 'bg-amber-100 dark:bg-amber-950 text-amber-600' : 'bg-slate-100 dark:bg-slate-700 text-slate-700 dark:text-slate-200'} hover:bg-amber-100 dark:hover:bg-amber-900 transition cursor-pointer" title="المفضلة">
              ${isFav ? '★' : '☆'}
            </button>
            <button type="button" onclick="resetSingleItem(${index})" class="p-2.5 rounded-xl bg-slate-100 dark:bg-slate-700 hover:bg-rose-100 dark:hover:bg-rose-950 text-slate-700 dark:text-slate-200 transition cursor-pointer" title="إعادة ضبط الذكر">
              🔄
            </button>
          </div>
        `;
        container.appendChild(card);
      });
    }

    // المسبحة الإلكترونية
    function showTasbeeh() {
      hideAllViews();
      document.getElementById('tasbeehView')?.classList.remove('hidden');
      renderTasbeehGrid();
    }

    function getTasbeehCount(id) {
      const saved = safeGetStorage('tasbeeh_counts_v5');
      const counts = saved ? JSON.parse(saved) : {};
      return counts[id] || 0;
    }

    function setTasbeehCount(id, val) {
      const saved = safeGetStorage('tasbeeh_counts_v5');
      const counts = saved ? JSON.parse(saved) : {};
      counts[id] = val;
      safeSetStorage('tasbeeh_counts_v5', JSON.stringify(counts));
    }

    function incrementTasbeeh(id) {
      const val = getTasbeehCount(id) + 1;
      setTasbeehCount(id, val);
      renderTasbeehGrid();
    }

    function resetSingleTasbeeh(id) {
      setTasbeehCount(id, 0);
      renderTasbeehGrid();
      showToast(currentLang === 'es' ? 'Contador reiniciado' : 'تم تصفير العداد');
    }

    function resetAllTasbeehs() {
      safeSetStorage('tasbeeh_counts_v5', JSON.stringify({}));
      renderTasbeehGrid();
      showToast(currentLang === 'es' ? 'Todos los contadores reiniciados' : 'تم تصفير جميع العدادات');
    }

    function renderTasbeehGrid() {
      const grid = document.getElementById('tasbeehGrid');
      if (!grid) return;
      grid.innerHTML = '';
      const isEs = currentLang === 'es';

      tasbeehItems.forEach(item => {
        const val = getTasbeehCount(item.id);
        const card = document.createElement('div');
        card.className = 'bg-white dark:bg-slate-800 p-6 rounded-3xl border border-slate-200 dark:border-slate-700 shadow-sm flex flex-col items-center justify-between space-y-4';
        card.innerHTML = `
          <div class="text-center space-y-1">
            <h3 class="text-xl font-bold text-slate-800 dark:text-slate-100">${item.ar}</h3>
            <p class="text-xs text-slate-500 dark:text-slate-400 italic">${item.latin}</p>
            <p class="text-xs text-slate-600 dark:text-slate-300">${item.es}</p>
          </div>

          <button type="button" onclick="incrementTasbeeh('${item.id}')" class="w-28 h-28 rounded-full bg-gradient-to-br from-amber-500 to-amber-700 hover:from-amber-600 hover:to-amber-800 text-white shadow-lg flex flex-col items-center justify-center transition transform active:scale-95 cursor-pointer border-4 border-amber-300">
            <span class="text-2xl font-extrabold">${val}</span>
            <span class="text-[10px] opacity-80 mt-0.5">${isEs ? 'Toca' : 'تسبيح'}</span>
          </button>

          <button type="button" onclick="resetSingleTasbeeh('${item.id}')" class="text-xs font-semibold text-slate-500 hover:text-rose-600 dark:text-slate-400 dark:hover:text-rose-400 transition cursor-pointer">
            ${isEs ? 'Reiniciar' : 'تصفير'}
          </button>
        `;
        grid.appendChild(card);
      });
    }

    // شاشة المفضلة
    function showFavorites() {
      hideAllViews();
      document.getElementById('favoritesView')?.classList.remove('hidden');
      loadFavorites();
      const container = document.getElementById('favoritesContainer');
      if (!container) return;
      container.innerHTML = '';
      const isEs = currentLang === 'es';
      const t = uiTexts[currentLang];

      if (!favorites.length) {
        container.innerHTML = `
          <div class="p-8 text-center text-slate-500 dark:text-slate-400 bg-white dark:bg-slate-800 rounded-3xl border border-slate-200 dark:border-slate-700">
            <p class="text-base font-medium">${t.noFavs}</p>
          </div>
        `;
        return;
      }

      favorites.forEach(text => {
        const card = document.createElement('div');
        card.className = 'bg-white dark:bg-slate-800 p-5 rounded-2xl border border-slate-200 dark:border-slate-700 shadow-sm space-y-3';
        card.innerHTML = `
          <p class="text-base font-medium leading-relaxed text-slate-800 dark:text-slate-100">${text}</p>
          <div class="flex items-center justify-between pt-2 border-t border-slate-100 dark:border-slate-700/50">
            <div class="flex items-center space-x-2 space-x-reverse">
              <button type="button" onclick="copyText('${escapeJsStr(text)}')" class="p-2 rounded-lg bg-slate-100 dark:bg-slate-700 text-xs font-bold text-slate-700 dark:text-slate-200">
                📋 ${isEs ? 'Copiar' : 'نسخ'}
              </button>
              <button type="button" onclick="shareText('${escapeJsStr(text)}')" class="p-2 rounded-lg bg-slate-100 dark:bg-slate-700 text-xs font-bold text-slate-700 dark:text-slate-200">
                🔗 ${isEs ? 'Compartir' : 'مشاركة'}
              </button>
            </div>
            <button type="button" onclick="toggleFavorite('${escapeJsStr(text)}')" class="text-xs font-bold text-rose-600 dark:text-rose-400 bg-rose-50 dark:bg-rose-950/50 px-3 py-1.5 rounded-lg border border-rose-200 dark:border-rose-800">
              ${t.removeFav}
            </button>
          </div>
        `;
        container.appendChild(card);
      });
    }

    // تشغيل الإعدادات المبدئية عند التحميل
    window.addEventListener('DOMContentLoaded', () => {
      loadSavedTheme();
      loadFavorites();
      applyLanguageUI();
    });
  </script>
</body>
</html>
