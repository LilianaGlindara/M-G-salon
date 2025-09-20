<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>M&G's Salon</title>
<style>
:root{
  --violet:#7c3aed;
  --violet-dark:#5b21b6;
  --orchid:#da70d6;
  --lav:#f6f0ff;
  --rose:#fff0f5;
  --ink:#2d1b4e;
  --ash:#a9a9a9;
  --green:#22c55e;
}
*{box-sizing:border-box}
body{
  margin:0;
  font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;
  background:var(--rose);
  color:var(--ink);
}
/* NAV */
nav{
  position:sticky;
  top:0;
  z-index:5;
  display:flex;
  gap:10px;
  justify-content:center;
  align-items:center;
  background:linear-gradient(180deg,var(--orchid),#c77bdc);
  padding:14px 10px;
  box-shadow:0 6px 16px rgba(0,0,0,.08);
}
.btn{
  background:var(--violet);
  color:#fff;
  border:none;
  font-weight:700;
  padding:10px 16px;
  border-radius:12px;
  cursor:pointer;
  transition:.2s transform,.2s background-color;
}
.btn:hover{background:var(--violet-dark); transform:translateY(-1px)}
.btn.ghost{background:#fff;color:var(--violet); border:2px solid var(--violet)}
main{max-width:1100px; margin:0 auto; padding:22px}
section{display:none}
section.active{display:block}
h1,h2{color:var(--violet); text-align:center; margin:10px 0 12px}
p.lead{font-size:1.05rem; line-height:1.65}
/* CARDS & GRID */
.grid{display:grid; gap:20px}
@media(min-width:720px){
  .grid.cols-3{grid-template-columns:repeat(3,1fr)}
  .grid.cols-2{grid-template-columns:repeat(2,1fr)}
}
.card{
  background:#fff;
  border-radius:16px;
  padding:16px;
  box-shadow:0 10px 26px rgba(124,58,237,.12);
}
.service-card img{
  width:100%;
  height:160px;
  object-fit:cover;
  border-radius:12px;
}
.price-chip{
  display:inline-flex;
  align-items:center;
  gap:8px;
  background:var(--violet);
  color:#fff;
  padding:8px 12px;
  border-radius:999px;
  font-weight:700;
  cursor:pointer;
  border:none;
}
.inline-panel{
  margin-top:10px;
  border:1.5px dashed var(--violet);
  border-radius:12px;
  padding:12px;
  background:var(--lav);
}
.confirm-btn{
  background:var(--violet);
  color:#fff;
  border:none;
  border-radius:10px;
  padding:8px 12px;
  font-weight:700;
  cursor:pointer;
}
.confirm-btn.ordered{ background:var(--green) }
.note{font-size:.9rem; color:#5e4a7f}
/* ORDER LIST */
.order-item{
  display:flex;
  align-items:center;
  gap:12px;
  padding:10px;
  border-radius:12px;
  background:#fff;
  box-shadow:0 6px 16px rgba(0,0,0,.06);
}
.order-item img{width:68px; height:68px; border-radius:10px; object-fit:cover}
.remove{background:#fff; border:2px solid #ef4444; color:#ef4444; padding:6px 10px; border-radius:10px; font-weight:700; cursor:pointer}
.stack{display:flex; flex-direction:column; gap:10px}
.chips{display:flex; flex-wrap:wrap; gap:8px}
.chip{ background:var(--lav); border:1px solid var(--violet); color:var(--violet); padding:6px 10px; border-radius:999px; font-weight:600; font-size:.9rem; }
/* CHECKOUT */
.checkout{ display:grid; gap:14px; max-width:520px; margin:14px auto 0; }
.field{display:flex; flex-direction:column; gap:6px}
input[type="text"],input[type="email"],input[type="number"],input[type="date"],input[type="time"]{ padding:10px 12px; border-radius:10px; border:1.5px solid #d7c9ff; outline:none; }
.status{margin-top:8px; font-weight:700}
.status.ok{color:var(--green)}
.status.warn{color:#eab308}
.status.err{color:#ef4444}
/* CALENDAR */
.calendar{
  display:grid;
  grid-template-columns:repeat(7,1fr);
  gap:8px;
}
.day{
  background:#fff;
  border-radius:10px;
  padding:10px;
  text-align:center;
  cursor:pointer;
  font-weight:700;
  border:1px solid #e7defa;
}
.day.selected{outline:3px solid var(--violet)}
.slots{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  margin-top:10px;
}
.slot{
  background:var(--violet);
  color:#fff;
  border:none;
  border-radius:10px;
  padding:6px 10px;
  cursor:pointer;
  font-weight:700;
}
.slot.booked{background:var(--ash); cursor:pointer}
/* AUTH */
.captcha{display:flex; align-items:center; gap:8px}
.center{text-align:center}
.muted{color:#6b7280; font-size:.9rem;}
</style>
</head>
<body>
<nav>
  <button class="btn" onclick="show('home')">Home</button>
  <button class="btn" onclick="show('about')">About Us</button>
  <button class="btn" onclick="show('offer')">What We Offer</button>
  <button class="btn" onclick="show('order')">Your Order</button>
  <button class="btn ghost" onclick="show('signup')">Signup</button>
</nav>
<main>
<!-- HOME -->
<section id="home" class="active">
<h1>M&G's Salon</h1>
<div class="card">
<p class="lead">Welcome to M&G's Salon. Our salon offers a variety of services including haircuts, styling, coloring, and treatments. Our experienced stylists are dedicated to providing you with the best service and ensuring you leave our salon feeling confident and beautiful.Step into a world where beauty meets relaxation. At M&G's salon, we believe self-care is more than a service—it’s an experience. From the moment you walk through our doors, you’ll be greeted with a calming atmosphere, personalized attention, and treatments designed to bring out your natural glow. Whether you’re here for a fresh new look, a touch of pampering, or a complete transformation, our expert team is dedicated to making you feel confident, radiant, and refreshed. Because when you look good, you feel unstoppable. Our services are designed for everyone — women, men, and anyone who wants to look and feel their best.</p>
</div>
</section>
<!-- ABOUT -->
<section id="about">
<h2>About M&G's Salon</h2>
<div class="card">
<p class="lead">At M&G's Salon, we are passionate about beauty, style, and self-care. Our journey began with a dream to create a space where everyone could feel pampered, confident, and radiant. With a team of experienced stylists and a commitment to personalized service, we ensure each visit is a luxurious and unforgettable experience. Your comfort, satisfaction, and glow are our top priorities. Step into M&G's Salon and discover the perfect blend of relaxation and transformation. </p>
</div>
</section>
<!-- WHAT WE OFFER -->
<section id="offer">
<h2>What We Offer</h2>
<div class="grid cols-3">
  <!-- Hair -->
  <div class="card service-card" data-service="Hair Care">
    <img src="https://images.pexels.com/photos/4056523/pexels-photo-4056523.jpeg" alt="Hair Care"/>
    <h3>Hair Care</h3>
    <p class="note">Snip, style & shine — expert pampering for your locks.</p>
    <button class="price-chip" onclick="openConfirm(this)">£5 • Add</button>
    <div class="inline-panel" hidden>
      <div class="stack">
        <div class="note">Confirm Hair Care for £5?</div>
        <div><button class="confirm-btn" onclick="toggleOrder(this)">Confirm</button></div>
        <div class="status" data-status></div>
      </div>
    </div>
  </div>
  <!-- Nails -->
  <div class="card service-card" data-service="Nail Care">
    <img src="https://images.pexels.com/photos/3765115/pexels-photo-3765115.jpeg" alt="Nail Care"/>
    <h3>Nail Care</h3>
    <p class="note">Polish, pamper & perfect — mani-pedi bliss.</p>
    <button class="price-chip" onclick="openConfirm(this)">£5 • Add</button>
    <div class="inline-panel" hidden>
      <div class="stack">
        <div class="note">Confirm Nail Care for £5?</div>
        <div><button class="confirm-btn" onclick="toggleOrder(this)">Confirm</button></div>
        <div class="status" data-status></div>
      </div>
    </div>
  </div>
  <!-- Foot -->
  <div class="card service-card" data-service="Foot Care">
    <img src="https://images.pexels.com/photos/4087792/pexels-photo-4087792.jpeg" alt="Foot Care"/>
    <h3>Foot Care</h3>
    <p class="note">Soothe & refresh — soft steps start here.</p>
    <button class="price-chip" onclick="openConfirm(this)">£5 • Add</button>
    <div class="inline-panel" hidden>
      <div class="stack">
        <div class="note">Confirm Foot Care for £5?</div>
        <div><button class="confirm-btn" onclick="toggleOrder(this)">Confirm</button></div>
        <div class="status" data-status></div>
      </div>
    </div>
  </div>
  <!-- Face -->
  <div class="card service-card" data-service="Face Care">
    <img src="https://images.pexels.com/photos/3765021/pexels-photo-3765021.jpeg" alt="Face Care"/>
    <h3>Face Care</h3>
    <p class="note">Personalized facials for that glow.</p>
    <button class="price-chip" onclick="openConfirm(this)">£5 • Add</button>
    <div class="inline-panel" hidden>
      <div class="stack">
        <div class="note">Confirm Face Care for £5?</div>
        <div><button class="confirm-btn" onclick="toggleOrder(this)">Confirm</button></div>
        <div class="status" data-status></div>
      </div>
    </div>
  </div>
  <!-- Body -->
  <div class="card service-card" data-service="Body Care">
    <img src="https://images.pexels.com/photos/4056527/pexels-photo-4056527.jpeg" alt="Body Care"/>
    <h3>Body Care</h3>
    <p class="note">Rejuvenate & relax from head to toe.</p>
    <button class="price-chip" onclick="openConfirm(this)">£5 • Add</button>
    <div class="inline-panel" hidden>
      <div class="stack">
        <div class="note">Confirm Body Care for £5?</div>
        <div><button class="confirm-btn" onclick="toggleOrder(this)">Confirm</button></div>
        <div class="status" data-status></div>
      </div>
    </div>
  </div>
</div>
<p class="center muted" id="add-msg"></p>
</section>
<!-- YOUR ORDER -->
<section id="order">
<h2>Your Order</h2>
<div class="grid cols-2" id="order-list"></div>
<div class="card">
<h3>Discounts</h3>
<div class="stack">
<div class="field">
  <label for="disc">Enter discount code</label>
  <input id="disc" type="text" placeholder="e.g., SALON10, SALONYAY"/>
</div>
<button class="btn" onclick="applyDiscount()">Apply Code</button>
<div class="chips" id="codes"></div>
<div class="status" id="disc-status"></div>
</div>
</div>
<div class="card checkout">
<h3 class="center">Checkout</h3>
<div class="field">
<label>Card Number</label>
<input id="card-number" type="text" inputmode="numeric" placeholder="1234 5678 9012 3456"/>
</div>
<div class="grid cols-2">
<div class="field">
<label>Expiry</label>
<input id="card-exp" type="text" placeholder="MM/YY"/>
</div>
<div class="field">
<label>CVV</label>
<input id="card-cvv" type="text" inputmode="numeric" placeholder="123"/>
</div>
</div>
<button class="btn" onclick="simulatePay()">Scan Card</button>
<div class="status" id="pay-status"></div>
<div id="total" class="center" style="font-weight:800; margin-top:6px;"></div>
</div>
<div id="booking" class="card" style="display:none;">
<h3>Choose Your Date & Time</h3>
<p class="muted">Pick a date, then select an available slot. Booked slots are ash (grey) but can be clicked again to unbook.</p>
<div class="calendar" id="calendar"></div>
<div class="slots" id="slots"></div>
<div class="status ok" id="book-status"></div>
</div>
</section>
<!-- SIGNUP -->
<section id="signup">
<h2>Create your account</h2>
<div class="card">
<div class="grid cols-2">
<div class="field">
<label>Email</label>
<input id="email" type="email" placeholder="you@example.com"/>
</div>
<div class="field">
<label>&nbsp;</label>
<button class="btn" onclick="sendCode()">Send 6-digit Code</button>
</div>
</div>
<div class="status" id="send-status"></div>
<p class="muted">For the prototype, the code will appear below so you can test verification.</p>
<div class="chip" id="show-code" style="display:none;"></div>
</div>
<div class="card" style="margin-top:16px;">
<h3>Verify</h3>
<div class="grid cols-2">
<div class="field">
<label>6-digit Code</label>
<input id="code" type="text" inputmode="numeric" placeholder="••••••"/>
</div>
<div class="field captcha">
<input id="not-robot" type="checkbox"/><span>I am not a robot</span>
</div>
</div>
<button class="btn" onclick="verify()">Verify</button>
<div class="status" id="verify-status"></div>
</div>
</section>
</main>
<script>
/* ======= STATE ======= */
const SERVICES = [
  {name:'Hair Care', img:'https://images.pexels.com/photos/4056523/pexels-photo-4056523.jpeg'},
  {name:'Nail Care', img:'https://images.pexels.com/photos/3765115/pexels-photo-3765115.jpeg'},
  {name:'Foot Care', img:'https://images.pexels.com/photos/4087792/pexels-photo-4087792.jpeg'},
  {name:'Face Care', img:'https://images.pexels.com/photos/3765021/pexels-photo-3765021.jpeg'},
  {name:'Body Care', img:'https://images.pexels.com/photos/4056527/pexels-photo-4056527.jpeg'},
];
let order = [];
let codes = [];
let payComplete = false;
let selectedDate = null;
let booked = JSON.parse(localStorage.getItem('booked')||'{}');
let orderCount = parseInt(localStorage.getItem('orderCount')||'0');

/* ======= NAV ======= */
function show(id){
  document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  if(id==='order'){ renderOrder(); updateTotals(); }
}

/* ======= OFFER INTERACTIONS ======= */
function openConfirm(btn){ btn.nextElementSibling.hidden = !btn.nextElementSibling.hidden; }
function toggleOrder(el){
  const card = el.closest('.service-card');
  const name = card.dataset.service;
  const status = card.querySelector('[data-status]');
  if(!el.classList.contains('ordered')){
    if(!order.includes(name)) order.push(name);
    el.classList.add('ordered'); el.textContent='Ordered';
    status.className='status ok'; status.textContent = `${name} added to your order.`;
  }else{
    order = order.filter(n=>n!==name);
    el.classList.remove('ordered'); el.textContent='Confirm';
    status.className='status warn'; status.textContent = `${name} removed from your order.`;
  }
  renderOrder(); updateTotals();
}

/* ======= ORDER RENDER ======= */
function renderOrder(){
  const wrap = document.getElementById('order-list');
  wrap.innerHTML='';
  if(order.length===0){
    wrap.innerHTML=`<div class="card"><p class="center muted">No services yet. Add from “What We Offer”.</p></div>`;
    return;
  }
  order.forEach(n=>{
    const svc = SERVICES.find(s=>s.name===n);
    wrap.insertAdjacentHTML('beforeend', `<div class="order-item">
      <img src="${svc.img}" alt="${n}"/>
      <div style="flex:1;"><div style="font-weight:800">${n}</div><div class="muted">Price: £5</div></div>
      <button class="remove" onclick="removeItem('${n}')">Remove</button>
    </div>`);
  });
}
function removeItem(n){
  order = order.filter(x=>x!==n);
  document.querySelectorAll('.service-card').forEach(c=>{
    if(c.dataset.service===n){
      const btn = c.querySelector('.confirm-btn');
      const status = c.querySelector('[data-status]');
      btn.classList.remove('ordered');
      btn.textContent='Confirm';
      status.className='status warn';
      status.textContent = `${n} removed from your order.`;
    }
  });
  renderOrder(); updateTotals();
}

/* ======= DISCOUNTS ======= */
function applyDiscount(){
  const input = document.getElementById('disc');
  const code = (input.value||'').trim().toUpperCase();
  const status = document.getElementById('disc-status');
  if(!code){ status.className='status err'; status.textContent='Please type a code.'; return; }
  if(!codes.includes(code)) codes.push(code); input.value='';
  renderCodes();
  const {valid,reason} = validateCodes();
  status.className = 'status ' + (valid.length? 'ok':'warn');
  status.textContent = valid.length ? `Applied: ${valid.join(', ')}` : (reason || 'No valid codes right now.');
  updateTotals();
}
function renderCodes(){
  const box = document.getElementById('codes'); box.innerHTML='';
  codes.forEach(c=>{
    const span = document.createElement('span'); span.className='chip'; span.textContent=c; box.appendChild(span);
  });
}
function validateCodes(){
  let valid=[]; let reason='';
  const hasAllFive = SERVICES.every(s=>order.includes(s.name));
  const possible = new Set(codes);
  if(possible.has('SALONYAY')){ if(hasAllFive) valid.push('SALONYAY'); else reason='SALONYAY needs all five services.'; }
  if(possible.has('SALON0')){ if(orderCount>=10) valid.push('SALON0'); else reason='SALON0 unlocks on your 10th order.'; }
  if(possible.has('SALON20')) valid.push('SALON20');
  if(possible.has('SALON10')) valid.push('SALON10');
  const ranking = {SALONYAY:50, SALON0:30, SALON20:20, SALON10:10};
  valid.sort((a,b)=> (ranking[b]||0)-(ranking[a]||0));
  return {valid, reason};
}
function currentDiscountPercent(){ const {valid} = validateCodes(); if(!valid.length) return 0; const top=valid[0]; return ({SALONYAY:50,SALON0:30,SALON20:20,SALON10:10}[top]||0); }

/* ======= TOTALS + CHECKOUT ======= */
function updateTotals(){
  const totalEl=document.getElementById('total');
  const count=order.length;
  let subtotal=count*5;
  const pct=currentDiscountPercent();
  const discount=+(subtotal*(pct/100)).toFixed(2);
  const total=+(subtotal-discount).toFixed(2);
  totalEl.textContent=`Items: ${count} • Subtotal £${subtotal.toFixed(2)} • Discount ${pct}% (£${discount.toFixed(2)}) • Total £${total.toFixed(2)}`;
}
function simulatePay(){
  const num=document.getElementById('card-number').value.trim();
  const exp=document.getElementById('card-exp').value.trim();
  const cvv=document.getElementById('card-cvv').value.trim();
  const status=document.getElementById('pay-status');
  if(order.length===0){ status.className='status warn'; status.textContent='Add at least one service before checkout.'; return; }
  if(num.length<12||!/\d/.test(num)){ status.className='status err'; status.textContent='Please enter a valid card number (simulated).'; return; }
  if(!/^\d{2}\/\d{2}$/.test(exp)){ status.className='status err'; status.textContent='Use MM/YY for expiry (simulated).'; return; }
  if(cvv.length<3){ status.className='status err'; status.textContent='Please enter a valid CVV (simulated).'; return; }
  payComplete=true;
  status.className='status ok';
  status.textContent='Payment simulated ✓ — choose your appointment below.';
  document.getElementById('booking').style.display='block';
  buildCalendar();
}

/* ======= CALENDAR & BOOKING ======= */
function buildCalendar(){
  const cal=document.getElementById('calendar'); const slots=document.getElementById('slots');
  cal.innerHTML=''; slots.innerHTML='';
  const base=new Date(); base.setHours(0,0,0,0);
  for(let i=0;i<28;i++){
    const d=new Date(base); d.setDate(base.getDate()+i);
    const iso=d.toISOString().slice(0,10);
    const div=document.createElement('div');
    div.className='day'; div.textContent=d.getDate(); div.title=iso;
    div.onclick=()=>{ selectedDate=iso; document.querySelectorAll('.day').forEach(x=>x.classList.remove('selected')); div.classList.add('selected'); renderSlots(); };
    cal.appendChild(div);
  }
}

function renderSlots(){
  const wrap=document.getElementById('slots'); const msg=document.getElementById('book-status');
  wrap.innerHTML=''; msg.textContent='';
  if(!selectedDate){ msg.className='status warn'; msg.textContent='Pick a date to see available times.'; return; }
  const taken=booked[selectedDate]||[];
  for(let h=9;h<=17;h++){
    const btn=document.createElement('button');
    btn.className='slot'+(taken.includes(h)?' booked':''); btn.textContent=`${h}:00`;
    btn.onclick=()=>toggleSlot(h);
    wrap.appendChild(btn);
  }
}

function toggleSlot(hour){
  if(!payComplete){ document.getElementById('book-status').className='status warn'; document.getElementById('book-status').textContent='Please complete checkout first.'; return; }
  booked[selectedDate] = booked[selectedDate]||[];
  const idx=booked[selectedDate].indexOf(hour);
  if(idx===-1){
    // Book
    booked[selectedDate].push(hour);
    document.getElementById('book-status').className='status ok';
    document.getElementById('book-status').textContent=`Booked ${selectedDate} at ${hour}:00 ✓`;
    // clear cart & payment
    order=[]; codes=[]; payComplete=false; renderOrder(); renderCodes(); updateTotals();
  }else{
    // Unbook
    booked[selectedDate].splice(idx,1);
    document.getElementById('book-status').className='status warn';
    document.getElementById('book-status').textContent=`Unbooked ${selectedDate} at ${hour}:00`;
  }
  localStorage.setItem('booked',JSON.stringify(booked));
  renderSlots();
}

/* ======= SIGNUP / VERIFY ======= */
function sendCode(){
  const email=document.getElementById('email').value.trim(); const status=document.getElementById('send-status');
  if(!email||!email.includes('@')){ status.className='status err'; status.textContent='Enter a valid email.'; return; }
  const code=String(Math.floor(100000+Math.random()*900000));
  localStorage.setItem('signupCode',code); status.className='status ok';
  status.textContent='Code sent (simulated). Use the code below to verify.';
  const show=document.getElementById('show-code'); show.style.display='inline-block'; show.textContent=`Your code: ${code}`;
  show('signup');
}
function verify(){
  const input=(document.getElementById('code').value||'').trim();
  const notRobot=document.getElementById('not-robot').checked;
  const real=localStorage.getItem('signupCode'); const status=document.getElementById('verify-status');
  if(!input){ status.className='status err'; status.textContent='Type your 6-digit code.'; return; }
  if(!notRobot){ status.className='status warn'; status.textContent='Please confirm you are not a robot.'; return; }
  if(input===real){ status.className='status ok'; status.textContent='Verified ✓ Welcome to M&G’s!'; }
  else{ status.className='status err'; status.textContent='Incorrect code. Try again.'; }
}

/* ======= INIT ======= */
renderOrder(); updateTotals();
</script>
</body>
</html>
