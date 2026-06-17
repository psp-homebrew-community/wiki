---
layout: default
title: Memory Cards & Adapters
---

<style>
.lb-overlay {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,.88);
  z-index: 9999;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  cursor: zoom-out;
}
.lb-overlay.active { display: flex; }
.lb-overlay img {
  max-width: 92vw;
  max-height: 82vh;
  object-fit: contain;
  border-radius: 3px;
  box-shadow: 0 4px 32px rgba(0,0,0,.6);
}
.lb-caption {
  color: #e8e8e8;
  margin-top: 14px;
  font-size: .9rem;
  text-align: center;
  max-width: 55ch;
  line-height: 1.5;
}
.lb-close {
  position: fixed;
  top: 16px;
  right: 22px;
  color: #fff;
  font-size: 1.8rem;
  font-weight: 300;
  cursor: pointer;
  line-height: 1;
  user-select: none;
}

.img-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
  margin: 1em 0 1.8em;
}
.img-card {
  flex: 1 1 180px;
  max-width: 260px;
  cursor: zoom-in;
  text-decoration: none;
}
.img-card figure {
  margin: 0;
  border: 1px solid #ddd;
  border-radius: 4px;
  overflow: hidden;
  background: #f8f8f8;
}
.img-card img {
  width: 100%;
  height: 170px;
  object-fit: cover;
  display: block;
  transition: opacity .15s;
}
.img-card:hover img { opacity: .82; }
.img-card figcaption {
  font-size: .78rem;
  color: #444;
  padding: 6px 8px 7px;
  line-height: 1.4;
  border-top: 1px solid #e5e5e5;
}
.section-label {
  display: inline-block;
  font-size: .7rem;
  font-weight: 700;
  letter-spacing: .06em;
  text-transform: uppercase;
  padding: 2px 7px;
  border-radius: 3px;
  margin-bottom: .6em;
}
.label-psp  { background: #d4edda; color: #1a6630; }
.label-no   { background: #f8d7da; color: #7b1c24; }
</style>

<div class="lb-overlay" id="lightbox" role="dialog" aria-modal="true">
  <span class="lb-close" id="lb-close" aria-label="Close">&#x2715;</span>
  <img id="lb-img" src="" alt="">
  <p class="lb-caption" id="lb-caption"></p>
</div>

## Memory Stick PRO Duo

<span class="section-label label-psp">PSP 1000 / 2000 / 3000</span>

The PSP uses the **Memory Stick PRO Duo** format. It is the only thing that fits the PSP's card slot. Sony made some, and third-party brands (SanDisk, Lexar) made hundreds.. Capacities went from 32 MB up to 32 GB (if you have a 32 GB memstick, gongrats - that's the fastest memroy card available - faster than sd cards). The card is roughly 31 × 20 mm with a beveled top-right corner. You'll know it immediately by the Memory Stick logo and the word "PRO Duo" printed on it, some cheap knock offs miss this, and are advised against being used.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="Sony Memory Stick PRO Duo (2GB).">
    <figure>
      <img src="{{ '/assets/images/memsticks/memorystick_pro_duo.webp' | relative_url }}" alt="sony memory stick pro duo 2gb">
      <figcaption>Sony MS PRO Duo 2GB</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="SanDisk Memory Stick PRO Duo (512MB), A small card.>
    <figure>
      <img src="{{ '/assets/images/memsticks/small_memstick.webp' | relative_url }}" alt="sandisk memory stick pro duo 512mb">
      <figcaption>SanDisk MS PRO Duo 512MB</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="A pile of various Memory Stick PRO Duo cards and third-party adapters. Image provided by TK.">
    <figure>
      <img src="{{ '/assets/images/memsticks/tk_memstick_pile.webp' | relative_url }}" alt="pile of memory stick pro duo cards and adapters">
      <figcaption>Various MS PRO Duo cards & adapters</figcaption>
    </figure>
  </a>
</div>

## microSD Adapter (PSP 1000 / 2000 / 3000)

<span class="section-label label-psp">PSP 1000 / 2000 / 3000</span>

Genuine Memory Stick PRO Duo cards are hard to find new and often expensive, especially the bigger sizes (8GB+) The modern way of doing this is a **microSD to Memory Stick PRO Duo adapter**. It's like a MSPRODUO... but has a microSD slot built in. You slot in an microSD card, then insert the whole thing into the PSP as normal. Compatibility with the PSP varies from not working to very good.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="microSD to Memory Stick PRO Duo adapter with a 4GB Lexar microSD inserted.">
    <figure>
      <img src="{{ '/assets/images/memsticks/memorystic_pro_duo_adapter.webp' | relative_url }}" alt="microsd to memory stick pro duo adapter with microsd inserted">
      <figcaption>microSD → MS PRO Duo adapter</figcaption>
    </figure>
  </a>
</div>

## PSP Go

<span class="section-label label-psp">PSP Go only</span>

The PSP Go (N1000) is different. It has **no Memory Stick PRO Duo slot**! It uses an internal Memory Stick Micro (M2) slot and has 16 GB of built-in flash. To expand storage on a PSP Go, a special flex-ribbon **microSD adapter** has been made by the community. It routes from the M2 slot inside the PSP Go to a microSD card that sticks out the side. This is a PSP Go-specific mod and does not apply to *any* other PSP model.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="A flex-ribbon adapter that connects to the PSP Go's internal M2 slot and accepts a standard microSD card. PSP Go only.">
    <figure>
      <img src="{{ '/assets/images/memsticks/psp_go_microsd_adapter.jpg' | relative_url }}" alt="psp go microsd flex ribbon adapter">
      <figcaption>PSP Go microSD adapter</figcaption>
    </figure>
  </a>
</div>

---

## Not for PSP

The following formats are **not compatible** with the PSP. They are shown here because they can look confusingly similar to Memory Stick PRO Duo... specially the Sony M2... and sometimes even the Vita's memory card!

### Sony M2 (Memory Stick Micro)

<span class="section-label label-no">Not for PSP</span>

The M2 is Sony's phone-era micro format, used in older Sony Ericsson handsets and early Walkman players. It is much smaller than a MS PRO Duo (15 × 12.5 mm vs 31 × 20 mm). Sony also made an **M2 Adaptor** (MSAC-MMS) that brings an M2 up to Memory Stick PRO Duo size — it looks like an MS PRO Duo shell with an M2 inserted. It does **not** work in a PSP; the PSP's firmware does not recognize it.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="Sony M2 (Memory Stick Micro, 8GB). Sony's phone-era micro format — much smaller than MS PRO Duo, not for PSP.">
    <figure>
      <img src="{{ '/assets/images/memsticks/m2_memcard.webp' | relative_url }}" alt="sony m2 memory stick micro 8gb">
      <figcaption>Sony M2 (Memory Stick Micro)</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="Sony M2 Adaptor (MSAC-MMS) with an M2 card inserted. It is the same size as an MS PRO Duo card, but only works in Sony phones and cameras — not the PSP.">
    <figure>
      <img src="{{ '/assets/images/memsticks/m2_and_m2adaptor.webp' | relative_url }}" alt="sony m2 with m2 adaptor msac-mms">
      <figcaption>M2 + M2 Adaptor (MSAC-MMS) — not for PSP</figcaption>
    </figure>
  </a>
</div>

### SD Cards

<span class="section-label label-no">Not for PSP</span>

Standard SD and microSD cards are not compatible with the PSP's card slot in any way.. The microSD-to-MS PRO Duo adapters described above are the only way to use microSD in a PSP. A bare microSD or a microSD in a plain SD adapter **will not work**.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="microSD card (Lexar 4GB). You cant use this alone.">
    <figure>
      <img src="{{ '/assets/images/memsticks/real_sd_card.webp' | relative_url }}" alt="lexar 4gb microsd card">
      <figcaption>microSD card, you cant use this alone</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="microSD in an SD adapter (Lexar C10/UHS-I)">
    <figure>
      <img src="{{ '/assets/images/memsticks/sd_card_adapter.webp' | relative_url }}" alt="microsd in sd card adapter">
      <figcaption>microSD + SD adapter</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="Full-size SD card (SanDisk Extreme PRO 128GB). Completely the wrong form factor..">
    <figure>
      <img src="{{ '/assets/images/memsticks/sd_card_big.webp' | relative_url }}" alt="sandisk extreme pro 128gb full-size sd card">
      <figcaption>Full-size SD card</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="A *probably* counterfeit microSD card. These report a false capacity, corrupt easily etc.">
    <figure>
      <img src="{{ '/assets/images/memsticks/fake_sd_card.png' | relative_url }}" alt="counterfeit microsd card">
      <figcaption>Fake/counterfeit microSD. Please try to avoid these.</figcaption>
    </figure>
  </a>
</div>

### PS Vita Memory Card & SD2VITA

<span class="section-label label-no">Not for PSP</span>

The PS Vita uses its own proprietary memory card format - physically similar in size to M2 but incompatible. The SD2VITA is an adapter for the PS Vita's *game card slot* that accepts microSD. Neither, obviously - support the PSP; but are shown here for brevity.

<div class="img-grid">
  <a class="img-card" href="#" data-caption="PS Vita Memory Card (64GB)">
    <figure>
      <img src="{{ '/assets/images/memsticks/ps_vita_memorycard.webp' | relative_url }}" alt="ps vita memory card 64gb">
      <figcaption>PS Vita Memory Card</figcaption>
    </figure>
  </a>
  <a class="img-card" href="#" data-caption="SD2VITA">
    <figure>
      <img src="{{ '/assets/images/memsticks/sd2vita.webp' | relative_url }}" alt="sd2vita microsd adapter for ps vita">
      <figcaption>SD2VITA</figcaption>
    </figure>
  </a>
</div>

<script>
(function () {
  var lb     = document.getElementById('lightbox');
  var lbImg  = document.getElementById('lb-img');
  var lbCap  = document.getElementById('lb-caption');
  var lbClose = document.getElementById('lb-close');

  function open(src, caption) {
    lbImg.src = src;
    lbImg.alt = caption;
    lbCap.textContent = caption;
    lb.classList.add('active');
  }

  function close() {
    lb.classList.remove('active');
    lbImg.src = '';
  }

  document.querySelectorAll('.img-card').forEach(function (card) {
    card.addEventListener('click', function (e) {
      e.preventDefault();
      var img = card.querySelector('img');
      var caption = card.dataset.caption || card.querySelector('figcaption').textContent;
      open(img.src, caption);
    });
  });

  lbClose.addEventListener('click', function (e) {
    e.stopPropagation();
    close();
  });

  lb.addEventListener('click', close);

  document.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') close();
  });
})();
</script>
