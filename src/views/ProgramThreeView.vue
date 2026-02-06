<script setup lang="ts">
import { BImg, BRow, BCol, BContainer, BFormCheckbox } from 'bootstrap-vue-3';
import { ref, computed } from 'vue'; 
import ProgramItem from '../components/ProgramItem.vue'
const background = new URL('../assets/friday_background_2.png', import.meta.url).href

// Set default language
const currentLang = ref<'en' | 'nl'>('en');

// Toggle function
const toggleLang = () => {
  currentLang.value = currentLang.value === 'en' ? 'nl' : 'en';
};

const translations = {
  en: {
    day: "Friday",
    date: "27 February 2026"
  },
  nl: {
    day: "Vrijdag",
    date: "27 Februari 2026"
  }
};

const agenda = [
{
  "id": 1,
  "image": new URL('../assets/friday1.png', import.meta.url).href,
  "title": "DAYDREAMS",
  "time": "12:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Remember those summer days, waking up from a hot dream that oozes out over your whole afternoon? Coming back home from a stroll through the dusty streets, where your shirt sticks to your nipples, the door knob feels pleasantly firm, a little drop of sweat runs down your spine like a cold tongue and the flower vase never looked this sensual before. You don’t know whether you are sleepy or horny, so you take a quick bath and slip back into bed with the window open to float between dreams and desire. Your body feels so good between the cool sheets…",
    "nl": "Zo’n zomerdag waarop je wakker wordt uit een hete droom die stroperig uitvloeit over de rest van je middag… Terug van een rondje door de stoffige straten kleeft je shirt aan je tepels, de deurknop ligt aangenaam stevig in je hand, een kleine zweetdruppel loopt als een koude tong over je rug en die vaas op tafel heeft plots wel heel verleidelijke welvingen. Ben je nou slaperig of geil? Je duikt even in bad en glijdt dan terug je bed in met het raam wijd open, om een nog tijdje te rond te dobberen tussen dromen en verlangens. Je lichaam voelt zo lekker tussen de koele lakens…"
  },
  "description": `<p>
    <strong>Hail Mary</strong> | Blake Baptiste | 2024 | Canada | 5’
    <br/>
    <strong>Chulicha</strong> | Sonia Patrinou | 2025 | Greece | 15’
    <br/>
    <strong>In love with a satyr</strong> | Sylvia Robyn Gionti | 2025 | Greece | 5’
    <br/>
    <strong>:// submersion</strong> | Twyla Twilight, Emma Grima | 2025 | Netherlands | 15’
    <br/>
    <strong>Buenos Aires</strong> | Evita, Emanuel and Jane June | 2024 | Argentina / Belgium | 8’
    <br/>
    <strong>Lesbian Fantasies</strong> | Goodyn Green & Jasko Fide | 2025 | Germany | 14’
    <br/>
    <strong>Mating Season</strong> | Juan Saez / Heavy Load Studio | 2025 | Germany | 9’
  </p>`,
"duration": {
  "en": "<strong>Total duration:</strong> 71 min + Q&A",
  "nl": "<strong>Totale duur:</strong> 71 min + Q&A"
},
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/agenda/20883"
},
{
  "id": 2,
  "image": new URL('../assets/friday_2.png', import.meta.url).href,
  "title": "FULL EXPOSURE",
  "time": "15:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Caught on camera: a picture you’ll never forget. We save our memories on film and project our emotions onto them like a music score. But a camera is not just a gateway to the past. It’s also a presence connecting us to the future. Even when shooting a home-made solo film, there’s always this red eye in a corner of the room, registering indifferently. Scrutinizing every move and moan. Mirroring us in all our imperfections. The reminder of a spectator in a different place and time. Or did we become the spectator ourselves? Do we move differently knowing we’ll be screened? Let’s zoom in on the camera, stare back into its silent eye. We’ll be watching you too.",
    "nl": "Vastgelegd op camera: een beeld dat je nooit meer vergeet. We bewaren onze herinneringen op film en projecteren daar onze emoties als een soundtrack overheen. Maar een camera is niet alleen een toegangspoort tot het verleden. Het is ook een aanwezigheid die ons met de toekomst verbindt. Zelfs als je thuis een solofilm opneemt is er altijd nog dat rode oog in een hoek van de kamer dat je onverschillig opneemt. Zelfs de kleinste beweging en kreun registreert. Ons spiegelt in al onze imperfecties. Het is de herinnering aan een toeschouwer in een andere tijd en plaats. Of zijn we zelf onze toeschouwer geworden? Bewegen we anders in de wetenschap dat we vertoond zullen worden? Laten we inzoomen op de camera, terugstaren naar dat stille oog: cameratoezicht."
  },
  "description": `<p>
    <strong>Blue Movie</strong> | dw zero | 2025 | Greece | 1’
    <br/>
    <strong>Embrasse-moi du Regard</strong> | Diamonds Bitch & Saphir Cocks | 2024 | Belgium | 21’
    <br/>
    <strong>No Refunds</strong> | Adamska Elizaveta Rakhilkina | 2025 | USA, Germany | 8’
    <br/>
    <strong>GLITCH</strong> | Alexandre Medeiros | 2023 | Brazil | 17’
    <br/>
    <strong>Echo Chamber</strong> | Four Chambers | 2025 | UK | 14’
    <br/>
    <strong>CAM GIRLS</strong> | Malena Masuelli & Loana Faerman | 2025 | Argentina | 5’
    <br/>
    <strong>Y2KAGE: Jacked Out</strong> | Jazzy Boho | 2025 | USA | 8’
  </p>`,
  "duration": {
      "en": "<strong>Total duration:</strong> 82 min + Q&A",
      "nl": "<strong>Totale duur:</strong> 82 min + Q&A"
    },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20918"
},{
  "id": 3,
  "image": new URL('../assets/friday_3.png', import.meta.url).href,
  "title": "FEATURE FILM: BEHIND THE OPEN DOOR",
  "time": "17:00",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Todd Verow documents a cum dump during a night in which he lets more than 20 men fuck and fill him with cum in a hotel room. With an unflinching, observational gaze, the camera captures the action while Corey narrates off-screen, sharing how he prepares for his sessions in different cities, offering practical advice and reflecting on his life as a cum dump. Candid, unapologetic and surprisingly informative, the film offers insight into a growing cum dump community.",
    "nl": "Todd Verow filmt een cum dump in een hotelkamer waar meer dan twintig mannen hem één nacht lang mogen nemen en opvullen. Met een nietsontziende, observerende blik legt de camera de actie vast terwijl Corey – wiens films ook online staan – buiten beeld vertelt hoe hij zich op zijn eigen sessies voorbereidt, praktische tips geeft en reflecteert over een leven als cum dump. Deze openhartige, onbeschaamde en verrassend informatieve film biedt een inkijkje in een groeiende cumdumpgemeenschap."
  },
  "description": `<p>
    <strong>Behind The Open Door</strong> | Todd Verow, James Kleinmann | 2025 | USA | 70’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 70 min",
    "nl": "<strong>Totale duur:</strong> 70 min"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/agenda/20885"
},
{
  "id": 4,
  "image": new URL('../assets/friday_4.png', import.meta.url).href,
  "title": "TRANSCENDING THE FLESH",
  "time": "18:00",
  "place": "Theater de Richel",
  "text": {
    "en": "Let’s submerge in a world not centered in us, humans. Where pornography transcends the flesh with performers not made out of organs, but of pixels, metal, data and plastic. Where pleasure is glitched, extra-terrestrial and takes place at the end of our human times. This film block is an invitation to transcend earthly delights. We will travel through the metaverse, accompanied by robots and aliens, landing in unexpected parts of the cosmos.",
    "nl": "Dompel jezelf onder in een wereld die niet meer alleen om mensen draait. Waar porno het menselijk lichaam ontstijgt en performers niet langer gemaakt zijn van vlees en bloed, maar uit pixels, metaal, data en plastic bestaan. Genot is hier een soort buitenaardse kortsluiting die plaatsvindt aan het einde van de mensheid. Dit is een uitnodiging om je aardse geneugten te overstijgen. Vergezeld door robots en ruimtewezens reizen we het metaversum af en landen we onderweg op verbazingwekkende plekken in de kosmos."
  },
  "description": `<p>
    <strong>Guided Meditation</strong> | Desirée Alagna | 2024 | Italy | 6’
    <br/>
    <strong>( CON - TACTOS )</strong> | Julu Martínez | 2024 | Spain | 7’
    <br/>
    <strong>alt.sex.fetish.robots</strong> | Zed Sheng | 2025 | USA, Thailand | 5’
    <br/>
    <strong>The Stage of Flesh</strong> | Alessandro Amaducci | 2025 | Italy | 7’
    <br/>
    <strong>Your REAL Companion</strong> | Officer Flower, Iris Glitzer | 2025 | Germany | 13’
    <br/>
    <strong>Y2KAGE</strong> | Jazzy Boho | 2025 | USA | 8’
    <br/>
    <strong>Close Encounters of the Sexth Kind</strong> | Werther Germondari | 2025 | Italy | 7’
    <br/>
    <strong>Planet Anthurium</strong> | Dario Campo, Loup Deflandre, Zélie Dartus-Parraud | 2025 | Germany | 16’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 71 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 71 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20912"
},
{
  "id": 5,
  "image": new URL('../assets/friday_5.png', import.meta.url).href,
  "title": "PHANTOM LOVE",
  "time": "19:30",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Can you desire someone who isn’t there? Ghosts of the past, people we never met in person, someone who only lives in our memories, frozen in time. Separated from us by oceans, borders, death, break-ups and other foul plot twists of life. How to love them in the face of their silence? Are we still allowed to imagine them naked, continue the conversation, look through the traces they left behind? A smell on our skin, scribbles in the sidelines of a book, a song, a hair, a voice note. Phantom loves we still feel near in their absence.",
    "nl": "Kun je iemand begeren die er niet is? Schimmen uit het verleden. Mensen die we nooit hebben ontmoet. Iemand die alleen nog in onze herinnering leeft, bevroren in de tijd. Van ons gescheiden door zeeën, grenzen, tijd, de dood of andere wrede plotwendingen van het leven. Hoe heb je ze lief als zij maar blijven zwijgen? Mogen we nog terugdenken aan hun naakte lijven, het gesprek voortzetten, ze zoeken in de sporen die ze achterlieten? Een geur op onze huid, krabbels in de kantlijn van een boek, een liedje, een haar, een spraakbericht. Fantoomliefdes die zo nabij voelen in afwezigheid."
  },
  "description": `<p>
    <strong>Untie</strong> | Oat Montien | 2023 | USA / Thailand | 5’
    <br/>
    <strong>Lost Belongings 유실물</strong> | Jaewon Cho | 2025 | South Korea | 10'
    <br/>
    <strong>Les fantômes du hard</strong> | Lazare Lazarus | 2025 | France | 28’
    <br/>
    <strong>Fluister voor me</strong> | Silkyway’s Universe | 2025 | Netherlands | 3’
    <br/>
    <strong>Annihilation</strong> | Cris Noon | 2023 | USA | 5’
    <br/>
    <strong>Unraveling Pleasure On Distance</strong> | L_i_l_a_k_i & Vili XG | 2024 | Greece | 6’
    <br/>
    <strong>Embrasse-moi du Regard</strong> | Diamonds Bitch, Saphir Cocks | 2024 | Belgium | 22’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 80 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 80 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20887"
},
{
  "id": 6,
  "image": new URL('../assets/friday_6.png', import.meta.url).href,
  "title": "WHAT A TIME TO BE (A)LIVE!",
  "time": "21:00",
  "place": "Theater de Richel",
  "text": {
    "en": "For a long time, you were only allowed to consume, not create. Desire was packaged by big studios that decided what you should want. So we learned to accept and desire what was offered. Then the internet arrived... and with that: cam models and independent creators. Suddenly, you could help shape your own fantasies: direct scenes, write scripts and connect with someone who truly reflects your desires. This shift changed lives on both sides of the screen. Clients meet themselves more honestly. Creators gain community, agency and possibility for authentic expression. Now, step into the worlds of seven different creators and discover what makes them feel (a)live.\n\nGuest Curator: Christina Castalia - Internationally-awarded cam model, creator and thought leader in erotica.\nSupported by: Kiiroo",
    "nl": "Lange tijd was het alleen toegestaan om te consumeren, niet om te creëren. Verlangen werd verpakt door grote studio’s die bepaalden wat je zou moeten willen. Dus leerden we om het aanbod te accepteren en verlangen. En toen kwam het internet… en daarmee ook cammodellen en onafhankelijke makers. Ineens kon je je eigen fantasieën vormgeven: scènes regisseren, scripts schrijven en in contact komen met iemand die jouw werkelijke verlangens weerspiegelt. Deze verschuiving veranderde levens aan beide kanten van het scherm. Klanten komen zichzelf op eerlijker manier tegen. Makers krijgen een publiek, agentschap en de mogelijkheid om zich op authentieke manier uit te drukken. Stap in de werelden van zeven verschillende makers en ontdek waarom ze live en vol leven zijn.\n\nGastprogrammeur: Christina Castalia - internationaal bekroond cammodel, maker en autoriteit op het gebied van erotiek. \n\nMet steun van: Kiiroo"
  },
  "description": `<p>
    <strong>Open Eyes, Twisted Cries</strong> | Mila / Lustful Orchid ft. Miss Suzanna Maxwell | 2025 | UK | 11’
    <br/>
    <strong>Pleasure Engineer</strong> | Christina Castalia | 2025 | Netherlands | 11’
    <br/>
    <strong>The birth of a sexual Goddess</strong> | Chayenne Johnson | 2025 | Netherlands | 4’
    <br/>
    <strong>Ten Years Live</strong> | Lydia Love | 2025 | USA | 8’
    <br/>
    <strong>Vanniall & Jaq Quicksilver</strong> | Vannial & Ashley Lake ft. Jaq Quicksilver | 2025 | Netherlands | 11’
    <br/>
    <strong>Why Can't Porn Be Beautiful Too?</strong> | Leila Lewis | 2025 | USA | 6’
    <br/>
    <strong>Little Puck's Monster Mash</strong> | Little Puck | 2024-2026 | USA | 10’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 61 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 61 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20919"
},
{
  "id": 7,
  "image": new URL('../assets/friday_7.png', import.meta.url).href,
  "title": "DON’T LOOK AWAY",
  "time": "22:00",
  "place": "Filmhuis Cavia",
  "text": {
    "en": "Sometimes we use film to escape. And even more often, we use porn for the same reason. To dissociate. To be someone else. Somewhere else. With someone else. To feel something… anything… other than what’s there. But not in this block. Here, there will be no escaping. We will confront disease, pain, pleasure, disability, loneliness and disgust. We invite you - warmly, sincerely - not to look away.",
    "nl": "Soms kijken we films om even te ontsnappen aan de wereld. En porno gebruiken we al helemaal om die reden. Om even los te komen. Iemand anders te worden. Ergens anders te zijn, met iemand anders. Iets te voelen… wat dan ook… alles behalve het alledaagse. Zo niet in dit blok. Hier is geen ontsnappen aan. Hier kijken we alles recht in de ogen: pijn, lust, obstakels, eenzaamheid, walging. Dit is een warme, hartelijke uitnodiging om niet weg te kijken."
  },
  "description": `<p>
    <strong>Mirrored</strong> | Lola Pistola and Rafal Żwirek | 2025 | Poland, Spain | 21'
    <br/>
    <strong>sexy plumber</strong> | maja m tekla | 2024 | Poland | 2'
    <br/>
    <strong>Fisting Club: Episode 1</strong> | Shu Lea Cheang | 2019 | France, Germany | 12'
    <br/>
    <strong>Forced Outing</strong> | Jan Soldat | 2025 | Germany | 11'
    <br/>
    <strong>Glimmer</strong> | Fennek Film | 2025 | Sweden | 2'
    <br/>
    <strong>Lost Belongings 유실물</strong> | Jaewon Cho | 2025 | South Korea | 10'
    <br/>
    <strong>Faces of Pain</strong> | L. H. Bararian and Fawn | 2025 | Netherlands | 25'
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 83 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 83 min + Q&A"
  },
  "imagelogo": new URL('../assets/CAVIA.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20905"
},
{
  "id": 8,
  "image": new URL('../assets/friday_8.png', import.meta.url).href,
  "title": "NIGHTDREAMS",
  "time": "23:00",
  "place": "Theater de Richel",
  "text": {
    "en": "For most mortals, it is way past bedtime and you cannot fall asleep. You’ve been here before but, this time, sleeplessness presents itself as an irresistible chance. Because in the small hours, feelings are more intense. Monsters and misfits loom in the half-light and when you meet them, you know right away that you belong to their kind. So you put on your leather boots and hit the town, wander through an abandoned circus and walk down to the basement of your local sex club. Sleep will come, but not before you squeeze out the night.",
    "nl": "Voor de meeste stervelingen is het allang bedtijd geweest, maar jij kan de slaap niet vatten. Dat ben je wel gewend, maar dit keer schuilt er in je slapeloosheid een onweerstaanbare kans. Want in de kleine uurtjes voel je alles heviger. Monsters en zonderlinge figuren doemen op uit het halfduister en zodra je ze ziet, voel je dat je een van hen bent. Je trekt je laarzen aan en loopt de stad in, dwaalt door een verlaten circus en daalt tenslotte af naar de kelder van je lokale seksclub. De slaap zal wel komen, maar niet voordat je de nacht tot aan haar laatste gitzwarte druppel hebt opgeslokt."
  },
  "description": `<p>
    <strong>Pillowcore</strong> | Nisa East & Rosie Always | 2025 | Australia | 9’
    <br/>
    <strong>Insomnia Incubus</strong> | Nick Bottom | 2024 | Germany | 6’
    <br/>
    <strong>The Nightmare</strong> | Phil Paris & Monsterbait | 2025 | France | 8’
    <br/>
    <strong>DREAMY DEVIANT</strong> | Alexandre Medeiros | 2024 | Brazil | 20’
    <br/>
    <strong>The Visitor</strong> | Angelssex | 2025 | Spain | 4’
    <br/>
    <strong>Close Encounters of the Sexth Kind</strong> | Werther Germondari | 2026 | Italy | 7’
    <br/>
    <strong>Resurrect Me as a Parasite</strong> | Gabi Dao & Lou Lou Sainsbury | 2025 | Netherlands | 9’
    <br/>
    <strong>The Sweet Escape</strong> | Max Broht | 2025 | Austria | 4’
    <br/>
    <strong>After Party</strong> | Jan Soldat | 2025 | Germany | 9’
  </p>`,
  "duration": {
    "en": "<strong>Total duration:</strong> 75 min + Q&A",
    "nl": "<strong>Totale duur:</strong> 75 min + Q&A"
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20920/nightdreams"
},{
  "id": 9,
  "image": new URL('../assets/friday_9.png', import.meta.url).href,
  "title": "<u>WORKSHOP:</u><br/>FUCK THE FASCISM: CONSPIRACY GATHERING",
  "time": "12:00 – 15:00",
  "place": "Prostitution Information Center",
  "text": {
    "en": `Fuck the Fascism is a series of decolonial actions made into short films led by Valentina Pantheon (aka MariaBasura). From Germany, to Spain, and Chile, the call for conspiracy arrives in Amsterdam, where Valentina is joined by JorgeTheObscene. The workshop consists of two sessions where participants will co-create the Amsterdam edition of this series. From researching, discussing and ideas to shooting the film. <br/><br/>
           While the participation of migrants and non-white people is strongly encouraged, this space welcomes all possible allies. Are you an experienced researcher, performer, sound person, editor, photographer, or want to learn through a collective political process any of these roles? This is your chance! <u><strong>Previous film making experience is not necessary.</strong></u><br/><br/>
           <ul>
             <li><strong>Friday 27:</strong> we watch the previous episodes of the project together, discuss the ideas for the new episode and plan its shooting together</li>
             <li><strong>Saturday 28:</strong> shooting of the new episode</li>
           </ul><br/>
           <strong>JorgeTheObscene</strong> is a Chilean pornographer, performer, film curator, therapist and sex worker, currently based in Europe. Since 2014 he has been part of the queer/alternative porn scene as producer, performer and editor in several films.<br/><br/>
           <strong>Valentina del Pantheon (formerly known as MariaBasura)</strong> is a South American Monstrosity and social agitator. Actress, performer, dancer, sex worker, independent filmmaker and fetish accessories designer.`,
    "nl": `Fuck the Fascism is een reeks dekoloniale, publieke acties, uitgevoerd en gefilmd door Valentina Pantheon (eerder bekend als MariaBasura). Na van Duitsland naar Spanje en Chili te zijn gereisd, bereikt deze oproep tot samenzwering Amsterdam, waar ook filmmaker JorgeTheObscene zich aansluit. <br/><br/>
           Deze workshop bestaat uit twee sessies waarin de deelnemers samen de Amsterdamse film in de reeks zullen maken. Onderzoek, ideeën en overleg in de sessie op vrijdag leiden tot het maken van een korte film in de sessie op zaterdag.<br/><br/>
           Hoewel de deelname van migranten en niet-witte mensen sterk wordt aangemoedigd, zijn alle mogelijke bondgenoten welkom om mee te doen. Ben je een ervaren onderzoeker, performer, editor, geluids- of camerapersoon? Of wil je dat juist leren in een collectief en politiek proces? Dan is dit je kans!<br/><br/>
           <strong>JorgeTheObscene</strong> (hij/hem) is een Chileense pornograaf, performer, filmprogrammeer, therapeut en sekswerker, die momenteel gevestigd is in Europa. Hij maakt sinds 2014 deel uit van de queer/alternatieve pornoscene als producer, performer en editor in verschillende films.<br/><br/>
           <strong>Valentina del Pantheon</strong> (zij/hen, eerder bekend als MariaBasura) is een Zuid-Amerikaanse Monstruositeit en sociaal agitator. Actrice, performer, danser, sekswerker, onafhankelijk filmmaker en ontwerper van fetish accessoires.`
  },
  "description": {
    "en": "<strong>Fuck the Fascism</strong> | Valentina del Pantheon & JorgeTheObscene | 3h + film shoot on Saturday<br/><br/><strong>Max. participants:</strong> 20<br/><strong>Language:</strong> English",
    "nl": "<strong>Fuck the Fascism</strong> | Valentina del Pantheon & JorgeTheObscene | 3h + filmopnames op zaterdag<br/><br/><strong>Maximaal aantal deelnemers:</strong> 20<br/><strong>Voertaal:</strong> Engels"
  },
  "duration": {
    "en": "<strong>Total duration:</strong> 3h + film shoot on Saturday",
    "nl": "<strong>Totale duur:</strong> 3h + filmopnames op zaterdag"
  },
  "imagelogo": new URL('../assets/PIC.png', import.meta.url).href,
  "ticket": "https://amsterdamalternative.nl/tickets/20921"
},
{
  "id": 10,
  "image": new URL('../assets/friday_10.png', import.meta.url).href,
  "title": "<u>INSTALLATION:</u><br/>A SHAMEFUL MIND",
  "time": {
    "en": "Friday – Sunday",
    "nl": "vrijdag tot zondag"
  },
  "place": {
    "en": "Theater de Richel: upstairs",
    "nl": "Theater de Richel: bovenzaal"
  },
  "text": {
    "en": "How far can shame and penance be commodified? And how much does it cost to be free from sin? The architectural installation ”A Shameful Mind” satirically explores shame within a Christian context. In the shape of a confessional booth, the installation invites the visitor to kneel and assume a pose of humility. But instead of asking for forgiveness, there is ownership, an embodiment of righteousness and authority.<br/><br/><strong>Anamar.jpg</strong>, a Romanian-born architect based in the Netherlands, works across research, visual arts and design. She explores themes such as gender, societal patterns and folklore.",
    "nl": "In hoeverre kunnen schaamte en boetedoening gecommodificeerd worden? En wat kost het om vrij van zonden te zijn? De architecturale installatie “A Shameful Mind” is een satirische verkenning van schaamte in christelijke context. In de vorm van een biechtstoel nodigt de installatie bezoekers uit om te knielen en een nederige houding aan te nemen. Maar in plaats van vragen om vergiffenis, is er eigenaarschap, een belichaming van gerechtigheid en autoriteit.<br/><br/><strong>Anamar.jpg</strong> werd in Roemenië geboren en is als architect gevestigd in Nederland. In haar onderzoek, ontwerp en visuele kunst verkent ze thema’s als gender, sociale patronen en folklore."
  },
  "description": {
    "en": "<strong>A Shameful Mind</strong> | @anamar.jpg | Installation",
    "nl": "<strong>A Shameful Mind</strong> | @anamar.jpg | Installatie"
  },
  "duration": {
  },
  "imagelogo": new URL('../assets/RICHEL.png', import.meta.url).href,
  "ticket": ""
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