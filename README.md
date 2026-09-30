Winter Arc: The Gu Master's 90 Days
A 90-day habit and goal tracker styled as a cultivation system from the web novel Reverend Insanity. Complete daily tasks to gather primeval essence, break through 90 levels across nine ranks, survive tribulations, and finish the arc as a Gu Immortal.

An unofficial fan project inspired by Reverend Insanity by Gu Zhen Ren. It is not affiliated with the author or any publisher. All maxims in the app are original.

Contents
What it is
Quick start
Installing on a phone
How the system works
Screens
Data and privacy
Customizing
Building a real APK
Project structure
Known limitations
Credits
What it is
Winter Arc turns a 90-day self-improvement challenge into a progression game.

90 levels for 90 days: one level for each 100 essence, and a perfect day is worth about 100.
9 ranks with 10 levels each. Ranks 1 to 5 are Gu Masters, ranks 6 to 9 are Gu Immortals.
Daily tasks you can edit freely (defaults: training, deep work, study, clean eating, cold shower, journaling, sleep).
Tribulations that guard each rank and force one hard real-life challenge before you can advance.
Novel mechanics: aptitude grade, vital Gu, Spring Autumn Cicada rewinds, primeval stones, and Dao marks.
It is a single self-contained HTML file with no build step and no backend.

Quick start
Open winter-arc-cultivation.html in any modern browser, or open the hosted link if you were given one.
Complete the Awakening Ceremony: enter your name, start date, up to three goals, an aptitude grade and a vital Gu.
Each day, tap your tasks on the Today tab as you finish them.
Watch the aperture fill, level up, and face each tribulation when you reach a Peak stage.
Installing on a phone
Android (Chrome): open the page, tap the three-dot menu, then choose Add to Home Screen or Install app. It opens full screen with its own icon.

iPhone (Safari): open the page, tap Share, then Add to Home Screen.

For a true .apk file, see Building a real APK.

How the system works
Essence and levels
Every task has a weight. Your daily essence is the share of total weight you completed, out of 100.

Every 100 essence raises your level by one, up to level 90.
Rank and stage come from your level: levels 1 to 3 are Initial, 4 to 6 Middle, 7 to 9 Upper, and 10 is Peak (repeating for each rank).
The aperture on the Today tab fills as you progress through the current level. The ring of 90 ticks shows each day of the arc: bright means cleared, amber means partial, dark red means missed, gold is today.
Ranks
Rank	Type	Essence
1	Gu Master	Green Copper primeval essence
2	Gu Master	Red Steel primeval essence
3	Gu Master	White Silver primeval essence
4	Gu Master	Yellow Gold primeval essence
5	Gu Master	Purple Crystal primeval essence
6	Gu Immortal	Green Grape immortal essence
7	Gu Immortal	Red Date immortal essence
8	Gu Immortal	White Litchi immortal essence
9	Gu Immortal	Yellow Apricot immortal essence
Tribulations and bottlenecks
When you reach the Peak level of a rank (10, 20, 30 and so on), extra essence keeps building but you cannot advance until you complete that rank's tribulation, a one-off real-life challenge. Marking it done gives +100 essence and +50 stones.

Rank	Tribulation	Challenge
1	Beast Tide of Qing Mao Mountain	One full day: 100% of tasks, no junk food or scrolling, in bed on time
2	The Flower Wine Monk's Inheritance	Finish one real deliverable toward your main goal
3	The Elder Assessment	Set a benchmark (timed run, test, max lift) and record it
4	The Road to Overlord	One uninterrupted 4-hour deep work block
5	Immortal Ascension: Earthly Calamity	Do the task you fear most first thing, then 10 minutes of cold exposure
6	Heavenly Tribulation	A 48-hour dopamine fast
7	Grand Tribulation	Teach someone or publish a real result
8	Myriad Tribulation	A hard physical event or personal best
9	Chaos Tribulation: The Eternal Life Trial	Write your 90-day retrospective and next-arc plan
Completing rank 9's tribulation at full progress grants Eternal Life, the end of the arc.

Aptitude grade
Chosen once, at the start. It sets how strict the game is.

Grade	A day counts as cleared at	Starting Cicada charges
D	50%	4
C	60%	3
B	70%	3
A	85%	2
A cleared day feeds your streak and lights the day tick.

Vital Gu
Chosen once, and it stays with you.

Liquor Worm: a perfect 100% day gives +10 bonus essence.
Moonlight Gu: your heaviest task gives 50% more essence.
Jade Skin Gu: your streak survives days up to 20 points below your clear line.
Spring Autumn Cicada
The Cicada rewinds time. On the Days tab, tap any past day that was not perfect and spend one Cicada to reopen it and complete its tasks. This cannot be undone. You can hold at most 5.

Primeval stones
Stones are earned, not bought: 10 stones per 100 essence, plus 50 per tribulation. Spend 150 stones in the Sect tab to refine another Cicada.

Dao marks
Every task belongs to a Dao path (Strength, Wisdom, Information, Food, Ice-Snow, Moon, Dream, Time). Each completion adds one mark to that path. Attainment grows with marks:

Marks	Attainment
1	Novice
15	Master
40	Grandmaster
70	Supreme Grandmaster
Screens
Today: the aperture, streak, essence, today's percent, Cicada count, a daily maxim, your task list, a daily note, and your goals.
Path: all nine ranks with their levels, lore, and tribulations.
Dao: your mark count and attainment on every path.
Days: the 90-day grid, one row per rank. Tap a day to review it or use a Cicada.
Sect: stones and Cicada shop, name, start date, goals, task editor, backup and reset.
Data and privacy
Everything is stored in your browser's localStorage under the key winterarc_gu_v2. Nothing is sent to a server.
Progress from the earlier version (winterarc_gu_v1) is migrated automatically on first load.
Clearing site data or switching browsers or devices loses progress. Use the backup box in the Sect tab: copy the text somewhere safe and paste it back with Restore from text.
Customizing
Everything is in one file, so edit winter-arc-cultivation.html directly. The main constants are near the top of the script:

RANKS: essence names, colors, lore, tribulation names and challenges.
APT: aptitude clear lines and starting Cicada charges.
VITAL: vital Gu descriptions (their effects are in the calc() function).
PATHS: Dao path names, colors and descriptions.
MAXIMS: the daily quote list.
DEF_TASKS: the default daily tasks.
CICADA_COST and CICADA_MAX: shop pricing and the Cicada cap.
Daily tasks, goals, name and start date can also be edited in the app under the Sect tab.

Building a real APK
The app is a web page, so it works as an installable web app as-is. To get an .apk, wrap it:

Option 1: PWABuilder (easiest). Host the page at a public URL, open pwabuilder.com, enter the URL, and choose the Android package. Note that PWABuilder works best when the site provides a web app manifest and service worker, so you may need to add those first.

Option 2: Capacitor. You need Node.js and Android Studio.

mkdir winter-arc && cd winter-arc
npm init -y
npm install @capacitor/core @capacitor/cli @capacitor/android
npx cap init "Winter Arc" com.example.winterarc --web-dir=www
mkdir www && cp /path/to/winter-arc-cultivation.html www/index.html
npx cap add android
npx cap sync
npx cap open android
Then build and run from Android Studio (Build, then Build APK). The web-view keeps localStorage, so progress persists inside the app.

Project structure
winter-arc-cultivation.html   The whole app (HTML, CSS, JS)
README.md                     This file
Known limitations
Fonts (IM Fell English, Hanken Grotesk, a small Noto Serif SC subset) load from Google Fonts. Offline, the app falls back to system fonts.
There are no push notifications or reminders.
Progress is per browser and per device, with no cloud sync.
The date logic uses your device's local date. Changing the start date after starting shifts which calendar days map to which arc days.
Credits
Reverend Insanity (蛊真人) by Gu Zhen Ren, the source of the setting, ranks, and terms.
Fonts: IM Fell English, Hanken Grotesk and Noto Serif SC via Google Fonts.
