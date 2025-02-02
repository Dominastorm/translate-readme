# ترجمة الإجراء التمهيدي

## README الترجمة

-   [إنجليزي](README.md)
-   [الصينية المبسطة](README.zh-CN.md)
-   [الصينية التقليدية](README.zh-TW.md)
-   [هندي](README.hi.md)
-   [فرنسي](README.fr.md)
-   [عربى](README.ar.md)

**GitHub Action لترجمة الملف التمهيدي إلى أي لغة**

هذا إجراء GitHub يقوم تلقائيًا بترجمة الملف التمهيدي في الريبو الخاص بك إلى لغة محددة.

_A submission for the [DEV: إجراءات جيثب للمصدر المفتوح!](https://dev.to/devteam/announcing-the-github-actions-hackathon-on-dev-3ljn)هاكاثون_

## يثبت

1.  **أضف ملف سير عمل**لمشروعك (على سبيل المثال`.github/workflows/readme.yml`):

```yaml
name: Translate README

on:
  push:
    branches:
      - main
      - master
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v1
        with:
          node-version: 12.x
      # ISO Langusge Codes: https://cloud.google.com/translate/docs/languages  
      - name: Adding README - Chinese Simplified
        uses: dephraiim/translate-readme@main
        with:
          LANG: zh-CN
      - name: Adding README - Chinese Traditional
        uses: dephraiim/translate-readme@main
        with:
          LANG: zh-TW
      - name: Adding README - Hindi
        uses: dephraiim/translate-readme@main
        with:
          LANG: hi
      - name: Adding README - Arabic
        uses: dephraiim/translate-readme@main
        with:
          LANG: ar
      - name: Adding README - French
        uses: dephraiim/translate-readme@main
        with:
          LANG: fr
```

## إعدادات

### خيارات

يمكنك تكوين الإجراء بشكل أكبر باستخدام الخيارات التالية:

-   `LANG`: اللغة التي تريد ترجمة الملف التمهيدي إليها. الافتراضي هو الصينية المبسطة. (أنا غاني) يمكن العثور على اللغات المدعومة أدناه.
    (تقصير:`zh-CH`) (مطلوب:`false`)

## اللغات المعتمدة

يمكن العثور على اللغات المدعومة هنا[هتبص://كلود.جوجل.كوم/ترانسلت/دكس/لانججص](https://cloud.google.com/translate/docs/languages)

### مشاكل

يفحص[هنا](https://github.com/dephraiim/translate-readme/issues/1)للقضايا المتعلقة بهذا الإجراء.

### تطوير

الاقتراحات والمساهمات مرحب بها دائمًا!

### رخصة

[مع](./LICENSE)
