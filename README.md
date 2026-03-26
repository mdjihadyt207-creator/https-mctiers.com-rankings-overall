<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>MCTIERS • PvP Tier List Rankings</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0c12;
            font-family: 'Inter', sans-serif;
            color: #eef2ff;
            padding: 2rem 1.5rem;
        }

        /* GLOW + DARK THEME */
        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* header / navbar */
        .navbar {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            border-bottom: 1px solid #1e2432;
            padding-bottom: 1rem;
        }

        .logo h1 {
            font-size: 1.9rem;
            font-weight: 800;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #ffffff, #9aa9ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .logo span {
            font-size: 0.8rem;
            font-weight: 400;
            color: #6c7a91;
            letter-spacing: 0px;
        }

        .search-section {
            display: flex;
            gap: 12px;
            background: #11161f;
            padding: 8px 16px;
            border-radius: 60px;
            border: 1px solid #252e3e;
        }

        .search-section i {
            color: #6c7a91;
            font-size: 1rem;
        }

        .search-section input {
            background: transparent;
            border: none;
            outline: none;
            color: white;
            font-size: 0.9rem;
            width: 200px;
        }

        .search-section input::placeholder {
            color: #4a5568;
        }

        .server-ip {
            background: #0f121b;
            border: 1px solid #2d3748;
            padding: 8px 18px;
            border-radius: 40px;
            font-family: monospace;
            font-weight: 500;
            font-size: 0.9rem;
        }

        .server-ip i {
            margin-right: 8px;
            color: #4c9aff;
        }

        /* tabs */
        .tabs {
            display: flex;
            gap: 8px;
            margin: 28px 0 20px 0;
            flex-wrap: wrap;
            border-bottom: 1px solid #1e2432;
            padding-bottom: 12px;
        }

        .tab {
            background: transparent;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: 0.2s;
            color: #8f9bb3;
        }

        .tab.active {
            background: #2c3e66;
            color: white;
            box-shadow: 0 2px 6px rgba(0,0,0,0.3);
        }

        .tab:hover:not(.active) {
            background: #1a202c;
            color: #ccd6f6;
        }

        /* main layout */
        .two-columns {
            display: flex;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .left-panel {
            flex: 2.2;
            min-width: 260px;
        }

        .right-panel {
            flex: 3.5;
            min-width: 320px;
        }

        /* region cards / tier list blocks */
        .region-card {
            background: #0f121b;
            border-radius: 28px;
            padding: 1.2rem 1rem;
            margin-bottom: 1.5rem;
            border: 1px solid #202633;
            backdrop-filter: blur(2px);
        }

        .region-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            padding-left: 8px;
            border-left: 4px solid #4c9aff;
        }

        .player-item {
            background: #141a24;
            margin: 12px 0;
            padding: 12px 16px;
            border-radius: 20px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            transition: all 0.2s;
            border: 1px solid #232b38;
        }

        .player-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .skin-icon {
            width: 40px;
            height: 40px;
            background: #1e2a3a;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            background-size: cover;
            background-position: center;
            box-shadow: 0 0 0 2px #2d3748;
        }

        .skin-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        .player-name {
            font-weight: 700;
            font-size: 1rem;
        }

        .player-region {
            font-size: 0.7rem;
            background: #1f2a3c;
            padding: 2px 8px;
            border-radius: 20px;
            color: #bbd1ff;
        }

        .combat-badge {
            font-size: 0.7rem;
            color: #9aa9c1;
        }

        .tier-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            align-items: center;
        }

        .tier {
            font-family: monospace;
            font-weight: 800;
            font-size: 0.75rem;
            padding: 4px 8px;
            border-radius: 20px;
            background: #0f1119;
            letter-spacing: 0.5px;
        }

        .ht1 { background: #d4af37; color: #1e1a0c; box-shadow: 0 0 3px gold; }
        .ht2 { background: #c0c0c0; color: #121212; }
        .ht3 { background: #cd7f32; color: #1f1b10; }
        .ht4 { background: #a56b2f; color: white; }
        .lt1 { background: #3c5a7d; color: white; }
        .lt2 { background: #2c4c6e; color: white; }
        .lt3 { background: #1f3e5c; color: #ccdeee; }
        .default-tier { background: #2a2f3f; color: white; }

        /* featured profile (IAM_BD_GAMER) */
        .featured-card {
            background: linear-gradient(145deg, #10141f, #0c0f18);
            border-radius: 32px;
            padding: 1.4rem;
            margin-bottom: 2rem;
            border: 1px solid #2d3748;
            box-shadow: 0 10px 20px -5px rgba(0,0,0,0.5);
        }

        .profile-header {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            align-items: center;
            margin-bottom: 20px;
        }

        .big-avatar {
            width: 80px;
            height: 80px;
            background: #2c3e66;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: bold;
            background-image: url('https://mc-heads.net/avatar/IAM_BD_GAMER/100');
            background-size: cover;
            background-position: center;
            border: 3px solid #ffcf4a;
        }

        .profile-name h2 {
            font-size: 1.9rem;
            font-weight: 800;
        }

        .profile-name p {
            color: #9aa5c2;
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .rank-position {
            background: #1e2a3a;
            padding: 4px 12px;
            border-radius: 40px;
            font-size: 0.8rem;
        }

        .tier-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 20px;
            justify-content: flex-start;
        }

        /* other players list */
        .players-list {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .footer-note {
            margin-top: 40px;
            text-align: center;
            font-size: 0.7rem;
            color: #4a5568;
            border-top: 1px solid #1e2432;
            padding-top: 20px;
        }

        @media (max-width: 780px) {
            body {
                padding: 1rem;
            }
            .tier-badges {
                margin-top: 8px;
            }
            .player-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 8px;
            }
        }
    </style>
</head>
<body>
<div class="container">
    <!-- NAVIGATION HEADER -->
    <div class="navbar">
        <div class="logo">
            <h1>MCTIERS <span>· PVP RANKINGS</span></h1>
        </div>
        <div class="search-section">
            <i class="fas fa-search"></i>
            <input type="text" placeholder="Search player...">
        </div>
        <div class="server-ip">
            <i class="fas fa-network-wired"></i> mcpvp.club
        </div>
    </div>

    <!-- TABS (Vanilla/UHC/Pot/Network) -->
    <div class="tabs">
        <div class="tab active">Vanilla</div>
        <div class="tab">UHC</div>
        <div class="tab">Pot</div>
        <div class="tab">Network</div>
        <div class="tab">LTMs</div>
    </div>

    <!-- MAIN 2 COLUMNS -->
    <div class="two-columns">
        <!-- LEFT PANEL: REGIONS & FEATURED -->
        <div class="left-panel">
            <!-- FEATURED PROFILE: IAM_BD_GAMER (burgerking skin theme) -->
            <div class="featured-card">
                <div class="profile-header">
                    <div class="big-avatar" style="background-image: url('https://mc-heads.net/avatar/IAM_BD_GAMER/100');"></div>
                    <div class="profile-name">
                        <h2>IAM_BD_GAMER <span style="font-size: 0.9rem;">✦ BurgerKing</span></h2>
                        <p><i class="fas fa-globe-asia"></i> Asia Region  •  <span class="rank-position"><i class="fas fa-trophy"></i> #12,083 OVERALL</span></p>
                    </div>
                </div>
                <div><strong>TIERLINE · COMBAT RATING</strong> <span style="color:#9aa5c2;">(Sword/Armor/Boots/Gloves/Heart/Eye/Shield)</span></div>
                <div class="tier-grid">
                    <span class="tier ht1">HT1</span>
                    <span class="tier ht1">HT1</span>
                    <span class="tier lt1">LT1</span>
                    <span class="tier lt1">LT1</span>
                    <span class="tier ht1">HT1</span>
                    <span class="tier ht1">HT1</span>
                    <span class="tier lt1">LT1</span>
                </div>
                <div style="margin-top: 14px; display: flex; gap: 20px; font-size: 0.8rem;">
                    <span><i class="fas fa-heart" style="color:#ff5e7e;"></i> Heart HT1</span>
                    <span><i class="fas fa-eye" style="color:#8bcbff;"></i> Eye HT1</span>
                    <span><i class="fas fa-shield-alt"></i> Shield LT1</span>
                    <span><i class="fas fa-sword"></i> Sword HT1</span>
                    <span><i class="fas fa-tshirt"></i> Armor LT1</span>
                    <span><i class="fas fa-shoe-prints"></i> Boots HT1</span>
                    <span><i class="fas fa-fist-raised"></i> Gloves LT1</span>
                </div>
                <div style="margin-top: 10px; background: #00000033; border-radius: 20px; padding: 6px 12px; font-size: 0.75rem;">
                    <i class="fas fa-crown"></i> "BurgerKingTiawan legacy" • PvP Ace • Top fragger
                </div>
            </div>

            <!-- REGION: TIER 1 PLAYERS (NA/EU) -->
            <div class="region-card">
                <div class="region-title"><i class="fas fa-map-marker-alt"></i> Tier 1 · North America</div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/ItzRealMC/48'); background-size: cover;"></div>
                        <div><span class="player-name">ItzRealMC</span><div class="combat-badge">Combat 9.2 · Sword</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span><span class="tier ht1">HT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/coldified/48'); background-size: cover;"></div>
                        <div><span class="player-name">coldified</span><div class="combat-badge">Combat 8.9 · PotPvP</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht3">HT3</span><span class="tier ht1">HT1</span><span class="tier lt1">LT1</span><span class="tier ht2">HT2</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/Swight/48'); background-size: cover;"></div>
                        <div><span class="player-name">Swight</span><div class="combat-badge">Combat 8.5 · NA</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span><span class="tier lt2">LT2</span><span class="tier ht3">HT3</span><span class="tier ht3">HT3</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span></div>
                </div>
            </div>

            <div class="region-card">
                <div class="region-title"><i class="fas fa-globe-europe"></i> Tier 2 · Europe</div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/janekv/48'); background-size: cover;"></div>
                        <div><span class="player-name">janekv</span><div class="combat-badge">Combat 8.1 · EU</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier lt1">LT1</span><span class="tier lt2">LT2</span><span class="tier lt2">LT2</span><span class="tier ht3">HT3</span><span class="tier lt3">LT3</span><span class="tier ht4">HT4</span><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/BlvckPvP/48'); background-size: cover;"></div>
                        <div><span class="player-name">BlvckPvP</span><div class="combat-badge">Combat 8.7 · EU</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier lt1">LT1</span><span class="tier ht2">HT2</span><span class="tier lt2">LT2</span><span class="tier ht3">HT3</span><span class="tier lt3">LT3</span><span class="tier lt3">LT3</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span></div>
                </div>
            </div>

            <!-- TIER 1 PRO LIST (reference from image: K1RBE, etc) -->
            <div class="region-card">
                <div class="region-title"><i class="fas fa-fire"></i> Elite Tier 1 (Global)</div>
                <div style="display: flex; flex-wrap: wrap; gap: 10px;">
                    <span class="tier ht1" style="background:#d4af37;">K1RBE</span>
                    <span class="tier ht1">Car</span>
                    <span class="tier ht1">Den</span>
                    <span class="tier ht1">King</span>
                    <span class="tier ht1">qPo</span>
                    <span class="tier ht1">Tok</span>
                    <span class="tier ht1">clot</span>
                    <span class="tier ht1">Cov</span>
                    <span class="tier ht1">Dw$</span>
                    <span class="tier ht1">Sup</span>
                    <span class="tier ht1">C1u</span>
                </div>
                <div style="margin-top: 10px; color:#8190aa; font-size:0.7rem;"><i class="fas fa-crown"></i> MCTIERS Hall of Fame</div>
            </div>
        </div>

        <!-- RIGHT PANEL: FULL RANKINGS & MORE MCTIERS -->
        <div class="right-panel">
            <div style="display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 18px;">
                <h3 style="font-weight: 700;"><i class="fas fa-chart-line"></i> Global Leaderboard · PvP Tiers</h3>
                <span style="font-size:0.7rem; background:#141a24; padding:4px 8px; border-radius: 20px;">updated daily</span>
            </div>
            <!-- list of additional players with mixed tiers, exactly like mctiers style -->
            <div class="players-list">
                <!-- BurgerKing Profile featured again but in the right as reference, and adding more -->
                <div class="player-item" style="background: linear-gradient(95deg, #1a212f, #11161f); border-left: 4px solid gold;">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/IAM_BD_GAMER/48');"></div>
                        <div><span class="player-name">IAM_BD_GAMER <i class="fas fa-check-circle" style="color:#4c9aff;"></i></span>
                        <div class="combat-badge">✦ BurgerKing skin • Asia #1 contender</div></div>
                    </div>
                    <div class="tier-badges">
                        <span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt1">LT1</span><span class="tier lt1">LT1</span>
                        <span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt1">LT1</span>
                    </div>
                </div>
                <!-- additional players with LT/HT combos -->
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/Burgerkingtiawan/48');"></div>
                        <div><span class="player-name">Burgerkingtiawan</span><div class="combat-badge">Unranked Iconic • Asia</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier lt1">LT1</span><span class="tier lt1">LT1</span><span class="tier lt1">LT1</span><span class="tier ht2">HT2</span><span class="tier ht2">HT2</span><span class="tier lt3">LT3</span><span class="tier ht1">HT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/K1RBE/48');"></div>
                        <div><span class="player-name">K1RBE</span><div class="combat-badge">S-Tier • NA</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier ht2">HT2</span><span class="tier lt1">LT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/Coldi/48');"></div>
                        <div><span class="player-name">coldified</span><div class="combat-badge">EU • Shield Master</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht3">HT3</span><span class="tier ht2">HT2</span><span class="tier lt2">LT2</span><span class="tier ht1">HT1</span><span class="tier lt3">LT3</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/CloutPvP/48');"></div>
                        <div><span class="player-name">CloutPvP</span><div class="combat-badge">NA • Pot God</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier lt2">LT2</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span><span class="tier ht3">HT3</span><span class="tier ht1">HT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/Dw$MC/48');"></div>
                        <div><span class="player-name">Dw$MC</span><div class="combat-badge">Network Leader</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt1">LT1</span><span class="tier ht2">HT2</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/SupremePvP/48');"></div>
                        <div><span class="player-name">Supreme</span><div class="combat-badge">EU • HT3+</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht3">HT3</span><span class="tier ht1">HT1</span><span class="tier lt2">LT2</span><span class="tier lt3">LT3</span></div>
                </div>
                <!-- Tier 2 extra -->
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/qPoGG/48');"></div>
                        <div><span class="player-name">qPo</span><div class="combat-badge">Arena master</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier lt1">LT1</span><span class="tier lt2">LT2</span><span class="tier ht1">HT1</span></div>
                </div>
                <div class="player-item">
                    <div class="player-info">
                        <div class="skin-icon" style="background-image: url('https://mc-heads.net/avatar/C1u/48');"></div>
                        <div><span class="player-name">C1u</span><div class="combat-badge">Top 50 UHC</div></div>
                    </div>
                    <div class="tier-badges"><span class="tier ht1">HT1</span><span class="tier ht1">HT1</span><span class="tier lt3">LT3</span><span class="tier ht2">HT2</span></div>
                </div>
            </div>

            <!-- Additional block: Heart/Eye/Shield/Sword/Armor/Boots/Gloves meta -->
            <div class="region-card" style="margin-top: 24px;">
                <div class="region-title"><i class="fas fa-layer-group"></i> Tier Categories (Meta)</div>
                <div style="display: flex; flex-wrap: wrap; gap: 14px; justify-content: space-between;">
                    <span><i class="fas fa-heart"></i> Heart <span style="color:gold;">HT1</span> · LT2</span>
                    <span><i class="fas fa-eye"></i> Eye <span class="tier ht1" style="background:gold;">HT1</span> · LT1</span>
                    <span><i class="fas fa-shield-alt"></i> Shield <span class="tier ht2">HT2</span> · LT1</span>
                    <span><i class="fas fa-sword"></i> Sword <span class="tier ht1">HT1</span> meta</span>
                    <span><i class="fas fa-tshirt"></i> Armor HT3/LT2</span>
                    <span><i class="fas fa-shoe-prints"></i> Boots HT2/HT1</span>
                    <span><i class="fas fa-fist-raised"></i> Gloves LT1/LT2</span>
                </div>
                <div style="margin-top: 15px; font-size: 12px; background:#00000033; border-radius: 18px; padding: 8px;">
                    🏆 MCTIERS official rankings powered by PVP CLUB • mcpvp.club
                </div>
            </div>
        </div>
    </div>

    <!-- bottom info server ip + credit -->
    <div class="footer-note">
        <i class="fas fa-crown"></i> MCTIERS · PvP tierlist database | SERVER IP: mcpvp.club | Updated with BurgerKing legacy & IAM_BD_GAMER profile (HT1/LT1 hybrid) 
        <br>✦ "IAM_BD_GAMER" skin: BurgerKing themed • All tiers: Heart HT1, Eye HT1, Shield LT1, Sword HT1, Armor LT1, Boots HT1, Gloves LT1 ✦
    </div>
</div>

<script>
    // small interactive search simulation (visual)
    const searchInput = document.querySelector('.search-section input');
    if(searchInput) {
        searchInput.addEventListener('input', (e) => {
            const val = e.target.value.toLowerCase();
            const players = document.querySelectorAll('.player-item');
            players.forEach(p => {
                const nameElement = p.querySelector('.player-name');
                if(nameElement) {
                    const name = nameElement.innerText.toLowerCase();
                    if(name.includes(val) || val === '') {
                        p.style.display = 'flex';
                    } else {
                        p.style.display = 'none';
                    }
                }
            });
            // also featured card name
            const featuredName = document.querySelector('.profile-name h2');
            if(featuredName && !featuredName.innerText.toLowerCase().includes(val) && val !== '') {
                // not hide, just optional but we keep visible
            }
        });
    }

    // tab switching dummy UI
    const tabs = document.querySelectorAll('.tab');
    tabs.forEach(tab => {
        tab.addEventListener('click', () => {
            tabs.forEach(t => t.classList.remove('active'));
            tab.classList.add('active');
            // visual feedback
        });
    });
</script>
</body>
</html>
