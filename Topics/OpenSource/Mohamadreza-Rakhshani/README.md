# بررسی رویکرد باز متن در تولید نرم افزار

## محمدرضا رخشانی

دانشجوی کارشناسی ، دانشگاه صنعتی همدان، همدان،  mohammadrezarakhshanii@gmail.com 9704223



 
### چکیده

توسعه و استفاده از نرم افزار باز متن (OSS) به طور قابل توجهی در سال های اخیر افزایش یافته است. بنابراین نیاز به تجزیه و تحلیل و درک این پروژه ها داریم. کیفیت نرم افزار یک مشخصه مهمی است که بر روی چرخه عمر سیستم، عملکرد و عمر مفید تاثیر میگذارد. مدل های موجود برای کیفیت نرم افزار مبتنی بر تجزیه و تحلیل تجربی نرم افزار منبع مناسب (PSS) است و باید در نرم افزار متن باز تایید شوند. تحقیقات روی PSS نشان داده است که کیفیت نرم افزار با افزایش سن کاهش می یابد. بخشی از این کاهش با فعالیت‌های تعمیر و نگهداری چرخه حیات مرتبط است که باعث تغییر در اندازه و پیچیدگی سیستم می‌شود، در حالی که خطاهای نرم‌افزاری را به سیستم اصلاح‌شده وارد می‌کند. فعالیت‌های نگهداری چرخه حیات در سیستم‌های OSS تحت یک پارادایم بسیار متفاوت پردازش می‌شوند. ما علاقه مند به بررسی اثرات فعالیت های تعمیر و نگهداری بر نتایج پروژه OSS هستیم. لینوکس یکی از محبوب ترین و پیچیده ترین پروژه های OSS موجود است. در تحقیق خود، ویژگی های کد منبع لینوکس را بررسی می کنیم و ما برخی از نتایج اولیه از اثرات انواع مختلف فعالیت‌های تعمیر و نگهداری بر کیفیت نرم‌افزار لینوکس را ارائه می‌کنیم.

### واژه های کلیدی

کیفیت نرم افزار، تعمیر و نگهداری نرم افزار، منبع باز، سیستم عامل لینوکس

### مقدمه

بیش از 30 سال پیش، فرد بروکس در مورد نیاز به یک گلوله نقره ای برای کمک به مهندسان نرم افزار و متخصصان IS نوشت که فرآیند ایجاد و نگهداری سیستم های نرم افزاری را سرعت می بخشد. در حال حاضر، حتی در قرن بیست و یکم، ساختن سیستم‌های نرم‌افزاری همچنان پرهزینه و نگهداری آنها دشوار است. در سال‌های اخیر استفاده مجدد از کد منبع و استفاده از نرم‌افزارهای خارج از قفسه رشد داشته است. در بسیاری از این موارد کد منبع برای تجزیه و تحلیل کاربر در دسترس نیست. اگر نرم‌افزار مطابق انتظار عمل نکند، مدیر IS و رهبران پروژه در اختیار دارنده کد منبع هستند که آیا می‌توان تغییری ایجاد کرد یا خیر. جنبش OSS در حال تغییر روش توسعه، نگهداری و به روز رسانی نرم افزار است [1-3]. سیستم‌های OSS معمولاً به صورت نرم‌افزار رایگان توسعه می‌یابند و با هزینه کم یا بدون هزینه در دسترس هستند. اخیراً OSS در سیستم های نرم افزاری بیشتر و بیشتر مورد استفاده قرار گرفته است. به عنوان مثال، Apache، یک پروژه OSS، 66.04 درصد از سهم بازار سرور وب را در اختیار دارد (Netcraft 2004). تعداد افرادی که از سیستم عامل لینوکس استفاده می کنند بر اساس کاربران ثبت نام شده لینوکس 150000 تخمین زده شده است. دلیل افزایش استفاده از OSS نه تنها هزینه کم و دسترسی آسان به کد است، بلکه کیفیت نرم افزار به طور مداوم بالا است [2] تحقیقات فعلی در مورد کیفیت نرم افزار بر اساس داده های تجربی از سیستم های نرم افزاری است که از طریق روش های سنتی توسعه یافته اند. متداول‌ترین معیارهای کیفی نرم‌افزار ذکر شده، تعداد خرابی سیستم، یعنی تعداد خاتمه‌های غیرعادی (abends)، و تعداد عدم انطباق با الزامات تعریف‌شده توسط کاربر است [4]. با OSS، ما نیاز به بررسی مجدد معیارهای مورد استفاده برای ارزیابی کیفیت سیستم نرم افزار داریم. لینوکس یکی از موفق ترین پروژه های OSS است و با بسیاری از برنامه های تجاری استفاده می شود [3، 9]. در این تحقیق برخی از ویژگی‌های مهم نرم‌افزاری را که به کیفیت نرم‌افزار سازگار در لینوکس کمک می‌کنند، بررسی می‌کنیم. در بخش‌های بعدی، برخی از ویژگی‌های مهم کیفی و فعالیت‌های نگهداری در OSS را ارائه می‌کنیم. سپس مدلی را برای کیفیت در OSS ایجاد می‌کنیم و با استفاده از داده‌های تاریخی برای تغییرات لینوکس و گزارش‌های مربوط به تغییرات نگهداری چرخه عمر، آن را به صورت تجربی آزمایش می‌کنیم.

### ویژگی های کیفی در OSS

کیفیت نرم افزار یکی از مهمترین معیارهای موفقیت یک پروژه نرم افزاری است. بری بوهم کیفیت نرم افزار را اینگونه تعریف می کند: «دستیابی به سطوح بالایی از رضایت کاربر، قابل حمل بودن، قابلیت نگهداری، استحکام و تناسب برای استفاده» [10]. جونز از کیفیت به عنوان «عدم نقصی که باعث می‌شود نرم‌افزار به طور کامل متوقف شود یا نتایج غیرقابل قبولی تولید کند» [11] اشاره می‌کند. این تعاریف از کیفیت نرم افزار را نمی توان مستقیماً برای OSS اعمال کرد. برخلاف CSS، الزامات کاربر به طور رسمی در OSS در دسترس نیست. مدل‌های کیفی موجود فهرستی از ویژگی‌های باکیفیت ارائه می‌دهند که مسئول کیفیت بالای نرم‌افزار (یا غیر آن) هستند. می‌توانیم OSS را به دو دسته عمده تقسیم کنیم: نوع 1: پروژه‌هایی که برای تکرار و جایگزینی نرم‌افزارهای CSS موجود توسعه داده می‌شوند. و نوع 2: پروژه‌هایی که برای ایجاد نرم‌افزار جدیدی که هیچ نرم‌افزار CSS معادل موجودی ندارد. 
لینوکس نمونه ای از نرم افزار نوع 1 است که در ابتدا به عنوان جایگزینی برای یونیکس توسعه یافت. Protégé، نرم افزار توسعه هستی شناسی نمونه ای از نرم افزار نوع 2 است. ما برخی از ویژگی های مهم حمل کیفیت را در OSS شناسایی می کنیم.

1.	قابلیت اطمینان
قابلیت اطمینان به تداوم خروجی ارائه شده توسط سیستم اشاره دارد. عامل قابلیت اطمینان به رفتار نرم افزار مربوط می شود. میزانی است که عملکردهای مورد نظر خود را با دقت لازم انجام می دهد. نرم افزار باید در تمام حالت های ممکن محیط، همانطور که انتظار می رود رفتار کند. اگرچه OSS بدون هزینه در دسترس است، اما چنین نرم افزاری باید حداقل قابلیت اطمینان عملیاتی را داشته باشد تا برای هر برنامه کاربردی مفید باشد. قابلیت اطمینان تأثیر قابل توجهی بر کیفیت نرم افزار دارد، زیرا مقبولیت کاربر به یک محصول به توانایی آن در عملکرد صحیح و مطمئن بستگی دارد.

2.	عملکرد
عملکرد به ارائه حداقل کارکردهای مورد نیاز کاربر اشاره دارد. برای OSS نوع 1 هیچ الزامات عملکرد رسمی وجود ندارد، با این حال سطح مشخصی از انتظارات از نظر عملکرد آن در مقایسه با یک CSS موجود وجود خواهد داشت. کاربران جدید نرم افزار نوع 1 را در صورتی که عملکرد اولیه معادل CSS خود را ارائه دهد، اتخاذ خواهند کرد. در مورد OSS نوع 2، هیچ نرم افزاری وجود ندارد که نیازهای عملکردی را از آن استخراج کند، بنابراین کاربران جدید مطابق نیازهای خود چنین نیازهایی را تعریف خواهند کرد. یک OSS نوع 1 در صورتی که عملکرد اولیه معادل CSS خود را ارائه دهد، از کیفیت بالایی برخوردار خواهد بود. از طرف دیگر OSS نوع 2 در صورتی که نیازهای عملکردی کاربران فعال خود را با سرعت ثابتی فراهم کند، از کیفیت بالایی برخوردار خواهد بود.

3.	دسترسی
در دسترس بودن به این معنی است که نرم افزار باید در حداقل زمان مورد نیاز در دسترس کاربر باشد. این ویژگی به ویژه در حوزه خدمات الکترونیکی بسیار مهم است. بسته به زمینه، در دسترس بودن معنای متفاوتی خواهد داشت، به عنوان مثال در نرم افزار فضای بحرانی ماموریت، در دسترس بودن توان پردازشی برای محاسبه الگوریتم های پیچیده است، در حالی که در زمینه خدمات الکترونیکی، در دسترس بودن سیستم نرم افزاری برای پشتیبانی از سخت افزار برای خدمات 24 ساعته (حملات هکرها در دسترس بودن سیستم را کاهش می دهد). در متن باز، در دسترس بودن رایگان کد ممکن است وضعیت متناقضی ایجاد کند. کد منبع نرم افزار به صورت جهانی در دسترس است. این بدان معنی است که کاربران می توانند آسیب پذیری های بالقوه را شناسایی کنند، اما همچنین به این معنی است که هکرها نیز می توانند به راحتی از این آسیب پذیری ها سوء استفاده کنند. از این رو کیفیت به میزان هوشیاری کاربران فعال در شناسایی آسیب‌پذیری‌ها و محافظت از نرم‌افزار در برابر فعالیت‌های هک مخرب بستگی دارد. پروژه‌هایی که نتوانند نرم‌افزار امنی ارائه کنند، کیفیت و کاربران کاهش می‌یابند.

4.	قابلیت نگهداری
قابلیت نگهداری به طور کلی به توانایی نگهداری سیستم در یک دوره زمانی اشاره دارد. این شامل سهولت تشخیص، جداسازی و حذف عیوب خواهد بود. علاوه بر این، عواملی مانند سهولت افزودن عملکرد جدید، رابط به اجزای جدید، توانایی برنامه نویسان در درک کدهای موجود و توانایی تیم آزمایش برای آزمایش سیستم (به دلیل گزینه هایی مانند دستورالعمل های تست و نقاط تست) قابلیت نگهداری یک سیستم را افزایش می دهد. تعمیر و نگهداری یک محرک هزینه هنگفت در پروژه های نرم افزاری است. OSS توسط یک جامعه جهانی از کاربران دانلود و استفاده می شود. هیچ گونه تعامل حضوری بین نگهبانان نرم افزار وجود ندارد. آنها باید بر مستندات موجود در کد منبع و ارتباط از طریق تابلوهای پیام تکیه کنند. بنابراین OSS باید بسیار قابل نگهداری باشد. عدم تعریف مناسب رابط، پیچیدگی ساختاری و مستندات ناکافی در نسخه موجود OSS می‌تواند مشارکت‌های جدید را کاهش دهد. از آنجایی که مشارکت داوطلبانه است، قابلیت نگهداری پایین حداقل مشارکت کاربران فعال را به همراه خواهد داشت و از این رو بر کیفیت اثر منفی خواهد داشت.

5.	قابلیت استفاده مجدد
در CSS از ماژول های موجود برای چندین پروژه استفاده می شود. هزینه های توسعه عامل اصلی تاثیرگذار بر این ویژگی کیفیت در حوزه CSS است. در OSS هیچ هزینه توسعه یا نگهداری وجود ندارد. جوامع OSS توسعه و استفاده از ماژول های قابل استفاده مجدد را تشویق می کنند که می توانند به راحتی به اشتراک گذاشته و پیاده سازی شوند. OSS که از ماژول های قابل استفاده مجدد استفاده می کند مشارکت های بیشتری را جذب کرده و کیفیت بالایی را حفظ می کند.






### تعمیر و نگهداری نرم افزار در OSS

تعمیر و نگهداری نرم افزار عبارت است از اصلاح یک محصول نرم افزاری پس از تکمیل توسعه، برای اصلاح عیوب، بهبود عملکرد یا سازگاری با محیط تغییر یافته (ANSI/IEEE، 1983). با توجه به Lehman و همکاران. «برنامه‌های نوع الکترونیکی1 به‌عنوان کیفیت رو به کاهش تلقی می‌شوند، مگر اینکه به‌دقت نگهداری شوند و با یک محیط عملیاتی در حال تغییر سازگار شوند». از این رو کیفیت سیستم در حال فروپاشی ثابت است [14-16]. یکی از عوامل اصلی این کاهش، فعالیت تعمیر و نگهداری چرخه حیات است [16]. در نرم‌افزاری که از طریق روش‌های مرسوم توسعه یافته و نگهداری می‌شود، تلاش صرف شده برای تعمیر و نگهداری بیشتر هزینه‌های متحمل شده در طول عمر مفید یک سیستم را نشان می‌دهد. محققانی که هزینه‌های نرم‌افزار چرخه عمر را مطالعه می‌کنند نشان داده‌اند که فعالیت‌های تعمیر و نگهداری نرم‌افزار تا 90 درصد هزینه چرخه عمر یک سیستم نرم‌افزاری را تشکیل می‌دهند [17]. تحقیقات گسترده ای در مورد چگونگی افزایش تلاش تعمیر و نگهداری با افزایش سن سیستم انجام شده است [14]. از آنجایی که سازمان‌های بیشتری در حال تطبیق OSS در سطوح مختلف هستند، بررسی عواملی که بر فعالیت‌های تعمیر و نگهداری در حوزه OSS تأثیر می‌گذارند بسیار مهم است. برخلاف PSS، هیچ تعهد قراردادی برای نگهداری وجود ندارد. از این رو هزینه های تعمیر و نگهداری می تواند به شکل از دست دادن کسب و کار و در دسترس نبودن عملکردها، در صورتی که پروژه رشد نکند، قابل توجه باشد. فعالیت های تعمیر و نگهداری را می توان به چهار دسته زیر تقسیم کرد.

1.	تعمیر و نگهداری اصلاحی
تعمیر و نگهداری اصلاحی برای رفع نقص انجام می شود و زمانی انجام می شود که نقصی رخ داده باشد. این عمل غیر قابل پیش بینی انجام می شود، زیرا هیچ اطلاع قبلی از وجود نقص وجود ندارد.

2.	تعمیر و نگهداری تطبیقی
تعمیر و نگهداری تطبیقی تغییر در نرم افزار برای تطبیق با تغییرات محیطی است که در آن کار می کند (مانند پلت فرم های سخت افزاری جدید یا قوانین تجاری جدید).

3.	تعمیر و نگهداری کامل
تعمیر و نگهداری کامل، افزودن قابلیت های جدید است که شامل ایجاد تغییراتی برای بهبود بخشی از جنبه های سیستم است، حتی زمانی که تغییرات ناشی از نقص نباشد.

4.	تعمیر و نگهداری پیشگیرانه	
تعمیر و نگهداری پیشگیرانه شامل تغییر برخی از جنبه های سیستم برای جلوگیری از خرابی است. تعمیر و نگهداری پیشگیرانه معمولاً زمانی حاصل می شود که یک برنامه نویس یک خطای واقعی یا بالقوه را پیدا کند که هنوز به یک خطا تبدیل نشده است و قبل از ایجاد آسیب برای اصلاح عیب اقدام می کند. این نوع فعالیت ها باعث کاهش پیچیدگی نرم افزار و بهبود کیفیت می شود.

### مدل تحقیق

پروژه‌های OSS در حالی که با عدم وجود کاربر، الزامات، هزینه‌ها یا زمان‌بندی‌های تعریف‌شده موجود هستند، کیفیت بالایی از خود نشان می‌دهند. OSS با مشارکت های داوطلبانه مکرر کاربران فعال در سراسر جهان مشخص می شود. روش های توسعه و نگهداری در OSS و PSS ذاتا متفاوت است. 

از این رو ما به مدل های جدیدی نیاز داریم که بتواند عوامل موثر بر ویژگی های مختلف نرم افزار در سیستم های OSS را توضیح دهد. به دلیل تفاوت بین فرآیندهای نرم افزاری برای سیستم های OSS و PSS، معیارهای معمول برای کیفیت نرم افزار را نمی توان برای سیستم های OSS جمع آوری کرد. ما معتقدیم که در طول مراحل مختلف چرخه زندگی، اهمیت ویژگی های کیفیت برای کاربر فعال تغییر خواهد کرد. در ابتدا، در صورتی که نیازهای عملکردی را برآورده کند کاربران شروع به استفاده از سیستم خواهند کرد. از این رو عملکرد یک ویژگی حیاتی خواهد بود. از آنجایی که نرم افزار رایگان است، کاربران ممکن است در مورد انتظارات قابلیت اطمینان نرم افزار راحت باشند. اکثر OSS نسخه‌های تولیدی و آزمایشی را به صورت موازی حفظ می‌کنند، بنابراین کاربران می‌توانند در صورتی که به قابلیت اطمینان یا نسخه‌ای کاربردی‌تر که ممکن است در حال حاضر چندان قابل اعتماد و پایدار نباشد، از نسخه پایدارتر استفاده کنند. 

همانطور که استفاده از OSS پیشرفت می کند و کاربران شروع به گزارش خطا می کنند، سایر عوامل نیز مهم خواهند شد. از دیدگاه مشارکت کنندگان، قابلیت نگهداری مهم خواهد بود، زیرا تصحیح خطاها یا ارتقاء کد موجود، کار مهمی است و هر چه کد قابل نگهداری تر باشد، انجام تغییرات برای نگهداری کنندگان آسان تر خواهد بود. اگر نرم افزار قابلیت نگهداری نداشته باشد، تیم تعمیر و نگهداری ممکن است علاقه خود را از دست بدهد و در نتیجه منجر به کاهش کیفیت شود. 

برای مشارکت کنندگان کد اصلی، با افزایش اندازه و عملکرد نرم افزار، قابلیت استفاده مجدد اهمیت پیدا می کند. اگر کاربران اجزای توسعه یافته در یک پروژه را قابل استفاده مجدد بیابند، به احتمال زیاد به استفاده از نرم افزار ادامه خواهند داد. ویژگی در دسترس بودن زمانی قابل توجه می شود که کاربر استفاده از نرم افزار را تثبیت کرده باشد و برنامه هایی را اجرا کند که توسط نرم افزار پشتیبانی می شوند، به عنوان مثال. یک سیستم عامل OSS در چنین حالتی در دسترس بودن سیستم و جنبه های امنیتی نیز به درک کلی کاربر از کیفیت می افزاید. 

برای هر نرم افزاری، بیشتر هزینه و تلاش چرخه عمر صرف تشخیص و حذف خطاها یا بهبود عملکرد در طول تعمیر و نگهداری می شود [16، 18]. افزودن قابلیت های جدید می تواند کار تعمیر و نگهداری را دشوارتر کند. افزودن ماژول های جدید معمولاً با خطاهای جدید همراه است و بنابراین کار تعمیر و نگهداری پیچیده تر می شود [19]. 

ما اثرات نگهداری اصلاحی، تطبیقی و پیشگیرانه را بر کیفیت نرم افزار مدل می کنیم. ما کامل و تطبیقی را با هم ترکیب کردیم زیرا تغییرات ایجاد شده برای مطابقت با الزامات محیطی و نیازهای کاربر از طریق همان فرآیند در OSS سرچشمه می گیرد.

 
شکل1: مدل تحقیق برای کیفیت OSS

در جوامع OSS، کاربر نرم افزار عیوب را شناسایی کرده و آنها را گزارش می دهد (کاربر می تواند یک نگهدارنده، نویسنده یا یک کاربر نهایی باشد). پروژه های فردی ساختار خاص خود را برای رفع عیوب دارند. افزودن کد جدید برای رفع نقص باعث افزایش پیچیدگی نرم افزار می شود. هر چه نرم افزار پیچیده تر باشد، افزودن کد به آن در آینده سخت تر خواهد بود. اگر کد به خوبی مستند نشده باشد، نگهبانان تمایلی به حذف خطوط کد موجود ندارند. تعمیر و نگهداری اصلاحی قابلیت اطمینان و نگهداری نرم افزار را کاهش می دهد. ما انتظار داریم بین تعمیر و نگهداری اصلاحی و کیفیت رابطه معکوس وجود داشته باشد.
 
نگهداری تطبیقی می تواند سناریوی پیچیده ای را در صورت استفاده شرکتی از OSS ارائه دهد. اگر OSS در سازمان‌هایی استفاده شود که برنامه‌های کاربردی PSS موجود دارند، تعمیر و نگهداری تطبیقی برای تطبیق رابط‌ها با PSS مورد نیاز خواهد بود. نگهداری کامل در OSS بسیار شبیه به نگهداری تطبیقی خواهد بود. بنابراین ما این دو را با هم در مدل خود گروه بندی می کنیم. تأثیر این دسته از نگهداری به دامنه وابسته خواهد بود. اگر محیط عملیاتی OSS بسیار پویا باشد، نیاز مکرر به چنین نگهداری وجود خواهد داشت. از طرف دیگر، اگر محیط عملیاتی پایدار باشد و کاربران خواستار اضافه کردن مکرر عملکردهای جدید نباشند، نیاز کمتری به چنین نگهداری وجود خواهد داشت. 

نگهداری پیشگیرانه یک رویکرد پیشگیرانه برای نگهداری است. ما معتقدیم که پروژه‌های OSS از طریق نگهداری پیشگیرانه قابل توجه سطح کیفیت بالایی را حفظ می‌کنند. ما انتظار داریم چنین تعمیر و نگهداری بر کیفیت نرم افزار تأثیر مثبت بگذارد.

تجزیه و تحلیل داده ها و نتایج
ما در حال بررسی مدل تحقیق با استفاده از داده‌های تجربی از تجزیه و تحلیل کد منبع لینوکس هستیم، زیرا از نسخه 2.4.0 تا 2.4.20 تکامل یافته است، در مجموع 21 نسخه منتشر شده است. دوره انتشار 2001 تا 2003 بود. ما اندازه ماژول‌های مجزا را در هر نسخه اندازه‌گیری می‌کنیم و سپس از یک معیار مجموع برای کل نسخه استفاده می‌کنیم. تعداد کل ماژول های تحلیل شده از 5571 در نسخه 2.4.0 به 11340 در نسخه 2.4.20 افزایش یافته است. اندازه نرم افزار با خطوط منبع کد (SLOC) اندازه گیری می شود. ما اندازه  SLOC را با استفاده از دستورات لینوکس برای هر ماژول و برای سیستم کامل اندازه گیری می کنیم. ما همچنین اندازه را بر حسب تعداد ماژول های C اندازه می گیریم. تمام نتایج در برابر فایل های آزمایشی تایید می شوند. تغییرات نسخه لینوکس در قالب یک پچ جدید ارائه شده است. کاربر می تواند به سادگی پچ جدید را دانلود کند و نسخه قدیمی به نسخه فعلی به روز می شود. ما فایل‌های پچ را تجزیه و تحلیل می‌کنیم تا معیارهای دقیق یکسانی را در هر پچ به دست آوریم. ما ابزاری را برای شمارش تعداد و نوع ماژول‌هایی که در نسخه جدیدتر اضافه، حذف یا به‌روزرسانی می‌شوند، ایجاد کردیم. ما ابزار خود را در برابر فایل های ماژول ها و تغییرات شناخته شده اعتبارسنجی کردیم. ما همچنین ابزاری برای شمارش تعداد تعمیرات اصلاحی، تطبیقی یا کامل از لاگ تغییرات ایجاد کردیم. تاکنون در مجموع 29580 وصله در 21 نسخه مورد تجزیه و تحلیل قرار گرفته است.
 
شکل2: رشد اندازه و نگهدارنده در لینوکس

تحقیقات قبلی نشان داده است که لینوکس رشد فوق العاده خطی دارد [5]. تجزیه و تحلیل ما نشان داد که افزایش اندازه با افزایش در تعداد نگهدارنده ها رابطه متناسبی دارد، همانطور که در شکل 1 نشان داده شده است کیفیت حفظ می شود زیرا افزایش اندازه نرم افزار با افزایش تلاش برای تعمیر و نگهداری همراه است. همانطور که قبلا توضیح داده شد، ما معتقدیم که اهمیت ویژگی های حمل کیفیت در OSS پویا خواهد بود. از آنجایی که هیچ وسیله ای برای جلب انطباق با نیازهای کاربر یا رضایت کاربر وجود ندارد، برای لینوکس کیفیت نرم افزار را بر حسب شاخص بلوغ نرم افزار (SMI) که توسط IEEE تعریف شده است، عملی می کنیم. همانطور که SMI شروع نزدیک شدن به 1.0 می کند، محصول نرم افزاری شروع به تثبیت می کند.

### مراجع و منابع 

[1]	M.-W. Wu and Y.-D. Ling, "Open source software development : An overview," IEEE Computing Practices,June2001. 
[2]	E.S.Raymond, http://www.tuxedo.org/~esr/writings/cathedral bazaar/cathedral-bazaar/," 2003.
[3]	 T. O'Reilly, "Lessons from Open-source software development," Communications of the ACM, vol. 42, 1999.
[4]	N. E. Fenton and S. Pfleeger, Software Metrics: A Rigorous Approach. New York: Chapman & Hall, 1991.
[5]	M. Godfrey and Q. Tu, "Growth, Evolution and Structural Change in Open Source Software," presented at IWPSE, Vienna Austria, 2001
[6]	. D. A. Wheeler, "More than a Gigabuck: Estimating GNU/Linux's size," 2003.
[7]	J. Paulson, G. Succi, and A. Eberlein, "An Empirical Study of Open Source and Closed-Source Software Products," IEEE Transactions of Software Engineering, vol. 30, April 2004.
[8]	T. O'Reilly, "Lessons from open source software developmet," Communications of the ACM, vol. 42, pp. 32-37, 1999.
[9]	A.Maccormack, "Red Hat and the Linux Revolution," in Harvard Business School Case: 9-600-009, 2002.
[10]	B.Boehm, "Software Engineering Economics," IEEE Transactions on Software Engineering, vol. 10, pp. 4-21, 1984.
[11]	C.L.Jones, "A Process-Integrated Approach to Defect Prevention," IBM Systems Journal, vol. 24, pp. 150-167, 1985.
[12]	L. J. Arthur, Measuring Programmer Productivity and Software Quality. New York: Wiley, 1984. 
[13]	M. M. Lehman and J. F. Ramil, "Rules and Tools for Software Evolution Planning and Management," Annals of Software Engineering, vol. 11, pp. 15-44, 2001.
[14]	] S. G. Eick, T. L. Graves, A. K. Karr, J. S. Marron, and A. Mockus, "Does Code Decay? Assessing he Evidence from Change Management Data," IEEE Transactions on Software Engineering, vol. 27, pp. 1-12, 2001.
[15]	C. F. Kemerer, "Software Complexity and Software Maintenance," Annals of Software Engineering, vol. 1, pp. 1-22, 1995.
[16]	M. M. Lehman and J. F. Ramil, "Software Evolution and Software Processes," Annals of Software Engineering, vol. 14, pp. 275-309, 2002.
[17]	K. H. Bennett, C. Knight, M. Munro, and J. Xu, "Centres of Excellence: Research Institute in Software Evolution, University of Durham," Computing and Control Engineering Journal, pp. 179-186, 2000.
[18]	E. B. Swanson and E. Dans, "System Life Expectency and the maintanance Effort: Exploring their Equilibrium," MIS Quarterly, vol. 24, pp. 277-297, 2000.
[19]	F. P. Brooks, The Mythical Man-Month: Addison Wesley, 1995.



 

