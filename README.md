
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>PDF Vault • UPI Content Store</title>
<style>
:root{--ink:#20203a;--muted:#6d6c86;--line:#e8e6f4;--bg:#f7f6ff;--purple:#6c43e8;--pink:#ff5c9a;--cyan:#31c7d8;--green:#17a673}
*{box-sizing:border-box}body{margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;color:var(--ink);background:radial-gradient(circle at 10% 0%,#fce7f3 0,transparent 27%),radial-gradient(circle at 95% 10%,#dffaff 0,transparent 26%),var(--bg)}
header{padding:30px 20px 18px;text-align:center}header .eyebrow{display:inline-block;padding:7px 12px;border-radius:99px;background:#eee8ff;color:#6240d7;font-size:12px;font-weight:800;letter-spacing:.08em;text-transform:uppercase}h1{font-size:clamp(28px,4vw,44px);line-height:1.08;margin:15px 0 10px;letter-spacing:-.04em}header p{color:var(--muted);max-width:700px;margin:0 auto;line-height:1.6}
main{width:min(1180px,calc(100% - 28px));margin:18px auto 50px;display:grid;gap:18px;grid-template-columns:1.05fr .95fr}
.card{background:rgba(255,255,255,.9);border:1px solid rgba(220,216,241,.9);border-radius:24px;padding:22px;box-shadow:0 12px 36px #35206b0b;min-width:0}.card h2{font-size:19px;margin:0 0 7px;letter-spacing:-.02em}.sub{font-size:13px;color:var(--muted);line-height:1.55;margin:0 0 18px}
label{display:block;font-size:13px;font-weight:750;margin:13px 0 7px}input,select,textarea{width:100%;border:1px solid #dedbed;background:#fff;border-radius:12px;padding:12px 13px;font:inherit;color:var(--ink);outline:none}input:focus,select:focus,textarea:focus{border-color:#9278f2;box-shadow:0 0 0 3px #9278f21c}input[type=file]{padding:10px}input[type=color]{height:46px;padding:5px}
.row{display:grid;grid-template-columns:1fr 1fr;gap:12px}.btn{display:inline-flex;justify-content:center;align-items:center;gap:8px;border:0;border-radius:12px;padding:12px 15px;font:inherit;font-weight:800;cursor:pointer;text-decoration:none;transition:.15s}.btn:hover{transform:translateY(-1px)}.primary{color:white;background:linear-gradient(110deg,var(--purple),#a34de0 60%,var(--pink));box-shadow:0 8px 18px #8156e52b}.secondary{background:#f0edff;color:#5f43cf}.ghost{background:#f7f6fb;color:#585672;border:1px solid var(--line)}.btn:disabled{opacity:.45;cursor:not-allowed;transform:none}.actions{display:flex;flex-wrap:wrap;gap:9px;margin-top:16px}
.notice{background:#fff7e7;border:1px solid #ffe1a7;color:#75510b;padding:12px 14px;border-radius:13px;font-size:12px;line-height:1.5;margin-top:14px}.notice strong{display:block;margin-bottom:3px}.content-list{display:grid;gap:10px;margin-top:15px}.content-item{display:flex;align-items:center;gap:12px;padding:12px;border:1px solid var(--line);border-radius:15px;background:#fff}.file-icon{width:42px;height:42px;flex:none;display:grid;place-items:center;border-radius:13px;background:linear-gradient(135deg,#ffe3ee,#e9e4ff);font-size:21px}.item-meta{flex:1;min-width:0}.item-meta strong{display:block;overflow-wrap:anywhere;font-size:13px}.item-meta small{display:block;color:var(--muted);margin-top:3px}.item-actions{display:flex;gap:6px;flex-wrap:wrap}.item-actions button{border:0;background:#f1effa;color:#5d4ba7;border-radius:9px;padding:7px 9px;cursor:pointer;font-weight:700;font-size:12px}
.qr-grid{display:grid;grid-template-columns:1fr 1fr;gap:13px}.qr-card{border:1px solid var(--line);border-radius:18px;padding:15px;text-align:center;overflow:hidden;background:linear-gradient(145deg,#fff,#fbfaff)}.qr-card h3{font-size:15px;margin:4px 0}.qr-card p{font-size:12px;color:var(--muted);line-height:1.45;min-height:35px;margin:5px 0 12px}.qr-wrap{width:min(100%,210px);aspect-ratio:1;margin:0 auto 12px;display:grid;place-items:center;background:#fff;border-radius:20px;padding:9px;box-shadow:inset 0 0 0 1px #eeeaf9}.qr-wrap canvas,.qr-wrap img{max-width:100%;height:auto!important;border-radius:10px}.qr-label{display:inline-block;font-size:10px;font-weight:900;letter-spacing:.1em;text-transform:uppercase;padding:5px 8px;border-radius:99px;background:#f1eaff;color:#6b47d6}.qr-card.payment .qr-label{background:#ffe8f1;color:#bf346c}.upi{font-size:12px;overflow-wrap:anywhere;background:#f7f5ff;padding:8px;border-radius:9px;margin-top:8px}
.preview{border:1px dashed #d9d2f4;border-radius:15px;padding:14px;background:#fcfbff;font-size:13px;color:var(--muted);line-height:1.6}.preview strong{color:var(--ink)}.full{grid-column:1/-1}.footer{text-align:center;color:var(--muted);font-size:12px;padding:0 20px 28px}
.status{font-size:12px;font-weight:750;margin-top:10px;color:var(--green);min-height:17px}.small{font-size:11px;color:var(--muted);line-height:1.5}
@media(max-width:850px){main{grid-template-columns:1fr}.full{grid-column:auto}}@media(max-width:480px){.card{padding:16px}.row,.qr-grid{grid-template-columns:1fr}.qr-card p{min-height:0}.item-actions{flex-direction:column}}
</style>
</head>
<body>
<header>
  <span class="eyebrow">✦ Your digital content storefront</span>
  <h1>PDF Vault <span style="background:linear-gradient(100deg,#6c43e8,#ff5c9a);color:transparent;background-clip:text">Studio</span></h1>
  <p>Organize PDF resources, share a content link, and create colorful QR codes for your library and UPI payments.</p>
</header>
<main>
  <section class="card">
    <h2>📚 Content drawer</h2>
    <p class="sub">Add PDF files or paste a Google Drive/share link. Items are shown in this browser demo; publish with a backend for a shared, unlimited-access library.</p>
    <label for="pdfFile">Upload a PDF</label>
    <input id="pdfFile" type="file" accept="application/pdf,.pdf">
    <div class="row">
      <div><label for="contentTitle">Content title</label><input id="contentTitle" placeholder="e.g. Study notes – Chapter 1"></div>
      <div><label for="contentPrice">Price (INR)</label><input id="contentPrice" type="number" min="0" step="1" value="99"></div>
    </div>
    <label for="contentUrl">PDF / Google Drive link</label>
    <input id="contentUrl" type="url" placeholder="https://drive.google.com/...">
    <div class="actions">
      <button class="btn primary" id="addContent">＋ Add to content drawer</button>
      <button class="btn ghost" id="clearForm" type="button">Clear fields</button>
    </div>
    <div id="contentList" class="content-list"><div class="preview">No content added yet. Upload a PDF or paste a share link to get started.</div></div>
    <div class="notice"><strong>🔐 About access</strong>This front-end demo stores the list only in this page session. For a public library, store content in cloud storage/database and control private PDF access on a server. A public Drive link is accessible to anyone who has the link.</div>
  </section>

  <section class="card">
    <h2>🎨 QR code generator</h2>
    <p class="sub">Create two separate QR codes: one for your content link and one to open a UPI payment app. Rounded styling and colors are supported; keep strong contrast for reliable scanning.</p>
    <label for="upiId">UPI ID</label><input id="upiId" value="adey6547@axl" autocomplete="off">
    <div class="row">
      <div><label for="qrColor">QR color</label><input id="qrColor" type="color" value="#623de3"></div>
      <div><label for="qrBg">Background</label><input id="qrBg" type="color" value="#ffffff"></div>
    </div>
    <label for="upiName">Payee name (optional)</label><input id="upiName" placeholder="Your store name">
    <label for="paymentAmount">Payment amount (INR)</label><input id="paymentAmount" type="number" min="1" step="1" value="99">
    <label for="paymentNote">Payment note</label><input id="paymentNote" value="PDF content purchase">
    <div class="qr-grid" style="margin-top:17px">
      <div class="qr-card">
        <span class="qr-label">Content access</span><h3>Scan for content</h3>
        <p>Opens the selected Google Drive or PDF link.</p>
        <div class="qr-wrap" id="contentQr"><span class="small">Add a content link to generate QR</span></div>
        <button class="btn secondary" id="downloadContentQr" disabled>Download PNG</button>
      </div>
      <div class="qr-card payment">
        <span class="qr-label">UPI payment</span><h3>Scan to pay</h3>
        <p>Opens a UPI app with your ID and amount prefilled.</p>
        <div class="qr-wrap" id="paymentQr"></div>
        <div class="upi" id="upiText">adey6547@axl</div>
        <button class="btn secondary" id="downloadPaymentQr">Download PNG</button>
      </div>
    </div>
    <div class="actions"><button class="btn primary" id="refreshQr">↻ Refresh QR codes</button><button class="btn ghost" id="copyUpi">Copy UPI ID</button></div>
    <div class="status" id="status"></div>
    <div class="notice"><strong>⚠️ Payment confirmation is not automatic</strong>A UPI QR only starts a payment. This demo cannot verify whether money arrived. Never release paid content based only on a screenshot or a customer clicking “paid”; verify payment server-side through a payment provider/webhook.</div>
  </section>

  <section class="card full">
    <h2>✉️ Customer delivery workflow</h2>
    <p class="sub">The intended production flow is: customer chooses a PDF → pays through a gateway/UPI → server verifies the transaction → server emails a PDF or secure download link to the customer.</p>
    <div class="row">
      <div><label for="customerEmail">Customer email (demo field)</label><input id="customerEmail" type="email" placeholder="customer@example.com"></div>
      <div><label for="customerItem">Selected content</label><select id="customerItem"><option value="">Choose content</option></select></div>
    </div>
    <div class="actions"><button class="btn primary" id="demoDelivery">Preview delivery email</button></div>
    <div id="deliveryPreview" class="preview" style="margin-top:13px">No email preview yet.</div>
    <p class="small" style="margin-top:12px">This button only previews the email text in your browser. Real email delivery requires a server-side email service (for example, an SMTP provider) and a verified payment webhook. Do not put secret API keys in browser JavaScript.</p>
  </section>
</main>
<div class="footer">PDF Vault Studio • Front-end starter template • No payment is processed or verified by this demo.</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script>
const $ = id => document.getElementById(id);
const items = [];
let selectedContentUrl = '';
function safeUrl(value){
  try { const u = new URL(value); return ['https:','http:'].includes(u.protocol) ? u.href : ''; } catch { return ''; }
}
function upiUrl(){
  const id = $('upiId').value.trim() || 'adey6547@axl';
  const amount = Number($('paymentAmount').value || 0);
  const params = new URLSearchParams({pa:id, cu:'INR', tn:$('paymentNote').value.trim() || 'PDF content purchase'});
  const name = $('upiName').value.trim(); if(name) params.set('pn',name);
  if(amount > 0) params.set('am',amount.toFixed(2));
  return 'upi://pay?' + params.toString();
}
function renderQr(target, value){
  $(target).innerHTML = '';
  if(!value){ $(target).innerHTML = '<span class="small">Add a valid content link to generate QR</span>'; return; }
  if(!window.QRCode){ $(target).textContent = 'QR library failed to load. Check your internet connection.'; return; }
  const color = $('qrColor').value, bg = $('qrBg').value;
  new QRCode($(target), {text:value,width:190,height:190,colorDark:color,colorLight:bg,correctLevel:QRCode.CorrectLevel.H});
}
function refreshQrs(){
  const contentUrl = safeUrl(selectedContentUrl || $('contentUrl').value.trim());
  renderQr('contentQr', contentUrl);
  renderQr('paymentQr', upiUrl());
  $('upiText').textContent = $('upiId').value.trim() || 'adey6547@axl';
  $('downloadContentQr').disabled = !contentUrl;
  $('status').textContent = contentUrl ? 'QR codes updated.' : 'Payment QR ready. Add a valid content URL for the content QR.';
}
function getQrCanvas(id){
  const box = $(id); return box.querySelector('canvas') || box.querySelector('img');
}
function downloadQr(id, name){
  const el = getQrCanvas(id); if(!el){ $('status').textContent='No QR code available to download.'; return; }
  const canvas = document.createElement('canvas'); canvas.width=el.width||190; canvas.height=el.height||190;
  const ctx=canvas.getContext('2d');
  if(el.tagName==='IMG'){const im=new Image();im.onload=()=>{ctx.drawImage(im,0,0,canvas.width,canvas.height);save();};im.src=el.src;}
  else {ctx.drawImage(el,0,0);save();}
  function save(){const a=document.createElement('a');a.download=name;a.href=canvas.toDataURL('image/png');a.click();}
}
function renderItems(){
  const list=$('contentList'); list.innerHTML='';
  $('customerItem').innerHTML='<option value="">Choose content</option>';
  if(!items.length){list.innerHTML='<div class="preview">No content added yet. Upload a PDF or paste a share link to get started.</div>';return;}
  items.forEach((item,index)=>{
    const node=document.createElement('div');node.className='content-item';
    const icon=document.createElement('div');icon.className='file-icon';icon.textContent='📄';
    const meta=document.createElement('div');meta.className='item-meta';
    const strong=document.createElement('strong');strong.textContent=item.title;
    const small=document.createElement('small');small.textContent=(item.file?'Uploaded PDF • local preview only':'Link content')+' • ₹'+item.price;
    meta.append(strong,small);
    const actions=document.createElement('div');actions.className='item-actions';
    const use=document.createElement('button');use.textContent='Use for QR';use.onclick=()=>{selectedContentUrl=item.url;$('contentUrl').value=item.url; $('contentTitle').value=item.title; $('contentPrice').value=item.price; $('paymentAmount').value=item.price;refreshQrs();};
    const open=document.createElement('button');open.textContent='Open';open.disabled=!item.url;open.onclick=()=>window.open(item.url,'_blank','noopener,noreferrer');
    actions.append(use,open);node.append(icon,meta,actions);list.append(node);
    const opt=document.createElement('option');opt.value=String(index);opt.textContent=item.title;$('customerItem').append(opt);
  });
}
$('addContent').addEventListener('click',()=>{
  const file=$('pdfFile').files[0], title=$('contentTitle').value.trim()||(file?file.name:'');
  let url=safeUrl($('contentUrl').value.trim());
  if(file && file.type!=='application/pdf' && !file.name.toLowerCase().endsWith('.pdf')){alert('Please choose a PDF file.');return;}
  if(!title){alert('Enter a title or choose a PDF.');return;}
  if(!file && !url){alert('Choose a PDF or enter a valid HTTPS/HTTP link.');return;}
  if(file && !url){url=URL.createObjectURL(file);}
  const price=Math.max(0,Number($('contentPrice').value||0));
  items.push({title,url,price,file:!!file});
  selectedContentUrl=url;
  renderItems();refreshQrs();
  $('status').textContent='Content added to this page session.';
});
$('clearForm').addEventListener('click',()=>{['pdfFile','contentTitle','contentUrl'].forEach(id=>$(id).value='');});
$('refreshQr').addEventListener('click',refreshQrs);
['upiId','upiName','paymentAmount','paymentNote','qrColor','qrBg','contentUrl'].forEach(id=>$(id).addEventListener('input',()=>{if(id==='contentUrl') selectedContentUrl='';refreshQrs();}));
$('downloadContentQr').addEventListener('click',()=>downloadQr('contentQr','content-qr.png'));
$('downloadPaymentQr').addEventListener('click',()=>downloadQr('paymentQr','upi-payment-qr.png'));
$('copyUpi').addEventListener('click',async()=>{try{await navigator.clipboard.writeText($('upiId').value.trim()||'adey6547@axl');$('status').textContent='UPI ID copied.';}catch{$('status').textContent='Copy not available in this browser; select the UPI ID manually.';}});
$('demoDelivery').addEventListener('click',()=>{
  const email=$('customerEmail').value.trim(), idx=$('customerItem').value;
  if(!email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){alert('Enter a valid customer email address.');return;}
  if(idx===''){alert('Choose a content item.');return;}
  const item=items[Number(idx)];
  $('deliveryPreview').innerHTML='';
  const heading=document.createElement('strong');heading.textContent='Subject: Your PDF content is ready';
  const body=document.createElement('p');body.textContent=`Hello! Thanks for your purchase. Your selected content is “${item.title}”. In the live system, this email is sent only after payment is verified.`;
  const link=document.createElement('p');
  if(item.url){const a=document.createElement('a');a.href=item.url;a.target='_blank';a.rel='noopener noreferrer';a.textContent='Open content link';link.append(a);}else link.textContent='A secure download link would appear here.';
  const note=document.createElement('small');note.textContent=`To: ${email} • Demo preview only — no email was sent and no payment was verified.`;
  $('deliveryPreview').append(heading,body,link,note);
});
refreshQrs();
</script>
</body>
</html>
