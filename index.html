/**
 * CONFIG
 * 1) Cole aqui a URL do seu Apps Script Web App (deployed)
 * 2) Defina um token simples (mesmo token no Apps Script)
 */
const CONFIG = {
  API_URL: "COLE_AQUI_A_URL_DO_WEB_APP",
  TOKEN: "troque_este_token"
};

const el = (id) => document.getElementById(id);

const statusPill = el("statusPill");
const frm = el("frm");
const btnAgora = el("btnAgora");
const btnLimpar = el("btnLimpar");
const btnEnviar = el("btnEnviar");

function setPill(kind, text){
  statusPill.className = "pill " + (kind || "neutral");
  statusPill.textContent = text;
}

function pad2(n){ return String(n).padStart(2,"0"); }

function setNow(){
  const d = new Date();
  const yyyy = d.getFullYear();
  const mm = pad2(d.getMonth()+1);
  const dd = pad2(d.getDate());
  const hh = pad2(d.getHours());
  const mi = pad2(d.getMinutes());
  el("data").value = `${yyyy}-${mm}-${dd}`;
  el("hora").value = `${hh}:${mi}`;
}

function clearForm(){
  frm.reset();
  setNow();
}

async function send(payload){
  const res = await fetch(CONFIG.API_URL, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "X-APP-TOKEN": CONFIG.TOKEN
    },
    body: JSON.stringify(payload)
  });

  const txt = await res.text();
  let json;
  try { json = JSON.parse(txt); } catch(e){ json = { ok:false, raw: txt }; }

  if(!res.ok || !json.ok){
    throw new Error(json.error || `Falha HTTP ${res.status}`);
  }
  return json;
}

btnAgora.addEventListener("click", () => setNow());
btnLimpar.addEventListener("click", () => clearForm());

frm.addEventListener("submit", async (e) => {
  e.preventDefault();

  btnEnviar.disabled = true;
  setPill("neutral", "Enviando...");

  const payload = {
    data: el("data").value,          // YYYY-MM-DD
    hora: el("hora").value,          // HH:MM
    lote: el("lote").value.trim(),
    traco: el("traco").value.trim(),
    flow_mm: Number(el("flow").value),
    resultado: el("resultado").value,
    corpo_de_prova: el("cp").value
  };

  try{
    const out = await send(payload);
    setPill("ok", "Salvo ✅");

    el("lastCard").style.display = "block";
    el("lastJson").textContent = JSON.stringify(out, null, 2);

    // comportamento “app”: limpa e mantém data/hora atual
    clearForm();
  }catch(err){
    console.error(err);
    setPill("bad", "Erro ❌");
    alert("Erro ao salvar: " + err.message);
  }finally{
    btnEnviar.disabled = false;
  }
});

// init
setNow();
setPill("neutral", "Pronto");
