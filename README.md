<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, shrink-to-fit=no">
  <title>Nia - Keuangan Jajan</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #fef6e4 0%, #fde9e0 100%);
      font-family: 'Segoe UI', 'Poppins', system-ui, -apple-system, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 1.5rem;
      margin: 0;
    }

    .app-container {
      max-width: 480px;
      width: 100%;
      background: rgba(255, 248, 245, 0.9);
      backdrop-filter: blur(18px);
      background: #fffbf5;
      border-radius: 2.5rem;
      box-shadow: 0 25px 45px rgba(180, 130, 90, 0.25), 0 10px 20px rgba(0, 0, 0, 0.1);
      padding: 1.8rem 1.5rem 2.2rem;
      border: 1px solid rgba(255, 215, 170, 0.7);
      transition: all 0.2s ease;
    }

    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 1.8rem;
    }

    .logo-area {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .nia-badge {
      background: #ff8c5a;
      color: white;
      font-weight: 800;
      font-size: 1.9rem;
      padding: 0.3rem 1.2rem;
      border-radius: 3rem;
      letter-spacing: 1px;
      box-shadow: 0 8px 14px rgba(255, 120, 60, 0.4);
      background: linear-gradient(135deg, #ff7b4a, #ff5e3a);
      cursor: pointer;
      transition: all 0.25s ease;
      user-select: none;
      border: none;
      display: inline-block;
    }

    .nia-badge:active {
      transform: scale(0.94);
      background: linear-gradient(135deg, #ff5e3a, #e64a2e);
      box-shadow: 0 5px 10px rgba(220, 70, 30, 0.5);
    }

    .saldo-card {
      background: #f9efe2;
      border-radius: 2rem;
      padding: 1.2rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2rem;
      background: linear-gradient(115deg, #fae7d3, #fff0e0);
      box-shadow: 0 10px 18px rgba(200, 140, 70, 0.2);
    }

    .saldo-label {
      font-weight: 600;
      color: #7b5e3b;
      font-size: 0.95rem;
      letter-spacing: 0.4px;
    }

    .saldo-value {
      font-weight: 800;
      font-size: 2.2rem;
      color: #3d2e1c;
      background: white;
      padding: 0.2rem 1.2rem;
      border-radius: 2.5rem;
      box-shadow: inset 0 1px 6px rgba(0,0,0,0.05);
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1.1rem;
      margin: 1.8rem 0 1.5rem;
    }

    .menu-item {
      background: white;
      border-radius: 1.8rem;
      padding: 1.3rem 0.6rem 0.9rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      box-shadow: 0 12px 20px rgba(150, 100, 60, 0.12);
      transition: all 0.2s ease;
      cursor: pointer;
      border: 1.5px solid #ffe5d0;
      background: #fffdf9;
      user-select: none;
    }

    .menu-item:active {
      transform: translateY(3px);
      box-shadow: 0 6px 14px rgba(140, 90, 40, 0.2);
      background: #fff5ea;
      border-color: #fbb68c;
    }

    .emoji-icon {
      font-size: 3rem;
      filter: drop-shadow(0 6px 6px rgba(0,0,0,0.15));
      margin-bottom: 0.25rem;
    }

    .menu-name {
      font-weight: 700;
      font-size: 1.1rem;
      color: #543e28;
      margin: 0.2rem 0;
    }

    .menu-price {
      background: #fcede4;
      padding: 0.35rem 1rem;
      border-radius: 2rem;
      font-weight: 700;
      color: #b4532e;
      font-size: 0.9rem;
      margin-top: 0.2rem;
    }

    .riwayat-title {
      font-weight: 700;
      color: #60452b;
      margin: 1.2rem 0 0.5rem;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .history-list {
      background: #fefaf2;
      border-radius: 1.6rem;
      padding: 0.8rem 1rem;
      max-height: 130px;
      overflow-y: auto;
      background: #fffcf3;
      box-shadow: inset 0 1px 8px rgba(180, 130, 70, 0.08);
      font-size: 0.9rem;
      color: #4d3b27;
      border: 1px solid #f3e1cb;
    }

    .history-item {
      display: flex;
      justify-content: space-between;
      padding: 0.4rem 0;
      border-bottom: 1px dashed #ebd7bc;
    }

    .history-item:last-child {
      border-bottom: none;
    }

    .reset-btn {
      background: none;
      border: 1.5px solid #d8b188;
      background: #fff8f2;
      color: #6b4a32;
      font-weight: 600;
      padding: 0.7rem 1.4rem;
      border-radius: 2.5rem;
      margin-top: 1rem;
      cursor: pointer;
      transition: 0.2s;
      font-size: 0.9rem;
      display: inline-flex;
      align-items: center;
      gap: 0.3rem;
      box-shadow: 0 4px 8px rgba(140, 100, 50, 0.1);
    }

    .reset-btn:active {
      background: #f5e2d1;
      border-color: #b0723a;
      color: #3e2a19;
    }

    .flex-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .empty-history {
      color: #aa8b72;
      font-style: italic;
      padding: 0.6rem 0;
      text-align: center;
    }
  </style>
</head>
<body>
<div class="app-container">
  <!-- Header dengan Nia yang bisa diklik -->
  <div class="header">
    <div class="logo-area">
      <span class="nia-badge" id="niaClickable">Nia</span>
      <span style="font-weight: 600; color: #956b42; margin-left: 0.2rem;">💰</span>
    </div>
    <div style="color: #b1895e; font-weight: 500; font-size: 0.9rem;">jajan tracker</div>
  </div>

  <!-- Saldo -->
  <div class="saldo-card">
    <span class="saldo-label">💵 Saldo Nia</span>
    <span class="saldo-value" id="saldoDisplay">Rp 50.000</span>
  </div>

  <!-- Menu grid: bakso, matcha, chikuro, pancong lumer -->
  <div class="menu-grid">
    <!-- Bakso -->
    <div class="menu-item" data-menu="bakso" data-harga="12000">
      <span class="emoji-icon">🍜</span>
      <span class="menu-name">Bakso</span>
      <span class="menu-price">Rp 12.000</span>
    </div>
    <!-- Matcha -->
    <div class="menu-item" data-menu="matcha" data-harga="15000">
      <span class="emoji-icon">🍵</span>
      <span class="menu-name">Matcha</span>
      <span class="menu-price">Rp 15.000</span>
    </div>
    <!-- Chikuro -->
    <div class="menu-item" data-menu="chikuro" data-harga="10000">
      <span class="emoji-icon">🍢</span>
      <span class="menu-name">Chikuro</span>
      <span class="menu-price">Rp 10.000</span>
    </div>
    <!-- Pancong Lumer -->
    <div class="menu-item" data-menu="pancong lumer" data-harga="13000">
      <span class="emoji-icon">🥞</span>
      <span class="menu-name">Pancong Lumer</span>
      <span class="menu-price">Rp 13.000</span>
    </div>
  </div>

  <!-- Riwayat Transaksi -->
  <div class="riwayat-title">
    <span>📋 Riwayat Jajan</span>
  </div>
  <div class="history-list" id="historyContainer">
    <div class="empty-history">Belum ada transaksi 🍃</div>
  </div>

  <!-- Tombol reset & info -->
  <div class="flex-row">
    <button class="reset-btn" id="resetButton">
      <span>🔄</span> Reset Saldo
    </button>
    <span style="font-size: 0.8rem; color: #b7a082;">klik menu untuk beli</span>
  </div>
</div>

<script>
  (function() {
    // --- Data Keuangan ---
    const SALDO_AWAL = 50000;
    let saldo = SALDO_AWAL;
    
    // Riwayat transaksi (array of objects)
    let historyTransactions = [];

    // Element references
    const saldoDisplay = document.getElementById('saldoDisplay');
    const historyContainer = document.getElementById('historyContainer');
    const menuItems = document.querySelectorAll('.menu-item');
    const resetBtn = document.getElementById('resetButton');
    const niaBadge = document.getElementById('niaClickable');

    // --- Fungsi format rupiah ---
    function formatRupiah(angka) {
      return 'Rp ' + angka.toLocaleString('id-ID');
    }

    // --- Update tampilan saldo ---
    function updateSaldoUI() {
      saldoDisplay.textContent = formatRupiah(saldo);
    }

    // --- Render riwayat ke HTML ---
    function renderHistory() {
      historyContainer.innerHTML = '';
      
      if (historyTransactions.length === 0) {
        historyContainer.innerHTML = '<div class="empty-history">Belum ada transaksi 🍃</div>';
        return;
      }

      // Tampilkan dari terbaru ke lama (paling atas adalah transaksi terakhir)
      const reversed = [...historyTransactions].reverse();
      
      reversed.forEach(trans => {
        const historyItem = document.createElement('div');
        historyItem.className = 'history-item';
        
        // Format: "Bakso -Rp12.000" 
        historyItem.innerHTML = `
          <span>🍴 ${trans.menu}</span>
          <span style="font-weight: 700; color: #c0452a;">-${formatRupiah(trans.harga)}</span>
        `;
        historyContainer.appendChild(historyItem);
      });
    }

    // --- Cek saldo cukup & lakukan pembelian ---
    function beliMenu(menuName, harga) {
      if (saldo < harga) {
        alert(`❌ Saldo tidak cukup untuk membeli ${menuName}.\nButuh ${formatRupiah(harga)}, saldo kamu ${formatRupiah(saldo)}.`);
        return false;
      }

      // Kurangi saldo
      saldo -= harga;
      
      // Tambah ke riwayat
      historyTransactions.push({
        menu: menuName,
        harga: harga,
        waktu: new Date().toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' })
      });
      
      // Update UI
      updateSaldoUI();
      renderHistory();
      
      // Feedback ringan (opsional bisa getar atau animasi kecil)
      return true;
    }

    // --- Reset saldo ke awal & kosongkan riwayat ---
    function resetKeuangan() {
      if (historyTransactions.length === 0 && saldo === SALDO_AWAL) {
        alert('✨ Saldo masih utuh dan belum ada transaksi.');
        return;
      }
      
      const konfirmasi = confirm('🔄 Yakin ingin mereset saldo ke Rp50.000 dan menghapus riwayat?');
      if (!konfirmasi) return;
      
      saldo = SALDO_AWAL;
      historyTransactions = [];
      updateSaldoUI();
      renderHistory();
    }

    // --- Klik pada nama "Nia" (bisa diklik) ---
    function handleNiaClick() {
      alert('🧸 Halo! Aku Nia, asisten keuangan jajanmu. Kelola bakso, matcha, chikuro & pancong lumer dengan bijak ya!');
    }

    // --- Event listener untuk setiap menu item ---
    menuItems.forEach(item => {
      item.addEventListener('click', function(e) {
        // Ambil data dari atribut
        const menu = this.getAttribute('data-menu');
        const harga = parseInt(this.getAttribute('data-harga'), 10);
        
        if (!menu || isNaN(harga)) return;
        
        // Panggil fungsi beli
        const sukses = beliMenu(menu, harga);
        
        // Sedikit animasi feedback jika berhasil (opsional)
        if (sukses) {
          // Bisa tambahkan efek kecil, misal getar kecil dengan class
          this.style.transition = '0.1s';
          this.style.transform = 'scale(0.96)';
          setTimeout(() => {
            this.style.transform = '';
          }, 120);
        }
      });
    });

    // --- Event listener tombol reset ---
    resetBtn.addEventListener('click', resetKeuangan);

    // --- Event listener untuk Nia badge (bisa diklik) ---
    niaBadge.addEventListener('click', handleNiaClick);

    // --- Inisialisasi UI pertama kali ---
    function initApp() {
      // Pastikan saldo sesuai awal
      saldo = SALDO_AWAL;
      historyTransactions = [];
      updateSaldoUI();
      renderHistory();
    }

    initApp();

    // Optional: Menjaga agar klik pada menu tidak memicu event aneh di mobile
    // dan mencegah double tap zoom (sudah ada viewport)
  })();
</script>
</body>
</html>
