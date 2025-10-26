<!DOCTYPE html>
<html lang="pt-BR" class="h-full">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Samir Ricardo - Engenheiro de Software</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet"/>

  <!-- SEO -->
  <meta name="description" content="Portfólio de Samir — Engenheiro de Software, SaaS, Cloud e DevOps. Estudos de caso: AgilizaVRA, VRASHOWS (site) e VRAMUSIC. Stack: Python/Flask, FastAPI, Docker, NGINX, CI/CD.">

  <style>
    body { box-sizing: border-box; }
    .gradient-gold{
      background: linear-gradient(135deg,#FFD700,#FFA500,#FF8C00);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
    }
    .hover-gold{ transition: all .3s ease; }
    .hover-gold:hover{ transform: translateY(-2px); box-shadow: 0 10px 25px rgba(255,215,0,.2); }

    /* cards */
    .skill-tag{
      background: linear-gradient(135deg, rgba(255,215,0,.08), rgba(0,0,0,.85));
      border: 1px solid rgba(255,215,0,.25);
      backdrop-filter: blur(10px);
    }
    .project-card{
      background: linear-gradient(135deg, rgba(255,215,0,.05), rgba(0,0,0,.8));
      border:1px solid rgba(255,215,0,.2); backdrop-filter: blur(10px);
    }
    .section-divider{ background: linear-gradient(90deg,transparent,#FFD700,transparent); height:1px; }

    /* animação */
    @keyframes fadeInUp{ from{opacity:0; transform:translateY(30px)} to{opacity:1; transform:translateY(0)} }
    .animate-fade-in{ animation: fadeInUp .6s ease-out forwards; }
    .animate-delay-1{ animation-delay:.1s } .animate-delay-2{ animation-delay:.2s } .animate-delay-3{ animation-delay:.3s }

    /* botões sempre visíveis + hover com borda gradiente discreta */
    .btn-solid{
      background: linear-gradient(90deg,#FFD43B,#FFB000);
      color:#0b0b0b; font-weight:600; border-radius:9999px; padding:.75rem 2rem; display:inline-flex; align-items:center; justify-content:center;
      transition: box-shadow .25s ease, transform .2s ease;
    }
    .btn-solid:hover{ transform: translateY(-1px); box-shadow: 0 8px 24px rgba(255, 204, 0, .35); }

    .btn-outline{
      position:relative; color:#FDE68A; font-weight:600; border-radius:9999px; padding:.75rem 2rem; display:inline-flex; align-items:center; justify-content:center;
      border:1px solid rgba(255,215,0,.55); background: transparent;
      transition: color .25s ease, transform .2s ease;
    }
    .btn-outline:hover{ color:#000; }
    .btn-outline::before{
      content:""; position:absolute; inset:0; border-radius:inherit;
      padding:1px; background: linear-gradient(135deg, rgba(255,215,0,.7), rgba(255,160,0,.7));
      -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
      -webkit-mask-composite: xor; mask-composite: exclude; opacity:0; transition:opacity .25s ease;
    }
    .btn-outline:hover::before{ opacity:1; }
    .btn-outline:hover{ background: linear-gradient(135deg, rgba(255,215,0,.85), rgba(255,160,0,.85)); }

    /* impressão para PDF */
    @media print{
      .btn-solid,.btn-outline,.cta,button { display:none !important; }
      body { color:#000; background:#fff; font-size:12pt; }
      a { color:#000; text-decoration:none; }
      .project-card, article { break-inside: avoid; }
    }
  </style>
</head>

<body class="bg-black text-white min-h-full font-sans">
  <!-- HERO -->
  <header class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-black via-gray-900 to-black overflow-hidden">
    <div class="absolute inset-0 bg-gradient-to-r from-yellow-400/5 to-orange-400/5"></div>

    <main class="container mx-auto px-6 text-center relative z-10">
      <div class="animate-fade-in">
        <img
          src="https://yata-apix-99c4b563-38d6-4212-b8e1-cd6a0d32e5c1.s3-object.locaweb.com.br/c9db926d9654427c8d8d77495faf7595.jpg"
          alt="Foto de perfil de Samir Ricardo de Oliveira Almeida"
          class="mx-auto mb-6 w-36 h-36 md:w-40 md:h-40 rounded-full object-cover ring-2 ring-yellow-400/70 shadow-lg shadow-yellow-400/20"
          loading="eager"
        />

        <h1 class="text-3xl md:text-5xl font-bold mb-3">
          <span class="text-white">SAMIR RICARDO</span><br/>
          <span class="text-white">DE OLIVEIRA ALMEIDA</span>
        </h1>

        <h2 class="text-xl md:text-2xl text-gray-300 mb-8 animate-fade-in animate-delay-1">
          Engenheiro de Software | Arquiteto de Soluções Cloud | Tech Lead
        </h2>

        <div class="flex flex-wrap justify-center gap-6 mb-10 animate-fade-in animate-delay-2">
          <div class="flex items-center gap-2 text-yellow-400"><i class="fas fa-map-marker-alt"></i><span>São Paulo/SP</span></div>
          <a class="flex items-center gap-2 text-yellow-400 hover:text-yellow-300" href="mailto:eliteasamir@gmail.com" aria-label="Enviar e-mail"><i class="fas fa-envelope"></i><span>eliteasamir@gmail.com</span></a>
          <a class="flex items-center gap-2 text-yellow-400 hover:text-yellow-300" href="tel:+5511953577804" aria-label="Ligar"><i class="fas fa-phone"></i><span>(11) 95357-7804</span></a>
          <a class="flex items-center gap-2 text-yellow-400 hover:text-yellow-300" href="https://www.vrashows.com.br" target="_blank" rel="noopener" aria-label="Site"><i class="fas fa-globe"></i><span>www.vrashows.com.br</span></a>
        </div>

        <div class="flex justify-center gap-4 animate-fade-in animate-delay-3 cta">
          <button onclick="scrollToSection('about')" class="btn-solid">Conhecer Perfil</button>
          <button onclick="scrollToSection('portfolio')" class="btn-outline">Ver Portfólio</button>
        </div>
      </div>
    </main>

    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-bounce">
      <i class="fas fa-chevron-down text-yellow-400 text-2xl"></i>
    </div>
  </header>

  <!-- ABOUT -->
  <section id="about" class="py-20 bg-gradient-to-b from-black to-gray-900">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-4"><span class="gradient-gold">Resumo Profissional</span></h2>
      <div class="section-divider mb-12"></div>

      <div class="max-w-4xl mx-auto text-lg text-gray-300 leading-relaxed">
        <p class="mb-6">
          Engenheiro de Software com experiência em desenvolvimento full stack, arquitetura de soluções em nuvem e automação de processos corporativos. Atuação em ambientes de alta performance, aplicando práticas de DevOps, POO, SOLID e Clean Code.
        </p>
        <p>
          Experiência em produtos SaaS e infraestrutura cloud (Azure, Oracle Cloud, AWS), com domínio em Python, Flask, FastAPI e JavaScript/TypeScript. Foco em desenvolvimento escalável, automação e entrega contínua de valor.
        </p>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="py-20 bg-gray-900">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-4"><span class="gradient-gold">Competências Técnicas</span></h2>
      <div class="section-divider mb-12"></div>

      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div class="skill-tag rounded-lg p-6 hover-gold text-white">
          <h3 class="text-yellow-400 font-semibold mb-4 flex items-center gap-2"><i class="fas fa-code"></i>Linguagens & Frameworks</h3>
          <div class="space-y-2 text-sm text-white">
            <div>Python (Flask, FastAPI)</div><div>JavaScript, TypeScript</div><div>HTML5, CSS3</div><div>React (básico)</div>
          </div>
        </div>
        <div class="skill-tag rounded-lg p-6 hover-gold text-white">
          <h3 class="text-yellow-400 font-semibold mb-4 flex items-center gap-2"><i class="fas fa-cloud"></i>Cloud & DevOps</h3>
          <div class="space-y-2 text-sm text-white">
            <div>Azure, Oracle Cloud, AWS</div><div>Docker, Docker Compose</div><div>NGINX, Gunicorn</div><div>CI/CD (GitHub Actions)</div>
          </div>
        </div>
        <div class="skill-tag rounded-lg p-6 hover-gold text-white">
          <h3 class="text-yellow-400 font-semibold mb-4 flex items-center gap-2"><i class="fas fa-database"></i>Banco de Dados</h3>
          <div class="space-y-2 text-sm text-white">
            <div>PostgreSQL, SQLite</div><div>MongoDB</div><div>APIs REST</div><div>Power Apps, Power Automate</div>
          </div>
        </div>
        <div class="skill-tag rounded-lg p-6 hover-gold text-white">
          <h3 class="text-yellow-400 font-semibold mb-4 flex items-center gap-2"><i class="fas fa-cogs"></i>Boas Práticas</h3>
          <div class="space-y-2 text-sm text-white">
            <div>SOLID, Clean Code</div><div>GitFlow</div><div>Testes (Pytest, Jest)</div><div>Scrum e Kanban</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- EXPERIÊNCIA -->
  <section class="py-20 bg-black">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-4"><span class="gradient-gold">Experiência Profissional</span></h2>
      <div class="section-divider mb-12"></div>

      <div class="max-w-4xl mx-auto space-y-8">
        <div class="border-l-4 border-yellow-400 pl-6 hover-gold">
          <h3 class="text-2xl font-bold text-yellow-400">VRASHOWS</h3>
          <h4 class="text-lg text-gray-300 mb-2">Tech Lead | Engenheiro de Software e Arquiteto de Soluções Cloud</h4>
          <p class="text-yellow-500 mb-4">2024 – Atual | São Paulo, SP</p>
          <ul class="text-gray-300 space-y-2">
            <li>• Desenvolvimento full stack completo de plataformas web e SaaS</li>
            <li>• AgilizaVRA: sistema SaaS com agenda, CRM e financeiro (demo ao vivo)</li>
            <li>• VRASHOWS (site): domínio, DNS, hospedagem, SSL/TLS, e-mail, desenvolvimento e integrações</li>
            <li>• VRAMUSIC: integração à Spotify API (Flask, Docker, Oracle Cloud)</li>
          </ul>
        </div>

        <div class="border-l-4 border-yellow-400 pl-6 hover-gold">
          <h3 class="text-2xl font-bold text-yellow-400">NSTECH</h3>
          <h4 class="text-lg text-gray-300 mb-2">Analista de Infraestrutura Cloud (Microsoft Azure)</h4>
          <p class="text-yellow-500 mb-4">2022 – 2024 | São Paulo, SP</p>
          <ul class="text-gray-300 space-y-2">
            <li>• Gestão e automação de ambientes Azure, Power Platform</li>
            <li>• Integração com sistemas TOTVS/Protheus</li>
            <li>• Administração de Active Directory, Exchange e M365</li>
          </ul>
        </div>

        <div class="border-l-4 border-yellow-400 pl-6 hover-gold">
          <h3 class="text-2xl font-bold text-yellow-400">ELITE A TECNOLOGIA</h3>
          <h4 class="text-lg text-gray-300 mb-2">Consultor de Soluções Empresariais</h4>
          <p class="text-yellow-500 mb-4">2011 – 2022 | São Paulo, SP</p>
          <ul class="text-gray-300 space-y-2">
            <li>• Consultoria para empresas como C&A, Fiat, Toyota e Sebrae</li>
            <li>• Planejamento e implantação de infraestrutura de TI</li>
            <li>• Liderança técnica em projetos de transformação digital</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJETOS (grid) — Agiliza primeiro + VRASHOWS (site) -->
  <section id="projects" class="py-20 bg-gradient-to-b from-gray-900 to-black">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-4"><span class="gradient-gold">Projetos de Destaque</span></h2>
      <div class="section-divider mb-12"></div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- AgilizaVRA PRINCIPAL -->
        <div class="project-card rounded-lg p-6 hover-gold">
          <div class="text-yellow-400 text-3xl mb-4"><i class="fas fa-calendar-alt"></i></div>
          <h3 class="text-xl font-bold text-yellow-400 mb-2">AgilizaVRA</h3>
          <p class="text-gray-300 mb-4">Sistema SaaS com CRM, financeiro e agenda de eventos. <span class="text-yellow-300">Demo ao vivo disponível.</span></p>
          <div class="flex flex-wrap gap-2 mb-4">
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">SaaS</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Flask</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Tailwind</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">SQLite→PostgreSQL</span>
          </div>
          <div class="space-y-2">
            <a class="btn-solid w-full" href="https://agilizadj.vrashows.com.br/" target="_blank" rel="noopener" aria-label="Abrir demo AgilizaVRA">Ver Demo</a>
            <p class="text-xs text-gray-400 text-center">Login: <span class="text-yellow-300">admin</span> · Senha: <span class="text-yellow-300">021150</span></p>
          </div>
        </div>

        <!-- VRASHOWS (SITE INSTITUCIONAL) -->
        <div class="project-card rounded-lg p-6 hover-gold">
          <div class="text-yellow-400 text-3xl mb-4"><i class="fas fa-globe"></i></div>
          <h3 class="text-xl font-bold text-yellow-400 mb-2">VRASHOWS (Site Institucional)</h3>
          <p class="text-gray-300 mb-4">Projeto end-to-end: domínio, DNS, hospedagem, SSL/TLS, e-mail, design, front-end, integrações e monitoramento.</p>
          <div class="flex flex-wrap gap-2">
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Tailwind</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">NGINX</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Linux</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">DNS/SSL</span>
          </div>
        </div>

        <!-- VRAMUSIC SECUNDÁRIO -->
        <div class="project-card rounded-lg p-6 hover-gold">
          <div class="text-yellow-400 text-3xl mb-4"><i class="fas fa-music"></i></div>
          <h3 class="text-xl font-bold text-yellow-400 mb-2">VRAMUSIC</h3>
          <p class="text-gray-300 mb-4">Plataforma para DJs com integração Spotify API e deploy em Oracle Cloud.</p>
          <div class="flex flex-wrap gap-2">
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Flask</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Docker</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">NGINX</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Oracle Cloud</span>
            <span class="bg-yellow-400/20 text-yellow-400 px-2 py-1 rounded text-xs">Spotify API</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PORTFÓLIO / ESTUDOS DE CASO — Agiliza primeiro + VRASHOWS -->
  <section id="portfolio" class="py-20 bg-black">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-3"><span class="gradient-gold">Estudos de Caso</span></h2>
      <div class="section-divider mb-10"></div>

      <!-- CASE: AGILIZA (PRINCIPAL) -->
      <article class="project-card rounded-xl p-8 mb-10">
        <header class="flex items-center justify-between flex-wrap gap-4 mb-4">
          <h3 class="text-2xl font-bold text-yellow-400">AgilizaVRA — Sistema SaaS (Agenda, CRM, Financeiro)</h3>
          <div class="flex flex-wrap gap-2">
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Flask</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Tailwind</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">SQLite→PostgreSQL</span>
          </div>
        </header>

        <div class="grid md:grid-cols-3 gap-6">
          <div class="md:col-span-2 space-y-3 text-gray-200">
            <p><strong>Problema:</strong> unificar gestão de eventos, clientes e finanças.</p>
            <p><strong>Solução:</strong> SaaS multi-módulos com RBAC, dashboards e automações de operação.</p>
            <p><strong>Decisões técnicas:</strong> Flask + Tailwind, Docker Compose, CI/CD (GitHub Actions), migração planejada para PostgreSQL.</p>
            <p><strong>Resultados:</strong> onboarding rápido, redução de tarefas manuais e visão em tempo real.</p>
          </div>

          <aside class="space-y-3">
            <a class="btn-solid w-full" href="https://www.vrashows.com.br/agilizadj" target="_blank" rel="noopener" aria-label="Abrir demo AgilizaVRA">Ver Demo</a>
            <p class="text-xs text-gray-400 text-center">Login: <span class="text-yellow-300">admin</span> · Senha: <span class="text-yellow-300">021150</span></p>
            <button class="btn-outline w-full" onclick="toggleDetails('arch-agiliza')">Arquitetura</button>
            <button class="btn-outline w-full" onclick="toggleDetails('code-agiliza')">Trechos de Código</button>
          </aside>
        </div>

        <div id="arch-agiliza" class="hidden mt-6 text-gray-200">
          <h4 class="text-yellow-400 font-semibold mb-2">Arquitetura (alto nível)</h4>
          <pre class="bg-black/40 p-4 rounded overflow-x-auto text-sm">
Client (Tailwind) → Flask + RBAC → Services (Agenda, CRM, Financeiro)
                             │
                         Auth & Logs
                             │
                Docker Compose → NGINX (TLS) → Gunicorn
                             │
                      VM Cloud + Backups
          </pre>
        </div>

        <div id="code-agiliza" class="hidden mt-6 text-gray-200">
          <h4 class="text-yellow-400 font-semibold mb-2">Pipeline CI/CD (exemplo)</h4>
          <pre class="bg-black/40 p-4 rounded overflow-x-auto text-sm">
name: deploy-agilizavra
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install -r requirements.txt
      - run: pytest -q
      - run: docker compose build --no-cache
      - name: Deploy
        run: ssh -o StrictHostKeyChecking=no $SSH_HOST 'docker compose up -d --build'
          </pre>
        </div>
      </article>

      <!-- CASE: VRASHOWS (SITE E2E) -->
      <article class="project-card rounded-xl p-8 mb-10">
        <header class="flex items-center justify-between flex-wrap gap-4 mb-4">
          <h3 class="text-2xl font-bold text-yellow-400">VRASHOWS — Site Institucional (E2E)</h3>
          <div class="flex flex-wrap gap-2">
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Tailwind</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">NGINX</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Linux</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">DNS/SSL/E-mail</span>
          </div>
        </header>

        <div class="grid md:grid-cols-3 gap-6">
          <div class="md:col-span-2 space-y-3 text-gray-200">
            <p><strong>Escopo end-to-end:</strong> compra e configuração de domínio, DNS, provisionamento de VM, NGINX + TLS/HTTP2, e-mail, deploy e automações.</p>
            <p><strong>Desenvolvimento:</strong> design, front-end responsivo, SEO/OG, métricas (analytics), formulários e integrações administrativas.</p>
            <p><strong>Confiabilidade:</strong> backups, logs, monitoramento e hardening básico.</p>
          </div>

          <aside class="space-y-3">
            <a class="btn-outline w-full" href="https://www.vrashows.com.br" target="_blank" rel="noopener" aria-label="Abrir site VRASHOWS">Abrir Site</a>
          </aside>
        </div>
      </article>

      <!-- CASE: VRAMUSIC -->
      <article class="project-card rounded-xl p-8">
        <header class="flex items-center justify-between flex-wrap gap-4 mb-4">
          <h3 class="text-2xl font-bold text-yellow-400">VRAMUSIC — Plataforma SaaS para DJs</h3>
          <div class="flex flex-wrap gap-2">
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Flask</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Docker</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">NGINX</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Oracle Cloud</span>
            <span class="bg-yellow-400/20 text-yellow-300 px-2 py-1 rounded text-xs">Spotify API</span>
          </div>
        </header>

        <p class="text-gray-200 mb-3"><strong>Solução:</strong> API + webapp Flask com integração à Spotify API, caching, autenticação e deploy containerizado.</p>
        <ul class="list-disc pl-5 text-gray-300">
          <li>NGINX+Gunicorn para performance e TLS/HTTP2.</li>
          <li>CI/CD com GitHub Actions.</li>
          <li>Infra otimizada em Oracle Cloud.</li>
        </ul>
      </article>
    </div>
  </section>

  <!-- EDU & CERTS -->
  <section class="py-20 bg-gray-900">
    <div class="container mx-auto px-6">
      <div class="grid md:grid-cols-2 gap-12">
        <div>
          <h2 class="text-3xl font-bold mb-6"><span class="gradient-gold">Formação</span></h2>
          <div class="bg-black/50 rounded-lg p-6 border border-yellow-400/20">
            <h3 class="text-xl font-semibold text-yellow-400 mb-2">Bacharelado em Tecnologia da Informação</h3>
            <p class="text-gray-300">UNIVESP / USP</p>
          </div>
        </div>
        <div>
          <h2 class="text-3xl font-bold mb-6"><span class="gradient-gold">Certificações</span></h2>
          <div class="space-y-3">
            <div class="flex items-center gap-3 text-gray-300"><i class="fas fa-certificate text-yellow-400"></i><span>Microsoft Azure Fundamentals (AZ-900)</span></div>
            <div class="flex items-center gap-3 text-gray-300"><i class="fas fa-certificate text-yellow-400"></i><span>Business Intelligence – FGV</span></div>
            <div class="flex items-center gap-3 text-gray-300"><i class="fas fa-certificate text-yellow-400"></i><span>Programação em Python</span></div>
            <div class="flex items-center gap-3 text-gray-300"><i class="fas fa-certificate text-yellow-400"></i><span>ITIL® 4 – KA Solution</span></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="py-12 bg-black border-t border-yellow-400/20">
    <div class="container mx-auto px-6 text-center">
      <h2 class="text-3xl font-bold mb-6"><span class="gradient-gold">Vamos Conversar?</span></h2>
      <p class="text-gray-300 mb-8 max-w-2xl mx-auto">
        Profissional orientado à entrega, automação e escalabilidade. Atuo com excelência em todas as etapas do ciclo de software — do planejamento à publicação em nuvem.
      </p>

      <div class="flex justify-center gap-6 mb-8">
        <a href="mailto:eliteasamir@gmail.com" class="btn-solid" aria-label="Enviar e-mail">Enviar Email</a>
        <a href="tel:+5511953577804" class="btn-outline" aria-label="Ligar agora">Ligar Agora</a>
      </div>

      <div class="text-gray-500 text-sm">
        <p>&copy; 2024 Samir Ricardo de Oliveira Almeida. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>

  <script>
    function scrollToSection(id){ const el=document.getElementById(id); if(el){ el.scrollIntoView({behavior:'smooth', block:'start'}); } }
    function toggleDetails(id){ const el=document.getElementById(id); if(!el) return; el.classList.toggle('hidden'); }
    const observerOptions={ threshold:0.1, rootMargin:'0px 0px -50px 0px' };
    const observer=new IntersectionObserver((entries)=>{ entries.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('animate-fade-in'); } }); },observerOptions);
    document.addEventListener('DOMContentLoaded',()=>{ document.querySelectorAll('section > div').forEach(sec=>observer.observe(sec)); });
  </script>
</body>
</html>
