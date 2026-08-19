# ⚔️ Dungeon Explorer

> *"Explore. Fight. Survive. Become a Legend."*

**Dungeon Explorer** adalah game *turn-based RPG dungeon crawler* berbasis web (*single-file client-side application*) bertema *Dark Fantasy*. Game ini dapat dimainkan langsung di browser mana pun tanpa memerlukan server, database eksternal, atau instalasi dependensi tambahan. Semua grafis menggunakan ilustrasi vektor SVG orisinal, audio prosedural berbasis Web Audio API, serta sistem penyimpanan otomatis (*auto-save*) menggunakan browser `localStorage`.

---

## 🎮 Fitur Utama

- **Turn-Based Combat & Dynamic Skills**: Pertarungan taktis berbasis giliran dengan formula penetrasi kerusakan seimbang, peluang *critical strike*, dan skill *Fire Strike* (terbuka di Lv. 3).
- **Pergantian Perlengkapan Langsung (*In-Combat Gear Switching*)**: Akses inventaris kapan saja untuk mengganti senjata, armor, atau meminum potion saat bertarung tanpa membatalkan pertempuran.
- **Sistem Potion Fleksibel (*Unlimited Free Action*)**: Meminum potion tidak memakan giliran menyerang (*Free Action*) dan tidak dibatasi per-turn, memberi kendali taktis penuh saat menghadapi pertarungan sulit.
- **Sistem Tingkat Kelangkaan (*Rarity Tier*)**: 5 tingkatan item (**Common 55%**, **Uncommon 25%**, **Rare 13%**, **Epic 6%**, dan **Legendary 1%**) dengan penskalaan bonus stat dan harga jual/beli.
- **Sistem Leveling & Pilihan Stat**: Setiap naik level memulihkan HP penuh dan memberikan 3 pilihan peningkatan stat permanen (+5 ATK, +3 DEF, atau +20 MAX HP).
- **Milestone Reward**: Mendapatkan 1 perlengkapan acak gratis setiap kelipatan 10 level (Level 10, 20, 30, dst.).
- **Eksplorasi Non-Linear 3 Arah**: Memilih rute `← Kiri`, `↑ Maju`, atau `→ Kanan` pada setiap ruangan.
- **Sistem Pendamping Tempur (*Companion System*)**: Membebaskan serigala di dungeon memungkinkan pemain merekrut *Tamed Shadow Wolf* yang menyerang otomatis dan bertindak sebagai penyerap kerusakan (*meat shield*).
- **Kedai & Ransum Penjelajah (*Tavern Pre-Run Buffs*)**: Menyantap hidangan hangat seharga 20 Gold di Sanctuary untuk memulihkan 100% HP dan membawa *Run Buff* pilihan (+10 Max HP, +1 ATK, +1 DEF, atau +10% Gold/Luck).
- **Encounter Dinamis & Teka-Teki**: Berisi event Landasan Tempa (*Ancient Anvil*), ujian teka-teki logika *The Riddler*, Robekan Dimensi (*Dimensional Rift*), Altar Darah, Mata Air Suci, Perkemahan, Dadu Goblin, dan Ruang Cermin Kloning.
- **Ekonomi & Toko Seimbang**: Town Shop di Sanctuary (fitur beli, jual dengan harga 50%, dan restock) serta Mysterious Merchant di dungeon dengan diskon 50–70%.
- **Sistem Kematian Aman (*Safe Haven Death*)**: Jika HP habis, pemain kembali ke Sanctuary dengan HP penuh tanpa kehilangan inventaris, perlengkapan yang terpasang, maupun Gold.
- **Penyimpanan Lokal & Ekspor**: Autosave berkala ke `localStorage`, tombol simpan manual, fitur ekspor save data JSON, dan reset data.

---

## 👹 Bestiary: Panduan Boss & Mini-Boss

Dungeon Explorer menghadirkan musuh-musuh elit dan boss dengan mekanik unik yang menuntut strategi berbeda:

### 1. Boss Utama Lantai (*Floor Bosses*)

#### 🗿 Dungeon Guardian Golem - *Boss Lantai 1*
- **Deskripsi**: Golem batu purba berlumut dengan inti magma menyala di bagian dada.
- **Karakteristik**: Memiliki pertahanan (DEF) dan HP yang tebal serta serangan gempa bumi (*Earth Slam*).
- **Hadiah Kemenangan**: Perlengkapan bertipe Epic, Gold melimpah, dan akses ke lantai berikutnya.

#### ⚖️ Taking and Giving (The Dual Arbiter) - *Boss Khusus Lantai 2*
- **Deskripsi**: Entitas kuno berwajah ganda dengan dua topeng simetris yang mengatur keseimbangan dungeon.
- **Mekanik Pertarungan Asimetris (Rotasi Mode Tiap 2 Turn)**:
  - **Mode Taking (Topeng Obsidian)**:
    - *Stat Siphon*: Menyerap 3 ATK dari pemain untuk memperkuat dirinya.
    - *Soul Drain*: Menghisap 12% HP pemain untuk memulihkan darah boss.
    - *Greed Tax*: Menyerang sambil mencuri Gold dari kantong pemain.
  - **Mode Giving (Topeng Emas)**:
    - *Dangerous Gift*: Memberikan pemain buff besar $+12\text{ ATK}$ selama 1 giliran (kesempatan emas pemain untuk menghabisi boss, namun waspada terhadap serangan balasan).
    - *Cursed Benevolence*: Memulihkan $+25\text{ HP}$ pemain tetapi menyegel penggunaan skill pemain selama 2 giliran.
- **Hadiah Kemenangan**: **Scales of Equilibrium (Legendary Relic/Armor)**, Gold dalam jumlah masif, dan EXP besar.

#### 🐉 Abyssal Shadow Dragon - *Boss Lantai 3+*
- **Deskripsi**: Naga hitam bertanduk ganda yang memuntahkan semburan api ungu kegelapan.
- **Karakteristik**: Serangan (ATK) tinggi dengan efek bakar (*Burn DoT*) yang menguji ketahanan armor dan manajemen potion.
- **Hadiah Kemenangan**: Senjata legendaris **Dragon Slayer** dan timbunan emas harta naga.

---

### 2. Mini-Boss Tersembunyi (*Encounter Mini-Bosses*)

| Mini-Boss | Cara Memicu / Lokasi | Mekanik Pertarungan | Hadiah Spesial |
| :--- | :--- | :--- | :--- |
| **🎭 The Riddler** | Gagal menjawab teka-teki atau menantang duel di event *Riddler's Trial*. | Memiliki serangan psikis (*Mind Blast*) dan kelincahan tinggi (peluang ilusi miss). | **Ring of Enigma / Monocle** (Bonus Critical Hit & EXP). |
| **⏳ Chrono Warden** | Terhisap ke dalam anomali waktu saat melompati *Dimensional Rift*. | Manipulasi waktu (*Time Reversal* saat darah kritis & *Haste* serangan beruntun). | **Chrono Relic** & Tumpukan Emas Dimensi. |
| **🪞 Doppelgänger** | Memasuki *The Obsidian Mirror Room*. | Kloning sempurna 1:1 dari stat, senjata, armor, dan HP pemain saat itu. | **Soul Mirror Shard** (+5 ATK & DEF permanen) + Status *Worthy Soul* (Peluang bertemu dewa naik $10\times$). |
| **⚖️ The Judge** | Menantang vonis pengadilan di event *The Judge*. | Memantulkan 20% damage fisik pemain (*recoil*) dan mengeksekusi *True Damage* tiap 3 turn. | **Judge's Gavel** (Senjata berefek Stun). |
| **👻 Specter of Fallen Hero** | Gagal menarik pedang kuno di event *Cursed Blade in Stone*. | Arwah ksatria yang menggunakan jurus tebasan beruntun (*Spectral Blade*). | **Cursed Longsword** (Senjata ATK sangat tinggi). |
| **🍖 Gluttony Mimic** | Memakan hidangan beracun di event *Suspicious Banquet*. | Meja makan berubah menjadi monster bertaring raksasa dengan rahang mematikan. | **Chef's Elixir (100% Full Heal Potion)** & Gold. |
| **👺 Goblin Loan Shark** | Menang beruntun di judi dadu di event *Goblin Gambler*. | Goblin raksasa bersenjatakan buku jari berduri (*Spiked Knuckles*). | **Gambler's Lucky Dice** (Meningkatkan drop rate) + Semua uang taruhan. |

---

## 🕹️ Cara Bermain

1. **Memulai Permainan**: Masukkan nama pahlawan Anda di menu *New Game*.
2. **Di Sanctuary (Town Hub)**:
   - Kunjungi **Tavern** untuk menikmati hidangan seharga 20 Gold yang memulihkan 100% HP dan memberikan *Run Buff*.
   - Kunjungi **Town Shop** untuk membeli perlengkapan baru atau menjual hasil jarahan.
   - Buka **Inventory** untuk memasang senjata dan armor terkuat.
   - Tekan **Enter Dungeon** untuk memulai penjelajahan.
3. **Di Dalam Dungeon**:
   - Pilih salah satu dari 3 lorong rute di setiap ruangan (`Left`, `Forward`, `Right`).
   - Bertarung melawan monster, tempa senjata di *Ancient Anvil*, rekrut *Shadow Wolf Companion*, atau pecahkan teka-teki *The Riddler*.
4. **Strategi Pertarungan**:
   - Manfaatkan *Fire Strike* (terbuka di Lv. 3) saat cooldown selesai.
   - Buka inventaris di tengah pertarungan kapan saja untuk meminum potion tanpa membuang giliran menyerang.

---

## 🛠️ Teknologi yang Digunakan

- **HTML5**: Struktur *single-page application* semantik.
- **CSS3**: Desain responsif bertema *Dark Fantasy*, tata letak CSS Grid & Flexbox, animasi getar (*shake effects*) & transisi halus.
- **JavaScript (ES6+)**: Engine permainan berbasis objek, status pertempuran, state management, dan algoritma probabilitas RNG.
- **Inline SVG**: Ilustrasi grafis vektor resolusi tinggi tanpa dependensi file eksternal.
- **Web Audio API**: Generator efek suara sintetis (SFX) prosedural *zero-dependency*.
- **Web Storage API**: Penyimpanan progres permainan lokal (*localStorage*).

---

## 📜 Changelog

### [v1.2.0] - Pembaruan Balancing, Ransum Kedai & Tampilan Tas (Terbaru)
- **Balancing & Perbaikan Formula Kerusakan**:
  - Memperbarui formula perhitungan damage: $\max(\text{ATK} \times 35\%, \text{ATK} - \text{DEF} \times 75\%)$. Mengatasi *bug* di mana serangan musuh (seperti Bandit) hanya menghasilkan 1 damage ketika pemain memiliki DEF tinggi.
  - Pembagian pool monster per lantai: Lantai 1 hanya memunculkan monster awal (*Slime, Goblin, Skeleton, Dark Wolf*), Lantai 2 menambahkan *Bandit & Orc*, Lantai 3+ membuka *Dark Knight & Demon*.
  - Multiplier HP musuh Elite di Lantai 1 dikalibrasi turun dari $1.9\times$ menjadi $1.3\times$ (berkisar 55–65 HP) dengan tingkat kemunculan diturunkan menjadi 0–5%.
- **Sistem Kedai & Ransum (*Tavern Feast 20 Gold*)**:
  - Mengubah fungsi Tavern menjadi hidangan berbayar 20 Gold yang memulihkan 100% HP dan memberikan buff penjelajahan (*Sup Daging +10 Max HP*, *Bir Rempah +1 ATK*, *Teh Kulit Besi +1 DEF*, *Kopi Rumor +10% Luck*).
  - Menambahkan opsi cadangan gratis *"Istirahat Bangku Kedai"* untuk memulihkan 100% HP tanpa buff jika pemain kehabisan Gold.
- **Penyempurnaan Tampilan Tas (*Backpack UI*)**:
  - Menghapus penomoran indeks urutan item (`[1]`, `[2]`) yang membingungkan.
  - Menambahkan badge jumlah otomatis (**`x2`**, **`x3`**) untuk potion dan item bertumpuk.
- **Sistem Potion Bebas (*Unlimited Free Action*)**:
  - Mengonfirmasi penggunaan potion sebagai *Free Action* tanpa membuang giliran menyerang dan tanpa batasan jumlah per-turn.

---

### [v1.1.0] - Ekspansi Encounter, Ilustrasi Vektor & Boss Unik
- **Visual Vektor SVG**:
  - Penambahan set ilustrasi vektor SVG resolusi tinggi untuk seluruh monster, mini-boss, dan boss.
- **Boss & Mini-Boss Baru**:
  - Penambahan Boss Khusus **Taking and Giving (The Dual Arbiter)** dengan mekanik dua fase (*Taking Mode* vs *Giving Mode*).
  - Penambahan Mini-Boss: **The Riddler**, **Chrono Warden**, **Doppelgänger**, **The Judge**, **Specter of the Fallen Hero**, **Gluttony Mimic**, dan **Goblin Loan Shark**.
- **Sistem Pendamping Tempur (*Companion*)**:
  - Penambahan fitur rekrutmen *Tamed Shadow Wolf* dengan bar HP mandiri yang membantu menyerang musuh dan menyerap damage di combat.
- **Encounter Dinamis**:
  - Penambahan Landasan Tempa (*Ancient Anvil*), Mata Air Suci (*Fountain of Purity*), Altar Darah (*Blood Shrine*), Robekan Dimensi (*Dimensional Rift*), dan Dadu Goblin.

---

### [v1.0.0] - Rilis Fondasi Awal (Initial Release)
- **Sistem Dasar**:
  - Pembuatan karakter hero, sistem stat dasar (Level, HP, Max HP, ATK, DEF, EXP, Gold).
  - Sistem leveling dengan penskalaan kebutuhan EXP dan pemilihan stat (+5 ATK, +3 DEF, +20 MAX HP).
  - Sistem *Milestone Reward* setiap kelipatan 10 level.
- **Combat & Inventory**:
  - Pertarungan berbasis giliran (*Turn-Based*) dengan opsi Attack, Skill (Fire Strike Lv. 3), Inventory, dan Flee.
  - Fitur pergantian senjata/armor dan konsumsi potion saat bertarung (*in-battle switching*).
  - Sistem 5 tingkat kelangkaan item (Common, Uncommon, Rare, Epic, Legendary).
- **Dungeon & Kota**:
  - Navigasi dungeon non-linear 3 arah (Left, Forward, Right).
  - Ruangan Monster, Ruangan Elite, Ruangan Boss, dan Ruangan Peti Harta/Jebakan.
  - Sanctuary Hub dengan Town Shop (beli/jual 50%/restock) dan Tavern Rest.
  - Autosave dan penyimpanan lokal via `localStorage`.

---

## 📄 Lisensi
Proyek ini dibuat untuk tujuan pembelajaran dan pengembangan game independen. Bebas dimodifikasi dan dikembangkan lebih lanjut.
---

## 🤖 Catatan Pengembangan & Transparansi AI

Game ini dikembangkan dengan bantuan AI (*Gemini Spark*) dalam proses pembuatannya, terutama untuk membantu penulisan kode awal, eksplorasi fitur teknis, dan debugging. 

Perancangan konsep permainan, arah kreatif, sistem balancing, pengujian (*testing*), serta penyempurnaan fitur dilakukan secara mandiri dan bertahap oleh pengembang.

---
