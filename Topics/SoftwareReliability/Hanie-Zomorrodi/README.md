### مهندسی نرم افزار | تمرین 2 فردی
### **موضوع**
مدل های رایج برای محاسبه قابلیت اطمینان نرم افزار
### **استاد درس**
دکتر حسن بشیری
### **دستیار استاد**
امیرحسین باباییان
### **نام دانشجو**
هانیه زمردی

## فهرست مطالب
### مقدمه
### مدل های رایج برای محاسبه قابلیت اطمینان نرم افزار
#### 1- دسته بندی لیو
##### 1-1 مدل های رده زمان شکست نمایی
##### 2-1 مدل های رده زمان شکست گاما
##### 3-1 مدل های رده شکست نامحدود
##### 4-1 مـدل هـای بیزی
#### 2- دسته بندی فام
##### 1-2 مدل های قطعی
##### 2-2 مدل های احتمالی
#### 3- دسته بندی بر اساس نوع داده های مورد نیاز
##### 1-3 مدل های تجربی
##### 2-3 مدل های تحلیلی
#### 4- دسته بندی سنتی و کلی بر اساس زمان استفاده از مدل
##### 1-4 مدل های پیش بینی قابلیت اطمینان نرم افزار
##### 2-4 مدل های تخمین قابلیت اطمینان نرم افزار
#### 5- دسته بندی بر اساس فاز چرخه ی توسعه ی نرم افزار
##### 1-5 مدل های پیش بینی در فازهای اولیه
##### 2-5 مدل های رشد قابلیت اطمینان نرم افزار
##### 3-5 مدل های مبتنی بر دامنه ی ورودی
##### 4-5 مدل های مبتنی بر معماری
##### 5-5 مدل های جعبه سیاه ترکیبی
##### 6-5 مدل های جعبه سفید ترکیبی
### نتیجه گیری
### فهرست منابع
---
## مقدمه
امروزه سیستم های نرم افزاری نقش مهمی در بسیاری از کاربرد‌های حساس و بحرانی ایفا می کنند. گاهی رخ دادن خطا در نر‌م افزار می تواند باعث ضررهای مالی و حتی در برخی موارد باعث ضررهای جانی گردد. به همین دلیل تضمین قابلیت اطمینان به عنوان یک نیازمندی کیفی از اهمیت بسزایی برخوردار است. یکی از اقدامات کلیدی در تضمین عملکرد عاری از خطای نرم‌ افزار، اندازه گیری کمی میزان قابلیت اطمینان مورد نیاز است. تاکنون مدل های متعددی برای کمی سازی قابلیت اطمینان نرم افزار ارائه شده است. هر کدام از این مدل‌ها دارای مزایا و محدودیت هایی هستند، لذا انتخاب مناسب ترین و بهترین مدل در کاربردهای مختلف اهمیت فراوانی دارد.

![](https://www.automation.com/getmedia/24bce89c-1ff2-4b31-8261-9212fe6e9e13/Reliability-news-OCt-12-2021-web.png?width=500&height=313&ext=.png)

## مدل های رایج برای محاسبه قابلیت اطمینان نرم افزار
تا کنون مدل های زیادی جهت کمی کردن و اندازه گیری قابلیت اطمینان نرم افزار معرفی شده است. هر یک از آن ها ویژگی های خاص خود را داشته و برای مراحل مشخصی از چرخه تولید نرم افزار طراحی شده اند. بر اساس استاندارد IEEE 729 که در سال 1991 ارائه شد، قابلیت اطمینان نرم افزار عبارت است از احتمال بدون شکست بودن عملکرد سیستم برای یک بازدهی زمانی معین و در یک محیط معین.
معیارهای متفاوتی برای پیش بینی و یا تخمین قابلیت اطمینان یک نرم افزار وجود دارد. در فازهای اولیه چرخه حیات نرم افزار، مدل هایی که برای پیش بینی قابلیت اطمینان آن مورد استفاده قرار می گیرند از معیارهایی مثل کاربرد نرم افـزار، محیط توسعه و ویژگی های نرم افزار بهره می برند. در حالیکه برای مدل هایی که در فازهای نهایی چرخه تولید و توسعه نرم افزار اعمال می شوند، از داده های شکست و اشکالات باقی مانده در نرم افزار برای محاسبه قابلیت اطمینان استفاده می کنند.
این مدل های اندازه گیری تا کنون از جهات مختلفی بررسی و دسته بندی شده اند. ما در ادامه به شرح برخی از پرکاردترین مدل های اندازه گیری قابلیت اطمینان پرداخته ایم.
### 1- دسته بندی لیو
این دسته بندی خود شامل چندین مدل مختلف می باشد که به شرح زیر هستند:
مدل های رده زمان شکست نمایی، مدل های رده زمان شکست گاما و ویبول، مدل های شکست نامحدود، مدل های بیزی.
#### 1-1 مدل های رده زمان شکست نمایی
این مدل جزء مهم ترین مدل ها است که مقـالات و پژوهش های بسیاری در مورد آن نوشته شده است. معروف ترین مدل های موجـود در این دسته، مدل جِی ام 10، مدل فرآینـد نامتجـانس پواسـن، مــدل زمــان اجــرای پایــه موســا، مــدل فــوق نمــایی و مــدل اشنیدویند می باشد. در این مدل ها تابع شدت شکست به صورت نمایی است.
#### 2-1 مدل های رده زمان شکست گاما
این مدل نیز مشابه مدل قبلی است با این تفاوت که در این روش به جای توزیع نمایی از توزیع گاما استفاده می شود. توزیع گاما از اهمیت ویژه ای برخوردار است زیرا دارای انعطاف پذیری بالایی در مدل کردن شکست ها می باشد. معروف ترین مدل های موجود در این دسته عبارت هستند از مدل ویبول و مدل رشد قابلیت اطمینان S شکل.
#### 3-1 مدل های رده شکست نامحدود
از آنجا که یک نرم افزار هیچگاه بدون خطا نخواهد بود، در این مدل نیز تعداد خطاها محدود نمی باشد. به دلیل ایجاد اشکالات جدید در حین فرآیند بازیابی و تصحیح خطاها، معمولا تعداد شکست ها با گذشت زمان بیشتر شده و تابع آن در زمان بی نهایت به سمت بی نهایت میل می کند. معروف ترین مدل های موجـود در ایـن دسـته عبارتنـد از مـدل دوان14، مدل هندسی و مدل پواسن لگاریتمی.
#### 4-1 مـدل هـای بیزی
آنچه که در مدل های قبلی مشاهده کردیم، قابلیت اطمینان تنها زمانی تغییر می کرد که یک خطا رخ دهد و ضریب تاثیر این خطاها نیز یکسان در نظر گرفته می شد. در مدل بیزی چنین چیزی وجود ندارد و حتی در صورتیکه هیچ شکستی هم رخ ندهد باز هم قابلیت اطمینان تغییر کرده و افزایش می یابد. همچنین در این مدل، تاثیر خطاهای مختلف یکسان نمی باشد و ضریب این خطاها از تعدادشان بسیار مهم تر است. در این مدل، قابلیت اطمینان به صورت تابعی از تعداد اشکالات کشف شده و تعداد فرایندهای بدون شکست تعریف می شود. معروف ترین مدل این دسته، مدل رشد قابلیت اطمینان لیتل وود ورال است.
### 2- دسته بندی فام
در این نوع دسته بندی، تمامی روش های تخمین قابلیت اطمینان نرم افزار به دو دسته کلی مدل های قطعی و مدل های احتمالی طبقه بندی می شوند.
#### 1-2 مدل های قطعی
همانطور که از نام این روش پیدا است، از هیچ داده تصادفی برای اندازه گیری قابلیت اطمینان استفاده نمی شود بلکه این محاسبه با استفاده از تعداد خطاها، تعداد دستورات ماشین، عملگرها و عملوندهای برنامه و سایر داده های قطعی انجام می گیرد. معروف ترین مدل های این دسته شامل متریک های نرم افزاری هالستید، برای تخمین تعداد خطاهای نرم افزار بر اساس تعداد عملگر و عملوندها هستند و دیگری متریک پیچیدگی سایکلومتیک مک کاب است که برای تعیین کران بالا برای تعداد تست های یک برنامه اعمال می شود.
#### 2-2 مدل های احتمالی
در این روش، با استفاده از یک سری داده های احتمالی، خطاها و قابلیت اطمینان اندازه گیری می شود. مهم ترین مدل های این دسته عبارت هستند از مدل های مبتنی بر زمان بین شکست ها، مدل های شمارش تعداد شکست ها، مدل های تزریق خطا و مدل های رشد قابلیت اطمینان.
### 3- دسته بندی بر اساس نوع داده های مورد نیاز
دسته بندی بر اساس نوع داده های مورد نیاز، مدلی دیگری از روش های محاسبه قابلیت اطمینان است که خود به دو دسته اصلی زیر طبقه بندی می شود.
#### 1-3 مدل های تجربی
مدل های تجربی با ایجاد و برقراری یک سری روابط میان معیارهای قابلیت اطمینان، سعی بر استفاده از نتایج تجربی حاصل از اطلاعات گذشته دارند. این مدل نیز شامل چندین روش مختلف می باشد که عبارت هستند از مدل میراندا، مدل هالسـتید و مدل اشنایدر.
#### 2-3 مدل های تحلیلی
مدل های تحلیلی در مراحل نهایی چرخه تولید نرم افزار مانند فازهای تست و پیاده سازی مورد استفاده قرار می گیرند. در این روش، با استفاده از اطلاعات شکست نرم افزار و مدل کردن آنها و استفاده از یک سری تئوری های آماری، قابلیت اطمینان نرم افزار تخمین زده می شود. این مدل نیز خود شامل دو زیر مجموعه مدل های پویا و ایستا است.
##### 1-2-3 مدل های پویا یا مـدل هـای رشـد قابلیـت اطمینـان نرم افزار
در این مدل، با اعمال روش های تست و کشف خطاهای بیشتر، قابلیت اطمینان نرم افزار افزایش می یابد به عبارت دیگر، با پیشرفت فرایند تست، فاکتورهای شکست پروژه مانند تعداد شکست ها و زمان بین شکست ها کاهش می یابد. یعنی در این روش می توان گفت رفتار شکست نرم افزار به زمان وابسته است. همینطور با توجه به زمان نیز، مدل های پویا خود شامل دو مدل زمان گسسته و زمان پیوسته می باشند.	
##### 2-2-3 مدل های ایستا
در این نوع از مدل های قابلیت اطمینان، رفتار شکست نرم افزار برخلاف مدل های پویا می باشد یعنی مستقل از زمان عمل می کند. همنطور فرایند محاسبه قابلیت اطمینان در فازهای ابتدایی پروژه مانند فاز طراحی و کد نویسی انجام می شود. این مدل نیز خود شامل دو دسته مدل های مبتنی بر دامنه شکست و مدل های مبتنی بر دامنه داده می باشد.
### 4- دسته بندی سنتی و کلی بر اساس زمان استفاده از مدل
در این نوع دسته بندی که بر مبنای زمان کاربرد عمل می کند، مدل ها به دو دسته کلی مدل های پیش بینی قابلیت اطمینان و مدل های تخمین قابلیت اطمینان تقسیم بندی می شوند.
#### 1-4 مدل های پیش بینی قابلیت اطمینان نرم افزار
مدل پیش بینی در فازهای اولیه چرخه تولید نرم افزار مورد استفاده قرار می گیرد و از آنجا که در این مراحل اطلاعات زیادی از خرابی ها و خطاها موجود نمی باشد، با بررسی فرایند طراحی، اندازه قابلیت اطمینان نرم افزار پیش بینی می شود.
#### 2-4 مدل های تخمین قابلیت اطمینان نرم افزار
بر خلاف مدل پیش بینی، روش های تخمینی در فازهای پایانی و معمولا در فاز تست و یا اجرای نرم افزار مورد استفاده قرار می گیرند. زمانی که نرم افزار به یک سطحی از بلوغ رسیده باشد که دیگر نیاز به تغییرات جدی و اساسی نداشته باشد، با توجه به اطلاعات خرابی بدست آمده، میزان قابلیت اطمینان تخمین زده می شود. تا کنـون مـدل هـای زیادی برای این تخمین ارائه شده است.
بر اساس یک سری خصوصیات مشترک، این مدل ها را میتوان به چهار دسته ی اصلی دسته بندی کرد که عبارتند از مدل های مبتنی بر زمان بین شکست ها، مدل هـای شـمارش تعـداد شکست ها، مدل های کاشت اشکال و مدل های مبتنی بر دامنه ی ورودی. در ادامه در مورد هریک از این مدل ها توضیح مختصری به همراه نام معروف ترین آنها آورده شده است. 
##### 1-2-4 مدل های مبتنی بر زمان بین شکست ها
در این روش قابلیت اطمینان سیستم با تخمین زمان بین شکست ها اندازه گیری می شود. معروف ترین مدل های این روش عبارت هستند از مدل شیک ولورتون، مدل جلینیسکی موراندا، مدل اشکال زدایی غیر ایده آل جی او و مدل بیزین لیتلوود ورال.
##### 2-2-4 مدل های مبتنی بر شمارش تعداد شکست ها
معیار انــدازه گیری قابلیت اطمینان، تعداد اشکالات اتفـاق افتـاده در یـک بـازه ی مشـخص زمانی است. از مدل های معروف این دسته می توان به مدل های نمایی شومن، مدل فرآینـد پواسـن نامتجـانس جیول اکیوموتو، مدل زمان اجرای موسـا و مـدل زمـان اجـرای پواسن لگاریتمی موسا اشاره کرد.
### 5-	دسته بندی بر اساس فاز چرخه ی توسعه ی نرم افزار
از آنجا که از این روش برای معرفی الگوریتم انتخاب مدل اسـتفاده می شود، از اهمیت بالایی برخوردار است. در این مدل بر اساس فازی که محاسبه قابلیت اطمینان نرم افزار در آن صورت می گیرد، به 6 دسته مختلف طبقه بندی می شود.
#### 1-5 مدل های پیش بینی در فازهای اولیه
همانطور که از نام این مدل مشخص است، این دسته بندی در فازهای اولیه ی چرخـه تولید نرم افزار از جمله فازهای نیازمندی ها، طراحی و پیاده سازی قابل استفاده هستند. معروف ترین مدل های موجود در این دسته عبارت هستند از مدل های مبتنی بر فاز، مدل آزمایشگاه رم، مدل لیغرا، مجموعه داده های صنعتی و مجموعه داده های تاریخی.
#### 2-5 مدل های رشد قابلیت اطمینان نرم افزار
این دسته از مدل ها در فاز تست نرم افزار و زمانی که برنامه به یک پایداری نسبی رسیده باشد و نیاز به تغییرات اساسی نداشته باشد، قابل استفاده هستند.
#### 3-5 مدل های مبتنی بر دامنه ی ورودی
در این روش که در فاز اعتبار سنجی مورد استفاده قرار می گیرد، داده های تست به صورت تصادفی و بر اساس ورودی هایی که احتمال رخ دادن بیشتری دارند، بدست می آیند. سپس با توجه به تعداد شکست های اتفاق افتاده، قابلیت اطمینان تخمین زده می شود. از معروف ترین مدل های موجود در این روش می توان به مدل نلسون، مدل تی سوکالاس، مدل ویس و ویوکر اشاره کرد.
#### 4-5 مدل های مبتنی بر معماری
مدل های مبتنی بر معماری در فازهای طراحی، پیاده سازی و تست قابل استفاده هستند.
#### 5-5 مدل های جعبه سیاه ترکیبی
این روش از ترکیب مدل های مبتنی بر دامنه ورودی با ویژگی های مدل های رشد قابلیت اطمینان بدست می آید و در فازهای تست و اعتبار سنجی مورد استفاده قرار می گیرند. از معروف ترین مدل های موجود در این دسته می توان مدل های رشد قابلیت اطمینان مبتنی بر دامنه ی ورودی را نام برد.
#### 6-5 مدل های جعبه سفید ترکیبی
این دسته نیز از ترکیب ویژگی های مدل های جعبه سیاه و جعبه سفید حاصل می شود. همچنین برای پیش بینی قابلیت اطمینان نرم افزار، ویژگی های معماری نرم افزار نیز در نظر گرفته می شوند و نهایتا در فاز تست مورد استفاده قرار می گیرند. از معروف ترین مدل موجود در این دسته به مدل مبتنی بر زمان برای تخمین قابلیت اطمینان می توان اشاره کرد.
## نتیجه گیری
در حال حاضر نرم افزار به عنوان یکی از اصلی تـرین بخـش های یک سیستم محسوب می شود و یکی از کلیدی ترین نقش هـا را در سیستم ایفا می کند به طوریکـه ایـن نقـش روز بـه روز در حالا پررنگ شدن می باشد. قابلیت اطمینان نرم افزار یکی از فاکتورهای مهم در تعیین کیفیت نرم افزار محسوب می شود. تا کنون مدل های زیادی جهت کمی کـردن و انـدازه گیری این فاکتور مهم و حیاتی معرفی شده است. اکثر این مدل ها پیچیده بوده و بیشتر در محیط های آکادمیک و آزمایشگاهی مورد استفاده قرار می گیرند.
ما در این مقاله به طور مختصر به شرح 5 مورد از این مدل های قابلیت اطمینان نرم افزار پرداختیم.
## فهرست منابع
- [https://magirans.com/دانلود-مقاله-روشهای-اندازهگیری-قابل.htm]
- [https://ymol.ru/fa/wi-fi/raschet-nadezhnosti-apparatno-programmnogo-obespecheniya-nad-zhnost-programmnogo-obespecheniya-uproshchenna/]
