# حفاظت ضد Brute Force
<!-- position: 2 -->

## حمله Brute Force چیست؟

حمله‌ای است که در آن تمام حالات ممکن تا رسیدن به جواب بررسی می‌گردد - [ویکیپدیا](https://fa.wikipedia.org/wiki/%D8%AD%D9%85%D9%84%D9%87_%D8%AC%D8%B3%D8%AA%D8%AC%D9%88%DB%8C_%D9%81%D8%B1%D8%A7%DA%AF%DB%8C%D8%B1)

## چطور کار میکند؟
بلودیت برای کاهش این نوع حملات یک سیستم حفاظت ضد Brute Force را ارائه می کند که بطور پیش فرض فعال است.

برای هر شکست در ورود به سیستم، بلودیت آدرس IP شخصی که موفق به تائید هویت نشده را در لیست سیاه قرار می‌دهد. هنگامی که کاربر چندین بار تلاشش برای ورود به سیستم با شکست مواجه شد، بلودیت این آدرس IP را برای یک دوره زمانی خاصی مسدود کرده و اجازه نمی‌دهد کاربر وارد سیستم شده تا زمانی که این حالت مسدودیت منقضی شود.

## Class و Object
یک `Security Object` به نام `$security` وجود دارد و class این object  `/bl-kernel/security.class.php` می باشد نگاهی به متغییر درون این کلاس بیاندازید.

<pre><code data-language="php">
private $dbFields = array(
    'minutesBlocked'=>5,
    'numberFailuresAllowed'=>10,
    'blackList'=>array()
);
</code></pre>

- `minutesBlocked`: مدت زمان به دقیقه که این آدرس IP مسدود خواهد شد.
- `numberFailuresAllowed`: تعداد دفعات تلاش های ناموفق تا اینکه مسدود کننده فعال شود.
- `blackList`: لیست سیاه IP های مسدود شده.

<div class="note">
<div class="title">توجه</div>
شما می توانید این مقادیر را به دلخواه خود تغییر دهید
</div>
