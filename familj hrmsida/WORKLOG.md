# Work Log – Familjen Almström webbplats

**Projekt:** Privat familjewebb  
**URL:** https://candid-elf-1749d5.netlify.app  
**Netlify Site ID:** `10ae9653-cf26-42a0-8c7e-28cff91880a8`  
**Supabase:** `vnxadbborwnfnenjnakm`  

---

## 2026-05-28 — Session 1–3 (sammanslagen)

### Vad som gjordes

**Infrastruktur**
- Netlify-sajt skapad och konfigurerad
- Supabase-projekt kopplat (`vnxadbborwnfnenjnakm`)
- Cloudinary konfigurerat för bilduppladdning (cloud: `dnl6r7axn`, preset: `family_porta`)

**Supabase-tabeller skapade**
| Tabell | Funktion |
|--------|----------|
| `memories` | Familjens dagboksinlägg med foton och reaktioner |
| `recipes` | Receptboken |
| `kalender` | Familjekalender |
| `wisdom` | Visdomsbanken |
| `quiz_questions` | Familje-quiz |
| `time_capsule` | Tidskapseln |
| `books` | Boktips (ny) |
| `album_photos` | Fotoalbum (ny) |
| `family_places` | Kartor/familjeplatser (ny) |

**HTML-sidor — totalt 17 st**

| Fil | Status | Kommentar |
|-----|--------|-----------|
| index.html | ✅ | Startsida |
| dagbok.html | ✅ | Familjens dagbok med Supabase + Cloudinary |
| admin.html | ✅ | Admin-panel |
| stamtavla.html | ✅ | Stamtavla |
| visdomsbanken.html | ✅ | Visdomsbanken |
| kalender.html | ✅ | Kalender |
| receptbok.html | ✅ | Receptbok |
| minnesladan.html | ✅ | Minneslådan |
| quiz.html | ✅ | Quiz |
| tidskapseln.html | ✅ | Tidskapseln |
| familjedialekten.html | ✅ | Familjens dialekt |
| familjerekord.html | ✅ | Familjerekord |
| login.html | ✅ | Inloggning via Supabase Auth |
| fotoalbum.html | ✅ NY | Bildgalleri |
| kartor.html | ✅ NY | Interaktiv karta (Leaflet.js) |
| familjetrad.html | ✅ NY | Familjeträd (SVG) |
| boktips.html | ✅ NY | Boktips |

**Nav-fix**
- Alla 17 filer har nu 15 nav-länkar: Hem, Dagbok, Foto, Stamtavla, Trädet, Visdom, Kalender, Recept, Minnen, Quiz, Kapsel, Dialekt, Rekord, Böcker, Kartor
- 10 befintliga filer fixades med `fix_nav.py` (lade till: Foto, Trädet, Böcker, Kartor)
- 4 nya sidor skapades direkt med rätt nav
- `dagbok.html` och `index.html` var redan korrekta → skip

**Netlify-deploy**
- Deploy ID: `6a17c9b9869b003430ef482d` (status: `uploading`)
- Uppladdade filer: `admin.html` ✅, `dagbok.html` ✅
- Återstår att ladda upp: 12 filer (se CHATTSAMMANFATTNING.md)
- Cachade av Netlify (behöver ej laddas upp): `boktips.html`, `familjetrad.html`, `login.html`

### Verktyg och skript skapade
- `fix_nav.py` — Fixade nav i 10 befintliga HTML-filer
- `gen_uploads3.py` — Genererade 14 st `up3_*.js` upload-skript (chunk=4000)
- `up3_adm.js` … `up3_vism.js` — Upload-skript per fil (i outputs-mappen)

### Skills skapade
| Skill | Beskrivning |
|-------|-------------|
| `netlify-chrome-deploy` | Full deploy-workflow via Chrome base64-injektion |
| `session-handover` | Strukturerade sammanfattningar för ny chatt |
| `html-nav-sync` | Synkronisera nav-länkar i alla HTML-filer |

### Lärdomar och regler
1. **Ny deploy alltid efter filändring** — SHA1 i manifestet måste stämma med faktiska filer
2. **Chunk max 4000 tecken** — Större chunks korrupteras i Chrome javascript_tool
3. **422 = SHA1-mismatch**, inte auth-fel
4. **Tab-ID:n är flyktiga** — kontrollera alltid med tabs_context_mcp i ny session
5. **Ny deploy → nya upload-skript** — scripts är hårdkodade med deploy-ID

---

## Pågående / återstår

- [ ] Ladda upp 12 återstående HTML-filer (se CHATTSAMMANFATTNING.md för detaljer)
- [ ] Verifiera deploy-state → `ready`
- [ ] Verifiera live-sajten på https://candid-elf-1749d5.netlify.app
- [ ] Testa alla 17 sidor fungerar med Supabase-auth

---

## Teknisk stack

| Komponent | Teknologi |
|-----------|-----------|
| Hosting | Netlify (static) |
| Auth + DB | Supabase (PostgreSQL + Auth) |
| Bildlagring | Cloudinary |
| Kartor | Leaflet.js |
| Typsnitt | Cormorant Garamond + Jost (Google Fonts) |
| Färgtema | Skogsgrönt `#3D5C3A` + terrakotta `#A84C2A` + kräm `#F5F0E8` |
| Familjemedlemmar | Peter 🌲, Carina 🌸, Elias 🎮, Tora ☀️, Mattias 🎷, Alva 🌺, Isak ⚡, Svea 🌼, Benke 🦌 |
