# Enterprise Employee Data Journey v8

نسخة v8 تعيد بناء تجربة الموظف بالكامل كمسار مؤسسي واضح بدل نموذج تقليدي.

## أهم التغييرات

- Dashboard افتتاحية قبل الدخول للنموذج.
- Timeline احترافي بحالات Completed / Current / Pending.
- Identity Header ثابت بعد التعرف على الموظف.
- Smart Section Cards لكل قسم مع وصف وتنبيهات.
- Live Validation لكل حقل.
- Auto Save كل 5 ثواني بعد التعرف على الموظف.
- Resume Later من المسودة المحلية.
- Missing Information Scanner.
- Search Inside Form.
- Change Detection System يظهر للموظف وللإدارة.
- Professional final review بصيغة قريبة من أنظمة Enterprise.
- Admin Dashboard داكن وموسع مع KPIs و Completion chart و Missing Fields Heatmap و Audit Center.
- تصميم responsive للموبايل والتابلت واللابتوب بدون 100vh أو overflow clipping في تجربة الموظف.

## الرفع على GitHub

ارفع كل الملفات الموجودة في هذا المجلد، وليس index.html فقط، لأن favicon والـ apple-touch-icon مطلوبان.

## الخصوصية

لا ترفع ملفات employee seed أو ملفات Excel الأصلية إلى GitHub العام.


## v8.1 Admin Accessibility and Login Fix

- Fixed the admin modal accessibility warning caused by opening the dashboard while `aria-hidden="true"` was still applied.
- Added `inert` to the employee application while the admin dashboard is open.
- Added safer focus handling when opening and closing the admin dashboard.
- Improved admin login validation and error messaging for invalid Firebase credentials.

Note: `auth/invalid-credential` is not a layout bug. It means the email/password entered does not match an existing Firebase Authentication user, Email/Password sign-in is not enabled, or the password is incorrect.


## v8.2 Stability Fix

- Fixed Arabic **ابدأ التحقق** button not responding due to decorative overlay intercepting clicks in RTL layout.
- Added delegated event binding for the start-verification action.
- Prevented decorative pseudo-elements from capturing pointer events.
- Preserved Firebase configuration, admin flow, validation rules, and export logic.
