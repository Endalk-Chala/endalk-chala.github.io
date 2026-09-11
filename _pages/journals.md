---
layout: archive
title: "Journal Navigator"
permalink: /journals/
author_profile: true
---

<div style="text-align:center; margin-bottom:1.5em; padding:1em 0;">
  <h2 style="font-size:1.8em; margin-bottom:0.2em; color:#2B4C7E;">Journal Navigator</h2>
  <p style="font-size:1.1em; color:#666; margin:0;">A curated guide to journals in communication, media, journalism, and adjacent fields</p>
</div>

<div style="background:#f0f4f8; border-left:4px solid #2B4C7E; border-radius:6px; padding:16px 20px; margin-bottom:1.2em; font-size:0.95em; line-height:1.7; color:#333;">
  I began building this guide in graduate school as a practical way to navigate scholarly publishing. It has since grown into a curated directory for graduate students, early-career researchers, and colleagues looking for journals across communication and related fields. Rather than ranking journals, the navigator is designed to help researchers identify plausible venues by <strong>research area, scope, and fit</strong>.
</div>

<div style="background:#fff8e6; border-left:4px solid #f0ad4e; border-radius:6px; padding:12px 16px; margin-bottom:1.5em; font-size:0.9em; line-height:1.6; color:#555;">
  <strong>Last reviewed: September 2026.</strong> Journal policies, editorial scope, open-access options, indexing, fees, and submission requirements can change. Always verify current information on the journal's official website before submitting.
</div>

<p style="font-size:0.95em; line-height:1.6; margin-bottom:1.2em; color:#555;">
  Search by journal, publisher, topic, or keyword, or filter by broad research area. The directory intentionally avoids hard-coded impact factors and other fast-changing metrics so it can remain useful over time.
</p>

<div id="journal-app">
  <div style="background:#f8f9fa; border:1px solid #e0e0e0; border-radius:8px; padding:18px 20px; margin-bottom:22px;">
    <input type="text" id="search-input" placeholder="Search journals by name, publisher, topic, or scope..."
      style="width:100%; padding:10px 14px; font-size:15px; border:1px solid #ccc; border-radius:6px; margin-bottom:14px; box-sizing:border-box;" />
    <div style="display:flex; flex-wrap:wrap; gap:12px; align-items:flex-end;">
      <div style="flex:1; min-width:240px;">
        <label style="font-size:13px; font-weight:600; display:block; margin-bottom:4px;">Research area</label>
        <select id="filter-area" style="width:100%; padding:8px 10px; font-size:14px; border:1px solid #ccc; border-radius:6px;">
          <option value="">All research areas</option>
          <option value="Core Communication">Core Communication</option>
          <option value="Journalism and Public Knowledge">Journalism and Public Knowledge</option>
          <option value="Platforms, AI, and Governance">Platforms, AI, and Governance</option>
          <option value="Political Communication">Political Communication</option>
          <option value="Migration and Intercultural Communication">Migration and Intercultural Communication</option>
          <option value="Nonprofit and Institutional Communication">Nonprofit and Institutional Communication</option>
          <option value="African and Global Media">African and Global Media</option>
          <option value="Critical and Cultural Studies">Critical and Cultural Studies</option>
          <option value="Methods">Methods</option>
        </select>
      </div>
      <div>
        <button onclick="resetFilters()" style="padding:8px 16px; font-size:14px; background:#6c757d; color:#fff; border:none; border-radius:6px; cursor:pointer;">Reset</button>
      </div>
    </div>
  </div>

  <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:14px; flex-wrap:wrap; gap:8px;">
    <span id="result-count" style="font-size:14px; color:#555;"></span>
    <div style="display:flex; align-items:center; gap:8px;">
      <label style="font-size:13px; font-weight:600;">Sort by:</label>
      <select id="sort-select" style="padding:6px 10px; font-size:14px; border:1px solid #ccc; border-radius:6px;">
        <option value="name">Name (A–Z)</option>
        <option value="area">Research area</option>
        <option value="publisher">Publisher</option>
      </select>
    </div>
  </div>

  <div id="journal-list"></div>
</div>

<script>
var journals = [
  {name:"Journal of Communication", publisher:"Oxford University Press", area:"Core Communication", url:"https://academic.oup.com/joc", scope:"Broad, theory-driven research across the communication discipline."},
  {name:"Communication Research", publisher:"SAGE", area:"Core Communication", url:"https://journals.sagepub.com/home/crx", scope:"Empirical research on communication processes across interpersonal, media, political, and organizational contexts."},
  {name:"Human Communication Research", publisher:"Oxford University Press", area:"Core Communication", url:"https://academic.oup.com/hcr", scope:"Theory-driven empirical research across major areas of human communication."},
  {name:"Communication Theory", publisher:"Oxford University Press", area:"Core Communication", url:"https://academic.oup.com/ct", scope:"Conceptual, theoretical, and metatheoretical scholarship in communication."},
  {name:"International Journal of Communication", publisher:"USC Annenberg", area:"Core Communication", url:"https://ijoc.org", scope:"Open-access scholarship across international, digital, political, and media communication."},
  {name:"Communication Methods and Measures", publisher:"Taylor & Francis", area:"Methods", url:"https://www.tandfonline.com/journals/hcms20", scope:"Methods, measurement, research design, and analytical tools for communication research."},
  {name:"Journal of Quantitative Description: Digital Media", publisher:"Journal of Quantitative Description", area:"Methods", url:"https://journalqd.org", scope:"Descriptive quantitative research on digital media platforms, audiences, and content."},

  {name:"Journalism & Mass Communication Quarterly", publisher:"SAGE", area:"Journalism and Public Knowledge", url:"https://journals.sagepub.com/home/jmq", scope:"Research on journalism, media, mass communication, and related institutions."},
  {name:"Journalism Studies", publisher:"Taylor & Francis", area:"Journalism and Public Knowledge", url:"https://www.tandfonline.com/journals/rjos20", scope:"International scholarship on journalism as a social, cultural, and institutional practice."},
  {name:"Journalism Practice", publisher:"Taylor & Francis", area:"Journalism and Public Knowledge", url:"https://www.tandfonline.com/journals/rjop20", scope:"Research connecting journalism studies with professional practice and news production."},
  {name:"Digital Journalism", publisher:"Taylor & Francis", area:"Journalism and Public Knowledge", url:"https://www.tandfonline.com/journals/rdij20", scope:"Digital transformation of journalism, platforms, computational journalism, and news production."},
  {name:"Journalism", publisher:"SAGE", area:"Journalism and Public Knowledge", url:"https://journals.sagepub.com/home/jou", scope:"International research on journalism theory, practice, institutions, and cultures."},
  {name:"American Journalism", publisher:"Taylor & Francis", area:"Journalism and Public Knowledge", url:"https://www.tandfonline.com/journals/uamj20", scope:"Media and journalism history in national and transnational contexts, including broadcasting, advertising, and public relations."},
  {name:"The International Journal of Press/Politics", publisher:"SAGE", area:"Journalism and Public Knowledge", url:"https://journals.sagepub.com/home/hij", scope:"Research on news media, political institutions, journalism, and democratic politics."},

  {name:"New Media & Society", publisher:"SAGE", area:"Platforms, AI, and Governance", url:"https://journals.sagepub.com/home/nms", scope:"Social, political, cultural, and institutional implications of digital media and communication technologies."},
  {name:"Information, Communication & Society", publisher:"Taylor & Francis", area:"Platforms, AI, and Governance", url:"https://www.tandfonline.com/journals/rics20", scope:"Social, political, economic, and cultural dimensions of information and communication technologies."},
  {name:"Social Media + Society", publisher:"SAGE", area:"Platforms, AI, and Governance", url:"https://journals.sagepub.com/home/sms", scope:"Social media, platforms, digital culture, politics, and society."},
  {name:"Journal of Computer-Mediated Communication", publisher:"Oxford University Press", area:"Platforms, AI, and Governance", url:"https://academic.oup.com/jcmc", scope:"Social and behavioral dimensions of computer-mediated and digitally networked communication."},
  {name:"Big Data & Society", publisher:"SAGE", area:"Platforms, AI, and Governance", url:"https://journals.sagepub.com/home/bds", scope:"Datafication, algorithms, AI, digital infrastructures, and their social implications."},
  {name:"Internet Policy Review", publisher:"Alexander von Humboldt Institute for Internet and Society", area:"Platforms, AI, and Governance", url:"https://policyreview.info", scope:"Internet regulation, platform governance, digital rights, policy, and technology governance."},
  {name:"Journal of Online Trust and Safety", publisher:"Stanford Internet Observatory", area:"Platforms, AI, and Governance", url:"https://tsjournal.org", scope:"Online trust and safety, platform governance, content moderation, integrity, and related policy and research."},
  {name:"Media and Communication", publisher:"Cogitatio Press", area:"Platforms, AI, and Governance", url:"https://www.cogitatiopress.com/mediaandcommunication/", scope:"Open-access research across media and communication, including digital media, platforms, journalism, and political communication."},
  {name:"Mobile Media & Communication", publisher:"SAGE", area:"Platforms, AI, and Governance", url:"https://journals.sagepub.com/home/mmc", scope:"Mobile media technologies and their social, cultural, and political implications."},

  {name:"Political Communication", publisher:"Taylor & Francis", area:"Political Communication", url:"https://www.tandfonline.com/journals/upcp20", scope:"Research at the intersection of communication, politics, public opinion, campaigns, and media."},
  {name:"Journal of Information Technology & Politics", publisher:"Taylor & Francis", area:"Political Communication", url:"https://www.tandfonline.com/journals/witp20", scope:"Digital technologies, governance, civic engagement, and political communication."},
  {name:"Political Communication and Society", publisher:"Various", area:"Political Communication", url:"https://www.tandfonline.com", scope:"Use the broader publisher search to locate specialized political communication venues and special issues."},

  {name:"Language and Intercultural Communication", publisher:"Taylor & Francis", area:"Migration and Intercultural Communication", url:"https://www.tandfonline.com/journals/rmli20", scope:"Interdisciplinary research on language, culture, identity, and intercultural communication."},
  {name:"Journal of International and Intercultural Communication", publisher:"Taylor & Francis", area:"Migration and Intercultural Communication", url:"https://www.tandfonline.com/journals/rjii20", scope:"Communication across cultural, national, racial, ethnic, and linguistic boundaries."},
  {name:"Journal of Intercultural Communication Research", publisher:"Taylor & Francis", area:"Migration and Intercultural Communication", url:"https://www.tandfonline.com/journals/rjic20", scope:"Empirical and theoretical research on intercultural communication processes."},
  {name:"Journal of Language and Social Psychology", publisher:"SAGE", area:"Migration and Intercultural Communication", url:"https://journals.sagepub.com/home/jls", scope:"Language, identity, communication, and social psychological processes."},

  {name:"Journal of Public Relations Research", publisher:"Taylor & Francis", area:"Nonprofit and Institutional Communication", url:"https://www.tandfonline.com/journals/hprr20", scope:"Theory, practice, philosophy, ethics, publics, and organizational communication in public relations."},
  {name:"Public Relations Review", publisher:"Elsevier", area:"Nonprofit and Institutional Communication", url:"https://www.sciencedirect.com/journal/public-relations-review", scope:"Public relations, strategic communication, stakeholder relations, and organizational communication."},
  {name:"International Journal of Strategic Communication", publisher:"Taylor & Francis", area:"Nonprofit and Institutional Communication", url:"https://www.tandfonline.com/journals/hstc20", scope:"Purposeful organizational communication, strategic communication, public relations, and related institutional processes."},
  {name:"Management Communication Quarterly", publisher:"SAGE", area:"Nonprofit and Institutional Communication", url:"https://journals.sagepub.com/home/mcq", scope:"Communication processes in organizations, management, institutions, and workplaces."},
  {name:"Journal of Applied Communication Research", publisher:"Taylor & Francis", area:"Nonprofit and Institutional Communication", url:"https://www.tandfonline.com/journals/rjac20", scope:"Applied communication research addressing real-world institutional, organizational, health, and community problems."},

  {name:"Journal of African Media Studies", publisher:"Intellect", area:"African and Global Media", url:"https://intellectdiscover.com/content/journals/jams", scope:"Media, journalism, digital culture, and communication across Africa."},
  {name:"African Journalism Studies", publisher:"Taylor & Francis", area:"African and Global Media", url:"https://www.tandfonline.com/journals/recj20", scope:"Journalism practices, media institutions, press freedom, and news cultures across Africa."},
  {name:"Communicatio", publisher:"Taylor & Francis", area:"African and Global Media", url:"https://www.tandfonline.com/journals/rcsa20", scope:"Communication theory and research with strong attention to Africa and the Global South."},
  {name:"Global Media and Communication", publisher:"SAGE", area:"African and Global Media", url:"https://journals.sagepub.com/home/gmc", scope:"Global media systems, international communication, power, globalization, and transnational communication."},

  {name:"Communication, Culture & Critique", publisher:"Oxford University Press", area:"Critical and Cultural Studies", url:"https://academic.oup.com/ccc", scope:"Critical and cultural approaches to communication, media, identity, power, and social justice."},
  {name:"Critical Studies in Media Communication", publisher:"Taylor & Francis", area:"Critical and Cultural Studies", url:"https://www.tandfonline.com/journals/rcsm20", scope:"Critical scholarship on media texts, industries, practices, power, and culture."},
  {name:"Feminist Media Studies", publisher:"Taylor & Francis", area:"Critical and Cultural Studies", url:"https://www.tandfonline.com/journals/rfms20", scope:"Feminist research on media, representation, production, audiences, technology, and culture."},
  {name:"Communication and Critical/Cultural Studies", publisher:"Taylor & Francis", area:"Critical and Cultural Studies", url:"https://www.tandfonline.com/journals/rccc20", scope:"Critical and cultural communication scholarship, including rhetoric, identity, politics, and social difference."}
];

function getEl(id) { return document.getElementById(id); }

function renderJournals() {
  var search = getEl('search-input').value.toLowerCase();
  var area = getEl('filter-area').value;
  var sort = getEl('sort-select').value;

  var filtered = journals.filter(function(j) {
    var haystack = (j.name + ' ' + j.publisher + ' ' + j.area + ' ' + j.scope).toLowerCase();
    if (search && haystack.indexOf(search) < 0) return false;
    if (area && j.area !== area) return false;
    return true;
  });

  filtered.sort(function(a, b) {
    if (sort === 'name') return a.name.localeCompare(b.name);
    if (sort === 'area') return a.area.localeCompare(b.area) || a.name.localeCompare(b.name);
    if (sort === 'publisher') return a.publisher.localeCompare(b.publisher) || a.name.localeCompare(b.name);
    return 0;
  });

  getEl('result-count').textContent = 'Showing ' + filtered.length + ' of ' + journals.length + ' journals';

  var html = '';
  for (var i = 0; i < filtered.length; i++) {
    var j = filtered[i];
    html += '<div style="border:1px solid #e0e0e0;border-radius:8px;padding:16px 20px;margin-bottom:12px;background:#fff;">';
    html += '<h3 style="margin:0 0 5px 0;font-size:17px;"><a href="' + j.url + '" target="_blank" rel="noopener" style="color:#2B4C7E;text-decoration:none;">' + j.name + '</a></h3>';
    html += '<div style="font-size:13px;color:#666;margin-bottom:7px;">' + j.publisher + ' &middot; ' + j.area + '</div>';
    html += '<p style="font-size:14px;line-height:1.5;color:#333;margin:8px 0;">' + j.scope + '</p>';
    html += '<a href="' + j.url + '" target="_blank" rel="noopener" style="font-size:13px;color:#2B4C7E;">Visit journal &rarr;</a>';
    html += '</div>';
  }

  if (filtered.length === 0) {
    html = '<div style="text-align:center;padding:40px;color:#888;font-size:16px;">No journals match your search. Try a different keyword or research area.</div>';
  }
  getEl('journal-list').innerHTML = html;
}

function resetFilters() {
  getEl('search-input').value = '';
  getEl('filter-area').value = '';
  getEl('sort-select').value = 'name';
  renderJournals();
}

getEl('search-input').addEventListener('input', renderJournals);
getEl('filter-area').addEventListener('change', renderJournals);
getEl('sort-select').addEventListener('change', renderJournals);
renderJournals();
</script>
