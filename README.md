# Drift & Destroy — Cloudflare Pages

## מה כלול
- `public/index.html` — קובץ המשחק המקורי שהועלה.
- `public/_headers` — כותרות HTTP בסיסיות.
- `wrangler.toml` — הגדרות Cloudflare Pages.
- `package.json` — פקודת פריסה דרך Wrangler.

## אפשרות 1: העלאה דרך Cloudflare Dashboard
1. חלץ את קובץ ה-ZIP למחשב.
2. פתח את Cloudflare Dashboard ובחר **Workers & Pages**.
3. בחר **Create application** ואז **Pages** (או פרויקט Pages חדש).
4. בחר **Direct Upload** אם האפשרות זמינה בחשבון שלך.
5. העלה את תיקיית `public` או את תוכנה, בהתאם למסך ההעלאה.
6. פרוס את האתר. קובץ הכניסה הוא `index.html`.

## אפשרות 2: פריסה דרך Wrangler
נדרשים Node.js וחשבון Cloudflare.

```bash
npm install
npx wrangler login
npm run deploy
```

אם הפרויקט כבר נוצר בשם אחר ב-Cloudflare, עדכן את `--project-name` ב-`package.json` לשם הפרויקט שלך.

## חשוב לדעת
- זו פריסה סטטית של המשחק. בקובץ המקורי לא נמצאה קריאת `fetch()` או שימוש ב-WebSocket, ולכן החבילה לא ממציאה API או שרת מולטיפלייר.
- המשחק מפנה ל-CrazyGames SDK חיצוני; מחוץ ל-CrazyGames חלק מפונקציות ה-SDK עשויות לא להיות זמינות. יש לוודא שהמשחק עובד גם במצב עצמאי.
- אין כאן סודות, מפתחות API או משתני סביבה.
