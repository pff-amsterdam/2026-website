<script setup lang="ts">
import { BImg, BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref, computed } from 'vue'; 
import ProgramItem from '../components/ProgramItem.vue'
const background = new URL('../assets/sat_background.png', import.meta.url).href

// Set default language
const currentLang = ref<'en' | 'nl'>('en');

// Toggle function
const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: {
    day: "Saturday",
    date: "28 February 2026"
  },
  nl: {
    day: "Zaterdag",
    date: "28 Februari 2026"
  }
};

const agenda = [
{
  "id": 1,
  "image": new URL('../assets/sat1.png', import.meta.url).href,
  "title": "CONSTRUCTION SITE",
  "time": "12:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Stuff. Tools, machines, household items, makeshift devices. Things picked up, repurposed, misused, obsessed over. Bodies meeting materials. Flesh meeting function. Pleasure being engineered, improvised, assembled piece by piece. These films play in the space where practicality turns perverse, where work becomes ritual, where control is negotiated through grips, surfaces, pressure and weight. A construction site is messy, noisy, unfinished. So is desire. Here, nothing arrives fully formed. Everything is in process.",
    "nl": "Spullen: gereedschap, machines, huishoudproducten, geïmproviseerde apparaten. Je raapt iets op, geeft er een nieuwe draai aan, gebruikt het helemaal verkeerd. Lievelingsdingen. Belichaamd materiaal. Lichamelijke functies. In deze films wordt genot eerst geschetst, uitgetekend en dan stuk voor stuk in elkaar geschroefd. Op dit terrein raakt functionaliteit geperverteerd en wordt werk een ritueel. Hier wordt toezicht gehouden met grip, oppervlakte, druk en gewicht. Een bouwplaats is vuil, luid, onaf. Verlangen ook. Niets wordt hier kant-en-klaar afgeleverd. Alles is in ontwikkeling."
  },
  "description": `<p>
    <strong>Sexy Plumber</strong> | maja m tekla | 2025 | Poland | 2’
    <br/>
    <strong>Chulicha</strong> | Sonia Patrinou | 2025 | Greece | 15’
    <br/>
    <strong>The Fixit Ape: TV Troubles</strong> | Monsterbait & Xavours | 2025 | France | 16’
    <br/>
    <strong>Dyson</strong> | Clac & Fara Renaud | 2025 | Belgium | 15’
    <br/>
    <strong>Mon Meilleur Poto</strong> | Marmone Bando | 2024 | Belgium | 4’
    <br/>
    <strong>Venus 2000</strong> | Jan Soldat | 2025 | Germany | 10’
    <br/>
    <strong>Metal Whoreshop</strong> | Nova Luv | 2025 | France | 10’
    <br/>
    <strong>Solidarity with the Garbage Workers on Strike</strong> | Lasse Långström & The homosex syndicate of precarious avant-garde artists | 2025 | Germany, Sweden | 4’
    <br/>
    <strong>OBJET #001</strong> | Petra Von Schatz | 2024 | France | 2’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 78 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 78 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20906"
},
{
  "id": 2,
  "image": new URL('../assets/sat2.png', import.meta.url).href,
  "title": "HOLY SHIT – PERFORMANCE,FILMS AND TALK",
  "time": "13:00",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Let’s admit that we all quiver with joy while defecating. Fecal matter is a bodily arousal, not a disgust. In this block, we reflect on scatology and the use of feces in various sexual acts.<br/><br/><strong><u>Performance:</u></strong> Baby one more time by Nor Okelei<br/><br/>An ongoing performance of becoming apart from one’s mother by way of costume operations. In this iteration, the unborn awaits its first bowel movement.<br/><br/><strong>Nor Okelei</strong> is an Amsterdam–based artist and researcher, also known as Brooms Tic, a member of the House of Løstbois, headquartered at the fetish Club Church.<br/><br/><strong><u>Talk:</u></strong> We Always Go Back to Our First Loves: Notes Toward a Theory of Scat by Diego Semerene<br/><br/>“Shit” is often one of the first words we utter, along with “mother.” At the age of three the child is willing to put any partial object in the mouth: shit, snot, mud. The unconscious itself can be seen as a kind of chamber pot for our shit –for rejected matter. While shit is one of the human subject’s earliest loves it becomes one of the most crucial cudgels for disciplining the child. We quickly learn to reject shit as an object of pleasure. But there is nothing natural about this rejection, which is often sustained in adult life even in the most supposedly kink-friendly of spaces, where scat is said to be one’s limit, or the limit. This talk accepts scat as a creative solution, not a pathological symptom, and provides some notes aimed at opening up the erotic and psychoanalytic possibilities of shit.<br/><br/><strong>Diego Semerene</strong> is an assistant Professor of Queer and Transgender Media at the University of Amsterdam, co-founder of the Queer Analysis Research Group at the Amsterdam School of Cultural Analysis (ASCA) and of the (Trans–)Sexualities + Psychoanalysis Summer School.",
    "nl": "Laten we toegeven dat we allemaal sidderen van genot tijdens de stoelgang. Ontlasting is geen gruwel maar een lichamelijke sensatie. In dit blok staan we stil bij scatologie en het gebruik van uitwerpselen in verschillende seksuele uitingen.<br/><br/><strong><u>Performance:</u></strong> Baby one more time | Nor Okelei | 5’<br/><br/>Een performance in wording over het loskomen van je moeder door middel van kostuumoperaties. In deze vertolking wacht een ongeborene op het in beweging komen van de darmen.<br/><br/><strong>Nor Okelei</strong> is als kunstenaar en onderzoeker gevestigd in Amsterdam en gaat ook onder de naam Brooms Tic, lid van het Huis van Løstbois met haar hoofdkwartier in de fetishClub Church.<br/><br/><strong><u>Talk:</u></strong> We Always Go Back to Our First Loves: Notes Toward a Theory of Scat door Diego Semerene<br/><br/>“Poep” was misschien wel een van je eerste woordjes, samen met “mama.” Rond ons derde jaar waren we nog bereid om alles in onze mond te stoppen: poep, snot, modder. Het onderbewuste kan gezien worden als een potje voor onze poep – voor afgestoten materie. Omdat poep een van onze eerste liefdes was, werd het ook een van de belangrijkste redenen voor disciplinering. We leerden al snel om poep als object van genot te zien. Maar er is niets natuurlijks aan deze afwijzing die vaak zelfs nog stand houdt in de meest kink-vriendelijke ruimtes, waar mensen aangeven dat scat hun grens is, of de grens. Deze lezing ziet scat niet als pathologisch symptoom maar accepteert het als creatieve oplossing en geeft wat aanzetjes tot het openen van de erotische en psychoanalytische mogelijkheden van scat.<br/><br/><strong>Diego Semerene</strong> is assistent-professor in Queer en Transgender Media aan de Universiteit van Amsterdam en is mede-oprichter van de Queer Analysis Onderzoeksgroep aan de Amsterdamse School voor Culturele Analyse (ASCA) en van de (Trans)seksualiteit + Psychoanalyse Zomerschool."
  },
  "description": `<p>
    <strong><u>Films:</u></strong>
    <br/>
    <strong>Florian</strong> | Jan Soldat | 2021 | Austria | 11’
    <br/>
    <strong>Breakfast Time</strong> | Peter Cage | 2024 | US | 18’
    <br/>
    <strong>Oda a la alegría (Ode to joy)</strong> | Lola Pistola | 2024 | Spain | 4’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 80 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 80 min"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20889"
},
{
  "id": 3,
  "image": new URL('../assets/sat3.png', import.meta.url).href,
  "title": "RE-INDIGENIZING",
  "time": "13:00",
  "place": "CliffordStudio",
  "text": {
    "en": "Expanding on our previous “Decolonizing our bodies, our worlds”, this selection invites us to embrace sexuality and pornography as liberating moments that can guide us back to forgotten origins. Those starting points where bodies move away from systems created by gender, race, religions, nations and money. The program moves from grassroots films – portraying how communities in Amsterdam and Cape Town reclaim lost senses and spaces – to humorous and essayistic films that reflect on the constraints shaping our emotional worlds. Poetic and experimental works to let go, rebel, return and reconnect with ancestral knowledge.",
    "nl": "Deze filmselectie is een vervolg op \"Decolonizing our bodies, our worlds\", een programma uit eerdere edities. Dit is een uitnodiging om seksualiteit en pornografie te zien als bevrijdende momenten die ons kunnen terugleiden naar vergeten origines. Beginpunten waar lichamen zich afzetten tegen door gender, ras, naties en economie gecreëerde systemen. De eerste films in dit programma tonen hoe gemeenschappen in Amsterdam en Cape Town hun verloren waarden en ruimtes voor zichzelf terugwinnen. Daarna volgen speelse en essayistische films die de begrenzingen van onze emotionele wereld reflecteren. Poëtisch en experimenteel werk om ons te bevrijden, ons af te zetten, terug te keren en verbinding te leggen met voorouderlijke kennis."
  },
  "description": `<p>
    <strong>Slut Club</strong> | Zoey Black | 2025 | South Africa | 23’
    <br/>
    <strong>Partial Drives: Their Physiology and Techniques</strong> | Iwo Tuleya | 2025 | Netherlands, Poland | 5’
    <br/>
    <strong>TARANTA TARANTA</strong> | Kiki Kazimi & Lola Pistola | 2025 | Italy | 5’
    <br/>
    <strong>Untie</strong> | Oat Montien | 2023 | USA, Thailand | 5’
    <br/>
    <strong>The Embrace Of Community</strong> | Melancholive | 2024 | Netherlands | 11’
    <br/>
    <strong>The war trilogy I: The strength</strong> | Colectivo.gore, Erotida Films & The Wicked Place | 2025 | Spain | 6’
    <br/>
    <strong>Miammy's clinic</strong> | Miammy | 2025 | Greece | 2’
    <br/>
    <strong>Puta Mestiza</strong> | Linda Porn | 2014 | Spain, Mexico | 10’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 67 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 67 min + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20910"
},{
  "id": 4,
  "image": new URL('../assets/sat4.png', import.meta.url).href,
  "title": "THE OFFICE",
  "time": "14:30",
  "place": "Theater de Richel",
  "text": {
    "en": "Sex is universal. So is bureaucracy. Often, bad decisions about our lives are taken not from an epic place of evil, but from a sleepy little office and someone with itching fingers and a big stamp. It involves spreadsheets, repeating patterns and a lot of saying yes because you’re too worn out to say no. All the more reason to turn to a professional if it comes to being dominated and chained to a cubicle. This film selection of slow bureaucratic torture, helpdesk-BDSM, painful power points and cringey clinical waiting rooms will bring you to a state of desperate nail-biting laughter and cathartic relief once you’re back out in the street.",
    "nl": "Seks is universeel. Bureaucratie ook. Vaak worden de slechtste beslissingen over ons leven niet genomen in een geducht en euvel oord, maar in een slaperig klein kantoortje en iemand met jeukende vingers en een hele grote stempel. Er komen wat spreadsheets en richtsnoeren bij kijken en vooral veel ja-knikken omdat je te uitgewoond bent om nog tegen te sputteren. Des te meer reden om je in het vervolg alleen nog door een professionele dominatrix te laten vastketenen aan je ergonomisch zit-sta-bureau. Deze filmselectie van trage bureaucratische kwellingen, pijnlijke powerpoints, helpdesk-BDSM en akelig klinische wachtkamers brengen je in een staat van nagelbijtend gehinnik en louterende opluchting zodra je weer buiten staat."
  },
  "description": `<p>
    <strong>The Eternal Whore</strong> | Rori Dior & Diego Gómez | 2024 | Germany | 11’
    <br/>
    <strong>Your REAL Companion</strong> | Officer Flower, Iris Glitzer | 2025 | Germany | 13’
    <br/>
    <strong>Am I Calling You At A Bad Time</strong> | Martta Tuomaala | 2025 | Finland | 15’
    <br/>
    <strong>Partial Drives</strong> | Iwo Tuleya | 2025 | Poland | 4’
    <br/>
    <strong>Miammy's Clinic</strong> | Miammy | 2025 | Greece | 2’
    <br/>
    <strong>Nicole Dickman</strong> | Jacquie Belen | 2025 | Colombia | 25’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 70 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 70 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20923"
},
{
  "id": 5,
  "image": new URL('../assets/sat5.png', import.meta.url).href,
  "title": "EL MUNDO FUE Y SERÁ UNA PORQUERÍA:110 YEARS OF ARGENTINE PORN",
  "time": "15:30",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Argentine porn was never docile or obedient: it emerged through cuts, shadows and detours, often forced into clandestine forms. Far from imitating foreign models, it invented its own language of pleasure, mobilizing bodies, desires and fantasies that power sought to silence. This interactive screening traces a journey from the first moving images of the early twentieth century to today’s post-porn, dismantling the myths of a nonexistent porn and celebrating its escapes and excesses. To watch these scenes today is also a political gesture: an active defense of desire in the face of censorship and the advance of reactionary, ultraconservative forces.<br/><br/><strong>Guest curators: Ornella Bodratto and Laura Milano</strong><br/><br/><strong>Laura Milano (She):</strong> author of three books and several academic articles on Argentinean pornography. Sex educator, curator and organizer of different events about porn, feminism and sexual education. @lauramilanook @p.rn.grafiadesbordada<br/><br/><strong>Ornella Bodratto (She):</strong> Researcher, artist, and pornography scholar. Coordinator of the collective HASTA LAS TETAS. Curator of several porn shows and events, such as Putas en Pantalla. Pro-sex transfeminist activist.",
    "nl": "Argentijnse porno is nooit braaf of volgzaam geweest. Ze ontsprong uit scheuren, schaduwen en omwegen en werd vaak gedwongen om clandestiene vormen aan te nemen. In plaats van buitenlandse modellen te volgen, bedacht ze een eigen taal voor genot waarmee ze lichamen, verlangens en fantasieën opriep om samen te komen en zich te verzetten tegen de machten die haar het zwijgen probeerden op te leggen. Deze interactieve filmvertoning traceert de reis: van de eerste bewegende beelden uit de vroege twintigste eeuw tot de post-porno van vandaag. Daarmee weerleggen we de mythe van niet-bestaande porno en vieren we haar escapades en excessen. Het bekijken van deze scènes is een politieke daad op zichzelf: een actieve verdediging van verlangen, oog in oog met censuur en de opkomst van reactionaire, ultra-conservatieve krachten.<br/><br/><strong>Gastcuratoren: Ornella Bodratto en Laura Milano</strong><br/><br/><strong>Laura Milano (zij):</strong> auteur van drie boeken en verschillende academische artikelen over Argentijnse pornografie. Seksvoorlichter, curator en organisator van verschillende evenementen over porno, feminisme en seksuele voorlichting. @lauramilanook @p.rn.grafiadesbordada<br/><br/><strong>Ornella Bodratto (zij):</strong> Onderzoeker, kunstenaar en pornografiewetenschapper. Coördinator van het collectief HASTA LAS TETAS. Curator van verschillende pornovertoningen en evenementen, zoals Putas en Pantalla. Pro-sex transfeministisch activist."
  },
  "description": {
    "en": "Interactive screening celebrating the history and political resistance of Argentine porn.",
    "nl": "Interactieve filmvertoning die de geschiedenis en het politieke verzet van de Argentijnse porno viert."
  },
  "duration": {
    "en": "<strong>Total duration:</strong> 80 minutes",
    "nl": "<strong>Totale duur:</strong> 80 min"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20890"
},
{
  "id": 6,
  "image": new URL('../assets/sat6.png', import.meta.url).href,
  "title": "THE BEAST WITHIN",
  "time": "15:30",
  "place": "CliffordStudio",
  "text": {
    "en": "The term ‘fucking like animals’ has never been more applicable. The mating rituals in these films match those of the most extraordinary creatures. When these people fuck, they don’t moan… they purrrrr. When climaxing they don’t scream... they bark. They gallop and they swim, they scurry and they graze. Don’t forget to feed your cat, walk your dog and milk your cows before entering this screening of the most beastly encounters.",
    "nl": "De uitdrukking 'neuken als beesten' was nog nooit zo toepasselijk. De paringsrituelen in deze films lijken op die van de meest merkwaardige dieren. Tijdens het neuken kreunen deze mensen niet… ze spinnen. En als ze klaarkomen, schreeuwen ze niet... maar blaffen ze. Ze galopperen, ze zwemmen, scharrelen en grazen. Vergeet je kat niet te voeren, je hond niet uit te laten en je koeien niet te melken voor je naar deze beestachtige filmvertoning komt."
  },
  "description": `<p>
    <strong>Mannenmelk</strong> | Iris van Kalsbeek | 2025 | Netherlands | 14’
    <br/>
    <strong>Taste like chicken</strong> | Jay Lincal | 2025 | France | 7’
    <br/>
    <strong>Animalation</strong> | Diego Tigrotto | 2025 | Italy | 4’
    <br/>
    <strong>Rat Trap</strong> | alterotics: Anais Alias & Avery Jaye | 2025 | USA | 15’
    <br/>
    <strong>Pussy Gazing</strong> | abcde Flash | 2023 | Switzerland | 7’
    <br/>
    <strong>Good Dogs go to Heaven</strong> | lasse långström | 2025 | Sweden | 3’
    <br/>
    <strong>Ride ‘til sunrise</strong> | Beatriz Candor | 2024 | Argentina | 15’
    <br/>
    <strong>La Bonne Éducation</strong> | Nour Beetch & Celio | 2025 | Belgium/France | 7’
    <br/>
    <strong>Octopussy</strong> | thany sanches | 2025 | Brasil | 11’
    <br/>
    <strong>+ ‘White Kitty’</strong> | Dgin | performance
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 83 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 83 min + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20907"
},
{
  "id": 7,
  "image": new URL('../assets/sat7.png', import.meta.url).href,
  "title": "QUEER EAST:HIGH HANDS SMALL HANDS",
  "time": "12:00",
  "place": "Theater de Richel",
  "text": {
    "en": "This line-up of films is most appropriately experienced in the discomfort of rope restraints. So you may find out that all things under heaven are inextricably and disconcertingly tied up in each other. There is no West and East, North and South. The trace of rope may sting, but it can also grant you the subtle ability to sense from a place of surrender. Doing so would not only startle the freedom/subjugation dichotomy, but could also, if your lucky stars align, lead to the hallowed arrangement of ‘topping from the bottom’. There’s something sexy to be found beyond 'Asianess', but first you have to resist the gravity.<br/><br/>After the screening, there will be a rope performance by <strong>Taro</strong>, a queer rope bondage practitioner based in the Netherlands. Taro finds pleasure in exploring how rope can be used to push the boundaries of how the body can feel, look, and move.<br/><br/><strong>Guest curator:</strong> Bart Seng Wen Long, in partnership with the festival Queer East (London).<br/><br/><strong>Queer East</strong> is a London-based cross-disciplinary festival that showcases boundary-pushing LGBTQ+ cinema, live arts, and moving image work from East and Southeast Asia and its diaspora communities.",
    "nl": "Deze line-up van films bekijk je het best in een ongemakkelijke, vastgebonden houding. Wellicht kom je er dan achter dat alle ondermaanse dingen onlosmakelijk en verwarrend genoeg met elkaar verknoopt zijn. Er is geen oost en west, noord en zuid. Het touw mag dan pijnlijke sporen achterlaten, het gunt je ook het subtiele vermogen om te voelen vanuit een positie van overgave. Dat schudt niet alleen de vrijheid-onderwerpingsdichotomie door elkaar, maar leidt ook (als je sterren tenminste goed staan) tot de verheven status ‘top als bottom’. Het is heel goed mogelijk om ‘asiatisch’ sexy te vinden, maar dan moet je wel eerst de zwaartekracht weerstaan.<br/><br/>Na de films is er een performance door queer rope bondage beoefenaar <strong>Taro</strong> die met touw de grenzen verkent en verlegt van hoe een lichaam voelt, eruitziet en beweegt.<br/><br/><strong>Gastprogrammeur:</strong> Bart Seng Wen Long in samenwerking met het Queer East festival (Londen).<br/><br/><strong>Queer East</strong> is een multi-disciplinair festival in Londen dat grensverleggende LGBTQ+ cinema, live art en visuele kunst vertoont uit Oost- en Zuidoost-Azië en haar gemeenschappen in diaspora."
  },
  "description": `<p>
    <strong>Dream Catcher</strong> | Fuyuhiko Takata | 2018 | Japan | 5’
    <br/>
    <strong>Mop</strong> | Joon Goh | 2023 | Malaysia | 9’
    <br/>
    <strong>There is No Sex Only Fans</strong> | Chi-Wen Ting | 2023 | Taiwan | 19’
    <br/>
    <strong>Disconnect</strong> | E8 and Janice Kei | 2024 | Hong Kong, UK | 4’
    <br/>
    <strong>glide by LILY CHOU-CHOU</strong> | Bart Seng Wen Long | 2024 | UK | 6’
    <br/>
    <strong>Obsolescence</strong> | Caviar to the General | 2021 | UK | 12’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 80 minutes",
    "nl": "<strong>Totale duur:</strong> 80 min"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20924"
},
{
  "id": 8,
  "image": new URL('../assets/sat8.png', import.meta.url).href,
  "title": "COMING OF AGE",
  "time": "17:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Stories of transition. Stories of becoming. This block explores thresholds: the before and after moments that crack something open. Coming of age isn’t bound to youth or tied to outdated ideas of purity, nor to a mainstream porn category or religious initiation. It can happen at any time, in countless forms. These films trace self-discovery, sexual awakenings, escapes from what was, returns to the self and the unstable in-between spaces where identity is still forming.",
    "nl": "Verhalen over transitie, in wording zijn. Dit blok verkent drempels: de momenten voor- en nadat er iets openbreekt. ‘Coming of age’ gaat niet alleen over jeugd of achterhaalde concepten als maagdelijkheid en ook niet over afgezaagde pornocategorieën of religieuze inwijdingen. Het kan op elk moment gebeuren, op ontelbare manieren. Deze films beschrijven zelfontdekking, seksuele bewustwording, ontsnappingen aan het oude, een terugkeer naar het zelf en de wiebelige tussenruimtes waarin identiteit in wording is."
  },
  "description": `<p>
    <strong>alt.sex.fetish.robots</strong> | Zed Sheng | 2025 | USA, Thailand | 5'
    <br/>
    <strong>Knots of Self</strong> | Laura Ropes | 2025 | Austria | 16'
    <br/>
    <strong>Feverish</strong> | Fabienne Garçonne and Jamal Phoenix | 2025 | Switzerland | 5'
    <br/>
    <strong>Pillowcore</strong> | Nisa East & Rosie Allways | 2025 | Australia | 10'
    <br/>
    <strong>In All the Rooms We Met</strong> | Bonaventure Tain | 2024 | Malaysia | 14'
    <br/>
    <strong>Our joyful endings</strong> | Lucie Babayan & La fille Renne | 2025 | France | 6'
    <br/>
    <strong>The Chemo Darkroom</strong> | Harvey Rabbit | 2018 | Germany | 17'
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 73 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 73 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20891/coming-of-age"
},
{
  "id": 9,
  "image": new URL('../assets/sat9.png', import.meta.url).href,
  "title": "EXCÉNTRICO:<br/>CHILE IN FOCUS",
  "time": "18:00",
  "place": "CliffordStudio",
  "text": {
    "en": "This is our juiciest pulp: the porn and post-porn made in Chile or by Chilean creators, a scene that has been mutating for nearly three decades. The festival Excéntrico is where it found a place to breathe and to connect, building a horny and radical community that keeps growing against all odds. The series of political events that took over the Chilean streets in 2019, known as Estallido Social, started just five days before what would have been the first edition of Excéntrico, which had to be suspended and postponed. But here we are: joining forces against the constant threat of censorship and moralism. This is a love letter to the creators of the New Chilean Porn – without their work and passion, Excéntrico simply wouldn’t exist.<br/><br/><strong>Guest curator:</strong> Nicola Ríos, Psychologist and independent researcher both in critical sex education and sex media. Sex positive activist, curator and head of programming of Excéntrico Film Festival (Chile).",
    "nl": "Dit is onze sappigste pulp: porno en post-porno gemaakt in Chili of door Chileense makers, een scene die al bijna drie decennia lang muteert. In Festival Excéntrico vond ze aansluiting en ruimte om te ademen en evolueerde zo tot een geile en radicale gemeenschap die tegen alle verwachtingen in blijft groeien. Vijf dagen vóór de eerste editie van Excéntrico in 2019, werden de straten van Chili overgenomen door politieke rellen, beter bekend als Estallido Social (sociale uitbarsting). Het festival kon niet doorgaan en werd uitgesteld. Maar hier zijn we dan toch: onze krachten bundelend tegen de constante dreiging van censuur en verstikkend moralisme. Dit is een liefdesbrief aan de makers van de New Chilean Porn: zonder hun werk en passie zou Excéntrico simpelweg niet bestaan.<br/><br/><strong>Gastprogrammeur:</strong> Nicola Ríos, psycholoog en onafhankelijk onderzoeker in kritische sekseducatie en seksmedia. Sekspositieve activist, curator en hoofd programmering van het Excéntrico Film Festival (Chili)."
  },
  "description": `<p>
    <strong>Nacer ceniza, Morir maleza</strong> | Diego Argote | 2020 | Chile | 3’
    <br/>
    <strong>Mosquerío</strong> | Fernanda Gallardo & Maria Catalina Jorquera | 2020 | Chile | 10’
    <br/>
    <strong>Poco hombre 1</strong> | Andrés Valenzuela Arellano | 2021 | Chile | 3’
    <br/>
    <strong>Ofensa al pudor</strong> | ValentinaXimena & Cat | 2021 | Chile | 6’
    <br/>
    <strong>Capucha caída</strong> | Cris Gomez | 2023 | Chile | 8’
    <br/>
    <strong>Lecturas prohibidas</strong> | Eva Gracia del Alba | 2025 | Chile | 4’
    <br/>
    <strong>Parafilia</strong> | Javiera Belem | 2025 | Chile | 8’
    <br/>
    <strong>Sombra</strong> | Dolmacé | 2025 | Chile | 20’
    <br/>
    <strong>Prácticas pornográficas frente a la pulsión de muerte</strong> | Errada | 2024 | Chile/Spain | 22’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 84 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 84 min + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20925"
},
{
  "id": 10,
  "image": new URL('../assets/sat10.png', import.meta.url).href,
  "title": "<u>PERFORMANCE:</u><br/>Noise from the Matrix",
  "time": "19:00 – 19:20",
  "place": {
    "en": "Theater de Richel: upstairs",
    "nl": "Theater de Richel: bovenzaal"
  },
  "text": {
    "en": "This action aims to generate a sound protest through female masturbation and thus raise the voice of a disputed territory: the dissident body cries out for the right to pleasure and its freedom of action. The interaction between the female pleasure and the audience will make it possible to create other points of conflict in the development of the performance, proposing imaginaries in the spectator that might have to do with specific structures of power and gender difference.<br/><br/><strong>Nicol Rivera Aro</strong>, performance artist, dramaturg and researcher from Chile. She is an actress and PhD-candidate. She focuses on the relationship between the body and technological interfaces, with special attention given to sextechnologies.",
    "nl": "Tijdens deze performance wordt een geluidsprotest op gang gebracht door middel van vrouwelijke masturbatie. Een omstreden terrein verheft de stem: het dissidente lichaam roept om het recht op genot en haar vrijheid van handelen. Deze interactie tussen het vrouwelijk genot en het publiek opent ook de ruimte voor andere conflictueuze punten. Terwijl de performance zich ontvouwt, komen mogelijk ook andere associaties bij de toeschouwer op die alles te maken hebben met machtsstructuren en genderverschillen.<br/><br/><strong>Nicol Rivera Aro</strong>, performancekunstenaar, dramaturg en onderzoeker uit Chili. Als actrice en PhD-kandidaat richt ze zich op de relatie tussen het lichaam en technologie, met een bijzondere aandacht voor sekstech."
  },
  "description": {
    "en": "<strong>Noise from the Matrix</strong> | Nicol Rivera Aro | 20’ | Free entrance",
    "nl": "<strong>Noise from the Matrix</strong> | Nicol Rivera Aro | 20’ | Gratis toegang"
  },
  "duration": {
    "en": "", // Leave empty as the duration is already in the description line
    "nl": ""
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "" // Free entrance, so the button is hidden
},
{
  "id": 11,
  "image": new URL('../assets/sat11.png', import.meta.url).href,
  "title": "KINKYSTRAAT",
  "time": "19:30",
  "place": "Theater de Richel",
  "text": {
    "en": "Consent. Pain. Endurance. Dynamics. Exploration. Vulnerability. Commitment. Fantasy. Memory. Discovery. Power. What is kink? Where does fantasy end and reality begin? Does there always have to be a separation? Whether we’ve chosen to enact our most forceful fantasies with help from those we trust deeply or we’re living gentle everyday lives with people whose desires happen to mesh with ours, elements of power exchange are always part of our realities. These films strive to broaden our perspectives about kink and challenge us to face our deepest fears and desires courageously.",
    "nl": "Consent. Pijn. Uithoudingssvermogen. Dynamieken. Verkenning. Kwetsbaarheid. Toewijding. Fantasie. Geheugen. Ontdekking. Macht. Wat is kink? Waar gaat de fantasie over in werkelijkheid? Moet daar altijd een onderscheid tussen bestaan? Machtsverhoudingen zijn altijd deel van onze werkelijkheid. Of we er nu voor kiezen om onze heftigste fantasieën tot leven te brengen met de hulp van iemand die we vertrouwen, of dat we ons dagelijks leven vreedzaam doorbrengen met mensen die toevallig dezelfde verlangens hebben als wij. Deze films willen onze opvattingen over kink verruimen en ons uitdagen om onze diepste angsten en verlangens dapper onder ogen te komen."
  },
  "description": `<p>
    <strong>Leathers: The Chain</strong> | Mahx Capacity | 2025 | USA | 11’
    <br/>
    <strong>Mouth Pleasure</strong> | Morgana Meyer | 2024 | Italy | 4’
    <br/>
    <strong>Flesh Release</strong> | Ira Rabidog | 2025 | Italy | 9’
    <br/>
    <strong>Fisting Club Ep. 2</strong> | Shu Lea Cheang | 2025 | Germany | 20’
    <br/>
    <strong>The Feminist’s Dungeon</strong> | Lady Rochester & Eugene Plantagenet | 2024 | France | 11’
    <br/>
    <strong>Ravine</strong> | Oat Montien | 2024 | USA | 7’
    <br/>
    <strong>Thing</strong> | Ori Di Vincenzo | 2024 | Germany | 11’
  </p>`,
  "duration": {
    "en": "<strong>Total Duration:</strong> 73 minutes + Q&A",
    "nl": "<strong>Totale Duur:</strong> 73 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20927"
},
{
  "id": 12,
  "image": new URL('../assets/sat12.png', import.meta.url).href,
  "title": "LOOKING BACK, PORN TREASURES",
  "time": "15:30",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "For a long time, the only places you could watch porn were small, not-too-obvious venues, and usually under the shadow of censorship and the constant threat of closure. Through archival footage and first-hand recollections, we revisit some of these sites: Theatro Gil Vicente in Barcelos, the Mineshaft in Marseille, Bada theatre in Seoul. We also meet Lynnee Breedlove, who spearheaded Homobiles, a queer cab service in San Francisco, and Luz Emilia García, one of the precursors of porn cinema in Colombia. We look back to cherish the oft-forgotten treasures of those who broke ground way before us.",
    "nl": "Lange tijd kon je alleen porno kijken op kleine onopvallende plekken, vaak onder de schaduw van censuur en de constante dreiging dat de tent zou worden opgedoekt. Met archiefbeelden en herinneringen uit eerste hand, bezoeken we een paar van deze plekken opnieuw: Theatro Gil Vicente in Barcelos, the Mineshaft in Marseille en het Bada Theater in Seoul. Ook ontmoeten we Lynnee Breedlove die aan het roer stond van Homobiles, een queer taxiservice in San Franscisco, en Luz Emilia García, een van de voorlopers in de Colombiaanse pornocinema. In deze terugblik koesteren we de vaak vergeten schatten en baanbrekers die aan ons voorafgingen."
  },
  "description": `<p>
    <strong>TGX</strong> | André Azevedo | 2025 | Portugal | 8’
    <br/>
    <strong>Les fantômes du hard</strong> | Lazare Lazarus | 2025 | France | 28’
    <br/>
    <strong>Backseat</strong> | Rae Threat, Jiz Lee, Robin Astera | 2025 | Germany, UK, US | 6’
    <br/>
    <strong>Paradise</strong> | Minki Hong | 2023 | South Korea | 30’
    <br/>
    <strong>The Night of the Minotaur</strong> | Juliana Zuluaga Montoya | 2023 | Colombia | 11’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 83 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 83 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "" 
},
{
  "id": 13,
  "image": new URL('../assets/sat13.png', import.meta.url).href,
  "title": "FOREPLAY",
  "time": "20:30",
  "place": "CliffordStudio",
  "text": {
    "en": "I’m here to make you squirm, make you ache, make you beg, make you need it. I’m here to make you drool. Bite your lip. Squeeze your legs tight, so nothing slips out. I’m here to make you feel things. To feel it crawl through all of you. Slow, sticky, insistent. Let your body answer before your mind can catch up. Let the heat take over, let the tension build, let yourself unravel a little.<br/><br/>These films are here to make you feel good. These films are here to make you hungry.",
    "nl": "Ik zal je doen kronkelen, smachten, smeken van verlangen. Begin je al te watertanden? Ja, bijt maar op je lip. Knijp je dijen goed tegen elkaar zodat er niks ontsnapt. Ik zal je iets laten voelen. Iets dat door je hele lijf trekt. Langzaam, plakkerig, onontkoombaar. Je lichaam wist al hoe laat het was, nog voor je zelf iets in de gaten had. Je wangen gloeien al, de spanning loopt op, geef je maar over. Deze films zullen je goed doen en je hongerig maken naar meer."
  },
  "description": `<p>
    <strong>LUPAExHARDWERK</strong> | Paulita Pappel, Rod Whyler: Hardwerk | 2023 | Germany | 5’
    <br/>
    <strong>Ride til Sunrise</strong> | Beatriz Candor | 2024 | Argentina | 15’
    <br/>
    <strong>Ravine</strong> | Oat Montien | 2024 | USA | 6’
    <br/>
    <strong>Lesbian Fantasies</strong> | Goodyn Green & Jasko Fide | 2025 | Germany | 14’
    <br/>
    <strong>PORNIGRAPHICA</strong> | Alex Mendo and Jordan Joel | 2023 | USA | 4’
    <br/>
    <strong>The Gooners</strong> | Frock The World | 2025 | USA | 5’
    <br/>
    <strong>Echo Chamber</strong> | Four Chambers | 2025 | UK | 14’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 63 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 63 minutes + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20902/foreplay"
},
{
  "id": 14,
  "image": new URL('../assets/sat14.png', import.meta.url).href,
  "title": "CLOSING PARTY",
  "time": "22:00 – 06:00",
  "place": "The Other Side",
  "text": {
    "en": "The cherry on top: get ready to shake your ass and celebrate the third edition of Porn Film Festival Amsterdam. Come as you are and cum as you please in a space where consent is mandatory and connection intentional. We welcome you from 22:00 to 06:00 at The Other Side.<br/><br/><strong>Lineup | Tundji | Lola Edo | OISHĪ | ZOBAYDA</strong><br/><strong>Performance | ANOmalie collective</strong><br/><br/>Pre-sale €20 – €25<br/>Door sale €30",
    "nl": "De kers op de taart: schud je heupen los en maak je klaar om de derde editie van Porn Film Festival Amsterdam te vieren. Kom zoals je bent en kom zoals je wil op deze plek waar consent de weg wijst in een speelse nacht vol ontmoetingen. Een zwoel welkom van 22:00 tot 06:00 in The Other Side.<br/><br/><strong>Lineup | Tundji | Lola Edo | OISHĪ | ZOBAYDA</strong><br/><strong>Performance | ANOmalie collective</strong><br/><br/><strong>kaartjes</strong> www.the-other-side.nl<br/><strong>Voorverkoop</strong> €20 – €25<br/><strong>Aan de deur</strong> €30"
  },
  "description": {
    "en": "",
    "nl": ""
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/OTHERSIDE.png', import.meta.url).href,
  "ticket": "https://shop.weeztix.com/6dd4df03-d776-11f0-a9cb-7e126431635e/tickets?shop_code=w6q6nj8w"
},
{
  "id": 15,
  "image": new URL('../assets/sat15.png', import.meta.url).href,
  "title": "<u>WORKSHOP:</u><br/>HACKING SEX",
  "time": "12:00 – 15:00",
  "place": "Prostitution Information Center",
  "text": {
    "en": "Sometimes in order to get a better understanding of how things actually work, you’ve got to take them apart. In this workshop we will hack sex toys, take control of their behavior and design them to our own desire. We will explore the technology that makes our toys vibe and share a variety of ways to go about hacking them. Sex tech can enable us to reclaim our agency, autonomy and voice in the sexual sphere. By experimenting with sex tech, we can break taboos, change the status quo, creating a more diverse, inclusive and positive culture of sexuality.<br/><br/><strong>Sabrina Verhage</strong> is a creative technologist highly fascinated by the influence of modern technology on human behavior. Striving to make knowledge more accessible and fun, Sabrina teaches how to hack sex toys for pleasure, intimacy and empowerment.",
    "nl": "Om beter te begrijpen hoe iets werkt, moet je het soms gewoon uit elkaar halen. In deze workshop hacken we sekspeeltjes, nemen controle over hun werking en geven ze aan de hand van onze eigen behoeftes opnieuw vorm. We verkennen de technologie die vibratie veroorzaakt en leren verschillende manieren om die te hacken. Met behulp van sekstechnologie kunnen we onze agentschap, autonomie en stem in seksuele context terugvorderen. Door met sekstech te experimenteren kunnen we taboes doorbreken, verandering brengen in de status quo en een seksuele cultuur creëren die diverser, inclusiever en positiever is.<br/><br/><strong>Sabrina Verhage (zij/haar)</strong> is als kunstzinnig technoloog gefascineerd door de invloed van moderne technologie op menselijk gedrag. Met het doel om kennis leuker en toegankelijker te maken, leert Sabrina hoe je sekspeeltjes kunt hacken om plezier, intimiteit en empowerment te vergroten."
  },
  "description": {
    "en": "<strong>Hacking Sex</strong> | Sabrina Verhage (she/her) | Between 2h and 3h",
    "nl": "<strong>Hacking Sex</strong> | Sabrina Verhage | tussen 2 en 3 uur<br/><strong>Maximum deelnemers:</strong> 15<br/><strong>Voertaal:</strong> Engels"
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/PIC.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20928"
},
{
  "id": 16,
  "image": new URL('../assets/sat16.png', import.meta.url).href,
  "title": "<u>WORKSHOP:</u><br/>HYSTERICAL PAROXYSM CHOIR",
  "time": "12:30 – 15:30",
  "place": "CliffordStudios",
  "text": {
    "en": "In this workshop we will create a collective sound experiment – an exploration of our internal resonances, fluids and pulsations – to materialize them into a hysterical vaginal noise choir through acts of sonic masturbation. Participants will be invited to explore their own bodily soundscapes through exercises of vocal, vibrational and sensorial activation, culminating in a collective noise performance that celebrates hysteria, pleasure and resonance as forms of resistance and creation. The workshop is open to anyone who’s up for masturbation.<br/><br/><strong>Nicol Rivera Aro</strong>, she/her. Chilean performance artist, dramaturg, and researcher. She is a PhD candidate in Philology at Leipzig University. Her work focuses on the relationship between the body and technological interfaces, delving into gender discourse and post-porn, with special attention given to sextechnologies.",
    "nl": "In deze workshop doen we een collectief geluidsexperiment: we verkennen onze innerlijke resonantie, ritmes en vloeistoffen. Door middel van sonische masturbatie geven we daar de vorm aan van een luid en hysterisch vaginaal koor. Deelnemers worden uitgenodigd om hun eigen lichamelijke landschappen te onderzoeken in oefeningen met vocale, vibrationele en zintuiglijke activatie. De workshop vindt zijn hoogtepunt in een collectieve geluidsperformance waarmee we hysterie, genot en weerklank vieren als vormen van verzet en creatie. Deze workshop is voor iedereen die open staat voor collectieve masturbatie.<br/><br/><strong>Nicol Rivera Aro (zij/haar)</strong> is een Chileense performance kunstenaar, dramaturg en onderzoeker. Ze doet een PhD in filologie aan de Universiteit van Leipzig. In haar werk richt ze zich op de relatie tussen lichaam en techniek, bestudeert genderdiscoursen en post-porno en heeft een speciale focus op sekstechnologie."
  },
  "description": {
    "en": "<strong>HYSTERICAL PAROXYSM CHOIR</strong> | Nicol Rivera (she/her) | 3h<br/><strong>Maximum participants:</strong> 15",
    "nl": "<strong>Hysterical Paroxysm Choir</strong> | Nicol Rivera | 3h<br/><strong>Maximum deelnemers:</strong> 15<br/><strong>Voertaal:</strong> Engels"
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20929"
},
{
  "id": 17,
  "image": new URL('../assets/sat17.png', import.meta.url).href,
  "title": "<u>WORKSHOP:</u><br/>FLIRTING MERMAIDS",
  "time": "16:00 – 15:30",
  "place": "CliffordStudios",
  "text": {
    "en": "A collective experience of erotic exploration for desiring dissident desiring and dissident bodies and sexualities. This workshop originates from training practices within the ballroom competition category “Sex Siren”. Participants are invited to an individual, dual and collective experience, exploring pleasure and eroticism through gaze, sexual provocation, and bodily dialogue. Together, we’ll reconfigure how we look at and are looked at, discovering new ways of creating and inhabiting the erotic body and its expansions. By the end of the workshop, each participant will create a short individual video using their own cellphone. <br/><strong>No prior stage experience necessary.</strong><br/><br/><strong>Juliette aka Juli Puch 007</strong>, Madrina Sirena de la Comunidad de La Plata, is a migrant actress, director, researcher and performer and has been active in the erotic arts and the ballroom scene since 2019.",
    "nl": "Een collectieve erotische verkenning voor verlangende dissidente lichamen en seksualiteiten. Deze workshop bouwt voort op trainingen voor de ballroomcategorie “Sex Siren”. De deelnemers worden uitgenodigd om alleen, in duo’s en met de hele groep genot en erotiek te onderzoeken aan de hand van de blik, seksuele uitdaging en lichaamstaal. Samen vinden we nieuwe vormen van kijken en bekeken worden en ontdekken we andere manieren om het erotische lichaam vorm te geven en te beleven. Aan het einde van de workshop maakt elke deelnemer een korte individuele film met diens eigen telefoon.<br/><strong>Podiumervaring is niet vereist.</strong><br/><br/><strong>Juliette (zij/haar)</strong> aka Juli Puch 007, Madrina Sirena de la Comunidad de La Plata, is actrice, regisseur, onderzoeker en performer met een migratieachtergrond. Sinds 2019 is Juliette actief in de ballroomscene en de erotische kunsten."
  },
  "description": {
    "en": "<strong>Flirting Mermaids</strong> | Juli Puch (she/her) | 3h<br/><strong>Maximum participants:</strong> 20",
    "nl": "<strong>Flirting Mermaids</strong> | Juli Puch | 3u<br/><strong>Maximum aantal deelnemers:</strong> 20<br/><strong>Voertaal:</strong> Engels"
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20930"
}
]
</script>

<template>
  <b-container fluid
    class="d-flex flex-column min-vh-100 px-0 view-background"
    :style="{ 
      backgroundImage: 'url(' + background + ')',
      backgroundSize: 'cover',
      backgroundPosition: 'center',
      backgroundRepeat: 'no-repeat',
      backgroundAttachment: 'fixed'
    }">
    
  <b-row class="mt-5">
    <b-col xs="12" class="text-center">
      <div class="titles mt-5">{{ translations[currentLang].day }}</div>
      
      <div class="titles">{{ translations[currentLang].date }}</div>
    </b-col>
  </b-row>

    <b-row class="justify-content-center my-4">
      <b-col cols="auto" class="d-flex align-items-center">
        <span class="lang-label me-2" :class="{ 'active-lang': currentLang === 'nl' }">NL</span>
        <b-form-checkbox 
          :model-value="currentLang === 'en'" 
          @change="toggleLang" 
          switch 
          size="lg"
          class="custom-switch"
        />
        <span class="lang-label ms-2" :class="{ 'active-lang': currentLang === 'en' }">ENG</span>
      </b-col>
    </b-row>

  <program-item 
      v-for="(item, index) in agenda" 
      :key="item.id" 
      :image="item.image"
      :title="item.title"
      
      :time="typeof item.time === 'object' ? item.time[currentLang] : item.time"
      :place="typeof item.place === 'object' ? item.place[currentLang] : item.place"
      
      :description="typeof item.description === 'object' ? item.description[currentLang] : item.description"
      :duration="item.duration[currentLang]"
      :text="item.text[currentLang]" 
      
      :imagelogo="item.imagelogo"
      :ticket="item.ticket"
      :reverse="index % 2 !== 0"
      :is-first="index === 0"
      :is-dutch="currentLang === 'nl'" 
  />
  </b-container>
</template>

<style scoped>
/* 1. The container for the toggle */
.lang-label {
  font-weight: bold;
  color: #555;
  font-family: sans-serif;
}

.active-lang {
  color: #000;
}

/* 2. Target the Switch Pill specifically */
:deep(.form-check-input) {
  cursor: pointer;
  background-color: #6a4da1 !important; /* The purple when NOT checked */
  border-color: #6a4da1 !important;
}

:deep(.form-check-input:checked) {
  background-color: #6a4da1 !important; /* The purple when CHECKED */
  border-color: #6a4da1 !important;
}

/* 3. Ensure the focus shadow isn't blue */
:deep(.form-check-input:focus) {
  box-shadow: 0 0 0 0.25rem rgba(106, 77, 161, 0.25);
  border-color: #6a4da1;
}

/* Main titles style */
.titles {
  font-size: 3em;
  font-weight: bold;
}

@media (max-width: 576px) {
  .titles {
    font-size: 1.5em;
  }
}
</style>