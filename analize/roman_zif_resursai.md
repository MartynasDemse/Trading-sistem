# Romanas Zifas (ProFXPortal): ką iš tikrųjų verta pasiimti

*Peržiūra: 2026-09-30*

## Šaltiniai ir apribojimai

Peržiūrėti resursai:

- Facebook [zifpamm](https://www.facebook.com/zifpamm/)
- Instagram [algo.invest.expert](https://www.instagram.com/algo.invest.expert/)
- YouTube [@proFXportal](https://www.youtube.com/@proFXportal)
- Telegram [profxtrade](https://t.me/profxtrade)

**Svarbu:** tiesiogiai atidaryti šių puslapių nepavyko, nes juos blokavo aplinkos tinklo filtras. Užblokuoti buvo ir Telegram archyvai (telemetr), smart-lab, vc.ru, cartel.market ir profxportal.com. Todėl išvados remiasi:

1. visa brošiūra „4 причины, почему ИИ не умеет в трейдинг“ (15 psl.);
2. paieškos sistemų ištraukomis iš jo Telegram, YouTube, vc.ru ir smart-lab įrašų.

Konkrečių vaizdo įrašų turinio neperžiūrėjau. Kur tvirtinimas paremtas tik paieškos ištrauka, tai pažymėta.

## Kas jis ir ką parduoda

- Pagal išsilavinimą teisininkas, anksčiau dirbo interneto rinkodaroje. Forex rinkoje nuo 2012 m. (pradėjo nuo PAMM investavimo), su robotais dirba nuo 2014 m.
- Kuria MT4/MT5 robotus: *Project Manhattan* (2015 m.), *Fly Dynamic*, *Forex-Fibo* ir kt.
- Parduoda mokymus (profxportal.com/school), knygas („Профессия Трейдер“). Yra klubo „Картель“ mentorius ir Gerchik & Co pranešėjas.
- Brošiūra yra piltuvėlio (funnel) pradžia: pabaigoje kviečia prenumeruoti ir žada „papildomus laiškus“.

**Esminis faktas.** Jo pagrindiniai robotai yra **vidurkinimo (grid) sistemos**. Paieškos ištraukos apie *Fly Dynamic*: „стратегия — усреднение“. v2 versijoje vidurkinimo orderių lotas didinamas pagal Fibonačio seką. Yra „antisliv“ sistema: pasiekus nustatytą nuosmukį atidaroma užrakinimo (lock) pozicija ir prekyba sustabdoma. Robotui reikia ne mažesnio kaip 1:100 sverto. Tai iš esmės martingeilo giminaitis.

## Ką verta pasiimti (ir kaip pritaikyti)

### 1. Kontrolinis sąrašas ir „statistika vietoj formuluotės“

Stipriausia brošiūros dalis, jau įtraukta į [mūsų hipotezės metodiką](../medziaga/Prekybos_hipoteze.docx). Klausimai, kuriuos verta laikyti kiekvienos idėjos pradžioje:

- Kiek kartų situacija pasikartojo? Kiek kartų suveikė?
- Kiek kaina nuėjo prieš poziciją (MAE)? Kiek laiko teko laukti?
- Kokia buvo blogiausia nuostolių serija ir ar ją ištverčiau nekeisdamas taisyklių?
- Ką darysiu po 5-ojo stopo iš eilės?

### 2. Išėjimas pagal sugriautą scenarijų, o ne pagal liniją

Pirmiausia nusakyti, **koks įvykis paneigia sandorį**: laikas be impulso, judėjimo prieš mus greitis, sąlygų išnykimas. Tik tada spręsti, kur išeiti. Tai lengva koduoti EA ir testuoti.

**Mūsų pataisa:** avarinis stopas serveryje lieka visada. „Nematomas“ stopas taikomas tik kaip pagrindinis, o ne vienintelis išėjimas.

### 3. Strategijos ir žmogaus suderinamumas

Prieš testą užrašyti savo ribas: sandorių dažnį, maksimalią serijos ilgį, kurią tikrai ištversiu, kiek laiko galiu laikyti poziciją, kada esu prie terminalo. Strategija, kuri šių ribų neatitinka, atmetama net jei testas geras.

### 4. Svopai gali suvalgyti didelę pelno dalį

Paieškos ištrauka iš jo Telegram: grid roboto pelnas prieš svopus buvo **$9 774,99**, svopai **−$2 768,11**, t. y. **~28 % pelno**. Jis pats pripažino, kad tai neįvertino.

**Pritaikymas:** į kiekvieną bandymą įtraukti realius svopus pagal brokerį ir instrumentą. Atskirai matuoti vidutinę laikymo trukmę. Kuo ilgiau laikoma, tuo svarbiau.

### 5. Tas pats robotas skirtinguose brokeriuose duoda skirtingą rezultatą

Paieškos ištrauka: šešios sąskaitos su tuo pačiu robotu (skirtingi brokeriai, depozitai, rizika) davė nuo **+0,25 % iki +9,82 %** per mėnesį, o maksimalus nuosmukis svyravo nuo **0,38 % iki 7,80 %**.

**Pritaikymas:** prieš gyvą prekybą paleisti strategiją 2–3 brokerių demo arba mažose sąskaitose ir palyginti vykdymą: spredą, praslydimą, svopus.

### 6. Nepriklausomas monitoringas kaip standartas

Jis pats remiasi myfxbook / mql5 signalais. Tai teisingas reikalavimas **visiems**, taip pat ir jam.

**Pritaikymas:** savo gyvą sąskaitą iš karto prijungti prie myfxbook. Tai bus mūsų žurnalas ir įrodymas sau.

### 7. DI kaip įrankis kodui ir testams, ne orakulas

Paieškos ištrauka: jo vaizdo įrašuose robotai kuriami su ChatGPT ir Claude, o rezultatai tikrinami optimizacija ir out-of-sample testu. Tai sutampa su mūsų keliu: DI rašo EA ir bandymų kodą, o sprendžia skaičiai.

## Ko **nepasiimti**, ir raudonos vėliavos

| Tema | Kodėl atsargiai |
|---|---|
| **Grid / vidurkinimas su didėjančiu lotu** | Aukštas laimėjimų procentas ir lygi balanso kreivė, bet reta katastrofiška rizika. Tai yra blogiausias brošiūros 4-osios priežasties atvejis: ilga ramybė, po to vienas įvykis panaikina metus pelno. Kritiniai scenarijai: CHF 2015 m., ilgos kryptingos tendencijos (pvz., JPY 2022 m.). |
| **„Antisliv“ užrakinimas** | Lokas nuostolio nepanaikina, tik jį užšaldo. Užrakinta pozicija toliau moka svopus, o ją atrakinti vėliau reikia rankiniu sprendimu. Nuosmukis realiai jau įvykęs. |
| **Mėnesio % ir mažas „max DD“** | Grid sistemose žiūrėti **equity** (su plaukiojančiu nuostoliu), o ne **balance** nuosmukį. Taip pat sąskaitos amžių (bent 2–3 metai) ir tai, ar sąskaita nebuvo „perkrauta“ po nuostolio. |
| **„Viena nuostata padidina pelningumą 3 kartus“** | Tai jo paties straipsnio antraštė (vc.ru / smart-lab). Didelis jautrumas vienam parametrui (tarpui tarp orderių) reiškia rizikos didinimą, o ne pranašumą. Pelningumas ir bankroto tikimybė auga kartu. |
| **„Turiu $100, ar galima išpūsti depozitą?“** | Rinkodaros formatas (jo vc.ru straipsnio pavadinimas). Nesuderinama su 0,5–1 % rizika sandoriui. |
| **Market-maker „stopų medžioklė“** | Įdomi interpretacija, bet nepatikrinama. Mums naudinga tik kaip patikrinama hipotezė (netikrų pramušimų testas), ne kaip tiesa. |
| **Prieštaravimas** | Brošiūra kritikuoja „standartinį stopą už lygio“, bet jo pagrindiniai produktai dažnai prekiauja be stopo, su vidurkinimu. Tai griežtesnė rizika, ne mažesnė. |
| **Verslo modelis** | Pajamos iš mokymų, klubų ir robotų pardavimo. Tai nereiškia, kad jis nesąžiningas, tačiau skatina rodyti gerus rezultatus ir slėpti blogus. Internete yra ir kritinių atsiliepimų (pvz., kad nerodoma sandorių statistika). Jų nepatikrinau, todėl vertinu neutraliai. |

## Konkretūs veiksmai mūsų sistemai

1. **Papildyti testų protokolą** (hipotezė H1, netikri pramušimai):
   - svopai pagal brokerį + laikymo trukmė;
   - equity nuosmukis, ne tik balanso;
   - parametrų jautrumo testas: rezultatas turi laikytis „plato“, o ne vieno taško;
   - 2–3 brokerių vykdymo palyginimas prieš gyvą prekybą.
2. **Asmeninis profilis prieš bet kokį testą:** vienas puslapis su suderinamumo klausimais iš brošiūros 13 psl.
3. **Jei kada svarstytume jo (ar bet kurį kitą) grid robotą:**
   - reikalauti myfxbook su equity DD, sąskaitos amžiumi > 2 m. ir patikrinta prekybos istorija;
   - patiems testuoti MT5 testeryje su „every tick based on real ticks“ ir realiais svopais;
   - stresinis testas 2008, 2015 (CHF), 2020 ir 2022 m. periodais;
   - Monte Karlo / bankroto tikimybės vertinimas, o ne vidutinis mėnesio %;
   - maksimali suma tokiam robotui: tik ta, kurią galima prarasti 100 %.
4. **Myfxbook** prijungti prie mūsų pačių gyvos sąskaitos nuo pirmos dienos.

## Išvada vienu sakiniu

Jo **metodologiniai klausimai** (statistika, išėjimas pagal scenarijų, strategijos ir žmogaus suderinamumas, svopai, vykdymo skirtumai tarp brokerių) yra vertingi ir tiesiogiai pritaikomi. Jo **produktai** (vidurkinimo robotai su didėjančiu lotu) yra būtent tokio tipo rizika, kurią mūsų metodika turi pagauti, o ne kopijuoti.

*Tai ne finansinė rekomendacija, o šaltinių analizė.*

## Šaltiniai (paieškos rezultatai)

- [Роман Зиф — Канал Трейдера (Telegram)](https://t.me/s/proFXtrade)
- [Роман Зиф — Трейдинг роботами (YouTube)](https://www.youtube.com/channel/UC_PxqobhQ3tDO7bA82P3e8Q)
- [Блог Трейдера — Роман Зиф (Facebook)](https://www.facebook.com/zifpamm/)
- [Есть 100$. Можно ли разогнать депозит роботом Fly Dynamic (vc.ru)](https://vc.ru/id1480019/1614885-est-100-mozhno-li-razognat-depozit-robotom-fly-dynamic)
- [Как всего одна настройка повышает доходность форекс робота в 3 раза (vc.ru)](https://vc.ru/id1480019/1852632-kak-vsego-odna-nastroika-povyshaet-dohodnost-foreks-robota-v-3-raza)
- [Фибоначчи в торговом роботе Forex-Fibo (smart-lab)](https://smart-lab.ru/blog/1040165.php)
- [Интервью с Романом Зифом (cartel.market)](https://cartel.market/ru/blog/intervyu-s-romanom-zifom/)
- [Роман Зиф (investcourses.ru)](https://investcourses.ru/author-roman-zif/)
- [Роман Зиф отзывы (cryptorussia.ru)](https://cryptorussia.ru/roman-zif-otzyvy)
- [Роман Зиф отзывы (profxportal forum)](https://profxportal.com/forum/threads/roman-zif-otzyvy.728/)
