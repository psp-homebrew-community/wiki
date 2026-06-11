---
layout: default
title: PSP Error Codes
---
# PSP Error Codes

A list of common PSP error codes and how to fix them.
This list is NOT
comprehensive and needs a lot of work.
Most codes cross referenced from 
[PSP Dev Wiki](https://www.psdevwiki.com/psp/index.php?title=Error_Codes)[]()

List of all error codes from [rivetdb-psp](https://github.com/isage/rivetdb-psp)


|Error Code|Reason|Solution|
|-|-|-|
|80000001|Not initialized|Restart application or PSP|
|80000002|Unmatched version|Update firmware or application|
|80000003|Not implemented|Feature not available on this firmware, Update to 6.61 (?)|
|80000004|Operation not supported|Check firmware compatibility, update to 6.61 (?)|
|80000020|Already being processed|Wait for current operation to finish|
|80000021|System busy|Close background apps, retry|
|80000022|Out of memory|Restart PSP|
|80000023|Invalid privilege|CFW Required|
|80000024|Timeout|Check network|
|80000025|Not found|Verify file path or that your memstick didnt de-inject itself|
|80010002|File or directory not found|Check path, reinstall app if needed|
|8001000D|No file access permission|Check file permissions on Memory Stick (corrupt ms?)|
|80010010|Device busy|Wait, then retry operation|
|80010011|File exists|Rename or delete existing file|
|80010013|Device not found|Reseat Memory Stick or UMD|
|80010016|Invalid argument|Restart app, may be software bug|
|8001001C|No space on device|Delete files to free space, get a bigger memory stick|
|8001006F|Connection refused|Check target service is running|
|80010072|Network unreachable|Verify router and internet connection|
|80010074|Connection timeout|Restart router, check signal strength, move closer to router|
|80010076|No route to host|Check DNS settings or use IP directly|
|8001B002|Invalid unit number|Try a system reset?|
|80020001|Generic kernel error|Restart app, reinstall if persistent|
|800200D1|Homebrew blocked|Enable homebrew mode in firmware|
|800200D9|Memory allocation failed|Close apps, restart PSP|
|80020130|Module file read error|Check Memory Stick, reformat if needed|
|80020148|Unsupported PRX type|Use correct homebrew build or firmware|
|8002014C|Kxploit homebrew blocked|Enable homebrew execution in settings|
|80020190|No memory available|Close background applications|
|800201A8|Wait timeout|Restart app, check peripheral response|
|80020321|No such device|Check kernel config or UMD/ISO mode|
|80020324|Invalid argument|Software bug, restart application|
|80110305|Memory Stick access failed|Reseat stick, check for corruption|
|80110404|Network error|Restore default network settings|
|80110482|WLAN infrastructure test failed|Check router settings and signal|
|80210001|UMD drive not ready|Open/close UMD lid, insert disc|
|80210002|Access beyond disc capacity|Clean disc, may be damaged or buggy|
|80210003|No UMD inserted|Insert a valid UMD disc|
|80210007|Media switching prohibited|Eject current disc before inserting new|
|80210008|Invalid UMD data layout|Clean disc, may be corrupted|
|80220001|General Memory Stick error|Check stick for errors, reformat|
|80220005|Memory Stick write protected|Slide write-protect switch to unlock|
|80220006|Memory Stick not formatted|Format stick using PSP system menu|
|8041040F|DNS resolution failed|Set manual DNS to 8.8.8.8 or 1.1.1.1 (Google or CF)|
|80410410|Cannot connect to access point|Verify SSID, password, signal strength, make sure WPA2 plugin is enabled)|
|80410A0B|WiFi hardware fault|Reseat WiFi antenna cable, may need repair|
|80410D07|General WLAN connection error|Restart router and PSP, check interference|
|80410D16|Network communication failed|Check firewall, router, or server status|
|80460001|Font file missing or corrupt|Change system language to supported one|
|80510207|Game data corrupted|Reinstall game, check if copy was sucessful|
|80108D50|PSP Camera not detected|Reseat camera connector, check for damage|
|CA000005|keys.bin missing for PS1 game|Place keys.bin in correct emulator folder|
|98765432|Language font removed in custom FW|Switch to a supported system language|
|00000001|No WiFi access points detected|Move closer to router|
|FFFFFFFF|System update failed|Redownload official firmware, retry update (if ark, what?)|
|UKN9000001|Update data corrupted|Redownload update|
|DRNFFFFFFB0|IDStorage key 0x8 header invalid|Use IdStorage Manager with correct key for motherboard (leaf fixer?)|
|CTA80000025|Region key damaged or missing|Restore from your own IDStorage backup only (leaf fixer?)|

<div id="error-db-app"></div>
<style>
  #error-search { width: 100%; padding: 0.75rem; margin-bottom: 1rem; background: var(--sidebar-bg); border: 1px solid var(--border); color: var(--text); border-radius: 4px; font-size: 1rem; }
  .hidden-row { display: none; }
</style>
<script>
  document.addEventListener("DOMContentLoaded", async () => {
    const existingTable = document.querySelector("table");
    if (!existingTable) return;
    const existingSolutions = new Map();
    existingTable.querySelectorAll("tbody tr").forEach(tr => {
      const code = tr.cells[0].textContent.trim().toUpperCase();
      existingSolutions.set(code, { reason: tr.cells[1].textContent.trim(), solution: tr.cells[2].textContent.trim() });
    });
    const appDiv = document.getElementById("error-db-app");
    existingTable.style.display = "none";
    appDiv.innerHTML = `<input type="text" id="error-search" placeholder="Filter by code, name, or solution..." aria-label="Filter Error Codes"><div id="error-table-container">Loading comprehensive database...</div>`;
    try {
      const res = await fetch("{{ '/assets/data/rivetdb.json' | relative_url }}");
      const db = await res.json();
      const allErrors = [];
      for (const [facHex, facility] of Object.entries(db)) {
        const facInt = parseInt(facHex, 16);
        for (const [errHex, error] of Object.entries(facility.errors)) {
          const errInt = parseInt(errHex, 16);
          const fullCode = ((0x80000000 | (facInt << 16) | errInt) >>> 0).toString(16).toUpperCase().padStart(8, '0');
          let solution = "";
          let reason = error.description || error.name;
          if (existingSolutions.has(fullCode)) {
             solution = existingSolutions.get(fullCode).solution;
             existingSolutions.delete(fullCode);
          }
          allErrors.push({ code: fullCode, name: error.name, reason: reason, facility: facility.name, solution: solution });
        }
      }
      for (const [code, data] of existingSolutions.entries()) {
        allErrors.push({ code: code, name: "Unknown", reason: data.reason, facility: "Unknown", solution: data.solution });
      }
      allErrors.sort((a, b) => a.code.localeCompare(b.code));
      const frag = document.createDocumentFragment();
      const table = document.createElement("table");
      table.innerHTML = `<thead><tr><th>Error Code</th><th>Name / Facility</th><th>Description</th><th>Solution</th></tr></thead><tbody id="error-tbody"></tbody>`;
      const tbody = table.querySelector("tbody");
      const rows = [];
      allErrors.forEach(err => {
        const tr = document.createElement("tr");
        const idStr = err.code.toUpperCase();
        tr.id = idStr;
        const nameCell = err.name !== "Unknown" ? `<strong>${err.name}</strong><br><small style="opacity:0.7">${err.facility}</small>` : `<em>Unknown</em>`;
        tr.innerHTML = `<td><a href="#${idStr}" style="color:inherit; text-decoration:none"><code>${err.code}</code></a></td><td>${nameCell}</td><td>${err.reason}</td><td>${err.solution || "<em>None</em>"}</td>`;
        tbody.appendChild(tr);
        rows.push({ el: tr, text: `${err.code} ${err.name} ${err.reason} ${err.solution} ${err.facility}`.toLowerCase() });
      });
      frag.appendChild(table);
      const container = document.getElementById("error-table-container");
      container.innerHTML = "";
      container.appendChild(frag);
      const searchInput = document.getElementById("error-search");
      searchInput.addEventListener("input", (e) => {
        const query = e.target.value.toLowerCase().trim();
        rows.forEach(r => { r.el.style.display = r.text.includes(query) ? "" : "none"; });
      });
      const checkHash = () => {
        if (window.location.hash) {
          const target = window.location.hash.substring(1).toUpperCase();
          const row = document.getElementById(target);
          if (row) {
            searchInput.value = target;
            searchInput.dispatchEvent(new Event("input"));
            row.scrollIntoView({ behavior: "smooth", block: "center" });
          }
        }
      };
      checkHash();
      window.addEventListener("hashchange", checkHash);
    } catch (e) {
      document.getElementById("error-table-container").innerHTML = `<p style="color:red">Failed to load expanded database. Showing basic list instead.</p>`;
      existingTable.style.display = "";
    }
  });
</script>
