<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cent pour Sang - Association pour les maladies du sang</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #c41e3a;
            --secondary: #8b0000;
            --accent: #ff6b6b;
            --light: #fff5f5;
            --dark: #2c3e50;
            --gray: #7f8c8d;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark);
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: opacity 0.3s;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(196, 30, 58, 0.8), rgba(139, 0, 0, 0.8)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23c41e3a" width="1200" height="600"/></svg>');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 8rem 2rem;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s;
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 2rem;
            animation: fadeInUp 1s 0.2s both;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s 0.4s both;
        }

        .btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: white;
            color: var(--primary);
            font-weight: bold;
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        /* Sections */
        section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        section:nth-child(even) {
            background: var(--light);
        }

        h2 {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 2rem;
            text-align: center;
        }

        /* Cards */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .card h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }

        /* Info Box */
        .info-box {
            background: linear-gradient(135deg, var(--accent), var(--primary));
            color: white;
            padding: 3rem;
            border-radius: 15px;
            margin: 3rem 0;
        }

        .info-box h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .info-box ul {
            list-style: none;
            padding-left: 0;
        }

        .info-box li {
            padding: 0.5rem 0;
            padding-left: 1.5rem;
            position: relative;
        }

        .info-box li:before {
            content: "✓";
            position: absolute;
            left: 0;
            font-weight: bold;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--dark);
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 3rem 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }

        .footer-section h4 {
            color: var(--accent);
            margin-bottom: 1rem;
        }

        .footer-section a {
            color: white;
            text-decoration: none;
            display: block;
            margin: 0.5rem 0;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--accent);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            font-size: 1.5rem;
            margin-top: 1rem;
        }

        .footer-bottom {
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        /* Animations */
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

        /* Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--secondary);
                flex-direction: column;
                padding: 1rem;
                display: none;
            }

            .nav-links.active {
                display: flex;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            h2 {
                font-size: 2rem;
            }
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">💉 Cent pour Sang</div>
            <button class="menu-toggle" onclick="toggleMenu()">☰</button>
            <ul class="nav-links" id="navLinks">
                <li><a href="#accueil" onclick="closeMenu()">Accueil</a></li>
                <li><a href="#association" onclick="closeMenu()">L'Association</a></li>
                <li><a href="#actions" onclick="closeMenu()">Nos Actions</a></li>
                <li><a href="#drepanocytose" onclick="closeMenu()">Drépanocytose</a></li>
                <li><a href="#engager" onclick="closeMenu()">S'engager</a></li>
                <li><a href="#actualites" onclick="closeMenu()">Actualités</a></li>
                <li><a href="#ressources" onclick="closeMenu()">Ressources</a></li>
                <li><a href="#contact" onclick="closeMenu()">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="accueil" class="hero">
        <h1>Bienvenue sur Cent pour Sang</h1>
        <p>Une association engagée pour la santé, la solidarité et l'amélioration de la qualité de vie des personnes touchées par les maladies du sang</p>
        <div class="cta-buttons">
            <a href="#engager" class="btn btn-primary">Faire un don</a>
            <a href="#engager" class="btn btn-secondary">Devenir bénévole</a>
            <a href="#contact" class="btn btn-secondary">Nous contacter</a>
        </div>
    </section>

    <section id="association">
        <h2>Qui sommes-nous ?</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 3rem; font-size: 1.1rem;">
            Cent pour Sang est une association loi 1901 dédiée à la sensibilisation, au soutien et à l'action en faveur des personnes concernées par les maladies du sang. Nous croyons en l'importance du partage d'information, de l'entraide et de l'engagement collectif.
        </p>
        
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">🤝</div>
                <h3>Solidarité</h3>
                <p>Nous créons des liens forts entre malades, familles et soignants pour ne laisser personne seul face à la maladie.</p>
            </div>
            <div class="card">
                <div class="card-icon">👂</div>
                <h3>Écoute</h3>
                <p>Nous offrons un espace d'écoute bienveillant et sans jugement pour tous ceux qui en ont besoin.</p>
            </div>
            <div class="card">
                <div class="card-icon">🔍</div>
                <h3>Transparence</h3>
                <p>Nous agissons avec clarté et honnêteté dans toutes nos actions et communications.</p>
            </div>
            <div class="card">
                <div class="card-icon">🎯</div>
                <h3>Impact social</h3>
                <p>Chaque action est pensée pour avoir un impact réel et mesurable sur la vie des personnes concernées.</p>
            </div>
        </div>

        <div class="info-box" style="margin-top: 3rem;">
            <h3>🌍 Cent pour Sang - La Vie</h3>
            <p>Chaque action est menée pour améliorer la vie des malades, soutenir leurs proches et encourager la prévention. Nous travaillons en lien avec des professionnels de santé, des partenaires associatifs et des bénévoles investis.</p>
        </div>
    </section>

    <section id="actions">
        <h2>Nos Actions</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 3rem; font-size: 1.1rem;">
            Cent pour Sang mène des actions concrètes dans plusieurs domaines pour améliorer la vie des personnes touchées par les maladies du sang.
        </p>

        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">📢</div>
                <h3>Sensibilisation</h3>
                <p>Nous organisons des campagnes d'information pour mieux faire connaître les enjeux liés aux maladies du sang et à leur prise en charge.</p>
            </div>
            <div class="card">
                <div class="card-icon">🔬</div>
                <h3>Dépistage & Prévention</h3>
                <p>Informer sur l'importance du dépistage précoce et des bonnes pratiques pour réduire les complications.</p>
            </div>
            <div class="card">
                <div class="card-icon">❤️</div>
                <h3>Accompagnement</h3>
                <p>Nous apportons écoute, soutien et ressources aux personnes touchées ainsi qu'à leurs familles.</p>
            </div>
            <div class="card">
                <div class="card-icon">🌐</div>
                <h3>Partenariats & Événements</h3>
                <p>Participation à des événements publics et à des réseaux associatifs pour renforcer notre impact.</p>
            </div>
            <div class="card">
                <div class="card-icon">🇫🇷</div>
                <h3>Actions en France</h3>
                <p>Mobilisation locale et nationale pour améliorer l'accès aux soins et à l'information.</p>
            </div>
            <div class="card">
                <div class="card-icon">🇬🇳</div>
                <h3>Actions en Guinée</h3>
                <p>Projets de solidarité internationale pour soutenir les populations touchées en Afrique.</p>
            </div>
        </div>
    </section>

    <section id="drepanocytose">
        <h2>La Drépanocytose</h2>
        
        <div class="info-box">
            <h3>🩸 Qu'est-ce que la drépanocytose ?</h3>
            <p style="margin-bottom: 1.5rem;">
                La drépanocytose est une maladie génétique du sang qui affecte la forme des globules rouges et peut entraîner des douleurs, une fatigue importante et des complications médicales. C'est l'une des maladies hématologiques les plus fréquentes dans le monde et un enjeu majeur de santé publique.
            </p>
            <p style="font-style: italic;">🌍 Drep Afrique - Notre engagement solidaire</p>
        </div>

        <div class="cards-grid">
            <div class="card">
                <h3>🎯 Notre objectif</h3>
                <ul style="list-style: none; padding: 0;">
                    <li style="padding: 0.5rem 0;">✓ Informer sans tabou</li>
                    <li style="padding: 0.5rem 0;">✓ Expliquer le diagnostic</li>
                    <li style="padding: 0.5rem 0;">✓ Présenter les traitements</li>
                    <li style="padding: 0.5rem 0;">✓ Partager les ressources disponibles</li>
                </ul>
            </div>
            <div class="card">
                <h3>📚 Contenus pédagogiques</h3>
                <p>Nous mettons à disposition des contenus pédagogiques pour aider les patients et leurs familles à mieux comprendre cette maladie et ses implications au quotidien.</p>
            </div>
            <div class="card">
                <h3>🏥 Prise en charge</h3>
                <p>Informations sur le suivi médical, les traitements disponibles et les structures de soins spécialisées.</p>
            </div>
        </div>
    </section>

    <section id="engager">
        <h2>S'engager à nos côtés</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 3rem; font-size: 1.1rem;">
            Vous pouvez agir à nos côtés de plusieurs façons. Chaque engagement compte et contribue à faire avancer la solidarité et la prise en charge des maladies du sang.
        </p>

        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">🙋</div>
                <h3>Devenir bénévole</h3>
                <p>Participez à nos campagnes, événements et actions de terrain. Votre temps et votre énergie font la différence.</p>
                <a href="#contact" class="btn btn-primary" style="margin-top: 1rem;">Je m'engage</a>
            </div>
            <div class="card">
                <div class="card-icon">💝</div>
                <h3>Faire un don</h3>
                <p>Votre soutien financier nous aide à développer nos projets, financer des actions de sensibilisation et accompagner les familles.</p>
                <a href="#contact" class="btn btn-primary" style="margin-top: 1rem;">Faire un don</a>
            </div>
            <div class="card">
                <div class="card-icon">🤝</div>
                <h3>Devenir partenaire</h3>
                <p>Entreprises, collectivités, associations — construisons ensemble des projets à fort impact social.</p>
                <a href="#contact" class="btn btn-primary" style="margin-top: 1rem;">Nous contacter</a>
            </div>
            <div class="card">
                <div class="card-icon">👥</div>
                <h3>Devenir membre</h3>
                <p>Rejoignez notre communauté et participez activement à la vie de l'association.</p>
                <a href="#contact" class="btn btn-primary" style="margin-top: 1rem;">Adhérer</a>
            </div>
        </div>
    </section>

    <section id="actualites">
        <h2>Actualités & Événements</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 3rem; font-size: 1.1rem;">
            Restez informé(e) de nos actualités, campagnes et événements à venir ! Nous publions régulièrement des articles, annonces et ressources pour vous tenir au courant de nos actions.
        </p>

        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">📰</div>
                <h3>Actualités récentes</h3>
                <p>Découvrez les dernières nouvelles de l'association et les avancées dans le domaine des maladies du sang.</p>
            </div>
            <div class="card">
                <div class="card-icon">📅</div>
                <h3>Événements à venir</h3>
                <p>Participez à nos événements, conférences et actions de sensibilisation programmés dans les prochains mois.</p>
            </div>
            <div class="card">
                <div class="card-icon">📸</div>
                <h3>Galerie & Témoignages</h3>
                <p>Revivez nos actions passées en images et découvrez les témoignages de ceux qui nous soutiennent.</p>
            </div>
        </div>

        <p style="text-align: center; margin-top: 2rem; font-style: italic; color: var(--gray);">
            👉 Reviens souvent pour ne rien manquer de nos actualités !
        </p>
    </section>

    <section id="ressources">
        <h2>Ressources</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 3rem; font-size: 1.1rem;">
            Nous mettons à votre disposition des documents utiles pour vous aider à approfondir vos connaissances et trouver l'aide dont vous avez besoin.
        </p>

        <div class="cards-grid">
            <div class="card">
                <div class="card-icon">📋</div>
                <h3>Documents officiels</h3>
                <ul style="list-style: none; padding: 0;">
                    <li style="padding: 0.3rem 0;">• Statuts de l'association</li>
                    <li style="padding: 0.3rem 0;">• Règlement intérieur</li>
                    <li style="padding: 0.3rem 0;">• Rapports d'activité</li>
                </ul>
            </div>
            <div class="card">
                <div class="card-icon">📖</div>
                <h3>Guides d'information</h3>
                <p>Brochures et guides pratiques sur les maladies du sang, leurs symptômes et leur prise en charge.</p>
            </div>
            <div class="card">
                <div class="card-icon">🏥</div>
                <h3>Articles de santé</h3>
                <p>Publications et articles scientifiques vulgarisés pour mieux comprendre les enjeux médicaux.</p>
            </div>
            <div class="card">
                <div class="card-icon">🔗</div>
                <h3>Liens utiles</h3>
                <p>Associations partenaires, structures de soins spécialisées et plateformes d'information reconnues.</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2>Nous Contacter</h2>
        <p style="text-align: center; max-width: 800px; margin: 0 auto 2rem; font-size: 1.1rem;">
            Vous avez une question ? N'hésitez pas à nous écrire via le formulaire ci-dessous. Nous sommes à votre écoute.
        </p>

        <div class="contact-form">
            <form onsubmit="handleSubmit(event)">
                <div class="form-group">
                    <label for="nom">Nom complet *</label>
                    <input type="text" id="nom" name="nom" required>
                </div>
                <div class="form-group">
                    <label for="email">Email *</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="telephone">Téléphone</label>
                    <input type="tel" id="telephone" name="telephone">
                </div>
                <div class="form-group">
                    <label for="sujet">Sujet *</label>
                    <input type="text" id="sujet" name="sujet" required>
                </div>
                <div class="form-group">
                    <label for="message">Message *</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Envoyer le message</button>
            </form>

            <div style="margin-top: 3rem; text-align: center;">
                <p style="margin: 0.5rem 0;"><strong>📍 Adresse :</strong> [À renseigner]</p>
                <p style="margin: 0.5rem 0;"><strong>📞 Téléphone :</strong> [À renseigner]</p>
                <p style="margin: 0.5rem 0;"><strong>✉️ Email :</strong> contact@centpoursang.fr</p>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4>Cent pour Sang</h4>
                <p>Association loi 1901 dédiée à la lutte contre les maladies du sang et au soutien des personnes touchées.</p>
                <div class="social-links">
                    <a href="#" title="Facebook">📘</a>
                    <a href="#" title="Twitter">🐦</a>
                    <a href="#" title="Instagram">📷</a>
                    <a href="#" title="LinkedIn">💼</a>
                </div>
            </div>
            <div class="footer-section">
                <h4>Liens rapides</h4>
                <a href="#association">L'Association</a>
                <a href="#actions">Nos Actions</a>
                <a href="#drepanocytose">Drépanocytose</a>
                <a href="#engager">S'engager</a>
            </div>
            <div class="footer-section">
                <h4>Ressources</h4>
                <a href="#ressources">Documents</a>
                <a href="#actualites">Actualités</a>
                <a href="#contact">Contact</a>
                <a href="#" onclick="alert('Mentions légales à venir')">Mentions légales</a>
            </div>
            <div class="footer-section">
                <h4>Informations légales</h4>
                <p style="font-size: 0.9rem;">
                    <strong>Éditeur :</strong> Cent pour Sang<br>
                    Association loi 1901<br>
                    <strong>Responsable :</strong> [À renseigner]<br>
                    <strong>Hébergement :</strong> [À renseigner]
                </p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Cent pour Sang. Tous droits réservés.</p>
            <p style="font-size: 0.9rem; margin-top: 0.5rem;">
                Protection des données : Conformément au RGPD, vos données personnelles sont traitées dans le strict respect de votre vie privée.
            </p>
        </div>
    </footer>

    <script>
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        function closeMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.remove('active');
        }

        function handleSubmit(event) {
            event.preventDefault();
            alert('Merci pour votre message ! Nous vous répondrons dans les plus brefs délais.\n\nNote : Ce formulaire est une démonstration. Dans la version finale, il sera connecté à votre système de messagerie.');
            event.target.reset();
        }

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
