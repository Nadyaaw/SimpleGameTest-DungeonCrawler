# ⚔️ Dungeon Explorer

> *"Explore. Fight. Survive. Become a Legend."*

**Dungeon Explorer** adalah game *turn-based RPG dungeon crawler* berbasis web (*single-file client-side application*) bertema *Dark Fantasy*. Game ini dapat dimainkan langsung di browser mana pun tanpa memerlukan server, database eksternal, atau instalasi dependensi tambahan. Semua grafis menggunakan ilustrasi vektor SVG orisinal, audio prosedural berbasis Web Audio API, serta sistem penyimpanan otomatis (*auto-save*) menggunakan browser `localStorage`.

---

## 🎮 Fitur Utama

- **Turn-Based Combat & Skill System**: Pertarungan taktis berbasis giliran dengan formula kalkulasi kerusakan seimbang, peluang *critical strike*, dan skill *Fire Strike* (terbuka di Lv. 3).
- **Pergantian Perlengkapan Langsung (*In-Combat Gear Switching*)**: Akses inventaris kapan saja untuk mengganti senjata, armor, atau meminum potion saat bertarung tanpa membatalkan pertempuran.
- **Sistem Tingkat Kelangkaan (*Rarity Tier*)**: 5 tingkatan item (**Common 55%**, **Uncommon 25%**, **Rare 13%**, **Epic 6%**, dan **Legendary 1%**) dengan penskalaan bonus stat dan harga jual/beli.
- **Sistem Leveling & Pilihan Stat**: Setiap naik level memulihkan HP penuh dan memberikan 3 pilihan peningkatan stat permanen (+5 ATK, +3 DEF, atau +20 MAX HP).
- **Milestone Reward**: Mendapatkan 1 perlengkapan acak gratis setiap kelipatan 10 level (Level 10, 20, 30, dst.).
- **Eksplorasi Non-Linear 3 Arah**: Memilih rute `← Kiri`, `↑ Maju`, atau `→ Kanan` pada setiap ruangan.
- **Sistem Pendamping Tempur (*Companion System*)**: Membebaskan serigala di dungeon memungkinkan pemain merekrut pendamping tempur yang menyerang otomatis dan bertindak sebagai penyerap kerusakan (*meat shield*).
- **Encounter Dinamis & Teka-Teki**: Berisi event Landasan Tempa (*Ancient Anvil*), ujian teka-teki logika *The Riddler*, Robekan Dimensi (*Dimensional Rift*), Altar Darah, Mata Air Suci, Perkemahan, dan Dadu Goblin.
- **Ekonomi & Toko Seimbang**: Town Shop di Sanctuary (fitur beli, jual dengan harga 50%, dan restock) serta Mysterious Merchant di dungeon dengan diskon 50–70%.
- **Sistem Kematian Aman (*Safe Haven Death*)**: Jika HP habis, pemain kembali ke Sanctuary dengan HP penuh tanpa kehilangan inventaris, perlengkapan yang terpasang, maupun Gold.
- **Penyimpanan Lokal & Ekspor**: Autosave berkala ke `localStorage`, tombol simpan manual, fitur ekspor save data JSON, dan reset data.

---

## 👹 Bestiary: Panduan Boss & Mini-Boss

Dungeon Explorer menghadirkan musuh-musuh elit dan boss dengan mekanik unik yang menuntut strategi berbeda:

### 1. Boss Utama Lantai (*Floor Bosses*)

#### ⚖️ Taking and Giving (The Dual Arbiter) - *Boss Khusus Lantai 2*
- **Deskripsi**: Entitas kuno berwajah ganda dengan dua topeng simetris yang mengatur keseimbangan dungeon.
- **Mekanik Pertarungan Asimetris**:
  - **Mode Taking (Topeng Obsidian)**:
    - *Stat Siphon*: Menyerap 3 ATK dari pemain untuk memperkuat dirinya.
    - *Soul Drain*: Menghisap 12% HP pemain untuk memulihkan darah boss.
    - *Greed Tax*: Menyerang sambil mencuri Gold dari kantong pemain.
  - **Mode Giving (Topeng Emas)**:
    - *Dangerous Gift*: Memberikan pemain buff besar $+12\text{ ATK}$ selama 1 giliran (kesempatan emas pemain untuk menghabisi boss, namun pemain harus waspada terhadap serangan balasan).
    - *Cursed Benevolence*: Memulihkan $+25\text{ HP}$ pemain tetapi menyegel penggunaan skill pemain selama 2 giliran.
- **Hadiah Kemenangan**: **Scales of Equilibrium (Legendary Armor/Relic)**, Gold dalam jumlah masif, dan EXP besar.

#### 🗿 Dungeon Guardian Golem - *Boss Lantai 1*
- **Deskripsi**: Golem batu purba berlumut dengan inti magma menyala di bagian dada.
- **Karakteristik**: Memiliki pertahanan (DEF) dan HP yang sangat tebal.
- **Hadiah Kemenangan**: Perlengkapan bertipe Epic, EXP besar, dan akses ke lantai berikutnya.

#### 🐉 Abyssal Shadow Dragon - *Boss Lantai 3+*
- **Deskripsi**: Naga hitam bertanduk ganda yang memuntahkan semburan api ungu kegelapan.
- **Karakteristik**: Serangan (ATK) luar biasa tinggi yang menuntut pemain memiliki armor bertaraf Rare/Epic dan persediaan potion yang cukup.
- **Hadiah Kemenangan**: Senjata legendaris *Dragon Slayer* dan pundi-pundi emas harta naga.

---

### 2. Mini-Boss Tersembunyi (*Encounter Mini-Bosses*)

| Mini-Boss | Cara Memicu / Lokasi | Mekanik Pertarungan | Hadiah Spesial |
| :--- | :--- | :--- | :--- |
| **🎭 The Riddler** | Gagal menjawab teka-teki atau menantang duel di event *Riddler's Trial*. | Memiliki serangan psikis (*Mind Blast*) dan kelincahan tinggi. | **Ring of Enigma / Monocle** (Bonus Critical Hit & EXP). |
| **⏳ Chrono Warden** | Terhisap ke dalam anomali waktu saat melompati *Dimensional Rift*. | Manipulasi waktu (*Time Reversal* & serangan cepat *Haste*). | **Chrono Relic** & Tumpukan Emas Dimensi. |
| **👻 Specter of Fallen Hero** | Gagal menarik pedang kuno di event *Cursed Blade in Stone*. | Arwah ksatria yang menggunakan jurus tebasan beruntun (*Spectral Blade*). | **Cursed Longsword** (Senjata ATK sangat tinggi). |
| **🍖 Gluttony Mimic** | Memakan hidangan beracun di event *Suspicious Banquet*. | Meja makan berubah menjadi monster bertaring raksasa dengan rahang mematikan. | **Chef's Elixir (100% Full Heal Potion)** & Gold. |
| **👺 Goblin Loan Shark** | Menang beruntun di judi dadu atau menolak membayar hutang di event *Goblin Gambler*. | Goblin raksasa bersenjatakan buku jari berduri (*Spiked Knuckles*). | **Gambler's Lucky Dice** (Meningkatkan drop rate) + Semua uang taruhan. |

---

## 🕹️ Cara Bermain

1. **Memulai Permainan**: Masukkan nama pahlawan Anda di menu *New Game*.
2. **Di Sanctuary (Town Hub)**:
   - Kunjungi **Town Shop** untuk membeli perlengkapan atau menjual hasil jarahan.
   - Gunakan **Tavern** untuk memulihkan HP secara gratis.
   - Tekan **Enter Dungeon** untuk memulai penjelajahan.
3. **Di Dalam Dungeon**:
   - Pilih salah satu dari 3 lorong rute di setiap ruangan (`Left`, `Forward`, `Right`).
   - Bertarung melawan monster, tempa senjata di *Ancient Anvil*, rekrut *Shadow Wolf Companion*, atau pecahkan teka-teki *The Riddler*.
4. **Strategi Pertarungan**:
   - Manfaatkan *Fire Strike* (Lv. 3) saat siap.
   - Buka inventaris di tengah pertarungan jika membutuhkan pergantian armor atau meminum potion pemulih HP.

---

## 🛠️ Teknologi yang Digunakan

- **HTML5**: Struktur *single-page application* semantik.
- **CSS3**: Desain responsif bertema *Dark Fantasy*, tata letak CSS Grid & Flexbox, animasi getar & transisi.
- **JavaScript (ES6+)**: Engine permainan berbasis objek, status pertempuran, state management, dan algoritma probabilitas RNG.
- **Inline SVG**: Ilustrasi grafis vektor resolusi tinggi tanpa dependensi file eksternal.
- **Web Audio API**: Generator efek suara sintetis (SFX) prosedural *zero-dependency*.
- **Web Storage API**: Penyimpanan progres permainan lokal (*localStorage*).

---

## 📜 Changelog

### [v1.1.0] - Update Boss Compendium, Mini-Bosses & Full Vector Art (Terbaru)
- **Ekspansi Boss & Mini-Boss Lengkap**:
  - Penambahan Boss Khusus **Taking and Giving (The Dual Arbiter)** dengan mekanik dua fase (*Taking Mode* vs *Giving Mode*).
  - Penambahan 5 Mini-Boss terpicu event: **The Riddler**, **Chrono Warden**, **Specter of the Fallen Hero**, **Gluttony Mimic**, dan **Goblin Loan Shark**.
- **Visual Vektor SVG**:
  - Penambahan set ilustrasi vektor SVG resolusi tinggi untuk seluruh monster, mini-boss, dan boss.
- **Sistem Pendamping Tempur (*Companion*)**:
  - Fitur rekrutmen *Tamed Shadow Wolf* dengan bar HP mandiri yang membantu menyerang musuh dan menyerap damage di combat.
- **Encounter Dinamis**:
  - Penambahan Landasan Tempa (*Ancient Anvil*), Mata Air Suci (*Fountain of Purity*), Altar Darah (*Blood Shrine*), Robekan Dimensi (*Dimensional Rift*), dan Dadu Goblin.

### [v1.0.0] - Rilis Fondasi Awal (Initial Release)
- **Sistem Dasar**:
  - Pembuatan karakter hero, sistem stat dasar (Level, HP, Max HP, ATK, DEF, EXP, Gold).
  - Sistem leveling dengan penskalaan kebutuhan EXP dan pemilihan
