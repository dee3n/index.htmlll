<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🇵🇹 Lisbon + Porto</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #FAF6EF;
    --terracotta: #F26419;
    --gold: #D4A843;
    --deep: #1C1A18;
    --tile: #2B5E8C;
    --green: #4A7C59;
    --soft: #EDE8DF;
    --muted: #8C7B6B;
    --orange-light: #FEF0E7;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { background-color: var(--cream); color: var(--deep); font-family: 'DM Sans', sans-serif; font-weight: 300; line-height: 1.7; }

  .hero { background: linear-gradient(160deg, #1C1A18 60%, #7A2E05 100%); color: var(--cream); padding: 70px 40px 50px; text-align: center; position: relative; overflow: hidden; }
  .hero::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(45deg, transparent, transparent 40px, rgba(242,100,25,0.08) 40px, rgba(242,100,25,0.08) 41px); }
  .hero-flag { font-size: 3rem; margin-bottom: 12px; display: block; }
  .hero h1 { font-family: 'Playfair Display', serif; font-size: clamp(2.2rem, 6vw, 4rem); font-weight: 700; letter-spacing: -1px; margin-bottom: 8px; }
  .hero-sub { font-size: 0.95rem; color: var(--terracotta); letter-spacing: 3px; text-transform: uppercase; margin-bottom: 20px; }
  .hero-note { display: inline-block; border: 1px solid rgba(242,100,25,0.35); padding: 10px 24px; border-radius: 100px; font-size: 0.88rem; color: rgba(250,246,239,0.75); font-style: italic; background: rgba(242,100,25,0.08); margin-bottom: 10px; }
  .hero-note.date-note { background: rgba(212,168,67,0.2); cursor: pointer; }

  .nav-tabs { display: flex; justify-content: center; gap: 8px; padding: 20px; background: var(--soft); flex-wrap: wrap; position: sticky; top: 0; z-index: 100; border-bottom: 1px solid #E0D9CE; }
  .tab-btn { background: none; border: 1.5px solid var(--muted); color: var(--muted); padding: 7px 18px; border-radius: 100px; font-family: 'DM Sans', sans-serif; font-size: 0.82rem; font-weight: 500; cursor: pointer; transition: all 0.2s; letter-spacing: 0.5px; }
  .tab-btn:hover, .tab-btn.active { background: var(--terracotta); border-color: var(--terracotta); color: white; }

  .content { max-width: 780px; margin: 0 auto; padding: 40px 24px 80px; }
  .section { display: none; }
  .section.active { display: block; }

  .day-card { background: white; border-radius: 16px; margin-bottom: 24px; overflow: hidden; box-shadow: 0 2px 12px rgba(28,26,24,0.06); animation: fadeUp 0.4s ease both; }
  @keyframes fadeUp { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }
  .day-header { padding: 20px 28px; display: flex; align-items: center; gap: 16px; border-bottom: 1px solid var(--soft); }
  .day-num { background: var(--terracotta); color: white; font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; width: 48px; height: 48px; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .day-title { font-family: 'Playfair Display', serif; font-size: 1.2rem; font-weight: 700; }
  .day-subtitle { font-size: 0.82rem; color: var(--muted); }
  .day-body { padding: 20px 28px; }
  .activity { display: flex; gap: 14px; padding: 12px 0; border-bottom: 1px solid var(--soft); align-items: flex-start; }
  .activity:last-child { border-bottom: none; }
  .activity-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--terracotta); margin-top: 8px; flex-shrink: 0; }
  .activity-text { flex: 1; font-size: 0.95rem; }
  .activity-note { font-size: 0.78rem; color: var(--muted); margin-top: 3px; }

  .act-bar { display: flex; align-items: center; gap: 6px; margin-top: 6px; opacity: 0; transition: opacity 0.15s; }
  .activity:hover .act-bar, .activity:focus-within .act-bar { opacity: 1; }
  .act-btn { background: none; border: 1px solid #DDD; border-radius: 6px; color: var(--muted); font-size: 0.72rem; padding: 2px 8px; cursor: pointer; font-family: 'DM Sans', sans-serif; transition: all 0.15s; white-space: nowrap; }
  .act-btn:hover { border-color: var(--terracotta); color: var(--terracotta); background: var(--orange-light); }
  .act-btn.delete-btn:hover { border-color: #c0392b; color: #c0392b; background: #fdf0ee; }
  .act-edit-input { width: 100%; border: 1.5px solid var(--terracotta); border-radius: 6px; padding: 3px 8px; font-family: 'DM Sans', sans-serif; font-size: 0.95rem; color: var(--deep); background: white; outline: none; margin-bottom: 2px; display: block; }

  .sub-bullets { list-style: none; margin-top: 8px; padding-left: 4px; }
  .sub-bullets li { display: flex; align-items: flex-start; gap: 7px; padding: 4px 0; font-size: 0.85rem; color: var(--deep); border-bottom: 1px dashed #E8E0D5; }
  .sub-bullets li:last-child { border-bottom: none; }
  .sub-bullet-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--gold); flex-shrink: 0; margin-top: 7px; }
  .sub-bullet-text { flex: 1; }
  .sub-bullet-link { font-size: 0.76rem; color: var(--tile); display: block; margin-top: 2px; }
  .sub-remove { background: none; border: none; color: #CCC; cursor: pointer; font-size: 0.78rem; padding: 0 2px; flex-shrink: 0; margin-left: auto; line-height: 1; margin-top: 2px; }
  .sub-remove:hover { color: var(--terracotta); }
  .add-sub-btn { display: inline-flex; align-items: center; gap: 4px; background: none; border: none; color: var(--muted); font-size: 0.75rem; font-style: italic; cursor: pointer; padding: 4px 0; margin-top: 4px; font-family: 'DM Sans', sans-serif; transition: color 0.15s; }
  .add-sub-btn:hover { color: var(--terracotta); }

  .dinner-block { margin-top: 10px; background: var(--soft); border-radius: 12px; padding: 14px 18px; }
  .dinner-label { font-size: 0.75rem; letter-spacing: 2px; text-transform: uppercase; color: var(--muted); font-weight: 500; margin-bottom: 10px; }

  .option-list { list-style: none; margin-bottom: 8px; }
  .option-list li { display: flex; align-items: flex-start; gap: 8px; padding: 6px 0; font-size: 0.88rem; border-bottom: 1px dashed #D5CCBF; flex-wrap: wrap; }
  .option-list li:last-child { border-bottom: none; }
  .opt-name { font-weight: 500; }
  .opt-note { color: var(--muted); font-size: 0.8rem; }
  .opt-link { font-size: 0.78rem; color: var(--tile); width: 100%; padding-left: 20px; }
  .opt-remove { margin-left: auto; background: none; border: none; color: #CCC; cursor: pointer; font-size: 0.85rem; padding: 0 2px; flex-shrink: 0; line-height: 1; }
  .opt-remove:hover { color: var(--terracotta); }

  .add-btn { display: inline-flex; align-items: center; gap: 6px; background: white; border: 1.5px dashed #C0B8AD; color: var(--muted); padding: 7px 14px; border-radius: 8px; font-size: 0.82rem; font-style: italic; cursor: pointer; transition: all 0.2s; margin-top: 4px; font-family: 'DM Sans', sans-serif; }
  .add-btn:hover { border-color: var(--terracotta); color: var(--terracotta); background: #FDF5F1; }

  .restaurant-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 16px; }
  @media (max-width: 540px) { .restaurant-grid { grid-template-columns: 1fr; } }

  .r-card { background: white; border-radius: 12px; padding: 16px; box-shadow: 0 1px 8px rgba(28,26,24,0.05); border-left: 3px solid var(--terracotta); animation: fadeUp 0.4s ease both; position: relative; }
  .r-card.fancy { border-left-color: var(--gold); }
  .r-card.brunch { border-left-color: var(--green); }
  .r-card.add-card { border: 1.5px dashed #C0B8AD; border-left: 1.5px dashed #C0B8AD; box-shadow: none; display: flex; flex-direction: column; align-items: center; justify-content: center; cursor: pointer; min-height: 100px; transition: all 0.2s; background: white; }
  .r-card.add-card:hover { border-color: var(--terracotta); background: #FDF5F1; }
  .r-card.add-card .plus { font-size: 1.6rem; color: #C0B8AD; margin-bottom: 4px; line-height: 1; }
  .r-card.add-card .add-label { color: var(--muted); font-size: 0.85rem; font-style: italic; }
  .r-card.add-card:hover .plus, .r-card.add-card:hover .add-label { color: var(--terracotta); }

  .r-name { font-family: 'Playfair Display', serif; font-weight: 700; font-size: 1rem; margin-bottom: 4px; }
  .r-stars { color: var(--gold); font-size: 0.8rem; margin-bottom: 5px; }
  .r-desc { font-size: 0.82rem; color: var(--muted); line-height: 1.5; }
  .r-link { font-size: 0.78rem; color: var(--tile); display: block; margin-top: 6px; word-break: break-all; }
  .r-tag { display: inline-block; background: var(--orange-light); color: var(--terracotta); font-size: 0.7rem; font-weight: 500; padding: 2px 8px; border-radius: 100px; margin-top: 8px; letter-spacing: 0.5px; }
  .r-tag.fancy-tag { background: #FDF6E3; color: #A07820; }
  .r-tag.brunch-tag { background: #EBF3ED; color: var(--green); }
  .r-delete { position: absolute; top: 10px; right: 10px; background: none; border: none; color: #DDD; cursor: pointer; font-size: 0.9rem; line-height: 1; }
  .r-delete:hover { color: var(--terracotta); }

  .section-title { font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 700; margin-bottom: 6px; }
  .section-divider { width: 40px; height: 3px; background: var(--terracotta); border-radius: 2px; margin-bottom: 20px; }
  .meal-label { font-size: 0.85rem; color: var(--terracotta); margin-bottom: 14px; font-style: italic; margin-top: 24px; font-weight: 500; }

  .tip-box { background: linear-gradient(135deg, var(--tile) 0%, #1A3E5C 100%); color: white; border-radius: 16px; padding: 24px 28px; margin-bottom: 16px; }
  .tip-box h3 { font-family: 'Playfair Display', serif; font-size: 1.1rem; margin-bottom: 12px; color: var(--gold); }
  .tip-item { display: flex; gap: 10px; margin-bottom: 8px; font-size: 0.88rem; opacity: 0.9; }
  a { color: var(--tile); text-decoration: none; font-weight: 500; }
  a:hover { text-decoration: underline; }

  /* Date edit inline */
  .date-edit-input { background: transparent; border: none; border-bottom: 1px solid rgba(212,168,67,0.6); color: rgba(250,246,239,0.9); font-family: 'DM Sans', sans-serif; font-size: 0.88rem; font-style: italic; text-align: center; outline: none; min-width: 180px; padding: 2px 4px; }

  /* MODAL */
  .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(28,26,24,0.55); z-index: 999; align-items: center; justify-content: center; padding: 20px; }
  .modal-overlay.open { display: flex; }
  .modal { background: white; border-radius: 20px; padding: 32px; width: 100%; max-width: 440px; box-shadow: 0 20px 60px rgba(0,0,0,0.25); animation: fadeUp 0.25s ease; }
  .modal h2 { font-family: 'Playfair Display', serif; font-size: 1.25rem; margin-bottom: 20px; }
  .field-group { margin-bottom: 14px; }
  .field-group label { display: block; font-size: 0.75rem; letter-spacing: 1.5px; text-transform: uppercase; color: var(--muted); font-weight: 500; margin-bottom: 5px; }
  .field-group input, .field-group select, .field-group textarea { width: 100%; border: 1.5px solid #E0D9CE; border-radius: 10px; padding: 10px 14px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; color: var(--deep); background: var(--cream); outline: none; transition: border 0.2s; }
  .field-group input:focus, .field-group select:focus, .field-group textarea:focus { border-color: var(--terracotta); }
  .field-group textarea { resize: vertical; min-height: 65px; }
  .field-group input.error { border-color: var(--terracotta); }
  .modal-actions { display: flex; gap: 10px; margin-top: 22px; }
  .btn-save { flex: 1; background: var(--terracotta); color: white; border: none; padding: 12px; border-radius: 10px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; font-weight: 500; cursor: pointer; transition: background 0.2s; }
  .btn-save:hover { background: #A8512E; }
  .btn-cancel { background: var(--soft); color: var(--muted); border: none; padding: 12px 20px; border-radius: 10px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; cursor: pointer; }
  .btn-cancel:hover { background: #DDD6CC; }
</style>
</head>
<body>

<!-- SUB-BULLET MODAL -->
<div class="modal-overlay" id="sub-modal" onclick="if(event.target===this)closeSubModal()">
  <div class="modal">
    <h2>＋ Add Detail</h2>
    <div class="field-group">
      <label>Detail *</label>
      <input type="text" id="sb-text" placeholder="e.g. Reservation required, book 2 weeks ahead">
    </div>
    <div class="field-group">
      <label>Link (optional)</label>
      <input type="url" id="sb-link" placeholder="https://...">
    </div>
    <div class="modal-actions">
      <button class="btn-cancel" onclick="closeSubModal()">Cancel</button>
      <button class="btn-save" onclick="saveSubBullet()">Save ✓</button>
    </div>
  </div>
</div>

<!-- MAIN MODAL -->
<div class="modal-overlay" id="modal" onclick="handleOverlayClick(event)">
  <div class="modal">
    <h2 id="modal-title">Add Entry</h2>
    <div class="field-group">
      <label>Name *</label>
      <input type="text" id="m-name" placeholder="e.g. Time Out Market">
    </div>
    <div class="field-group">
      <label>Notes / Description</label>
      <textarea id="m-desc" placeholder="e.g. Great for groups, try the custard tarts"></textarea>
    </div>
    <div class="field-group">
      <label>Rating (optional)</label>
      <input type="text" id="m-rating" placeholder="e.g. ⭐ 4.7">
    </div>
    <div class="field-group">
      <label>Link (optional)</label>
      <input type="url" id="m-link" placeholder="https://...">
    </div>
    <div class="field-group" id="type-row">
      <label>Category</label>
      <select id="m-type">
        <option value="dinner">Dinner</option>
        <option value="brunch">Brunch / Breakfast</option>
        <option value="lunch">Lunch</option>
        <option value="fancy">Special Occasion</option>
        <option value="cocktails">Cocktails / Bar</option>
        <option value="hotel">Hotel</option>
        <option value="activity">Activity</option>
      </select>
    </div>
    <div class="modal-actions">
      <button class="btn-cancel" onclick="closeModal()">Cancel</button>
      <button class="btn-save" onclick="saveEntry()">Save ✓</button>
    </div>
  </div>
</div>

<!-- HERO -->
<div class="hero">
  <span class="hero-flag">🇵🇹</span>
  <h1>Lisbon & Porto</h1>
  <div class="hero-sub">6 Days · Girls Trip 👯‍♀️</div>
  <div class="hero-note date-note" onclick="editTripDate()">
    🗓️ <span id="display-date">Sep 17 – Sep 21, 2026</span>
  </div>
  <br>
  <span class="hero-note">A relaxed itinerary — less traveling, more living</span>
</div>

<div class="nav-tabs">
  <button class="tab-btn active" onclick="showTab('itinerary', this)">🗓 Itinerary</button>
  <button class="tab-btn" onclick="showTab('lisbon-eats', this)">🍽 Lisbon Eats</button>
  <button class="tab-btn" onclick="showTab('porto-eats', this)">🥂 Porto Eats</button>
  <button class="tab-btn" onclick="showTab('confirmations', this)">📂 Confirmations</button>
  <button class="tab-btn" onclick="showTab('tips', this)">💡 Additional Info</button>
</div>

<div class="content">

  <!-- ITINERARY -->
  <div class="section active" id="itinerary">

    <div class="day-card" style="animation-delay:0.05s">
      <div class="day-header">
        <div class="day-num">1</div>
        <div><div class="day-title">USA → Lisbon ✈️</div><div class="day-subtitle">Arrival Day</div></div>
      </div>
      <div class="day-body">
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">Land in Lisbon<div class="activity-note">Redeye — arriving around 10–11AM</div></div>
        </div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Check into Hotel
            <div class="dinner-block">
              <div class="dinner-label">Hotel Options</div>
              <ul class="option-list" id="day1-hotels"></ul>
              <button class="add-btn" onclick="openModal('day1-hotels','Hotel Options','hotel',false)">＋ Add hotel</button>
            </div>
          </div>
        </div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">Walk around / Lunch</div>
        </div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Dinner
            <div class="dinner-block">
              <div class="dinner-label">Restaurant Options</div>
              <ul class="option-list" id="day1-dinner"></ul>
              <button class="add-btn" onclick="openModal('day1-dinner','Dinner Options','dinner',false)">＋ Add restaurant</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card" style="animation-delay:0.1s">
      <div class="day-header">
        <div class="day-num">2</div>
        <div><div class="day-title">Lisbon Highlights</div><div class="day-subtitle">History, Trams & Food</div></div>
      </div>
      <div class="day-body">
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Belém Tower<div class="activity-note">⚠️ Check if renovation is complete before visiting</div></div></div>
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">LX Factory — markets, cafes, independent shops</div></div>
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Tram 28 — iconic ride through Alfama<div class="activity-note">Go early to avoid crowds</div></div></div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Dinner
            <div class="dinner-block">
              <div class="dinner-label">Restaurant Options</div>
              <ul class="option-list" id="day2-dinner"></ul>
              <button class="add-btn" onclick="openModal('day2-dinner','Dinner Options','dinner',false)">＋ Add restaurant</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card" style="animation-delay:0.15s">
      <div class="day-header">
        <div class="day-num">3</div>
        <div><div class="day-title">Cascais Beach Day 🏖️</div><div class="day-subtitle">Day Trip from Lisbon</div></div>
      </div>
      <div class="day-body">
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Train to Cascais<div class="activity-note">~40 min · ~€5 · from Cais do Sodré station</div></div></div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Beach, Shopping & Lunch
            <div class="dinner-block">
              <div class="dinner-label">Beach Options</div>
              <ul class="option-list" id="day3-beaches">
                <li><span>🏖</span><span class="opt-name">Praia de Rainha</span><button class="opt-remove" onclick="this.parentElement.remove()">✕</button></li>
                <li><span>🏖</span><span class="opt-name">Praia de Santa Marta</span><button class="opt-remove" onclick="this.parentElement.remove()">✕</button></li>
              </ul>
              <button class="add-btn" onclick="openModal('day3-beaches','Beach / Lunch Options','activity',false)">＋ Add spot</button>
            </div>
          </div>
        </div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Dinner back in Lisbon
            <div class="dinner-block">
              <div class="dinner-label">Restaurant Options</div>
              <ul class="option-list" id="day3-dinner"></ul>
              <button class="add-btn" onclick="openModal('day3-dinner','Dinner Options','dinner',false)">＋ Add restaurant</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card" style="animation-delay:0.2s">
      <div class="day-header">
        <div class="day-num">4</div>
        <div><div class="day-title">Lisbon → Porto 🚂</div><div class="day-subtitle">Travel Day + First Taste of Porto</div></div>
      </div>
      <div class="day-body">
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Train to Porto<div class="activity-note">~3.5 hours · book in advance on <a href="https://www.cp.pt" target="_blank">cp.pt</a></div></div></div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Check into Hotel
            <div class="dinner-block">
              <div class="dinner-label">Hotel Options</div>
              <ul class="option-list" id="day4-hotels"></ul>
              <button class="add-btn" onclick="openModal('day4-hotels','Hotel Options','hotel',false)">＋ Add hotel</button>
            </div>
          </div>
        </div>
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Livraria Lello<div class="activity-note">One of the world's most beautiful bookstores · €8 entry (deducted from any book purchase)</div></div></div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Dinner / Evening
            <div class="dinner-block">
              <div class="dinner-label">Options</div>
              <ul class="option-list" id="day4-dinner">
                <li><span>🍷</span><span><span class="opt-name">Caves Cálem</span><span class="opt-note"> — port wine tour (€20–45) + optional Fado show</span></span><button class="opt-remove" onclick="this.parentElement.remove()">✕</button></li>
              </ul>
              <button class="add-btn" onclick="openModal('day4-dinner','Evening Options','dinner',false)">＋ Add restaurant</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card" style="animation-delay:0.25s">
      <div class="day-header">
        <div class="day-num">5</div>
        <div><div class="day-title">Douro Valley Wine Tour 🍇</div><div class="day-subtitle">Day Trip into Wine Country</div></div>
      </div>
      <div class="day-body">
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Douro Valley Day Trip<div class="activity-note"><a href="https://oportoroadtrips.com/#tours" target="_blank">oportoroadtrips.com</a> — browse tours here</div></div></div>
        <div class="activity">
          <div class="activity-dot"></div>
          <div class="activity-text">
            Dinner
            <div class="dinner-block">
              <div class="dinner-label">Restaurant Options</div>
              <ul class="option-list" id="day5-dinner"></ul>
              <button class="add-btn" onclick="openModal('day5-dinner','Dinner Options','dinner',false)">＋ Add restaurant</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card" style="animation-delay:0.3s">
      <div class="day-header">
        <div class="day-num">6</div>
        <div><div class="day-title">Porto → Home ☹️</div><div class="day-subtitle">Departure Day</div></div>
      </div>
      <div class="day-body">
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Breakfast & Check Out</div></div>
        <div class="activity"><div class="activity-dot"></div><div class="activity-text">Flights home — until next time 🇵🇹</div></div>
      </div>
    </div>

  </div><!-- end #itinerary -->

  <!-- LISBON EATS -->
  <div class="section" id="lisbon-eats">
    <div class="section-title">Lisbon Restaurants</div>
    <div class="section-divider"></div>

    <div class="meal-label">☀️ Breakfast & Brunch</div>
    <div class="restaurant-grid" id="lisbon-brunch-grid">
      <div class="r-card brunch">
        <div class="r-name">Seagull Method Cafe</div>
        <div class="r-stars">⭐ 4.7</div>
        <div class="r-desc">Walk-ins only, 9AM–4PM</div>
        <span class="r-tag brunch-tag">Brunch</span>
      </div>
      <div class="r-card brunch">
        <div class="r-name">QUEST</div>
        <div class="r-stars">⭐ 4.8</div>
        <div class="r-desc">Famous cinnamon rolls & full breakfast menu</div>
        <span class="r-tag brunch-tag">Brunch</span>
      </div>
      <div class="r-card brunch">
        <div class="r-name">Confeitaria Nacional</div>
        <div class="r-stars">⭐ 4.4</div>
        <div class="r-desc">Lisbon's oldest patisserie — stunning interior</div>
        <span class="r-tag brunch-tag">Patisserie</span>
      </div>
      <div class="r-card add-card" onclick="openModal('lisbon-brunch-grid','Brunch Spot','brunch',true)">
        <div class="plus">＋</div><span class="add-label">Add a spot</span>
      </div>
    </div>

    <div class="meal-label">🍽 Lunch & Dinner</div>
    <div class="restaurant-grid" id="lisbon-dinner-grid">
      <div class="r-card">
        <div class="r-name">O Velho Eurico</div>
        <div class="r-stars">⭐ 4.6</div>
        <div class="r-desc">Local must-stop — reservation needed or expect a long wait</div>
        <span class="r-tag">Dinner</span>
      </div>
      <div class="r-card">
        <div class="r-name">Lupita</div>
        <div class="r-stars">⭐ 4.7</div>
        <div class="r-desc">Classic pizza spot beloved by locals</div>
        <span class="r-tag">Pizza</span>
      </div>
      <div class="r-card fancy">
        <div class="r-name">Belcanto</div>
        <div class="r-stars">⭐ 4.8 · ✦✦ Michelin</div>
        <div class="r-desc">Two Michelin stars, top 50 restaurant in the world. ~€265/pp</div>
        <span class="r-tag fancy-tag">Special Occasion</span>
      </div>
      <div class="r-card">
        <div class="r-name">Toca da Raposa</div>
        <div class="r-stars">⭐ 4.6</div>
        <div class="r-desc">Cute cocktail bar — great evening stop</div>
        <span class="r-tag">Cocktails</span>
      </div>
      <div class="r-card add-card" onclick="openModal('lisbon-dinner-grid','Restaurant','dinner',true)">
        <div class="plus">＋</div><span class="add-label">Add a spot</span>
      </div>
    </div>
  </div>

  <!-- PORTO EATS -->
  <div class="section" id="porto-eats">
    <div class="section-title">Porto Restaurants</div>
    <div class="section-divider"></div>

    <div class="meal-label">☀️ Breakfast & Brunch</div>
    <div class="restaurant-grid" id="porto-brunch-grid">
      <div class="r-card brunch">
        <div class="r-name">Garden Porto Cafe</div>
        <div class="r-stars">⭐ 4.7</div>
        <div class="r-desc">Aesthetic, lush surroundings with excellent savory brunch</div>
        <span class="r-tag brunch-tag">Brunch</span>
      </div>
      <div class="r-card brunch">
        <div class="r-name">Manteigaria</div>
        <div class="r-stars">⭐ 4.8</div>
        <div class="r-desc">Allegedly the best natas (custard tarts) in the country</div>
        <span class="r-tag brunch-tag">Pastéis de Nata</span>
      </div>
      <div class="r-card brunch">
        <div class="r-name">Leitaria da Quinta do Paço</div>
        <div class="r-stars">⭐ 4.5</div>
        <div class="r-desc">Famous for éclairs topped with real whipped cream</div>
        <span class="r-tag brunch-tag">Pastries</span>
      </div>
      <div class="r-card add-card" onclick="openModal('porto-brunch-grid','Brunch Spot','brunch',true)">
        <div class="plus">＋</div><span class="add-label">Add a spot</span>
      </div>
    </div>

    <div class="meal-label">🥪 Lunch</div>
    <div class="restaurant-grid" id="porto-lunch-grid">
      <div class="r-card">
        <div class="r-name">Gazela Cachorrinhos</div>
        <div class="r-stars">⭐ 4.6</div>
        <div class="r-desc">Home of the "Cachorrinho" — Porto's unique crispy hot dog</div>
        <span class="r-tag">Lunch</span>
      </div>
      <div class="r-card">
        <div class="r-name">Brasão Aliados</div>
        <div class="r-stars">⭐ 4.7</div>
        <div class="r-desc">High-quality Francesinhas — Porto's iconic sandwich</div>
        <span class="r-tag">Lunch</span>
      </div>
      <div class="r-card add-card" onclick="openModal('porto-lunch-grid','Lunch Spot','lunch',true)">
        <div class="plus">＋</div><span class="add-label">Add a spot</span>
      </div>
    </div>

    <div class="meal-label">🌙 Dinner</div>
    <div class="restaurant-grid" id="porto-dinner-grid">
      <div class="r-card">
        <div class="r-name">Taberna dos Mercadores</div>
        <div class="r-stars">⭐ 4.7</div>
        <div class="r-desc">Locals' must-stop in Ribeira — famous salt-crusted fish</div>
        <span class="r-tag">Dinner</span>
      </div>
      <div class="r-card">
        <div class="r-name">Culto ao Bacalhau</div>
        <div class="r-stars">⭐ 4.6</div>
        <div class="r-desc">Modern cod-centric dining inside the Bolhão Market</div>
        <span class="r-tag">Dinner</span>
      </div>
      <div class="r-card fancy">
        <div class="r-name">Euskalduna Studio</div>
        <div class="r-stars">⭐ 4.8 · ✦ Michelin</div>
        <div class="r-desc">Innovative tasting menu experience. ~€160/pp</div>
        <span class="r-tag fancy-tag">Special Occasion</span>
      </div>
      <div class="r-card add-card" onclick="openModal('porto-dinner-grid','Restaurant','dinner',true)">
        <div class="plus">＋</div><span class="add-label">Add a spot</span>
      </div>
    </div>
  </div>

  <!-- CONFIRMATIONS -->
  <div class="section" id="confirmations">
    <div class="section-title">Confirmations & Bookings</div>
    <div class="section-divider"></div>
    <div class="restaurant-grid" id="conf-grid">
      <div class="r-card add-card" onclick="openModal('conf-grid','Confirmation','hotel',true)">
        <div class="plus">＋</div>
        <span class="add-label">Add Booking</span>
      </div>
    </div>
  </div>

  <!-- TIPS -->
  <div class="section" id="tips">
    <div class="section-title">Additional Info</div>
    <div class="section-divider"></div>
    <div class="tip-box">
      <h3>🚂 Getting Around</h3>
      <div class="tip-item"><span>→</span><span>Train Lisbon → Porto: ~3.5 hrs. Book on <a href="https://www.cp.pt" target="_blank" style="color:var(--gold)">cp.pt</a></span></div>
      <div class="tip-item"><span>→</span><span>Cascais: ~40 min, ~€5 each way from Cais do Sodré</span></div>
      <div class="tip-item"><span>→</span><span>Tram 28 is iconic but crowded — go early morning</span></div>
    </div>
    <div class="tip-box" style="background: linear-gradient(135deg, #4A7C59, #2E5C3A);">
      <h3>🍷 Douro Valley</h3>
      <div class="tip-item"><span>→</span><span>Book ahead at <a href="https://oportoroadtrips.com/#tours" target="_blank" style="color:var(--gold)">oportoroadtrips.com</a></span></div>
      <div class="tip-item"><span>→</span><span>Most tours include wine tastings and lunch</span></div>
      <div class="tip-item"><span>→</span><span>Caves Cálem port tour: €20–45 + optional Fado show</span></div>
    </div>
    <div class="tip-box" style="background: linear-gradient(135deg, #8C5A2B, #6B3E1A);">
      <h3>🏛 Sights</h3>
      <div class="tip-item"><span>→</span><span>Livraria Lello: €8 entry, deducted from book purchase</span></div>
      <div class="tip-item"><span>→</span><span>Belém Tower: <strong>check renovation status</strong> before visiting</span></div>
      <div class="tip-item"><span>→</span><span>Book O Velho Eurico & Belcanto well in advance</span></div>
    </div>
  </div>

</div><!-- end .content -->

<script>
  function esc(s) { return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
  function escAttr(s) { return s.replace(/"/g,'&quot;'); }

  function showTab(id, btn) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    btn.classList.add('active');
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  // Enhance all activity bullets on load
  document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('.activity').forEach(act => enhanceActivity(act));
  });

  function enhanceActivity(act) {
    const textEl = act.querySelector('.activity-text');
    if (!textEl) return;
    let labelNode = null;
    for (let node of textEl.childNodes) {
      if (node.nodeType === Node.TEXT_NODE && node.textContent.trim()) { labelNode = node; break; }
    }
    const labelText = labelNode ? labelNode.textContent.trim() : '';
    const subList = document.createElement('ul');
    subList.className = 'sub-bullets';
    const bar = document.createElement('div');
    bar.className = 'act-bar';
    bar.innerHTML = '<button class="act-btn edit-btn">✏️ edit</button><button class="act-btn delete-btn">✕ delete</button><button class="act-btn sub-btn">＋ add note</button>';
    textEl.appendChild(subList);
    textEl.appendChild(bar);
    bar.querySelector('.delete-btn').addEventListener('click', () => act.remove());
    bar.querySelector('.edit-btn').addEventListener('click', () => {
      const current = labelNode ? labelNode.textContent.trim() : labelText;
      const input = document.createElement('input');
      input.type = 'text'; input.value = current; input.className = 'act-edit-input';
      if (labelNode) labelNode.textContent = '';
      textEl.insertBefore(input, textEl.firstChild);
      input.focus();
      const commit = () => { const val = input.value.trim() || current; if (labelNode) labelNode.textContent = val; input.remove(); };
      input.addEventListener('blur', commit);
      input.addEventListener('keydown', e => { if (e.key === 'Enter') input.blur(); if (e.key === 'Escape') { input.value = current; input.blur(); } });
    });
    bar.querySelector('.sub-btn').addEventListener('click', () => openSubModal(subList));
  }

  // Sub-note modal
  let _subTarget = null;
  function openSubModal(ulEl) {
    _subTarget = ulEl;
    document.getElementById('sb-text').value = '';
    document.getElementById('sb-link').value = '';
    document.getElementById('sb-text').classList.remove('error');
    document.getElementById('sub-modal').classList.add('open');
    setTimeout(() => document.getElementById('sb-text').focus(), 150);
  }
  function closeSubModal() { document.getElementById('sub-modal').classList.remove('open'); }
  function saveSubBullet() {
    const text = document.getElementById('sb-text').value.trim();
    if (!text) { document.getElementById('sb-text').classList.add('error'); document.getElementById('sb-text').focus(); return; }
    const link = document.getElementById('sb-link').value.trim();
    const li = document.createElement('li');
    let html = '<span class="sub-bullet-dot"></span><span class="sub-bullet-text">' + esc(text);
    if (link) { const label = link.replace(/^https?:\/\//, '').replace(/\/$/, ''); html += '<a class="sub-bullet-link" href="' + escAttr(link) + '" target="_blank">🔗 ' + esc(label) + '</a>'; }
    html += '</span><button class="sub-remove" onclick="this.parentElement.remove()">✕</button>';
    li.innerHTML = html;
    _subTarget.appendChild(li);
    closeSubModal();
  }

  // Main modal
  let _targetId = null, _isCard = false, _defaultType = 'dinner';
  function openModal(targetId, title, defaultType, isCard) {
    _targetId = targetId; _isCard = isCard; _defaultType = defaultType;
    document.getElementById('modal-title').textContent = '＋ Add ' + title;
    ['m-name','m-desc','m-rating','m-link'].forEach(id => document.getElementById(id).value = '');
    document.getElementById('m-type').value = defaultType;
    document.getElementById('m-name').classList.remove('error');
    document.getElementById('type-row').style.display = isCard ? 'block' : 'none';
    document.getElementById('modal').classList.add('open');
    setTimeout(() => document.getElementById('m-name').focus(), 150);
  }
  function closeModal() { document.getElementById('modal').classList.remove('open'); }
  function handleOverlayClick(e) { if (e.target === document.getElementById('modal')) closeModal(); }
  document.addEventListener('keydown', e => { if (e.key === 'Escape') { closeModal(); closeSubModal(); } });

  function saveEntry() {
    const name = document.getElementById('m-name').value.trim();
    if (!name) { document.getElementById('m-name').classList.add('error'); document.getElementById('m-name').focus(); return; }
    const desc = document.getElementById('m-desc').value.trim();
    const rating = document.getElementById('m-rating').value.trim();
    const link = document.getElementById('m-link').value.trim();
    const type = document.getElementById('m-type').value;
    if (_isCard) addCard(_targetId, name, desc, rating, link, type);
    else addListItem(_targetId, name, desc, rating, link);
    closeModal();
  }

  function addListItem(listId, name, desc, rating, link) {
    const ul = document.getElementById(listId);
    const li = document.createElement('li');
    let html = '<span>📍</span><span><span class="opt-name">' + esc(name) + '</span>';
    if (rating) html += ' <span style="color:var(--gold);font-size:0.78rem;">' + esc(rating) + '</span>';
    if (desc) html += '<span class="opt-note"> — ' + esc(desc) + '</span>';
    if (link) { const label = link.replace(/^https?:\/\//, '').split('/')[0]; html += '<br><a class="opt-link" href="' + escAttr(link) + '" target="_blank">🔗 ' + esc(label) + '</a>'; }
    html += '</span><button class="opt-remove" onclick="this.parentElement.remove()">✕</button>';
    li.innerHTML = html;
    ul.appendChild(li);
  }

  function addCard(gridId, name, desc, rating, link, type) {
    const grid = document.getElementById(gridId);
    const addCardEl = grid.querySelector('.add-card');
    const card = document.createElement('div');
    const typeToClass = { brunch:'brunch', fancy:'fancy' };
    const typeToTag = { dinner:'Dinner', brunch:'Brunch', lunch:'Lunch', fancy:'Special Occasion', cocktails:'Cocktails', hotel:'Hotel', activity:'Activity' };
    const typeToTagClass = { brunch:'brunch-tag', fancy:'fancy-tag' };
    card.className = 'r-card ' + (typeToClass[type]||'');
    let html = '<button class="r-delete" onclick="this.parentElement.remove()">✕</button>';
    html += '<div class="r-name">' + esc(name) + '</div>';
    if (rating) html += '<div class="r-stars">' + esc(rating) + '</div>';
    if (desc) html += '<div class="r-desc">' + esc(desc) + '</div>';
    if (link) { const label = link.replace(/^https?:\/\//, '').replace(/\/$/, ''); html += '<a class="r-link" href="' + escAttr(link) + '" target="_blank">🔗 ' + esc(label) + '</a>'; }
    html += '<span class="r-tag ' + (typeToTagClass[type]||'') + '">' + (typeToTag[type]||'Restaurant') + '</span>';
    card.innerHTML = html;
    grid.insertBefore(card, addCardEl);
  }

  // Inline date editing — click to turn into input, blur/enter to save
  function editTripDate() {
    const span = document.getElementById('display-date');
    if (span.querySelector('input')) return; // already editing
    const current = span.textContent;
    const input = document.createElement('input');
    input.className = 'date-edit-input';
    input.value = current;
    span.textContent = '';
    span.appendChild(input);
    input.focus();
    input.select();
    const commit = () => {
      const val = input.value.trim() || current;
      span.textContent = val;
    };
    input.addEventListener('blur', commit);
    input.addEventListener('keydown', e => {
      if (e.key === 'Enter') input.blur();
      if (e.key === 'Escape') { input.value = current; input.blur(); }
    });
  }
</script>
</body>
</html>
