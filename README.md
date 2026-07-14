<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sraz ročníku 2007-2011</title>
    <style>
        /* Základní nastavení stránky */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #fdfbf7;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }

        /* --- Vizuál girlandy (papíry na šňůrce) --- */
        .garland-container {
            position: relative;
            text-align: center;
            margin-top: 40px;
            margin-bottom: 50px;
            overflow: hidden;
            padding-bottom: 20px;
        }

        /* Šňůrka */
        .string {
            position: absolute;
            top: 20px;
            left: -10%;
            width: 120%;
            height: 100px;
            border-top: 3px solid #8c7b75;
            border-radius: 50%;
            z-index: 1;
        }

        .papers {
            position: relative;
            z-index: 2;
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .paper {
            background-color: #fff;
            padding: 20px 30px;
            font-size: 1.8rem;
            font-weight: 900;
            text-transform: uppercase;
            box-shadow: 2px 5px 15px rgba(0,0,0,0.15);
            position: relative;
            border-radius: 3px;
        }

        /* Kolíčky/díry na papíru */
        .paper::before {
            content: '';
            position: absolute;
            top: 5px;
            left: 50%;
            transform: translateX(-50%);
            width: 10px;
            height: 10px;
            background: #333;
            border-radius: 50%;
            box-shadow: inset 1px 1px 3px rgba(0,0,0,0.5);
        }

        /* Různé barvy a natočení papírů */
        .paper:nth-child(1) { background-color: #ffb7b2; transform: rotate(-3deg) translateY(10px); }
        .paper:nth-child(2) { background-color: #e2f0cb; transform: rotate(2deg) translateY(20px); }
        .paper:nth-child(3) { background-color: #ffdac1; transform: rotate(-1deg) translateY(15px); }

        /* --- Informační text --- */
        .info-text {
            text-align: center;
            background: #fff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            margin-bottom: 40px;
        }

        .info-text h3 {
            margin: 5px 0;
            color: #444;
        }

        .info-text p {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 20px auto 0;
            font-style: italic;
        }

        /* --- 3 Fotky vedle sebe --- */
        .three-photos {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 60px;
        }

        .three-photos img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        /* --- Účastníci --- */
        .attendance-section {
            text-align: center;
        }

        .attendance-section h2 {
            font-size: 2.5rem;
            color: #2c3e50;
            margin-bottom: 20px;
        }

        .hero-img {
            width: 100%;
            height: 400px;
            object-fit: cover;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            margin-bottom: 40px;
        }

        /* Grid jmen */
        .name-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            text-align: left;
        }

        .person {
            background: #fff;
            padding: 10px 15px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            border-left: 4px solid #eee;
            font-weight: 500;
        }

        /* Zvýraznění hrany podle účasti */
        .person.yes { border-left-color: #27ae60; }
        .person.no { border-left-color: #e74c3c; }

        /* --- Responzivita (pro mobily a tablety) --- */
        @media (max-width: 900px) {
            .name-grid { grid-template-columns: repeat(3, 1fr); }
            .three-photos img { height: 200px; }
        }
        @media (max-width: 700px) {
            .name-grid { grid-template-columns: repeat(2, 1fr); }
            .three-photos { grid-template-columns: 1fr; }
            .three-photos img { height: auto; }
            .paper { font-size: 1.2rem; padding: 15px 20px; }
            .hero-img { height: 250px; }
        }
        @media (max-width: 450px) {
            .name-grid { grid-template-columns: 1fr; }
            .papers { flex-direction: column; gap: 10px; align-items: center; }
            .string { display: none; /* Na malém mobilu šňůrku schováme */ }
            .paper { transform: none !important; width: 80%; }
        }
    </style>
</head>
<body>

<div class="container">

    <!-- HLAVNÍ NADPIS (Girlanda) -->
    <header class="garland-container">
        <div class="string"></div>
        <div class="papers">
            <div class="paper">VÍTEJ</div>
            <div class="paper">ROČNÍKU</div>
            <div class="paper">2007-2011</div>
        </div>
    </header>

    <!-- ZÁKLADNÍ INFO -->
    <section class="info-text">
        <h3>Co: 4.LA PO 15 LETECH</h3>
        <h3>Kdy: 17. 10. 2026</h3>
        <h3>Kde: Čtrnáctka, kde jinde</h3>
        <p>
            Sejdeme se, vypijeme pár vín a hlavně si povíme, jak se máme. Nezapomeňte fotky, vzpomínky, historky. A ano, i na fotky dětí se dostane..
        </p>
    </section>

    <!-- 3 FOTKY VEDLE SEBE (zde změň src="..." za url tvých fotek) -->
    <section class="three-photos">
        <img src="https://picsum.photos/400/300?random=1" alt="Vzpomínka 1">
        <img src="https://picsum.photos/400/300?random=2" alt="Vzpomínka 2">
        <img src="https://picsum.photos/400/300?random=3" alt="Vzpomínka 3">
    </section>

    <!-- ÚČASTNÍCI -->
    <section class="attendance-section">
        <h2>KDO SE ZÚČASTNÍ?</h2>
        
        <!-- VELKÁ FOTKA NA ŠÍŘKU -->
        <img class="hero-img" src="https://picsum.photos/1000/400?random=4" alt="Společná fotka ročníku">

        <!-- SEZNAM 32 JMÉN -->
        <div class="name-grid">
            <!-- Příklad potvrzené účasti (class="person yes", znak ✅) -->
            <div class="person yes"><span>Jan Novák</span> <span>✅</span></div>
            <div class="person yes"><span>Petr Dvořák</span> <span>✅</span></div>
            <!-- Příklad zamítnuté účasti (class="person no", znak 🔴) -->
            <div class="person no"><span>Jana Svobodová</span> <span>🔴</span></div>
            <div class="person yes"><span>Eva Černá</span> <span>✅</span></div>
            
            <div class="person yes"><span>Tomáš Procházka</span> <span>✅</span></div>
            <div class="person yes"><span>Martin Kučera</span> <span>✅</span></div>
            <div class="person no"><span>Lucie Veselá</span> <span>🔴</span></div>
            <div class="person yes"><span>Anna Horáková</span> <span>✅</span></div>

            <div class="person yes"><span>Michal Němec</span> <span>✅</span></div>
            <div class="person yes"><span>Jakub Pokorný</span> <span>✅</span></div>
            <div class="person yes"><span>Lenka Marková</span> <span>✅</span></div>
            <div class="person no"><span>Kateřina Pospíšilová</span> <span>🔴</span></div>

            <div class="person yes"><span>Ondřej Hájek</span> <span>✅</span></div>
            <div class="person yes"><span>Filip Král</span> <span>✅</span></div>
            <div class="person yes"><span>Zuzana Jelínková</span> <span>✅</span></div>
            <div class="person yes"><span>Petra Růžičková</span> <span>✅</span></div>

            <div class="person no"><span>Lukáš Fiala</span> <span>🔴</span></div>
            <div class="person yes"><span>Matěj Sedláček</span> <span>✅</span></div>
            <div class="person yes"><span>Veronika Zemanová</span> <span>✅</span></div>
            <div class="person yes"><span>Tereza Kolářová</span> <span>✅</span></div>

            <div class="person yes"><span>David Bartoš</span> <span>✅</span></div>
            <div class="person no"><span>Pavel Kříž</span> <span>🔴</span></div>
            <div class="person yes"><span>Barbora Vlčková</span> <span>✅</span></div>
            <div class="person yes"><span>Markéta Kovářová</span> <span>✅</span></div>

            <div class="person yes"><span>Adam Šmíd</span> <span>✅</span></div>
            <div class="person yes"><span>Vojtěch Malý</span> <span>✅</span></div>
            <div class="person yes"><span>Klára Novotná</span> <span>✅</span></div>
            <div class="person no"><span>Simona Hrubá</span> <span>🔴</span></div>

            <div class="person yes"><span>Jiří Sýkora</span> <span>✅</span></div>
            <div class="person yes"><span>Marek Vávra</span> <span>✅</span></div>
            <div class="person yes"><span>Martina Machová</span> <span>✅</span></div>
            <div class="person yes"><span>Daniela Bláhová</span> <span>✅</span></div>
        </div>
    </section>

</div>

</body>
</html>