<script setup lang="ts">
import { BImg, BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref, computed } from 'vue'; 
import ProgramItem from '../components/ProgramItem.vue'
const background = new URL('../assets/sun_background.png', import.meta.url).href

// Set default language
const currentLang = ref<'en' | 'nl'>('en');

// Toggle function
const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: {
    day: "Sunday",
    date: "1 March 2026"
  },
  nl: {
    day: "Zondag",
    date: "1 Maart 2026"
  }
};

const agenda = [
{
  "id": 1,
  "image": new URL('../assets/sun1.png', import.meta.url).href,
  "title": "CRIPPING PLEASURE",
  "time": "12:00",
  "place": "CliffordStudio",
  "text": {
    "en": "Being ill or disabled means that something is disrupted against the dominant order. The pleasures of physical and neurological diversity you will see in this block are a form of enmeshment, of entanglement. And this process is neither a blessing nor a curse, it is simply the form of existence called life. These films want to invite you to rethink the integrity of the body in the context of openness, vulnerability and responsibility, rather than in the essentialism imposed by purity and the false illusion of the body's immortality.",
    "nl": "Ziek of gehandicapt zijn is een onderbreking van de dagelijkse orde. De genoegens van lichamelijke en neurologische diversiteit die je in dit filmprogramma ziet, zijn vormen van verstrengeling, verwikkeling. En dit proces is vloek noch zege, het is gewoonweg een vorm van bestaan. Deze films nodigen je uit om de integriteit van het lichaam te her-denken in de context van openheid, kwetsbaarheid en verantwoordelijkheid, en het essentialisme los te laten dat ons wordt voorgeschreven door het idee van zuiverheid en de valse illusie van het onsterfelijke lichaam."
  },
  "description": `<p>
    <strong>DAMP</strong> | Etsen Chen | 2025 | Taiwan, Korea | 12’
    <br/>
    <strong>The Assessment</strong> | The Philosowhore | 2024 | Belgium | 12’
    <br/>
    <strong>Chemo Darkroom</strong> | Harvey Rabbit | 2018 | Germany | 17’
    <br/>
    <strong>Sexual Being</strong> | Paul Stavropoulos | 2018 | Canada | 17’
    <br/>
    <strong>Spit and Swallow</strong> | Jaewon Kim | 2021 | South Korea | 8’
    <br/>
    <strong>Fisting Club 2</strong> | Shu Lea Cheang | 2025 | Germany | 20’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 86 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 86 min + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20940/cripping-pleasure"
},
{
  "id": 2,
  "image": new URL('../assets/sun2.png', import.meta.url).href,
  "title": "POLDER PORNO",
  "time": "12:00",
  "place": "Theater de Richel",
  "text": {
    "en": "The streets in the Netherlands are empty. The mills have stopped and the bikes have stalled. The coffeeshops are closed and the NS has, against character, announced mass delays. What is happening? Where is everybody headed? Rumour has it that Porn Film Festival Amsterdam, for the first time ever, has a screening dedicated to films solely produced in the Netherlands! Could this really be? Put on your klompen and come to De Richel to find out!",
    "nl": "De straten in Nederland zijn verlaten. De molens staan stil. De fietsen staan op slot. Alle coffeeshops zijn dicht en de NS kondigt (hoe zal het ook anders) massale vertragingen aan. Wat is er aan de hand? Waar is iedereen heen? Het gerucht gaat dat Porn Film Festival Amsterdam voor de eerste keer ooit een vertoning heeft van uitsluitend in Nederland geproduceerde films! Zou dat nou waar zijn?? Trek je klompen aan en kom naar De Richel om het zelf te zien!"
  },
  "description": `<p>
    <strong>Only Sticks</strong> | The Annoying Kids: Lokin & Yola | 2025 | Netherlands | 4’
    <br/>
    <strong>Mannenmelk</strong> | Iris van Kalsbeek | 2025 | Netherlands | 14’
    <br/>
    <strong>Pleasure Engineer</strong> | Christina Castalia | 2025 | Netherlands | 11’
    <br/>
    <strong>://submersion</strong> | Twyla Twilight and Emma Grima | 2025 | Netherlands | 15’
    <br/>
    <strong>Tie me up</strong> | Melancholive | 2025 | Netherlands | 12’
    <br/>
    <strong>Faces of Pain</strong> | L. H. Bararian and Fawn | 2025 | Netherlands | 25’
    <br/>
    <strong>Fluister voor me</strong> | Silkyway's Universe | 2025 | Netherlands | 4’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 83 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 83 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20909"
},
{
  "id": 3,
  "image": new URL('../assets/sun3.png', import.meta.url).href,
  "title": "QUEER.RED, UNFINISHED BUSINESS",
  "time": "13:00",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "What does it take to make porn? Technical skills, the right hardware and software, money, people and time. For sex workers, gathering all of these resources can be a challenge. But sex workers are resourceful as fuck! Often creating art that injects a breath of fresh air into the language of porn. More than that, they’re reshaping how porn is produced, infusing their sets with fun and care that is unmistakable to the audience.<br/><br/>Believing in the audacious creativity of sex workers, queer.red presents! gave a final push to three queer sex workers to bring their porn projects to completion. In this session, we’ll celebrate the premiere of these films and dive into a conversation with the filmmakers about their creative processes, the obstacles they faced and how they overcame them.<br/><br/><strong>Guest curator: queer.red</strong><br/>queer.red is a foundation working to increase the visibility of sex workers, challenge stigma and support their empowerment, rights and autonomy across social and economic spheres.",
    "nl": "Wat is er voor nodig om een pornofilm te maken? Technische vaardigheden, de juiste hardware en software, geld, mensen en tijd. Voor sekswerkers kan het verzamelen van al deze middelen een uitdaging zijn. Maar sekswerkers zijn ongelooflijk vindingrijk! Vaak is hun kunst een frisse wind die door de porno waait. Sterker nog, door hun sets met onmiskenbaar plezier en zorgvuldigheid te organiseren, hervormen ze de manier waarop porno wordt geproduceerd.<br/><br/>Vertrouwend op de gedurfde creativiteit van sekswerkers gaf queer.red presents! aan drie queer sekswerkers het laatste zetje om hun pornoprojecten te voltooien. In deze sessie gaan drie films in première en spreken we met de filmmakers over hun creatieve processen, de obstakels die ze tegenkwamen en hoe ze die hebben overwonnen.<br/><br/><strong>Gastprogrammeur: queer.red</strong><br/>queer.red is een stichting die zich inzet voor de zichtbaarheid van sekswerkers, stigma aan de kaak stelt en hun empowerment, rechten en autonomie ondersteunt op sociaal en economisch gebied."
  },
  "description": `<p>
    <strong>A Queer.Red Presentation</strong>
    <br/>
    World Premiere of three supported projects + Filmmaker Talk
  </p>`,
  "duration": {
    "en": "<strong>Estimated duration:</strong> 60 minutes + Q&A",
    "nl": "<strong>Duur:</strong> ca. 60 min"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20894"
},{
  "id": 4,
  "image": new URL('../assets/sun4.png', import.meta.url).href,
  "title": "SATURN RETURN",
  "time": "14:00",
  "place": "CliffordStudio",
  "text": {
    "en": "At the beginning of the 20th century, Vienna was not only a hotspot for art and philosophy, but also home to one of the world’s first erotic film studios. Between 1906 and 1911, Saturn-Films produced dozens of playful, spicy scenes that still surprise today with their lightness. Daniela Zahler remade thirteen of these films, watching them through a present-day lens. Saturn Return is a humorous and fresh reimagination of the origins of European erotic cinema.",
    "nl": "Aan het begin van de 20e eeuw was Wenen niet alleen een hotspot voor kunst en filosofie, maar ook de thuisbasis van een van 's werelds eerste erotische filmstudio's. Tussen 1906 en 1911 produceerde Saturn-Films tientallen speelse, pikante scènes die ook vandaag de dag nog verrassen met hun lichtvoetigheid. Daniela Zahler bekijkt dertien van deze films door een hedendaagse lens. Saturn Return is een humoristische en frisse herinterpretatie van de oorsprong van de Europese erotische cinema."
  },
  "description": `<p>
    <strong>Saturn Return</strong> | Daniela Zahler | 2024 | Austria | 50’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 50 minutes",
    "nl": "<strong>Totale duur:</strong> 50 min"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20941"
},
{
  "id": 5,
  "image": new URL('../assets/sun5.png', import.meta.url).href,
  "title": "PORN, PEACE, POLITICS",
  "time": "15:00",
  "place": "Theater de Richel",
  "text": {
    "en": "What is more pornographic: the representation of sex… or the representation of war? If, according to some, porn (and sex work) must disappear, should we also censor images of war (and war itself)? Is this a matter of censorship or rather the denial of human reality? These films resist silencing by using pornography to speak out against fascism, xenophobia, whorephobia and imperialism.",
    "nl": "Wat is pornografischer: de visuele representatie van seks…. of die van oorlog? Als we porno (en sekswerk) zoals sommigen beweren, zouden moeten verbieden, zouden we dan ook niet oorlogsbeelden moeten censureren, en oorlog zelf? Is dit censuur of een ontkenning van menselijke werkelijkheid? Deze films laten zich de mond niet snoeren en gebruiken pornografie om zich uit te spreken tegen fascisme, xenofobie, whorephobia en imperialisme. Want ook op seksuele ervaringen laat het politieke geheugen zijn sporen na."
  },
  "description": `<p>
    <strong>Solidarity with the Garbage Workers on Strike</strong> | Lasse Långström | 2025 | Germany | 4’
    <br/>
    <strong>Rat trap</strong> | alterotics: Anais Alias & Avery Jaye | 2025 | USA | 5’
    <br/>
    <strong>The Red Analects</strong> | YuChen & Carlos Hurtado Múnera | 2025 | Germany | 7’
    <br/>
    <strong>The feminist's dungeon</strong> | Lady Rochester & Eugène Plantagenet | 2024 | France | 11’
    <br/>
    <strong>The war trilogy I: The strength</strong> | Colectivo.gore, Erotida Films & The Wicked Place | 2025 | Spain | 7’
    <br/>
    <strong>Gregory Übermensch Smoking Hot</strong> | Margie Schnibbe | 2025 | USA | 6’
    <br/>
    <strong>You’re not a Regular: A Porn made for Almans</strong> | Silicone Pussy | 2025 | Germany | 25’
    <br/>
    <strong>Good Dogs go to Heaven</strong> | Lasse Långström | 2025 | Germany | 3’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 81 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 81 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20911"
},
{
  "id": 6,
  "image": "",
  "title": "FUCKING FICTION: schrijven over porno",
  "time": "15:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Three writers engage in a conversation about how they depict sexuality and porn in their work. How do you give words to something as intimate and physical as sex, without trivializing it?<br/><br/>With <strong>Emma Zuiderveen, Thom Wijenberg and Kyrian Esser.</strong><br/><br/><em>Please note: This is a Dutch-spoken program.</em>",
    "nl": "Drie schrijvers gaan met elkaar in gesprek over hoe ze seksualiteit en porno verbeelden in hun werk. Hoe geef je woorden aan iets intiems en fysieks als seks, zonder het te banaliseren?<br/><br/>Met <strong>Emma Zuiderveen, Thom Wijenberg en Kyrian Esser.</strong>"
  },
  "description": {
    "en": "<strong>Public Talk</strong> | 60’ | Free entrance | Dutch spoken",
    "nl": "<strong>Publiek gesprek</strong> | 60’ | Gratis toegankelijk | Nederlandstalig"
  },
  "duration": {
    "en": "60 min",
    "nl": "60 min"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": ""
},
{
  "id": 7,
  "image": new URL('../assets/sun7.png', import.meta.url).href,
  "title": "BEHIND TREE TRUNKS AND BIG BUSHES",
  "time": "15:30",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "What better place to unwind than the forest. Curled up on the soft moss under a green sky with specks of blue, birds singing, leaves rustling. It all seems so quiet and peaceful, right? Well, look again. It’s buzzing with life in here. This forest is moist and fertile, smells of decay and young sprouts. Mushrooms shoot up, while big tits and woodcocks call for a mate. Put your ear against a tree and you’ll hear its juices flow and little creatures frantically path their way under its bark. Wanna play hide-and-seek with me? Find out who lives behind those brambles? Watch out, they’re sweet but will rip your clothes and stain your lips.",
    "nl": "Waar kun je nu beter ontspannen dan in het bos? Opgekruld op het zachte mos onder een blauwgespikkelde groene hemel, vogelzang en ruisend lover… Het lijkt allemaal zo vredig, nietwaar? Nou, kijk dan nog maar eens goed, want het bruist hier van leven. Dit bos is vochtig en vruchtbaar, het ruikt naar rottend blad en jonge scheuten. Paddenstoelen schieten uit de grond terwijl de paringsroep van roodborstjes, beflijsters, notenkrakers en braamsluipers tussen de bomen galmt. Leg je oor tegen een boomstam en je hoort hoe haar sap stroomt en hoe kleine beestjes zich verwoed een weg knagen onder haar bast. Zullen we verstoppertje spelen? Kijken wie zich achter die bramen verschanst? Pas op, ze zijn zoet, maar scheuren je kleren en verkleuren je lippen."
  },
  "description": `<p>
    <strong>Garden of Adams</strong> | Alex Mendo | 2025 | USA | 3’
    <br/>
    <strong>Fairies</strong> | HotHotHot Kollektiv | 2025 | Germany, France | 11’
    <br/>
    <strong>Vernal</strong> | Vesperal | 2025 | Canada | 5’
    <br/>
    <strong>Scribula</strong> | Andrew G., Tallulah B, Friedrich Kreuz | 2025 | Australia | 14’
    <br/>
    <strong>Butt monster</strong> | Arjun Lal | 2025 | Canada, Germany | 8’
    <br/>
    <strong>Dyke Deer</strong> | Bea Blue | 2025 | Germany | 17’
    <br/>
    <strong>The Pornithologist</strong> | José Pouchucq | 2024 | Chile, Spain | 9’
    <br/>
    <strong>Wealth of Whoredom</strong> | RedInsight.org | 2025 | Netherlands | 3’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 70 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 70 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20895"
},
{
  "id": 8,
  "image": new URL('../assets/sun8.png', import.meta.url).href,
  "title": "LOVE IS STRANGE",
  "time": "17:00",
  "place": "CliffordStudio",
  "text": {
    "en": "With clothes on and in public, most of us have the habit of behaving. A different story begins when the main door shuts and, even before the curtains are drawn, one starts to undress. Because sex is weird and when others are not watching, couples, throuples and more speak their most loving, most feral language. Shame gives way to trust and bodies become pieces of an ever-evolving mess. A tender, horny and deeply intimate ride.",
    "nl": "Met onze kleren aan en in het openbaar gedragen de meesten van ons zich keurig. Dat wordt een ander verhaal zodra de voordeur in het slot valt en we ons beginnen uit te kleden, nog voordat de gordijnen dicht zijn. Want seks is vreemd en wanneer er niemand meekijkt spreken koppels, throuples en anderen hun meest liefdevolle en dierlijke taal. Schaamte maakt plaats voor vertrouwen en lichamen smelten samen in een steeds veranderende wirwar. Een tedere, geile en diep intieme rit."
  },
  "description": `<p>
    <strong>Registros (postpornográficos) de la intimidad</strong> | Lola Pistola | 2025 | Spain | 10’
    <br/>
    <strong>Bunny Fairy Tales</strong> | Lilla & Tasa | 2025 | Netherlands | 19’
    <br/>
    <strong>Loving Wake-up</strong> | Ben Nordmann | 2024 | Netherlands | 12’
    <br/>
    <strong>The Elephant in the Room</strong> | abcde Flash | 2024 | Switzerland | 7’
    <br/>
    <strong>Flames</strong> | Michelle Rue | 2025 | Germany | 9’
    <br/>
    <strong>Thing</strong> | Ori Di Vincenzo | 2024 | Germany | 11’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 69 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 69 min + Q&A"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20942"
},
{
  "id": 9,
  "image": new URL('../assets/sun9.png', import.meta.url).href,
  "title": "<u>PERFORMANCE:</u><br/>FUAIM NA hAINGEAL",
  "time": "17:00",
  "place": {
    "en": "Theater de Richel: upstairs",
    "nl": "Theater de Richel: bovenzaal"
  },
  "text": {
    "en": "The body is transformed into a harp, with needles and hooks acting as the tuning pins, anchoring the harp-strings into the skin. Personal pain is plucked into sound, forming a communal sonic confrontation. Tension and release move through the performance, drawing performers and audience into the same space. The harp carries ancestral memory, and its resonance with industrial textures creates a mystical, subversive atmosphere. Pain and sound meet, a living ceremony in progress, where discomfort and ritual unfold.<br/><br/><strong>Arda (IO):</strong> formerly Unf4ir.io, brings together a plethora of styles. Utilising percussive samples reminiscent of electronic dance music, the result and mindset are clearly experimental.<br/><strong>møønmîlk (kiki kazimi):</strong> a visual artist working through performance, moving image and ritual, exploring pain, pleasure and intensity. Under møønmîlk, their sonic vessel, they summon sacred disorientation and re-enchantment.<br/><strong>Rick Jansen:</strong> experienced tattoo artist, piercer, body modifier will be the piercer for this performance. He has long-standing experience within body-mod culture and will ensure a safely executed performance.",
    "nl": "Het lichaam wordt getransformeerd tot een harp, met naalden en haken als stemsleutels die de harpsnaren in de huid verankeren. Persoonlijke pijn wordt omgezet in geluid, wat een gezamenlijke sonische confrontatie vormt. Spanning en ontspanning bewegen door de performance en trekken artiesten en publiek in dezelfde ruimte. De harp draagt voorouderlijke herinneringen met zich mee en de resonantie met industriële texturen creëert een mystieke, subversieve sfeer. Pijn en geluid ontmoeten elkaar in een levende ceremonie waarin ongemak en ritueel zich ontvouwen.<br/><br/><strong>Arda (IO):</strong> eerder bekend als Unf4ir.io, brengt een stortvloed aan stijlen samen. Percussiesamples doen denken aan electronic dance, het resultaat en de houding zijn altijd experimenteel.<br/><strong>møønmîlk (kiki kazimi):</strong> verkent als visuele kunstenaar pijn, genot en intensiteit door middel van performance, bewegend beeld en ritueel. Als møønmîlk, hun sonische schip, worden heilige desoriëntatie en hertovering opgeroepen.<br/><strong>Rick Jansen:</strong> is als ervaren tattoo-artiest, piercer en lichaamsvervormer de piercer in deze performance. Met zijn jarenlange ervaring in de lichaamsmodificatie-cultuur zorgt hij voor een veilige uitvoering van deze performance."
  },
  "description": {
    "en": "<strong>Fuaim Na hAingeal</strong> | Arda, møønmîlk & Rick Jansen | 30’ | Free entrance",
    "nl": "<strong>Fuaim Na hAingeal</strong> | Arda, møønmîlk & Rick Jansen | 30’ | Gratis toegang"
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": ""
},
{
  "id": 10,
  "image": new URL('../assets/sun10.png', import.meta.url).href,
  "title": "SOUND / SILENCE",
  "time": "18:00",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Do you also love to spy on your neighbours through the wall? Giggles, the curtains drawn shut, a zipping sound, shoes dropping on the floor, a sigh, a gasp, furniture moving, more giggles, a buzz, moaning, thumps, a long stretched humming, someone opening a window. Sound invokes images, colours our perception. Put a silly song under a hot movie and it turns into a comedy. In these films, sound takes the lead, liberates itself from the image and tells its own story. Let it whisper into your ear, leave a long meaningful silence and return vibrating into your body.",
    "nl": "Luister jij ook graag naar je buren? Gegiechel, gordijnen worden dichtgetrokken, iets ritst, vier doffe klappen op de vloer —schoenen? Een kreet, geschuif van meubels, meer gegiechel, gezoem, gekreun, gebonk, een langgerekt neuriën, iemand zet een raampje open. Geluid roept beelden op, kleurt onze waarneming. Zet een gek deuntje onder een geile film en het wordt vanzelf een komedie. In deze films speelt geluid de hoofdrol, bevrijdt zichzelf van het beeld en vertelt haar eigen verhaal. Ze fluistert in je oor, laat een lange betekenisvolle stilte vallen en keert dan zinderend terug in je lichaam."
  },
  "description": `<p>
    <strong>The Sound of your Body</strong> | Sakura Ardila Ortiz | 2024 | Colombia | 8’
    <br/>
    <strong>Ravine</strong> | Oat Montien | 2024 | USA | 6’
    <br/>
    <strong>Richard sucht Isolde</strong> | Daniel Rajcsanyi | 2025 | Austria | 15’
    <br/>
    <strong>Glimmer</strong> | Fennek Films | 2025 | Sweden | 2’
    <br/>
    <strong>Fluister voor me</strong> | Silkyway's Universe | 2025 | Netherlands | 3’
    <br/>
    <strong>Blue Movie</strong> | dw zero | 2025 | Greece | 1’
    <br/>
    <strong>Dissonance</strong> | Alex Mendo | 2025 | Netherlands | 3’
    <br/>
    <strong>Free-Fall</strong> | Ho Bin Kim | 2024 | Japan, South-Korea | 31’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 69 minutes + Q&A",
    "nl": "<strong>Totale duur:</strong> 69 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20897/sound-silence"
},
{
  "id": 11,
  "image": new URL('../assets/sun11.png', import.meta.url).href,
  "title": "NO MONEY NO HONEY",
  "time": "18:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Sex work is woven into our lives in more ways than we might realize. Because of the ways it’s often talked about and portrayed, it can be difficult to recognize the gifts that sex work can bring us, such as self discovery, healing and reconnection to the natural world. While society aims to “protect” and “save” sex workers, its practitioners are regularly found on the front lines of social struggles, like migrant solidarity, anti-gentrification and labor rights, while still engaging in a profession that’s constantly under pressure from legal threat and moral panic. Marginalized, sensationalized, demonized, these films created by sex workers seek not just to normalize the business, but to make clear that any of us could become sex workers, since we’ve all got bills to pay.",
    "nl": "Sekswerk is op meer manieren met ons leven verweven dan we misschien beseffen. Vaak wordt het werk zo besproken en afgeschilderd dat het lastig kan zijn om nog te zien wat voor moois sekswerk ons brengt: zelfontdekking, herstel of een hernieuwde band met onze natuur. Terwijl de maatschappij sekswerkers probeert te “beschermen” en “redden”, vind je de beoefenaars ervan vaak aan de frontlinies van sociale strijd. Ze vechten voor solidariteit met migranten, arbeidsrechten en tegen gentrificatie terwijl ze ondertussen zelf een beroep uitoefenen dat nog altijd onder zware druk staat van juridische dreiging en morele paniek. Gemarginaliseerd, gedemoniseerd en tot een sensatie gemaakt. Deze films, gemaakt door sekswerkers, willen hun beroep niet alleen normaliseren, maar ook duidelijk maken dat iedereen sekswerker zou kunnen worden omdat iedereen rekeningen te betalen heeft."
  },
  "description": `<p>
    <strong>Knots of Self</strong> | Laura Ropes | 2025 | Austria | 17’
    <br/>
    <strong>The Eternal Whore. Regulation of Sex Work Through History</strong> | Rori Dior & Diego Gómez | 2024 | Germany | 12’
    <br/>
    <strong>Pussy Honey (Miel de Concha)</strong> | Juli Puch | 2025 | Chile | 6’
    <br/>
    <strong>Am I Calling You At A Bad Time?</strong> | Martta Tuomaala | 2025 | Finland | 15’
    <br/>
    <strong>Just For Piss</strong> | Menelas | 2025 | Greece | 10’
    <br/>
    <strong>Dyson</strong> | Clac and Fara Renaud | 2025 | Belgium | 15’
    <br/>
    <strong>Wealth of Whoredom</strong> | RedInsight.org | 2025 | Netherlands | 3’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 78 minutes",
    "nl": "<strong>Totale duur:</strong> 78 min"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": ""
},
{
  "id": 12,
  "image": new URL('../assets/sun12.png', import.meta.url).href,
  "title": "<u>FEATURE FILM:</u><br/>TRUTH OR DARE",
  "time": "20:00",
  "place": "CliffordStudio",
  "text": {
    "en": "“Truth, or dare?” Which one would you pick? In the past, I always chose ‘truth’, fearing that taking the ‘dare’ would get me into some troublesome and humiliating situation. I quickly found out though, that simply telling the truth can be just as intense, thrilling, painful, exhilarating, bonding and ultimately liberating as taking on the craziest dare. This beautiful documentary asks the same question to its performers, after which they share their truths and complete their dares in the most intimate way. Truth or Dare is about self discovery, connection, sexuality, interpersonal relationships and healing after difficult life events. You bravely choose ‘dare’? I dare you to come see this film.",
    "nl": "'Doen, durven of de waarheid?' Wat zou jij kiezen? Vroeger koos ik altijd voor 'waarheid' uit angst dat het 'durven en doen' tot een vernederende situatie zou leiden. Maar ik kwam er al snel achter dat het vertellen van de waarheid net zo intens, spannend, pijnlijk, opwindend, verbindend en uiteindelijk bevrijdend kan zijn als het aangaan van de meest krankzinnige uitdaging. Deze prachtige documentaire stelt aan alle performers dezelfde vraag, waarna ze hun waarheden delen en uitdagingen op de meest intieme manier aangaan. Truth or Dare gaat over zelfontdekking, verbinding, seksualiteit, interpersoonlijke relaties en herstel na moeilijke levensgebeurtenissen. Koos jij dapper voor ‘durven’? Dan daag ik je uit om deze film te komen kijken."
  },
  "description": `<p>
    <strong>Truth or Dare</strong> | Maja Classen | 2024 | Germany | 79’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 79 minutes",
    "nl": "<strong>Totale duur:</strong> 79 min"
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20944"
},
{
  "id": 13,
  "image": new URL('../assets/sun13.png', import.meta.url).href,
  "title": "<u>FEATURE FILM:</u><br/>JANINE MOVES TO THE COUNTRY",
  "time": "20:30",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Janine and her boyfriend decide to change their Berlin plattenbau apartment for a house in the countryside. But the picturesque landscape cannot hide a plain truth: the villagers receive them with clear-cut hostility. For their neighbour Peter, however, Janine’s presence means something entirely different. Overwhelmed by domestic struggles with an overworked mother and disabled brother, he sees his sexual desires awakened and begins to make clumsy, inappropriate advances. Campy, dark and musical, Janine moves to the Country is a story about sexual vigilance in small communities and the realities of breaking away from those around you.",
    "nl": "Janine en haar vriend besluiten hun Berlijnse plattenbau-appartement te verruilen voor een huis op het platteland. Maar het pittoreske landschap kan de onmiskenbare realiteit niet verhullen: de dorpelingen ontvangen hen met onverholen vijandigheid. Maar voor hun buurman Peter betekent de aanwezigheid van Janine iets heel anders. Overweldigd door huiselijke problemen, een overwerkte moeder en een gehandicapte broer ziet hij zijn seksuele verlangens ontwaken en begint hij onhandige, ongepaste avances te maken. Janine Moves to the Country is een campy, donker en diep verhaal over seksuele controle in kleine gemeenschappen en de moeilijke beslissing om los te breken van de mensen om je heen."
  },
  "description": `<p>
    <strong>Janine Moves to the Country</strong> | Jan Eilhardt | 2025 | Germany | 74’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 74 minutes",
    "nl": "<strong>Totale duur:</strong> 74 min"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20901"
},
{
  "id": 14,
  "image": new URL('../assets/sun14.png', import.meta.url).href,
  "title": "<u>WORKSHOP:</u><br/>ANAL FISTING",
  "time": "14:00 – 16:00",
  "place": "CliffordStudio",
  "text": {
    "en": "In the workshop we will give an overview of anal anatomy, talk about the philosophical aspect of fisting, give the lowdown on lube and other anal aides, and give a demonstration. After the demonstration, folks who would like to stay and practice with our input are welcome to do so, but should be aware that the venue does not have a shower. This workshop is directed to people who are interested in anal fisting, but who might not have access to the regular spaces. We will put effort into making this a safe and welcoming space for AFABs. <br/><br/><strong>NB:</strong> Bring your own yoga mat and towel. If you wish to practice, please bring your own partner.<br/><br/><strong>Arnaud</strong> brings over 40 years of practicing fisting within gay communities, approaching the practice as a sexual exploration and philosophy of freedom. Arnaud’s work is rooted in respect, care, safety and understanding.<br/><br/><strong>Kjetil</strong> is a non-binary weirdo with some 30 years experience in advanced anal play with AFAB and non-cis people, exploring the various dynamics within gender expression in both workshops and informal settings.",
    "nl": "In deze workshop bespreken we de filosofische aspecten van fisting, krijg je een overzicht van anale anatomie, updates over glijmiddel en geven we een demonstratie. Iedereen die na de demonstratie zelf wil oefenen is welkom, maar hou er rekening mee dat er geen douche is. Deze workshop is bedoeld voor mensen die geïnteresseerd zijn in anaal fisten maar zich misschien minder thuis voelen in de gebruikelijke ruimtes. We doen er alles aan om deze ruimte veilig te maken voor AFABs.<br/><br/><strong>NB:</strong> Neem je eigen yogamat en handdoek mee. Als je wilt oefenen, neem dan een partner mee.<br/><br/><strong>Arnaud</strong> heeft meer dan 40 jaar ervaring met fisten in homo-gemeenschappen en benadert het thema als een vorm van seksuele exploratie en vrijheidsfilosofie. Arnaud’s werk is gefundeerd op respect, zorg, veiligheid en begrip.<br/><br/><strong>Kjetil</strong> is een non-binaire weirdo met meer dan 30 jaar ervaring in geavanceerd anaal spel. In workshops en informele settingen verkent Kjetil de verschillende dynamieken in genderexpressie met AFAB en non-cis personen."
  },
  "description": {
    "en": "<strong>Anal fisting workshop</strong> | 2 hours<br/><strong>Maximum participants:</strong> 16",
    "nl": "<strong>Anal fisting workshop</strong> | 2 uur<br/><strong>Maximum aantal deelnemers:</strong> 16<br/><strong>Voertaal:</strong> Engels"
  },
  "duration": {
    "en": "",
    "nl": ""
  },
  "imagelogo": new URL('../assets/CLIFFORD.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20950"
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