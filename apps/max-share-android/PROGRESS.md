# سجل التقدم — Max Share Android

**آخر تحديث:** 2026-10-13
**المستودع:** https://github.com/sultansy1221/waredvvv-gmail.com
**مسار التطبيق:** apps/max-share-android
**الطلب:** إنتاج APK جديد مستقر ومناسب لأحدث إصدار Android مستقر.

## ما أُنجز

- تم توصيل GitHub وتحديد مستودع المصدر؛ المستودع Max-Share-Android-app فارغ، وsharing-app-reorganization يحتوي APK وملفات مصدر ZIP فقط.
- تمت مراجعة README.md وBUILD_REPORT.md وGradle وManifest وMainActivity وسجل Actions.
- تأكدت صفحة Android الرسمية أن Android 16/API 36 هو المستقر، بينما Android 17 ما زال Beta؛ يبدأ فرض صلاحية الشبكة المحلية عند استهداف API 37.
- تأكدت من أن MainActivity لم يكن يعالج insets، وأن workflow السابق متداخل تحت مجلد التطبيق ويستخدم مسار بناء قديماً.
- بيئة المحادثة لا تحتوي Java أو Gradle أو Android SDK؛ لذلك سيُستخدم GitHub Actions للبناء.
- تم حفظ خطة العمل في commit سابق.

## التغيير الجاري

- إصدار التطبيق 2.3.1 / versionCode 24؛ compileSdk وtargetSdk على API 36، مع إبقاء minSdk 26.
- AGP 8.13.2 وGradle 8.13 وKotlin 2.3.20 على JDK 17.
- إضافة معالجة حواف system bars ولوحة المفاتيح في MainActivity قبل تفعيل targetSdk 36.
- إنشاء workflow جذري يبني debug APK ويشغّل Android Lint ويرفع APK كـ artifact؛ إزالة workflow القديم غير النشط.

## الخطوات التالية

1. انتظار تشغيل GitHub Actions لهذا التغيير.
2. إذا فشل البناء أو Lint، إصلاح السبب وإعادة التشغيل.
3. عند النجاح، تسجيل رابط run/artifact وحجم APK وSHA-256 في BUILD_REPORT.md.
4. توضيح أن APK بتوقيع debug؛ لا يوجد مفتاح توقيع إصدار ولا اختبار جهاز Android فعلي متاح حتى الآن.

## حدود النطاق

لم أرفع targetSdk إلى 37؛ يتطلب Android 17 تدفقاً مناسباً لصلاحية الشبكة المحلية، لذا يلزم اختبار مستقل قبل اعتماده. لا يوجد مفتاح توقيع المطوّر الأصلي في المستودع.

**الحالة:** تغييرات التطبيق وسير البناء قيد التنفيذ؛ APK لم يُبنَ بعد.
