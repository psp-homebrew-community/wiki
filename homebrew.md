---
title: Homebrew
layout: home
nav_order: 10
---

# Homebrew
{: .fs-8 .fw-700 .text-center }

This page contains a list of homebrew made for the PSP that can be searched through and downloaded. Shoutouts to wouter & co for compiling this list!

<input id="search" type="text" placeholder="Search homebrew..." aria-label="Search homebrew">

<div id="pagination" class="pagination-container"></div>
<table id="homebrew_table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Author</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>
<div id="pagination-bottom" class="pagination-container"></div>

<style>
  #search { width: 100%; padding: 0.75rem; margin: 1rem 0; background: var(--sidebar-bg); border: 1px solid var(--border); color: var(--text); border-radius: 4px; font-size: 1rem; }
  .pagination-container { display: flex; gap: 0.5rem; justify-content: center; margin: 1rem 0; flex-wrap: wrap; }
  .pagination-container button { padding: 0.5rem 1rem; background: var(--sidebar-bg); border: 1px solid var(--border); color: var(--text); border-radius: 4px; cursor: pointer; }
  .pagination-container button:disabled { opacity: 0.5; cursor: not-allowed; }
  .pagination-container button.active { font-weight: bold; background: var(--border); }
</style>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    const data = [
      {% for item in site.data.homebrew.response.docs %}
        {
          name: {{ item.title | jsonify }},
          description: {{ item.description | jsonify }},
          author: {{ item.creator | jsonify }},
          date: {{ item.date | jsonify }},
          identifier: {{ item.identifier | jsonify }}
        }{% unless forloop.last %},{% endunless %}
      {% endfor %}
    ];

    const rowsPerPage = 20;
    let currentPage = 1;
    let currentData = data;
    const tbody = document.querySelector("#homebrew_table tbody");
    const paginationTop = document.getElementById("pagination");
    const paginationBottom = document.getElementById("pagination-bottom");

    const renderTable = (page) => {
      const start = (page - 1) * rowsPerPage;
      const end = start + rowsPerPage;
      const slice = currentData.slice(start, end);
      
      const frag = document.createDocumentFragment();
      slice.forEach(item => {
        const tr = document.createElement("tr");
        
        const tdName = document.createElement("td");
        const a = document.createElement("a");
        a.href = `https://archive.org/details/${item.identifier || ''}`;
        a.textContent = item.name || 'Unknown';
        tdName.appendChild(a);
        
        const tdDesc = document.createElement("td");
        tdDesc.textContent = item.description || '';
        
        const tdAuthor = document.createElement("td");
        tdAuthor.textContent = item.author || '';
        
        tr.appendChild(tdName);
        tr.appendChild(tdDesc);
        tr.appendChild(tdAuthor);
        frag.appendChild(tr);
      });
      
      tbody.innerHTML = "";
      tbody.appendChild(frag);
      currentPage = page;
      renderPagination();
    };

    const renderPagination = () => {
      const pageCount = Math.ceil(currentData.length / rowsPerPage);
      const createNav = () => {
        const frag = document.createDocumentFragment();
        
        const btnFirst = document.createElement("button");
        btnFirst.textContent = "<< First";
        btnFirst.disabled = currentPage === 1;
        btnFirst.onclick = () => renderTable(1);
        frag.appendChild(btnFirst);

        const btnPrev = document.createElement("button");
        btnPrev.textContent = "< Prev";
        btnPrev.disabled = currentPage === 1;
        btnPrev.onclick = () => renderTable(currentPage - 1);
        frag.appendChild(btnPrev);

        const currentLabel = document.createElement("button");
        currentLabel.textContent = `Page ${currentPage} of ${pageCount || 1}`;
        currentLabel.disabled = true;
        currentLabel.className = "active";
        frag.appendChild(currentLabel);

        const btnNext = document.createElement("button");
        btnNext.textContent = "Next >";
        btnNext.disabled = currentPage === pageCount || pageCount === 0;
        btnNext.onclick = () => renderTable(currentPage + 1);
        frag.appendChild(btnNext);

        const btnLast = document.createElement("button");
        btnLast.textContent = "Last >>";
        btnLast.disabled = currentPage === pageCount || pageCount === 0;
        btnLast.onclick = () => renderTable(pageCount);
        frag.appendChild(btnLast);
        
        return frag;
      };

      paginationTop.innerHTML = "";
      paginationTop.appendChild(createNav());
      paginationBottom.innerHTML = "";
      paginationBottom.appendChild(createNav());
    };

    document.getElementById("search").addEventListener("input", (e) => {
      const text = e.target.value.toLowerCase().trim();
      currentData = text ? data.filter(item => 
        (item.name && item.name.toLowerCase().includes(text)) || 
        (item.description && item.description.toLowerCase().includes(text)) ||
        (item.author && item.author.toLowerCase().includes(text))
      ) : data;
      renderTable(1);
    });

    renderTable(1);
  });
</script>
