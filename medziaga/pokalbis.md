# Pokalbis: „4 причины, почему ИИ не умеет в трейдинг“

*2026-09-29 – 2026-09-30*

---

## Vartotojas

*(Pridėtas PDF: Romano Zifo brošiūra „4 причины, почему ИИ не умеет в трейдинг“, 15 psl.)*

## Claude

Это брошюра Романа Зифа о том, почему ChatGPT и другие языковые модели не дают готового торгового преимущества. Раз вы принесли её мне, ИИ, отвечу честно.

**С чем я согласен.** Главная мысль верна: если спросить у меня «лучшую стратегию», я скорее всего выдам самые популярные идеи. Это пересечение средних, RSI, пробой с ретестом, стоп за уровнем, 1:3. Всё это действительно отражает то, о чём чаще всего пишут. Преимущества в таком наборе нет по определению. Сильные разделы брошюры — про статистику («не верьте формулировке, считайте»), про длину убыточных серий и про то, что стратегия должна подходить человеку. Пример с тремя месяцами стопов очень точный: многие системы ломаются не на рынке, а на исполнителе. Чек-лист из 12 вопросов полезен к любой стратегии, не только к предложенной ИИ.

**Где я бы поспорил.**

- **Маркет-мейкер.** Его экономика изложена сильно упрощённо. На спотовом форексе ликвидность раздроблена между многими поставщиками. «Охота за стопами» как объяснение каждого выбивания удобна, но её трудно проверить: легко увидеть задним числом и сложно доказать статистически.
- **Невидимые стопы.** Выход по ситуации — здравая идея. Но есть реальные риски: гэпы, обрыв связи, сбой робота. Кроме того, «мысленный» стоп у живого человека легко превращается в отсутствие стопа. Об этом в брошюре почти не сказано.
- **Почему популярные стратегии теряют.** Чаще причина не в стопах за уровнем, а просто в отсутствии статистического перевеса плюс спреды и комиссии.
- **Что ИИ «не умеет».** В чем-то брошюра себе противоречит. Сама же предлагает считать статистику ситуаций, а это как раз то, где ИИ полезен: написать бэктест, посчитать просадки и длину серий, проверить формулировку на данных. Слабость не в инструменте, а в вопросе «дай лучшую стратегию» вместо «проверь мою гипотезу».

Стоит помнить и о жанре: это лид-магнит, цель которого — подписка. Поэтому тезисы подаются уверенно, но без цифр. Хотя сама брошюра требует цифр от стратегий.

Что вы хотите с этим сделать? Могу сделать краткий конспект, разобрать какой-то тезис подробнее или пройтись этим чек-листом по вашей конкретной стратегии. Сразу оговорюсь: я не финансовый консультант, так что это будет разбор логики, а не рекомендация торговать.

---

## Vartotojas

Kaip panaudoti šią informaciją? Pats suformuluok hipotezę ir pats ją išnagrinėk? Rask kliutis sėkmingam tradingui ir rask būdus, kaip tas kliutis apeiti ir gauti ilgalaikį teigiamą rezultatą.

## Claude

Gerai, pabandysiu tai, ką siūlo pati brošiūra: ne „duoti strategiją“, o suformuluoti patikrinamą hipotezę ir parodyti, kaip ją patikrinti. Iš karto pasakysiu svarbiausią dalyką: be tikrų istorinių duomenų aš negaliu jums pasakyti, ar hipotezė veikia. Jei tvirtinčiau kitaip, būtų lygiai tas pats „įtikinamas atsakymas be skaičių“, prieš kurį perspėja Zifas.

### Hipotezė

Remiuosi brošiūros idėja apie likvidumą už akivaizdžių lygių.

**Formuluotė.** Kai kaina pramuša ankstesnės N dienų minimumą (ten, kur susitelkę stopai), bet per 1–2 barus grįžta virš jo, pirkimas sugrįžimo momentu duoda teigiamą matematinę lūkestį, įskaičiavus sąnaudas.

**Priešinga (nulinė) hipotezė.** Tokie „netikri pramušimai“ nėra geresni už atsitiktinį įėjimą su ta pačia išėjimo logika.

### Kaip ją išnagrinėčiau

1. **Duomenys.** EURUSD, GBPUSD, XAUUSD ir vienas indeksas, H1, bent 10 metų. Keli instrumentai todėl, kad efektas, veikiantis tik viename, greičiausiai yra atsitiktinumas.
2. **Tikslios taisyklės iš anksto.** Kas yra „lygis“ (pvz., 20 barų minimumas), kas yra „pramušimas“ (kiek punktų), kas yra „grįžimas“ (uždarymas virš lygio). Išėjimas pagal situaciją, kaip siūlo brošiūra: jei per X barų nėra impulso, išeinama. Plius avarinis stopas už pramušimo ekstremumo.
3. **Sąnaudos.** Realus spredas, komisija, svopai, praslydimas. Daugelis „veikiančių“ strategijų miršta būtent čia.
4. **Palyginimas su atsitiktiniu įėjimu.** Tie patys išėjimai, tik įėjimas atsitiktiniu laiku. Pranašumas yra tik skirtumas tarp šių dviejų rezultatų.
5. **Padalijimas.** Pirmi 7 metai skirti idėjai derinti, paskutiniai 3 metai – vieną kartą patikrinti. Jokio derinimo po to.
6. **Tai, ko reikalauja brošiūros kontrolinis sąrašas:**
   - sandorių skaičius (bent kelios šimtinės);
   - pelningų dalis ir vidutinis R;
   - kiek kaina eina prieš poziciją (MAE);
   - ilgiausia nuostolių serija;
   - Monte Karlo simuliacija: kokia realistiška blogiausia serija ir nuosmukis.

Jei po sąnaudų lūkestis artimas nuliui arba efektas yra tik viename instrumente, hipotezė atmetama. Toks rezultatas yra normalus ir vertingas: jis sutaupo pinigų.

### Kliūtys ir kaip jas apeiti

- **Nėra pranašumo.** Dauguma strategijų, ne tik ChatGPT pasiūlytos, po sąnaudų neduoda nieko. Reguliuotojų reikalaujami atskleidimai rodo, kad maždaug 70–80 % mažmeninių CFD sąskaitų praranda pinigus.
  → Tikrinti hipotezes su duomenimis ir palyginti su atsitiktiniu įėjimu.
- **Sąnaudos.**
  → Rečiau prekiauti, siekti didesnių judesių santykiu su spredu, rinktis pigų brokerį ir likvidžius instrumentus.
- **Persimokymas (overfitting).** Daug parametrų plius daug bandymų garantuoja gražų, bet netikrą testą.
  → Mažai parametrų, out-of-sample ir walk-forward testai, keli rinkos instrumentai. Užsirašyti, kiek variantų išbandyta.
- **Pranašumas išnyksta.** Rinka keičiasi.
  → Iš anksto nustatyti sustabdymo kriterijų. Pavyzdžiui: jei gyva serija viršija 1,5 karto blogiausią testuotą, strategija stabdoma ir peržiūrima.
- **Bankroto rizika.**
  → Rizikuoti 0,5–1 % sąskaitos sandoriui. Dydį skaičiuoti pagal Monte Karlo blogiausią nuosmukį, o ne pagal vidurkį.
- **Psichologija.** Tai brošiūros 4-oji priežastis.
  → Automatizuoti vykdymą (EA). Dydį rinktis tokį, kad nuosmukis būtų pakeliamas. Iš anksto užrašyti, ką darysite po 5-ojo stopo. Vesti žurnalą: kur nukrypote nuo taisyklių.
- **Vykdymas.** Praslydimas, ryšio sutrikimai ir „nematomi stopai“, kai robotas neveikia.
  → Visada palikti avarinį stopą serveryje, net jei pagrindinis išėjimas yra situacinis.

### Sąžininga pastaba

Net gerai atliktas tyrimas dažniausiai baigiasi išvada „pranašumo nėra“. Tai ne nesėkmė, o metodo esmė. Daugumai žmonių patikimiausias ilgalaikis teigiamas rezultatas vis dar yra pigus, diversifikuotas ilgalaikis investavimas. Aktyvi prekyba verta tik tada, kai skaičiai patvirtina pranašumą. Tai ne finansinė rekomendacija, o metodologija.

**Konkretus kitas žingsnis.** Jei eksportuosite istorinius duomenis iš MT5 (CSV, pvz., EURUSD H1, kuo daugiau metų) ir atsiųsite čia, aš realiai paleisiu šį testą. Grąžinsiu skaičius: lūkestį po sąnaudų, palyginimą su atsitiktiniu įėjimu, blogiausią seriją ir Monte Karlo nuosmukį. Tada matysime, ar hipotezė gyva.

---

## Vartotojas

Create a Word document from your last answer.

## Claude

Here's the Word document, **Prekybos_hipoteze.docx** (2 pages, in Lithuanian). It has everything from my last answer: the hypothesis, how to test it, the obstacles and how to get around them, the honest caveat, and the next step. I only changed the closing line from "send me the data" to a neutral "next step," so the document reads as a standalone piece.

---

## Vartotojas

išsaugok pokalbį .md faile
