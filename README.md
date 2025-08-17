<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>G2LUX - Corporate Solutions in Luxembourg | Solutions Corporatives au Luxembourg | Εταιρικές Λύσεις στο Λουξεμβούργο</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .hero {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 20"><defs><radialGradient id="a" cx="50" cy="50" r="50" gradientUnits="userSpaceOnUse"><stop stop-color="rgba(255,255,255,0.1)" offset="0%"/><stop stop-color="rgba(255,255,255,0)" offset="100%"/></radialGradient></defs><circle cx="10" cy="10" r="1.5" fill="url(%23a)"/><circle cx="30" cy="5" r="1" fill="url(%23a)"/><circle cx="60" cy="15" r="2" fill="url(%23a)"/><circle cx="80" cy="8" r="1.5" fill="url(%23a)"/></svg>') repeat;
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .hero-content {
            text-align: center;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero .subtitle {
            font-size: 1.3rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .hero .tagline {
            font-size: 1.1rem;
            margin-bottom: 40px;
            font-style: italic;
            color: #ffd700;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            color: #1e3c72;
            padding: 15px 35px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3); }
            50% { box-shadow: 0 8px 25px rgba(255, 215, 0, 0.5); }
            100% { box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3); }
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(255, 215, 0, 0.5);
        }

        .language-switcher {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            display: flex;
            gap: 10px;
            background: rgba(255,255,255,0.95);
            padding: 10px 15px;
            border-radius: 25px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            backdrop-filter: blur(10px);
        }

        .lang-btn {
            padding: 8px 12px;
            border: 2px solid #1e3c72;
            background: transparent;
            color: #1e3c72;
            border-radius: 15px;
            cursor: pointer;
            font-weight: bold;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .lang-btn:hover, .lang-btn.active {
            background: #1e3c72;
            color: white;
        }

        .lang-content {
            display: none;
        }

        .lang-content.active {
            display: block;
        }

        .section {
            padding: 80px 0;
            position: relative;
        }

        .section:nth-child(even) {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        .section h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: #1e3c72;
            position: relative;
        }

        .section h2::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            margin: 20px auto;
            border-radius: 2px;
        }

        .unique-value {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 60px;
            font-size: 1.2rem;
            color: #555;
            line-height: 1.8;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .service-card {
            background: white;
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 215, 0, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.6s ease;
            opacity: 0;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .service-card:hover::before {
            opacity: 1;
            transform: rotate(45deg) translate(50%, 50%);
        }

        .service-icon {
            font-size: 3rem;
            color: #1e3c72;
            margin-bottom: 20px;
            display: block;
        }

        .service-card h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: #1e3c72;
        }

        .service-card p {
            color: #666;
            line-height: 1.6;
        }

        .why-us {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
        }

        .why-us-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .why-item {
            text-align: center;
            padding: 30px 20px;
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
            transition: all 0.3s ease;
        }

        .why-item:hover {
            background: rgba(255,255,255,0.15);
            transform: scale(1.05);
        }

        .why-item h3 {
            color: #ffd700;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .testimonial {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            margin: 40px 0;
            position: relative;
            font-style: italic;
            text-align: center;
        }

        .testimonial::before {
            content: '"';
            font-size: 4rem;
            color: #ffd700;
            position: absolute;
            top: -10px;
            left: 30px;
        }

        .contact-section {
            background: linear-gradient(135deg, #2a5298 0%, #1e3c72 100%);
            color: white;
            text-align: center;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }

        .contact-item {
            padding: 30px;
            background: rgba(255,255,255,0.1);
            border-radius: 15px;
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(255,255,255,0.15);
            transform: translateY(-5px);
        }

        .footer {
            background: #1a1a1a;
            color: #ccc;
            text-align: center;
            padding: 40px 0;
        }

        .greek-flag {
            display: inline-block;
            width: 30px;
            height: 20px;
            background: linear-gradient(to bottom, #0066cc 0%, #0066cc 11%, white 11%, white 22%, #0066cc 22%, #0066cc 33%, white 33%, white 44%, #0066cc 44%, #0066cc 55%, white 55%, white 66%, #0066cc 66%, #0066cc 77%, white 77%, white 88%, #0066cc 88%, #0066cc 100%);
            border: 1px solid #ccc;
            margin: 0 10px;
            vertical-align: middle;
        }

        .lux-flag {
            display: inline-block;
            width: 30px;
            height: 20px;
            background: linear-gradient(to bottom, #ed2939 0%, #ed2939 33%, white 33%, white 66%, #00a1de 66%, #00a1de 100%);
            border: 1px solid #ccc;
            margin: 0 10px;
            vertical-align: middle;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .container {
                padding: 0 15px;
            }
            
            .services-grid, .why-us-grid {
                grid-template-columns: 1fr;
            }

            .language-switcher {
                position: relative;
                top: auto;
                right: auto;
                justify-content: center;
                margin-bottom: 20px;
            }
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }
    </style>
</head>
<body>
    <!-- Language Switcher -->
    <div class="language-switcher">
        <button class="lang-btn active" onclick="switchLanguage('en')">EN</button>
        <button class="lang-btn" onclick="switchLanguage('fr')">FR</button>
        <button class="lang-btn" onclick="switchLanguage('el')">ΕΛ</button>
    </div>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <!-- English Content -->
                <div class="lang-content active" data-lang="en">
                    <h1>G2LUX</h1>
                    <p class="subtitle">Specialized Corporate Solutions in Luxembourg</p>
                    <p class="tagline">Where Greek heritage meets Luxembourg excellence</p>
                    <a href="#contact" class="cta-button">Get Started Now</a>
                </div>

                <!-- French Content -->
                <div class="lang-content" data-lang="fr">
                    <h1>G2LUX</h1>
                    <p class="subtitle">Solutions Corporatives Spécialisées au Luxembourg</p>
                    <p class="tagline">Où l'héritage grec rencontre l'excellence luxembourgeoise</p>
                    <a href="#contact" class="cta-button">Commencer Maintenant</a>
                </div>

                <!-- Greek Content -->
                <div class="lang-content" data-lang="el">
                    <h1>G2LUX</h1>
                    <p class="subtitle">Εξειδικευμένες Εταιρικές Λύσεις στο Λουξεμβούργο</p>
                    <p class="tagline">Όπου η ελληνική κουλτούρα συναντά τη λουξεμβουργιανή αριστεία</p>
                    <a href="#contact" class="cta-button">Ξεκινήστε Τώρα</a>
                </div>
            </div>
        </div>
        <div class="scroll-indicator">
            <div style="color: white; font-size: 2rem;">↓</div>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <!-- English Content -->
            <div class="lang-content active" data-lang="en">
                <h2>Why We Are Unique</h2>
                <div class="unique-value">
                    At G2LUX, you are not just a number. We understand the unique Greek business culture and the challenges you face when expanding to Luxembourg. Our team combines Greek hospitality with European expertise, offering personalized solutions that perfectly match your needs.
                </div>

                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">🏢</div>
                        <h3>Company Formation</h3>
                        <p>Complete support for establishing your company in Luxembourg, from selecting the appropriate legal structure to completing all formalities with specialized guidance in your preferred language.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">📊</div>
                        <h3>Accounting Services</h3>
                        <p>Comprehensive accounting management compliant with Luxembourg regulations, while providing reports and explanations in your language for complete understanding of your financial position.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">⚖️</div>
                        <h3>Legal Advisory</h3>
                        <p>Specialized legal support for all aspects of your business operations, with emphasis on cross-border compliance between Greece and Luxembourg.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">💼</div>
                        <h3>Tax Planning</h3>
                        <p>Strategic tax planning that maximizes the benefits of your Luxembourg presence while ensuring full compliance with Greek and European regulations.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🔒</div>
                        <h3>Confidentiality & Security</h3>
                        <p>Highest standards of confidentiality and data protection, with complete transparency in our cooperation and personal approach to each client.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🌐</div>
                        <h3>International Network</h3>
                        <p>Leverage our extensive European network for business opportunities, partnerships and expansion into new markets with expert consultant support.</p>
                    </div>
                </div>
            </div>

            <!-- French Content -->
            <div class="lang-content" data-lang="fr">
                <h2>Pourquoi Nous Sommes Uniques</h2>
                <div class="unique-value">
                    Chez G2LUX, vous n'êtes pas qu'un simple numéro. Nous comprenons la culture d'entreprise grecque unique et les défis que vous rencontrez lors de votre expansion au Luxembourg. Notre équipe combine l'hospitalité grecque avec l'expertise européenne, offrant des solutions personnalisées qui répondent parfaitement à vos besoins.
                </div>

                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">🏢</div>
                        <h3>Constitution de Sociétés</h3>
                        <p>Support complet pour l'établissement de votre société au Luxembourg, de la sélection de la structure juridique appropriée à l'accomplissement de toutes les formalités avec un accompagnement spécialisé dans votre langue préférée.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">📊</div>
                        <h3>Services Comptables</h3>
                        <p>Gestion comptable complète conforme aux réglementations luxembourgeoises, tout en fournissant rapports et explications dans votre langue pour une compréhension complète de votre position financière.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">⚖️</div>
                        <h3>Conseil Juridique</h3>
                        <p>Support juridique spécialisé pour tous les aspects de vos opérations commerciales, avec un accent sur la conformité transfrontalière entre la Grèce et le Luxembourg.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">💼</div>
                        <h3>Planification Fiscale</h3>
                        <p>Planification fiscale stratégique qui maximise les avantages de votre présence luxembourgeoise tout en assurant une conformité totale avec les réglementations grecques et européennes.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🔒</div>
                        <h3>Confidentialité & Sécurité</h3>
                        <p>Les plus hauts standards de confidentialité et de protection des données, avec une transparence complète dans notre coopération et une approche personnelle pour chaque client.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🌐</div>
                        <h3>Réseau International</h3>
                        <p>Tirez parti de notre vaste réseau européen pour les opportunités commerciales, les partenariats et l'expansion vers de nouveaux marchés avec le soutien de consultants experts.</p>
                    </div>
                </div>
            </div>

            <!-- Greek Content -->
            <div class="lang-content" data-lang="el">
                <h2>Γιατί Είμαστε Μοναδικοί</h2>
                <div class="unique-value">
                    Στη G2LUX, δεν είστε απλώς ένας αριθμός. Κατανοούμε τη μοναδική ελληνική επιχειρηματική κουλτούρα και τις προκλήσεις που αντιμετωπίζετε όταν επεκτείνεστε στο Λουξεμβούργο. Η ομάδα μας συνδυάζει την ελληνική φιλοξενία με την ευρωπαϊκή τεχνογνωσία, προσφέροντας εξατομικευμένες λύσεις που ταιριάζουν ακριβώς στις ανάγκες σας.
                </div>

                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">🏢</div>
                        <h3>Σύσταση Εταιρειών</h3>
                        <p>Πλήρης υποστήριξη για τη σύσταση της εταιρείας σας στο Λουξεμβούργο, από την επιλογή της κατάλληλης νομικής μορφής έως την ολοκλήρωση όλων των διατυπώσεων με εξειδικευμένη καθοδήγηση στα ελληνικά.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">📊</div>
                        <h3>Λογιστικές Υπηρεσίες</h3>
                        <p>Ολοκληρωμένη λογιστική παρακολούθηση που συμμορφώνεται με τους λουξεμβουργιανούς κανονισμούς, ενώ παρέχουμε αναφορές και επεξηγήσεις στην ελληνική γλώσσα για πλήρη κατανόηση της οικονομικής σας θέσης.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">⚖️</div>
                        <h3>Νομική Συμβουλευτική</h3>
                        <p>Εξειδικευμένη νομική υποστήριξη για όλες τις πτυχές της λειτουργίας της επιχείρησής σας, με έμφαση στη διασυνοριακή συμμόρφωση μεταξύ Ελλάδας και Λουξεμβούργου.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">💼</div>
                        <h3>Φορολογικός Σχεδιασμός</h3>
                        <p>Στρατηγικός φορολογικός σχεδιασμός που μεγιστοποιεί τα οφέλη της παρουσίας σας στο Λουξεμβούργο, ενώ διασφαλίζει πλήρη συμμόρφωση με τους ελληνικούς και ευρωπαϊκούς κανόνες.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🔒</div>
                        <h3>Εμπιστευτικότητα & Ασφάλεια</h3>
                        <p>Υψηλότερα στάνταρ εμπιστευτικότητας και προστασίας δεδομένων, με πλήρη διαφάνεια στη συνεργασία μας και προσωπική προσέγγιση σε κάθε πελάτη.</p>
                    </div>
                    <div class="service-card">
                        <div class="service-icon">🌐</div>
                        <h3>Διεθνές Δίκτυο</h3>
                        <p>Αξιοποιήστε το εκτεταμένο δίκτυό μας στην Ευρώπη για επιχειρηματικές ευκαιρίες, συνεργασίες και επέκταση σε νέες αγορές με την υποστήριξη έμπειρων συμβούλων.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section why-us">
        <div class="container">
            <!-- English Content -->
            <div class="lang-content active" data-lang="en">
                <h2 style="color: white;">Why Choose Us</h2>
                <div class="why-us-grid">
                    <div class="why-item">
                        <h3>🎯 Personalized Approach</h3>
                        <p>Each client has a personal consultant who knows their business and is available 24/7 for immediate support.</p>
                    </div>
                    <div class="why-item">
                        <h3>🇬🇷 Greek Understanding</h3>
                        <p>We understand the unique Greek business mindset and adapt our strategies accordingly.</p>
                    </div>
                    <div class="why-item">
                        <h3>⚡ Speed & Efficiency</h3>
                        <p>Digitized processes that save time and money, with immediate response to all your needs.</p>
                    </div>
                    <div class="why-item">
                        <h3>💎 High Quality</h3>
                        <p>Over 15 years of experience in international business solutions with 100% success rate in company formations.</p>
                    </div>
                </div>

                <div class="testimonial">
                    <p>"G2LUX transformed the complex process of establishing a company in Luxembourg into a simple and pleasant experience. Their personal approach and expertise in the Greek market made all the difference."</p>
                    <div style="margin-top: 20px; font-weight: bold; color: #1e3c72;">- Nikos P., CEO TechStart Hellas</div>
                </div>
            </div>

            <!-- French Content -->
            <div class="lang-content" data-lang="fr">
                <h2 style="color: white;">Pourquoi Nous Choisir</h2>
                <div class="why-us-grid">
                    <div class="why-item">
                        <h3>🎯 Approche Personnalisée</h3>
                        <p>Chaque client a un consultant personnel qui connaît son entreprise et est disponible 24h/24 et 7j/7 pour un support immédiat.</p>
                    </div>
                    <div class="why-item">
                        <h3>🇬🇷 Compréhension Grecque</h3>
                        <p>Nous comprenons la mentalité d'entreprise grecque unique et adaptons nos stratégies en conséquence.</p>
                    </div>
                    <div class="why-item">
                        <h3>⚡ Rapidité & Efficacité</h3>
                        <p>Processus numérisés qui économisent temps et argent, avec réponse immédiate à tous vos besoins.</p>
                    </div>
                    <div class="why-item">
                        <h3>💎 Haute Qualité</h3>
                        <p>Plus de 15 ans d'expérience dans les solutions d'affaires internationales avec 100% de taux de réussite dans les créations de sociétés.</p>
                    </div>
                </div>

                <div class="testimonial">
                    <p>"G2LUX a transformé le processus complexe de création d'une société au Luxembourg en une expérience simple et agréable. Leur approche personnelle et leur expertise du marché grec ont fait toute la différence."</p>
                    <div style="margin-top: 20px; font-weight: bold; color: #1e3c72;">- Nikos P., CEO TechStart Hellas</div>
                </div>
