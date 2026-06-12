# laudo-us<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>LaudoUS · Checklist</title>
<style>
:root {
  --bg: #0D1B26; --card: #132030; --border: #1E3448;
  --accent: #00B4D8; --accent-dim: rgba(0,180,216,0.15);
  --green: #3DD68C; --green-dim: rgba(61,214,140,0.15); --green-b: #1A6640;
  --gold: #F0B429; --gold-dim: rgba(240,180,41,0.12); --gold-b: #7A5A10;
  --text: #C8E6F0; --muted: #4A7A90; --faint: #1E3448; --red: #FF6B6B;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body { background: var(--bg); color: var(--text); font-family: -apple-system, Inter, sans-serif; padding-bottom: 60px; }

/* HEADER */
#header { background: linear-gradient(135deg,#081420,#0D2035); border-bottom: 1px solid var(--border);
  padding: 13px 14px; position: sticky; top: 0; z-index: 100; }
#header-top { display: flex; align-items: center; justify-content: space-between; margin-bottom: 10px; }
#logo { display: flex; align-items: center; gap: 8px; }
#logo span { font-size: 16px; font-weight: 700; color: var(--accent); }
#logo em { background: var(--accent-dim); border: 1px solid var(--accent); color: var(--accent);
  font-size: 10px; font-style: normal; padding: 2px 7px; border-radius: 10px; font-weight: 600; }
#btn-novo { background: var(--accent-dim); border: 1px solid var(--accent);
  border-radius: 7px; color: var(--accent); padding: 5px 11px; font-size: 11px; font-weight: 700; cursor: pointer; }

/* ABAS */
#abas { display: flex; gap: 5px; }
.aba { flex: 1; padding: 8px 4px; border-radius: 8px; font-size: 12px; font-weight: 600;
  border: 1px solid var(--faint); background: transparent; color: var(--muted); cursor: pointer; }
.aba.ativa { border-color: var(--accent); background: var(--accent-dim); color: var(--accent); }

/* CONTEÚDO */
#conteudo { padding: 12px 14px 0; }

/* CARDS */
.secao { background: var(--card); border-radius: 12px; margin-bottom: 10px; border: 1px solid var(--border); overflow: hidden; }
.secao-header { display: flex; align-items: center; }
.secao-titulo { flex: 1; background: transparent; border: none; padding: 12px 14px;
  display: flex; align-items: center; gap: 8px; cursor: pointer; color: var(--text); text-align: left; font-size: 14px; font-weight: 600; }
.secao-titulo .icone { font-size: 16px; }
.badge-normal { font-size: 10px; background: var(--green-dim); border: 1px solid var(--green-b);
  color: var(--green); padding: 1px 7px; border-radius: 10px; font-weight: 700; }
.badge-alt { font-size: 11px; color: var(--gold); margin-left: 4px; }
.btn-normal { background: transparent; border: 1px solid var(--faint); border-radius: 7px;
  color: #2A5A3A; font-size: 11px; font-weight: 700; padding: 5px 10px; cursor: pointer; margin-right: 10px; white-space: nowrap; }
.btn-normal.ativo { background: var(--green-dim); border-color: var(--green-b); color: var(--green); }
.secao-corpo { display: none; padding: 0 14px 14px; border-top: 1px solid var(--faint); padding-top: 12px; }
.secao-corpo.aberto { display: block; }

/* BLOCO SIMPLES */
.bloco { background: var(--card); border-radius: 12px; margin-bottom: 10px; border: 1px solid var(--border); padding: 14px; }
.bloco-titulo { font-size: 13px; font-weight: 600; color: var(--text); margin-bottom: 12px; }

/* TAGS */
.tag-label { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 5px; margin-top: 8px; }
.tag-row { display: flex; flex-wrap: wrap; gap: 5px; margin-bottom: 8px; }
.tag { padding: 5px 12px; border-radius: 20px; font-size: 12px; font-weight: 400;
  border: 1.5px solid var(--faint); background: transparent; color: var(--muted); cursor: pointer; white-space: nowrap; }
.tag.ativo-accent { border-color: var(--accent); background: var(--accent-dim); color: var(--accent); font-weight: 600; }
.tag.ativo-gold   { border-color: var(--gold);   background: var(--gold-dim);   color: var(--gold);   font-weight: 600; }
.tag.ativo-green  { border-color: var(--green);  background: var(--green-dim);  color: var(--green);  font-weight: 600; }

/* INPUTS */
.num-group { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 8px; }
.num-wrap label { display: block; font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 4px; }
.num-wrap input { width: 72px; background: #08141E; border: 1px solid var(--faint); border-radius: 7px;
  color: var(--text); padding: 5px 8px; font-size: 13px; outline: none; }
.vol-badge { display: flex; align-items: flex-end; padding-bottom: 4px;
  font-size: 12px; color: var(--accent); font-weight: 600; }

/* TEXTAREA NOTA */
.nota-label { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 5px; margin-top: 10px; }
.nota-input { width: 100%; background: #08141E; border: 1px solid var(--faint); border-radius: 8px;
  color: var(--text); font-size: 12px; padding: 8px 10px; resize: vertical; outline: none; font-family: inherit; }

/* NÓDULOS / CISTOS */
.item-card { background: #08141E; border-radius: 10px; padding: 12px; margin-bottom: 8px; border: 1px solid var(--faint); }
.item-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
.item-titulo { font-size: 12px; font-weight: 600; color: var(--accent); }
.btn-rem { background: transparent; border: none; color: var(--red); cursor: pointer; font-size: 15px; }
.btn-add { border-radius: 8px; font-size: 12px; font-weight: 700; padding: 5px 12px; cursor: pointer; }
.btn-add.accent { background: var(--accent-dim); border: 1px solid var(--accent); color: var(--accent); }
.btn-add.gold   { background: var(--gold-dim);   border: 1px solid var(--gold-b);  color: var(--gold); }

/* RESUMO */
#resumo-box { background: var(--card); border-radius: 12px; border: 1px solid var(--faint); padding: 14px; margin-top: 10px; }
#resumo-label { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 1.5px; margin-bottom: 8px; }
#resumo-pre { color: #7EECC8; font-family: monospace; font-size: 11px; line-height: 1.7; white-space: pre-wrap; }
#btn-copiar { width: 100%; border: none; border-radius: 12px; margin-top: 10px;
  background: linear-gradient(135deg,#006B8A,#00B4D8); color: #fff;
  font-size: 14px; font-weight: 700; padding: 15px; cursor: pointer; }
#btn-copiar.copiado { background: linear-gradient(135deg,#00705A,#009070); }

.nota-geral-box { background: var(--card); border-radius: 12px; border: 1px solid var(--border); padding: 14px; margin-top: 4px; }
.nota-geral-label { font-size: 12px; font-weight: 600; color: var(--gold); margin-bottom: 8px; }

select { background: #08141E; border: 1px solid var(--faint); border-radius: 7px; color: var(--text); padding: 6px 8px; font-size: 12px; outline: none; }
</style>
</head>
<body>

<div id="header">
  <div id="header-top">
    <div id="logo">
      <span>🔊 LaudoUS</span>
      <em>CHECKLIST</em>
    </div>
    <button id="btn-novo" onclick="novoLaudo()">＋ Novo laudo</button>
  </div>
  <div id="abas">
    <button class="aba ativa" onclick="setAba('abd')" id="aba-abd">🫃 Abdômen</button>
    <button class="aba" onclick="setAba('tir')" id="aba-tir">🦋 Tireoide</button>
    <button class="aba" onclick="setAba('mam')" id="aba-mam">🩷 Mama</button>
    <button class="aba" onclick="setAba('tv')"  id="aba-tv">🔵 TV</button>
  </div>
</div>

<div id="conteudo"></div>

<script>
// ── ESTADO ────────────────────────────────────────────────────────────────────
let estado = { abd:{}, tir:{}, mam:{}, tv:{} };
let abaAtiva = 'abd';
let notaGeral = '';

function s(mod) { return estado[mod] || {}; }
function u(mod, k, v) {
  if (!estado[mod]) estado[mod] = {};
  if (v === null || v === undefined || v === '') delete estado[mod][k];
  else estado[mod][k] = v;
  render();
}
function uArr(mod, k, arr) { if (!estado[mod]) estado[mod] = {}; estado[mod][k] = arr; render(); }
function toggle(mod, k, v) {
  const cur = (estado[mod] || {})[k];
  u(mod, k, cur === v ? null : v);
}
function toggleArr(mod, k, v) {
  const arr = ((estado[mod] || {})[k]) || [];
  uArr(mod, k, arr.includes(v) ? arr.filter(x=>x!==v) : [...arr, v]);
}
function vol(a,b,c) {
  if (!a||!b||!c) return null;
  return (0.524*parseFloat(a)*parseFloat(b)*parseFloat(c)).toFixed(1);
}

function novoLaudo() {
  if (confirm('Iniciar novo laudo? Todos os dados serão apagados.')) {
    estado = { abd:{}, tir:{}, mam:{}, tv:{} };
    notaGeral = '';
    abaAtiva = 'abd';
    render();
  }
}
function setAba(a) { abaAtiva = a; render(); }

// ── HELPERS HTML ──────────────────────────────────────────────────────────────
function tagRow(mod, k, opts, cor='accent', label='', multi=false) {
  const cur = (estado[mod]||{})[k];
  const arr = Array.isArray(cur) ? cur : [];
  let h = label ? `<div class="tag-label">${label}</div>` : '';
  h += '<div class="tag-row">';
  opts.forEach(o => {
    const ativo = multi ? arr.includes(o) : cur===o;
    const cls = ativo ? `tag ativo-${cor}` : 'tag';
    const fn = multi
      ? `toggleArr('${mod}','${k}','${o.replace(/'/g,"\\'")}');`
      : `toggle('${mod}','${k}','${o.replace(/'/g,"\\'")}');`;
    h += `<button class="${cls}" onclick="${fn}">${o}</button>`;
  });
  h += '</div>';
  return h;
}

function numInput(mod, k, lbl, unit='cm', w=72) {
  const v = (estado[mod]||{})[k] || '';
  return `<div class="num-wrap">
    <label>${lbl}</label>
    <input type="number" step="0.1" value="${v}" style="width:${w}px"
      oninput="u('${mod}','${k}',this.value)" placeholder="—">
    ${unit ? `<span style="font-size:11px;color:var(--muted);margin-left:3px">${unit}</span>` : ''}
  </div>`;
}

function notaInput(mod, k, ph='Detalhar no áudio...') {
  const v = (estado[mod]||{})[k] || '';
  return `<div class="nota-label">📝 Comentário / detalhar no áudio</div>
    <textarea class="nota-input" rows="2" placeholder="${ph}"
      oninput="u('${mod}','${k}',this.value)">${v}</textarea>`;
}

function volBadge(a,b,c) {
  const v = vol(a,b,c);
  return v ? `<div class="vol-badge">Vol: ${v} cm³</div>` : '';
}

function secao(id, titulo, icone, corpo, mod, normalKey) {
  const aberto = (estado['__open']||{})[id];
  const normal = (estado[mod]||{})[normalKey||'_normal'];
  const temAlt = !normal && Object.keys(estado[mod]||{}).some(k=>!k.startsWith('_')&&estado[mod][k]);
  return `<div class="secao">
    <div class="secao-header">
      <button class="secao-titulo" onclick="toggleOpen('${id}')">
        <span class="icone">${icone}</span>
        <span>${titulo}</span>
        ${normal&&!aberto?'<span class="badge-normal">NORMAL</span>':''}
        ${temAlt&&!aberto?'<span class="badge-alt">✎</span>':''}
        <span style="margin-left:auto;opacity:0.4;font-size:12px">${aberto?'▲':'▼'}</span>
      </button>
      <button class="btn-normal ${normal?'ativo':''}"
        onclick="u('${mod}','_normal',${normal?'null':true});${normal?'':`closeOpen('${id}');`}">✓ Normal</button>
    </div>
    <div class="secao-corpo ${aberto?'aberto':''}" id="corpo-${id}">${aberto?corpo:''}</div>
  </div>`;
}

function toggleOpen(id) {
  if (!estado['__open']) estado['__open'] = {};
  estado['__open'][id] = !estado['__open'][id];
  render();
}
function closeOpen(id) {
  if (!estado['__open']) estado['__open'] = {};
  estado['__open'][id] = false;
}

// ── ABDÔMEN ───────────────────────────────────────────────────────────────────
function htmlAbdomen() {
  const m = 'abd';
  const d = estado[m] || {};

  function orgCorpo(key) {
    const s = d[key] || {};
    switch(key) {
      case 'figado': return `
        ${tagRow(m,'figAchado',['Esteatose leve','Esteatose moderada','Esteatose acentuada','Hepatopatia crônica','Cirrose','Hepatomegalia'],'gold','⚡ Frases rápidas')}
        <div class="tag-label">Medidas (cm)</div>
        <div class="num-group">
          ${numInput(m,'figD','Lobo D')} ${numInput(m,'figE','Lobo E')} ${numInput(m,'figCaud','Caudado')}
        </div>
        ${tagRow(m,'figLesoes',['Nódulo hipoecoico','Nódulo hiperecoico','Metástase(s)','Cisto simples','Cisto complicado','Hemangioma'],'accent','Lesão focal',true)}
        ${(s.figLesoes||[]).some(l=>l.includes('Nódulo')||l.includes('Metástase')) ? `<div class="num-group">${numInput(m,'figNodTam','Maior nódulo','mm')}</div>` : ''}
        ${(s.figLesoes||[]).some(l=>l.includes('Cisto')) ? `<div class="num-group">${numInput(m,'figCistoTam','Maior cisto','mm')}</div>` : ''}
        ${notaInput(m,'figNota')}`;

      case 'vesicula': return `
        ${tagRow(m,'vesAchado',['Colelitíase','Lama biliar','Pólipo','Parede espessada','Não visualizada','Colecistectomia'],'gold','Achado')}
        ${s.vesAchado==='Colelitíase' ? `
          ${tagRow(m,'vesCalcQtd',['Único','Múltiplos'],'accent','Quantidade')}
          <div class="num-group">${numInput(m,'vesCalcTam','Maior','mm')}</div>` : ''}
        ${s.vesAchado==='Pólipo' ? `<div class="num-group">${numInput(m,'vesPolTam','Tamanho','mm')}</div>` : ''}
        ${notaInput(m,'vesNota')}`;

      case 'pancreas': return `
        ${tagRow(m,'pancAchado',['Parcialmente visto (gás)','Parcialmente visto (fácies)','Ducto dilatado','Lesão expansiva','Pancreatite crônica'],'gold','Achado')}
        ${s.pancAchado==='Ducto dilatado' ? `<div class="num-group">${numInput(m,'pancDucto','Calibre','mm')}</div>` : ''}
        ${notaInput(m,'pancNota')}`;

      case 'rins': return `
        ${tagRow(m,'rinsAchado',['Nefropatia / Ecogen↑ DCM preservada','Nefropatia / Ecogen↑ DCM prejudicada','DRC / DCM perdida','Hidronefrose D','Hidronefrose E','Litíase'],'gold','Achado')}
        <div class="tag-label">Eixo longitudinal (cm)</div>
        <div class="num-group">${numInput(m,'rinsEixoD','Rim D')} ${numInput(m,'rinsEixoE','Rim E')}</div>
        <div class="tag-label">Parênquima (mm)</div>
        <div class="num-group">${numInput(m,'rinsParD','Parênq D','mm')} ${numInput(m,'rinsParE','Parênq E','mm')}</div>
        ${tagRow(m,'rinsCistos',['Cisto simples D','Cisto simples E','Cisto complicado'],'accent','Cisto',true)}
        ${(s.rinsCistos||[]).length ? `<div class="num-group">${numInput(m,'rinsCistoTam','Maior cisto','mm')}</div>` : ''}
        ${notaInput(m,'rinsNota')}`;

      case 'baco': return `
        ${tagRow(m,'bacoAchado',['Esplenomegalia','Lesão focal'],'gold','Achado')}
        ${s.bacoAchado==='Esplenomegalia' ? `<div class="num-group">${numInput(m,'bacoTam','Maior eixo')}</div>` : ''}
        ${notaInput(m,'bacoNota')}`;

      case 'aorta': return `
        ${tagRow(m,'aortaAchado',['Ateromatose','Ectasia','Aneurisma'],'gold','Achado')}
        ${(s.aortaAchado==='Ectasia'||s.aortaAchado==='Aneurisma') ? `<div class="num-group">${numInput(m,'aortaDiam','Diâmetro máx','mm')}</div>` : ''}
        ${notaInput(m,'aortaNota')}`;

      case 'bexiga': return `
        ${tagRow(m,'bexAchado',['Cálculo vesical','Espessamento parietal','Lesão intraluminal','Sem repleção'],'gold','Achado')}
        ${s.bexAchado==='Cálculo vesical' ? `<div class="num-group">${numInput(m,'bexTam','Tamanho','mm')}</div>` : ''}
        ${notaInput(m,'bexNota')}`;

      case 'cavidade': return `
        ${tagRow(m,'cavAchado',['Ascite pequena','Ascite moderada','Ascite volumosa'],'gold','Achado')}
        ${notaInput(m,'cavNota')}`;
    }
  }

  const orgaos = [
    ['figado','Fígado','🟤'],['vesicula','Vesícula Biliar','💛'],['pancreas','Pâncreas','🔬'],
    ['rins','Rins','🫘'],['baco','Baço','🔴'],['aorta','Aorta','🩸'],['bexiga','Bexiga','🫧'],['cavidade','Cavidade','⬜']
  ];
  return orgaos.map(([key,titulo,icone]) =>
    secao('abd-'+key, titulo, icone, orgCorpo(key), m, '_normal_'+key)
  ).join('');
}

// ── TIREOIDE ──────────────────────────────────────────────────────────────────
function htmlTireoide() {
  const m = 'tir';
  const s = estado[m] || {};
  const nods = s.nodulos || [];

  const nodsHtml = nods.map((n,i) => `
    <div class="item-card">
      <div class="item-header">
        <span class="item-titulo">Nódulo ${i+1}</span>
        <button class="btn-rem" onclick="remNodTir(${i})">✕</button>
      </div>
      ${tagRow(m,'nod_'+i+'_lobo',['Direito','Esquerdo','Istmo'],'accent','Lobo')}
      ${tagRow(m,'nod_'+i+'_polo',['Superior','Médio','Inferior'],'accent','Polo')}
      <div class="tag-label">Medidas (mm)</div>
      <div class="num-group">
        ${numInput(m,'nod_'+i+'_m1','Med 1','mm')} ${numInput(m,'nod_'+i+'_m2','Med 2','mm')} ${numInput(m,'nod_'+i+'_m3','Med 3','mm')}
      </div>
      ${tagRow(m,'nod_'+i+'_comp',['Sólido','Predomin. sólido','Misto','Espongiforme','Cisto'],'gold','Composição')}
      ${tagRow(m,'nod_'+i+'_ecogen',['Hipoecoico','Isoecoico','Hiperecoico','Muito hipoecoico'],'accent','Ecogenicidade')}
      ${tagRow(m,'nod_'+i+'_forma',['Mais largo que alto','Mais alto que largo'],'','Forma')}
      ${tagRow(m,'nod_'+i+'_margem',['Regular','Lobulada','Irregular','Espiculada','Extraparenquimatosa'],'','Margem')}
      ${tagRow(m,'nod_'+i+'_focos',['Macrocalcificações','Calcif. periféricas','Foco puntiforme','Artefato cauda de cometa','Ausentes'],'','Focos ecogênicos',true)}
      ${notaInput(m,'nod_'+i+'_nota','Vascularização, características adicionais...')}
    </div>`).join('');

  const cistoColHtml = (s.cistoCol==='Único'||s.cistoCol==='Múltiplos') ? `
    <div style="margin-top:8px">
      ${tagRow(m,'cistoColLado',['Direito','Esquerdo','Bilateral'],'accent','Lobo')}
      <div class="num-group">${numInput(m,'cistoColTam','Maior','mm')}</div>
    </div>` : '';

  const volD = vol(s.tirDC,s.tirDL,s.tirDA);
  const volE = vol(s.tirEC,s.tirEL,s.tirEA);

  return `
    <div class="bloco">
      <div class="bloco-titulo">🔲 Parênquima</div>
      ${tagRow(m,'tirDim',['Normais','Aumentadas (bócio)','Reduzidas'],'','Dimensões')}
      ${tagRow(m,'tirEcotex',['Homogênea','Heterogênea'],'','Ecotextura')}
      ${tagRow(m,'tirEcogen',['Normal','Reduzida (tireoidite?)'],'gold','Ecogenicidade')}
      <div class="tag-label">Lobo Direito — C × L × A (mm)</div>
      <div class="num-group">
        ${numInput(m,'tirDC','C','mm',60)} ${numInput(m,'tirDL','L','mm',60)} ${numInput(m,'tirDA','A','mm',60)}
        ${volD ? `<div class="vol-badge">Vol: ${volD} mL</div>` : ''}
      </div>
      <div class="tag-label">Lobo Esquerdo — C × L × A (mm)</div>
      <div class="num-group">
        ${numInput(m,'tirEC','C','mm',60)} ${numInput(m,'tirEL','L','mm',60)} ${numInput(m,'tirEA','A','mm',60)}
        ${volE ? `<div class="vol-badge">Vol: ${volE} mL</div>` : ''}
      </div>
      <div class="num-group">${numInput(m,'tirIstmo','Istmo AP','mm')}</div>
      <div style="background:#08141E;border-radius:8px;padding:10px;margin-top:8px;border:1px solid var(--faint)">
        ${tagRow(m,'cistoCol',['Não','Único','Múltiplos'],'','Cistos coloides')}
        ${cistoColHtml}
      </div>
      ${notaInput(m,'tirParNota','Nódulo incidental, vascularização, linfonodos...')}
    </div>
    <div class="bloco">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <span class="bloco-titulo">🔵 Nódulos (${nods.length})</span>
        <button class="btn-add accent" onclick="addNodTir()">+ Adicionar nódulo</button>
      </div>
      ${nods.length===0 ? '<div style="font-size:12px;color:var(--muted);text-align:center;padding:10px 0">Sem nódulos identificados</div>' : nodsHtml}
    </div>`;
}

function addNodTir() { uArr('tir','nodulos',[...(estado.tir.nodulos||[]),{}]); }
function remNodTir(i) { uArr('tir','nodulos',(estado.tir.nodulos||[]).filter((_,j)=>j!==i)); }

// ── MAMA ──────────────────────────────────────────────────────────────────────
function htmlMama() {
  const m = 'mam';
  const s = estado[m] || {};
  const nods = s.nodulos || [];

  const cistoSimpHtml = (s.cistoSimp==='Único'||s.cistoSimp==='Múltiplos') ? `
    <div style="margin-top:8px">
      ${tagRow(m,'cistoSimpLoc',['Raio','Quadrante'],'accent','Localização')}
      ${s.cistoSimpLoc==='Raio' ? `
        ${tagRow(m,'cistoSimpLado',['Direita','Esquerda','Bilateral'],'','Mama')}
        <div class="num-group">${numInput(m,'cistoSimpRaio','Raio (h)','h',55)}</div>` : ''}
      ${s.cistoSimpLoc==='Quadrante' ? `
        ${tagRow(m,'cistoSimpLado',['Direita','Esquerda','Bilateral'],'','Mama')}
        ${tagRow(m,'cistoSimpQuad',['QSE','QSD','QIE','QID','JQS','JQI','JQE','JQD','Retroareolar'],'','Quadrante')}` : ''}
      <div class="num-group">${numInput(m,'cistoSimpTam','Maior','mm')}</div>
    </div>` : '';

  const nodsHtml = nods.map((n,i) => `
    <div class="item-card">
      <div class="item-header">
        <span class="item-titulo">Nódulo ${i+1}</span>
        <button class="btn-rem" onclick="remNodMam(${i})">✕</button>
      </div>
      ${tagRow(m,'mam_'+i+'_lado',['Direita','Esquerda'],'accent','Mama')}
      <div class="num-group">
        ${numInput(m,'mam_'+i+'_raio','Raio (h)','h',55)}
        ${numInput(m,'mam_'+i+'_distMam','Dist. mamilo')}
        ${numInput(m,'mam_'+i+'_distPele','Dist. pele')}
      </div>
      <div class="tag-label">Medidas (mm)</div>
      <div class="num-group">
        ${numInput(m,'mam_'+i+'_m1','Med 1','mm')} ${numInput(m,'mam_'+i+'_m2','Med 2','mm')} ${numInput(m,'mam_'+i+'_m3','Med 3','mm')}
      </div>
      ${tagRow(m,'mam_'+i+'_comp',['Sólido','Predomin. sólido','Misto','Cisto simples','Cisto complicado'],'gold','Composição')}
      ${tagRow(m,'mam_'+i+'_ecogen',['Hipoecoico','Isoecoico','Hiperecoico','Anecoico'],'accent','Ecogenicidade')}
      ${tagRow(m,'mam_'+i+'_forma',['Oval','Redondo','Irregular'],'','Forma')}
      ${tagRow(m,'mam_'+i+'_orient',['Paralelo à pele','Não paralelo (mais alto)'],'','Orientação')}
      ${tagRow(m,'mam_'+i+'_margem',['Circunscrita','Não circunscrita','Irregular','Espiculada','Microlobulada'],'','Margens')}
      ${tagRow(m,'mam_'+i+'_assoc',['Sombra acústica posterior','Reforço acústico','Calcificações','Edema perilesional','Alteração pele'],'','Achados associados',true)}
      ${notaInput(m,'mam_'+i+'_nota','Detalhes adicionais...')}
    </div>`).join('');

  return `
    <div class="bloco">
      <div class="bloco-titulo">🔲 Parênquima Mamário</div>
      ${tagRow(m,'compD',['A (gordurosa)','B (fibrog. dispersa)','C (fibrog. heterogênea)','D (extremamente densa)'],'gold','Mama Direita — Composição BI-RADS')}
      ${tagRow(m,'compE',['A (gordurosa)','B (fibrog. dispersa)','C (fibrog. heterogênea)','D (extremamente densa)'],'gold','Mama Esquerda — Composição BI-RADS')}
      ${tagRow(m,'ecotex',['Homogênea','Heterogênea','Lipossubstituída','Fibroglandular densa'],'accent','Ecotextura bilateral')}
      <div style="background:#08141E;border-radius:8px;padding:10px;margin-top:8px;border:1px solid var(--faint)">
        ${tagRow(m,'cistoSimp',['Não','Único','Múltiplos'],'','Cistos simples')}
        ${cistoSimpHtml}
      </div>
      ${notaInput(m,'mamParNota','Alteração difusa, edema...')}
    </div>
    <div class="bloco">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <span class="bloco-titulo">🔵 Nódulos (${nods.length})</span>
        <button class="btn-add accent" onclick="addNodMam()">+ Adicionar nódulo</button>
      </div>
      ${nods.length===0 ? '<div style="font-size:12px;color:var(--muted);text-align:center;padding:10px 0">Sem nódulos identificados</div>' : nodsHtml}
    </div>`;
}

function addNodMam() { uArr('mam','nodulos',[...(estado.mam.nodulos||[]),{}]); }
function remNodMam(i) { uArr('mam','nodulos',(estado.mam.nodulos||[]).filter((_,j)=>j!==i)); }

// ── TRANSVAGINAL ──────────────────────────────────────────────────────────────
function htmlTV() {
  const m = 'tv';
  const s = estado[m] || {};
  const miomas = s.miomas || [];
  const cistosD = s.cistosD || [];
  const cistosE = s.cistosE || [];

  const volUt = vol(s.utC,s.utL,s.utA);
  const volOvD = vol(s.ovDC,s.ovDL,s.ovDA);
  const volOvE = vol(s.ovEC,s.ovEL,s.ovEA);

  const miomasHtml = miomas.map((mi,i) => `
    <div class="item-card">
      <div class="item-header">
        <span style="font-size:12px;font-weight:600;color:var(--gold)">Mioma ${i+1}</span>
        <button class="btn-rem" onclick="remMioma(${i})">✕</button>
      </div>
      ${tagRow(m,'mi_'+i+'_tipo',['Intramural','Submucoso','Subseroso','Pediculado'],'gold','Tipo')}
      ${tagRow(m,'mi_'+i+'_parede',['Fúndica anterior','Fúndica posterior','Anterior','Posterior','Lateral D','Lateral E','Fundo'],'','Parede')}
      <div class="num-group">
        ${numInput(m,'mi_'+i+'_C','C')} ${numInput(m,'mi_'+i+'_L','L')} ${numInput(m,'mi_'+i+'_A','A')}
      </div>
    </div>`).join('');

  function cistoOvHtml(lista, lado) {
    return lista.map((ci,i) => {
      const vci = vol(s['cis'+lado+'_'+i+'_C'],s['cis'+lado+'_'+i+'_L'],s['cis'+lado+'_'+i+'_A']);
      return `<div class="item-card">
        <div class="item-header">
          <span class="item-titulo">Cisto ${i+1}</span>
          <button class="btn-rem" onclick="remCistoOv('${lado}',${i})">✕</button>
        </div>
        ${tagRow(m,'cis'+lado+'_'+i+'_asp',['Simples','Endometrioma','Dermoide','Complexo','Hemorrágico','Paraovarian'],'gold','Aspecto')}
        <div class="num-group">
          ${numInput(m,'cis'+lado+'_'+i+'_C','C')} ${numInput(m,'cis'+lado+'_'+i+'_L','L')} ${numInput(m,'cis'+lado+'_'+i+'_A','A')}
          ${vci ? `<div class="vol-badge">Vol: ${vci} cm³</div>` : ''}
        </div>
        ${tagRow(m,'cis'+lado+'_'+i+'_cont',['Regulares','Irregulares'],'','Contornos')}
        ${tagRow(m,'cis'+lado+'_'+i+'_pap',['Ausente','Presente'],'gold','Projeção papilar')}
        ${s['cis'+lado+'_'+i+'_pap']==='Presente' ? tagRow(m,'cis'+lado+'_'+i+'_dop',['Ausente','Presente'],'accent','Fluxo Doppler') : ''}
        ${tagRow(m,'cis'+lado+'_'+i+'_sep',['Ausentes','Finos septos','Septos espessos'],'','Septações')}
      </div>`;
    }).join('');
  }

  return `
    <div class="bloco">
      <div class="bloco-titulo">🔵 Útero</div>
      ${tagRow(m,'utPos',['AVF','MVF','RVF','Lateralizado D','Lateralizado E','Mediano'],'','Posição')}
      <div class="tag-label">Dimensões — C × L × A (cm)</div>
      <div class="num-group">
        ${numInput(m,'utC','C')} ${numInput(m,'utL','L')} ${numInput(m,'utA','A')}
        ${volUt ? `<div class="vol-badge">Vol: ${volUt} cm³</div>` : ''}
      </div>
      ${tagRow(m,'utTex',['Homogênea','Heterogênea'],'','Textura miometrial')}
      ${tagRow(m,'utAden',['Ausente','Presente','Suspeita'],'gold','Adenomiose')}
      ${tagRow(m,'utDiu',['Não','Posicionado','Mal posicionado'],'accent','DIU')}
    </div>

    <div class="bloco">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
        <span class="bloco-titulo">🔶 Miomas (${miomas.length})</span>
        <button class="btn-add gold" onclick="addMioma()">+ Mioma</button>
      </div>
      ${tagRow(m,'miomaSt',['Ausentes','Presentes'],'gold')}
      ${s.miomaSt==='Presentes' ? miomasHtml : ''}
    </div>

    <div class="bloco">
      <div class="bloco-titulo">🟡 Endométrio</div>
      <div class="num-group">${numInput(m,'endEsp','Espessura')}</div>
      ${tagRow(m,'endAsp',['Centrado e homogêneo','Heterogêneo','Deslocado','Não visualizado'],'accent','Aspecto')}
      ${tagRow(m,'laminaLiq',['Ausente','Presente'],'gold','Lâmina líquida intracavitária')}
      ${s.laminaLiq==='Presente' ? `<div class="num-group">${numInput(m,'laminaEsp','Espessura')}</div>` : ''}
      ${notaInput(m,'endNota','Pólipos, irregularidades...')}
    </div>

    <div class="bloco">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
        <span class="bloco-titulo">🔴 Ovário Direito</span>
        <button class="btn-add accent" onclick="addCistoOv('D')">+ Cisto</button>
      </div>
      ${tagRow(m,'ovDVis',['Sim','Não'],'','Visualizado')}
      ${s.ovDVis==='Sim' ? `
        <div class="num-group">
          ${numInput(m,'ovDC','C')} ${numInput(m,'ovDL','L')} ${numInput(m,'ovDA','A')}
          ${volOvD ? `<div class="vol-badge">Vol: ${volOvD} cm³</div>` : ''}
        </div>
        ${tagRow(m,'ovDAsp',['Normal','Aumentado','Policístico'],'','Aspecto')}
        ${cistoOvHtml(cistosD,'D')}` : ''}
    </div>

    <div class="bloco">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
        <span class="bloco-titulo">🟠 Ovário Esquerdo</span>
        <button class="btn-add accent" onclick="addCistoOv('E')">+ Cisto</button>
      </div>
      ${tagRow(m,'ovEVis',['Sim','Não'],'','Visualizado')}
      ${s.ovEVis==='Sim' ? `
        <div class="num-group">
          ${numInput(m,'ovEC','C')} ${numInput(m,'ovEL','L')} ${numInput(m,'ovEA','A')}
          ${volOvE ? `<div class="vol-badge">Vol: ${volOvE} cm³</div>` : ''}
        </div>
        ${tagRow(m,'ovEAsp',['Normal','Aumentado','Policístico'],'','Aspecto')}
        ${cistoOvHtml(cistosE,'E')}` : ''}
    </div>

    <div class="bloco">
      <div class="bloco-titulo">💧 Líquido livre</div>
      ${tagRow(m,'tvLiquido',['Ausente','Presente — pequena quantidade','Presente — moderada quantidade'],'gold')}
      ${notaInput(m,'tvNota','Outros achados...')}
    </div>`;
}

function addMioma()        { uArr('tv','miomas',[...(estado.tv.miomas||[]),{}]); }
function remMioma(i)       { uArr('tv','miomas',(estado.tv.miomas||[]).filter((_,j)=>j!==i)); }
function addCistoOv(lado)  { uArr('tv','cistos'+lado,[...(estado.tv['cistos'+lado]||[]),{}]); }
function remCistoOv(lado,i){ uArr('tv','cistos'+lado,(estado.tv['cistos'+lado]||[]).filter((_,j)=>j!==i)); }

// ── RESUMO ────────────────────────────────────────────────────────────────────
function gerarResumo() {
  const aba = abaAtiva;
  const L = [];

  if (aba==='abd') {
    L.push('=== ULTRASSOM ABDÔMEN ===\n');
    const m = estado.abd || {};
    const orgaos = [
      ['fig','Fígado',['figAchado','figLesoes','figD','figE','figCaud','figNodTam','figCistoTam','figNota']],
      ['ves','Vesícula',['vesAchado','vesCalcQtd','vesCalcTam','vesPolTam','vesNota']],
      ['panc','Pâncreas',['pancAchado','pancDucto','pancNota']],
      ['rins','Rins',['rinsAchado','rinsEixoD','rinsEixoE','rinsParD','rinsParE','rinsCistos','rinsCistoTam','rinsNota']],
      ['baco','Baço',['bacoAchado','bacoTam','bacoNota']],
      ['aorta','Aorta',['aortaAchado','aortaDiam','aortaNota']],
      ['bex','Bexiga',['bexAchado','bexTam','bexNota']],
      ['cav','Cavidade',['cavAchado','cavNota']],
    ];
    const normais = [];
    orgaos.forEach(([pfx,nome,campos]) => {
      if (m['_normal_'+pfx]) { normais.push(nome); return; }
      const ac = [];
      campos.forEach(k => {
        const v = m[k];
        if (!v || (Array.isArray(v) && v.length===0)) return;
        if (k.endsWith('Nota')) ac.push('⚠ '+v);
        else if (Array.isArray(v)) ac.push(v.join(', '));
        else if (k.includes('Tam')||k.includes('Eixo')||k.includes('Par')&&!k.includes('Panc')||k.includes('Diam')||k.includes('Ducto')) ac.push(k.replace(pfx,'').replace(/([A-Z])/g,' $1').trim()+': '+v);
        else ac.push(v);
      });
      if (ac.length) L.push('• '+nome+': '+ac.join(' | '));
    });
    if (normais.length) L.push('\nNormais: '+normais.join(', '));
  }

  if (aba==='tir') {
    L.push('=== ULTRASSOM TIREOIDE ===\n');
    const s = estado.tir || {};
    const par = [];
    if (s.tirDim)    par.push('dimensões '+s.tirDim);
    if (s.tirEcotex) par.push('ecotextura '+s.tirEcotex.toLowerCase());
    if (s.tirEcogen) par.push(s.tirEcogen.toLowerCase());
    const vD = vol(s.tirDC,s.tirDL,s.tirDA);
    const vE = vol(s.tirEC,s.tirEL,s.tirEA);
    if (s.tirDC&&s.tirDL&&s.tirDA) par.push('lobo D: '+s.tirDC+'×'+s.tirDL+'×'+s.tirDA+'mm'+(vD?' (vol:'+vD+'mL)':''));
    if (s.tirEC&&s.tirEL&&s.tirEA) par.push('lobo E: '+s.tirEC+'×'+s.tirEL+'×'+s.tirEA+'mm'+(vE?' (vol:'+vE+'mL)':''));
    if (s.tirIstmo) par.push('istmo AP: '+s.tirIstmo+'mm');
    L.push('Parênquima: '+(par.length?par.join(' | '):'não informado'));
    if (s.cistoCol&&s.cistoCol!=='Não') {
      const cc = [s.cistoCol+' cisto(s) coloide(s)'];
      if (s.cistoColLado) cc.push(s.cistoColLado);
      if (s.cistoColTam)  cc.push('maior '+s.cistoColTam+'mm');
      L.push('Cistos coloides: '+cc.join(', '));
    }
    if (s.tirParNota) L.push('⚠ '+s.tirParNota);
    const nods = s.nodulos||[];
    L.push(nods.length===0 ? 'Nódulos: nenhum identificado' : 'Nódulos ('+nods.length+'):');
    nods.forEach((n,i) => {
      const info=[];
      if (s['nod_'+i+'_lobo'])   info.push('lobo '+s['nod_'+i+'_lobo']);
      if (s['nod_'+i+'_polo'])   info.push('polo '+s['nod_'+i+'_polo']);
      const med=[s['nod_'+i+'_m1'],s['nod_'+i+'_m2'],s['nod_'+i+'_m3']].filter(Boolean).join('×');
      if (med) info.push(med+'mm');
      if (s['nod_'+i+'_comp'])   info.push(s['nod_'+i+'_comp']);
      if (s['nod_'+i+'_ecogen']) info.push(s['nod_'+i+'_ecogen']);
      if (s['nod_'+i+'_forma'])  info.push(s['nod_'+i+'_forma']);
      if (s['nod_'+i+'_margem']) info.push('margem '+s['nod_'+i+'_margem']);
      const focos=(s['nod_'+i+'_focos']||[]).join(', ');
      if (focos) info.push('focos: '+focos);
      if (s['nod_'+i+'_nota'])   info.push('⚠ '+s['nod_'+i+'_nota']);
      L.push('  Nódulo '+(i+1)+': '+info.join(' | '));
    });
  }

  if (aba==='mam') {
    L.push('=== ULTRASSOM MAMA ===\n');
    const s = estado.mam || {};
    if (s.compD||s.compE) L.push('Composição: '+[s.compD&&'MD '+s.compD,s.compE&&'ME '+s.compE].filter(Boolean).join(' | '));
    if (s.ecotex) L.push('Ecotextura: '+s.ecotex);
    if (s.cistoSimp&&s.cistoSimp!=='Não') {
      const cs=[s.cistoSimp+' cisto(s) simples'];
      if (s.cistoSimpLado) cs.push(s.cistoSimpLado);
      if (s.cistoSimpLoc==='Raio'&&s.cistoSimpRaio) cs.push('raio '+s.cistoSimpRaio+'h');
      if (s.cistoSimpLoc==='Quadrante'&&s.cistoSimpQuad) cs.push(s.cistoSimpQuad);
      if (s.cistoSimpTam) cs.push('maior '+s.cistoSimpTam+'mm');
      L.push('Cistos simples: '+cs.join(', '));
    }
    if (s.mamParNota) L.push('⚠ '+s.mamParNota);
    const nods=s.nodulos||[];
    L.push(nods.length===0?'Nódulos: nenhum identificado':'Nódulos ('+nods.length+'):');
    nods.forEach((n,i)=>{
      const info=[];
      if (s['mam_'+i+'_lado'])    info.push('mama '+s['mam_'+i+'_lado']);
      if (s['mam_'+i+'_raio'])    info.push('raio '+s['mam_'+i+'_raio']+'h');
      if (s['mam_'+i+'_distMam']) info.push(s['mam_'+i+'_distMam']+'cm do mamilo');
      if (s['mam_'+i+'_distPele'])info.push(s['mam_'+i+'_distPele']+'cm da pele');
      const med=[s['mam_'+i+'_m1'],s['mam_'+i+'_m2'],s['mam_'+i+'_m3']].filter(Boolean).join('×');
      if (med) info.push(med+'mm');
      if (s['mam_'+i+'_comp'])    info.push(s['mam_'+i+'_comp']);
      if (s['mam_'+i+'_ecogen'])  info.push(s['mam_'+i+'_ecogen']);
      if (s['mam_'+i+'_forma'])   info.push('forma '+s['mam_'+i+'_forma']);
      if (s['mam_'+i+'_orient'])  info.push(s['mam_'+i+'_orient']);
      if (s['mam_'+i+'_margem'])  info.push('margens '+s['mam_'+i+'_margem']);
      const assoc=(s['mam_'+i+'_assoc']||[]).join(', ');
      if (assoc) info.push(assoc);
      if (s['mam_'+i+'_nota'])    info.push('⚠ '+s['mam_'+i+'_nota']);
      L.push('  Nódulo '+(i+1)+': '+info.join(' | '));
    });
  }

  if (aba==='tv') {
    L.push('=== ULTRASSOM TRANSVAGINAL ===\n');
    const s = estado.tv || {};
    const ut=[];
    if (s.utPos) ut.push(s.utPos);
    const vut=vol(s.utC,s.utL,s.utA);
    if (s.utC&&s.utL&&s.utA) ut.push(s.utC+'×'+s.utL+'×'+s.utA+'cm'+(vut?' (vol:'+vut+'cm³)':''));
    if (s.utTex) ut.push('textura '+s.utTex.toLowerCase());
    if (s.utAden&&s.utAden!=='Ausente') ut.push('adenomiose: '+s.utAden.toLowerCase());
    if (s.utDiu&&s.utDiu!=='Não') ut.push('DIU '+s.utDiu.toLowerCase());
    L.push('Útero: '+(ut.length?ut.join(' | '):'não informado'));
    const miomas=s.miomas||[];
    if (s.miomaSt==='Ausentes') L.push('Miomas: ausentes');
    else if (miomas.length) {
      L.push('Miomas ('+miomas.length+'):');
      miomas.forEach((_,i)=>{
        const mi=[];
        if (s['mi_'+i+'_tipo'])   mi.push(s['mi_'+i+'_tipo'].toLowerCase());
        if (s['mi_'+i+'_parede']) mi.push('parede '+s['mi_'+i+'_parede'].toLowerCase());
        const med=[s['mi_'+i+'_C'],s['mi_'+i+'_L'],s['mi_'+i+'_A']].filter(Boolean).join('×');
        if (med) mi.push(med+'cm');
        L.push('  Mioma '+(i+1)+': '+mi.join(' | '));
      });
    }
    const end=[];
    if (s.endEsp) end.push('espessura: '+s.endEsp+'cm');
    if (s.endAsp) end.push(s.endAsp.toLowerCase());
    if (s.laminaLiq==='Presente') end.push('lâmina líquida'+(s.laminaEsp?': '+s.laminaEsp+'cm':''));
    if (s.endNota) end.push('⚠ '+s.endNota);
    L.push('Endométrio: '+(end.length?end.join(' | '):'não informado'));
    ['D','E'].forEach(lado=>{
      const vis=s['ov'+lado+'Vis'];
      if (vis==='Não'){L.push('Ovário '+lado+': não visualizado');return;}
      if (!vis) return;
      const ov=[];
      const vov=vol(s['ov'+lado+'C'],s['ov'+lado+'L'],s['ov'+lado+'A']);
      if (s['ov'+lado+'C']&&s['ov'+lado+'L']&&s['ov'+lado+'A'])
        ov.push(s['ov'+lado+'C']+'×'+s['ov'+lado+'L']+'×'+s['ov'+lado+'A']+'cm'+(vov?' (vol:'+vov+'cm³)':''));
      if (s['ov'+lado+'Asp']&&s['ov'+lado+'Asp']!=='Normal') ov.push(s['ov'+lado+'Asp'].toLowerCase());
      const cistos=s['cistos'+lado]||[];
      cistos.forEach((_,i)=>{
        const ci=[];
        const asp=s['cis'+lado+'_'+i+'_asp']; if(asp) ci.push(asp.toLowerCase());
        const med=[s['cis'+lado+'_'+i+'_C'],s['cis'+lado+'_'+i+'_L'],s['cis'+lado+'_'+i+'_A']].filter(Boolean).join('×');
        if(med) ci.push(med+'cm');
        const vcis=vol(s['cis'+lado+'_'+i+'_C'],s['cis'+lado+'_'+i+'_L'],s['cis'+lado+'_'+i+'_A']);
        if(vcis) ci.push('vol:'+vcis+'cm³');
        const cont=s['cis'+lado+'_'+i+'_cont']; if(cont) ci.push('contornos '+cont.toLowerCase());
        const pap=s['cis'+lado+'_'+i+'_pap']; if(pap==='Presente') ci.push('projeção papilar, fluxo Doppler '+(s['cis'+lado+'_'+i+'_dop']||'não avaliado').toLowerCase());
        const sep=s['cis'+lado+'_'+i+'_sep']; if(sep&&sep!=='Ausentes') ci.push(sep.toLowerCase());
        ov.push('cisto '+(i+1)+': '+ci.join(', '));
      });
      L.push('Ovário '+lado+': '+(ov.length?ov.join(' | '):'normal'));
    });
    if (s.tvLiquido) L.push('Líquido livre: '+s.tvLiquido.replace('Presente — ','').toLowerCase());
    if (s.tvNota)    L.push('⚠ '+s.tvNota);
  }

  if (notaGeral) L.push('\nOBSERVAÇÕES GERAIS:\n'+notaGeral);
  return L.join('\n');
}

function copiar() {
  const txt = gerarResumo();
  navigator.clipboard.writeText(txt).then(()=>{
    const btn = document.getElementById('btn-copiar');
    btn.textContent = '✅ Copiado! Cole no Claude para gerar o laudo.';
    btn.classList.add('copiado');
    setTimeout(()=>{ btn.textContent='📋 Copiar resumo para o Claude'; btn.classList.remove('copiado'); },2200);
  });
}

// ── RENDER ────────────────────────────────────────────────────────────────────
function render() {
  // Atualizar abas
  ['abd','tir','mam','tv'].forEach(a => {
    const el = document.getElementById('aba-'+a);
    if (el) el.className = 'aba' + (a===abaAtiva?' ativa':'');
  });

  // Conteúdo principal
  let html = '';
  if (abaAtiva==='abd')  html = htmlAbdomen();
  if (abaAtiva==='tir')  html = htmlTireoide();
  if (abaAtiva==='mam')  html = htmlMama();
  if (abaAtiva==='tv')   html = htmlTV();

  // Nota geral
  html += `<div class="nota-geral-box">
    <div class="nota-geral-label">📝 Observações gerais / detalhar no áudio</div>
    <textarea class="nota-input" rows="3" placeholder="Achados para descrever no áudio ou ajustar no Claude..."
      oninput="notaGeral=this.value">${notaGeral}</textarea>
  </div>`;

  // Resumo
  html += `<div id="resumo-box">
    <div id="resumo-label">Resumo para o Claude</div>
    <pre id="resumo-pre">${gerarResumo()}</pre>
  </div>
  <button id="btn-copiar" onclick="copiar()">📋 Copiar resumo para o Claude</button>`;

  document.getElementById('conteudo').innerHTML = html;
}

render();
</script>
</body>
</html>
