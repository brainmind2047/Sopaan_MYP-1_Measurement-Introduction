<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Measurement: Introduction</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,700&family=Source+Sans+3:wght@400;600;700&family=IBM+Plex+Mono:wght@500;600&display=swap">
<style>
  html,body{margin:0;} img{max-width:100%;} [hidden]{display:none !important;}
  :root{
    --navy:#16264A; --navy-2:#1F3B6B; --gold:#C79A3E; --gold-soft:#F3E7C9;
    --paper:#FBF9F4; --paper-2:#F1EAD8; --card:#FFFFFF;
    --ink:#211E1A; --ink-soft:#655D4C; --rule:#E4DCC8;
    --success:#2E8B57; --success-soft:#E1F2E7;
    --danger:#BF4B45; --danger-soft:#FAE3E1;
    --locked:#C7BEA9;
    --focus:#1F3B6B;
    --accent-text:#1F3B6B; --retry-text:#8A661F;
    color-scheme:light;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
      --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
      --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
      --success:#7BC79A; --success-soft:#1B2E22;
      --danger:#E38884; --danger-soft:#331D1B;
      --locked:#4A4436;
      --focus:#E0B75B;
      --accent-text:#E0B75B; --retry-text:#E0B75B;
      color-scheme:dark;
    }
  }
  :root[data-theme="dark"]{
    --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
    --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
    --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
    --success:#7BC79A; --success-soft:#1B2E22;
    --danger:#E38884; --danger-soft:#331D1B;
    --locked:#4A4436;
    --focus:#E0B75B;
    --accent-text:#E0B75B; --retry-text:#E0B75B;
    color-scheme:dark;
  }

  *{box-sizing:border-box;}
  body{background:var(--paper); color:var(--ink); font-family:'Source Sans 3',-apple-system,'Segoe UI',sans-serif; padding-inline:0; padding-block:0;}
  h1,h2,h3{font-family:'Fraunces',Georgia,serif; text-wrap:balance; margin:0;}
  .num{font-family:'IBM Plex Mono',ui-monospace,monospace; font-variant-numeric:tabular-nums;}

  header.brand{
    background:linear-gradient(155deg,var(--navy) 0%, var(--navy-2) 100%);
    color:#F4EFDF; padding-block:calc(20px + env(safe-area-inset-top,0px)) 18px; padding-inline:20px;
  }
  .brand-row{display:flex; align-items:center; gap:12px; max-width:900px; margin:0 auto;}
  .crest{
    width:42px; height:42px; border-radius:10px; background:var(--gold); color:var(--navy);
    display:flex; align-items:center; justify-content:center; font-family:'Fraunces',serif; font-weight:700; font-size:18px; flex-shrink:0;
  }
  .brand-name{font-size:12px; letter-spacing:.08em; text-transform:uppercase; color:var(--gold); font-weight:700;}
  .series-name{font-size:19px; font-weight:700; font-family:'Fraunces',serif;}
  .chapter-eyebrow{max-width:900px; margin:14px auto 0; font-size:12px; letter-spacing:.06em; text-transform:uppercase; color:#AEB9D6;}
  .chapter-title{font-size:28px; max-width:900px; margin:2px auto 0;}
  .chapter-sub{font-size:14.5px; color:var(--gold); font-weight:700; max-width:900px; margin:3px auto 0;}

  .chapter-progress{max-width:900px; margin:14px auto 0; display:flex; align-items:center; gap:10px;}
  .cp-track{flex:1; height:6px; border-radius:99px; background:rgba(255,255,255,.18); overflow:hidden;}
  .cp-fill{height:100%; background:var(--gold); border-radius:99px; transition:width .3s ease;}
  .cp-label{font-size:11.5px; color:#CFD7EA; white-space:nowrap;}

  .tabbar{position:sticky; top:env(safe-area-inset-top,0px); z-index:15; background:var(--paper); border-bottom:1px solid var(--rule); overflow-x:auto; white-space:nowrap;}
  .tabbar-inner{max-width:900px; margin:0 auto; display:flex; padding-inline:16px;}
  .tab-btn{font-family:inherit; font-size:14px; font-weight:600; color:var(--ink-soft); background:none; border:none; padding:13px 16px; cursor:pointer; position:relative; flex-shrink:0;}
  .tab-btn.active{color:var(--accent-text);}
  .tab-btn.active::after{content:''; position:absolute; left:12px; right:12px; bottom:0; height:3px; background:var(--gold); border-radius:3px 3px 0 0;}
  .tab-count{font-size:11px; color:var(--ink-soft); margin-left:5px;}

  .slide-progress{max-width:900px; margin:0 auto; padding:10px 16px 0; display:flex; align-items:center; gap:10px;}
  .sp-track{flex:1; height:5px; border-radius:99px; background:var(--rule); overflow:hidden;}
  .sp-fill{height:100%; background:var(--accent-text); border-radius:99px; transition:width .3s ease;}
  .sp-label{font-size:12px; color:var(--ink-soft); white-space:nowrap; font-weight:600;}

  .wrap{max-width:900px; margin:0 auto; padding:16px 16px calc(110px + env(safe-area-inset-bottom,0px));}

  .qcard{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px;}
  .qhead{display:flex; align-items:flex-start; gap:10px; margin-bottom:10px;}
  .qnum{width:32px; height:32px; border-radius:8px; background:var(--gold-soft); color:var(--accent-text); display:flex; align-items:center; justify-content:center; font-weight:700; font-family:'Fraunces',serif; flex-shrink:0; font-size:14px;}
  .qtext{font-size:16px; line-height:1.55; flex:1;}
  .qtag{font-size:10.5px; color:var(--gold); background:var(--gold-soft); padding:2px 7px; border-radius:99px; font-weight:700; margin-left:6px; white-space:nowrap;}
  .marks-pill{font-size:11px; font-weight:700; color:var(--ink-soft); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; margin-left:auto; flex-shrink:0; white-space:nowrap;}
  .step-badge{font-size:11px; font-weight:700; color:var(--accent-text); background:var(--paper-2); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; display:inline-block; margin-bottom:12px;}

  .options{display:flex; flex-direction:column; gap:8px; margin-top:10px;}
  .opt{display:flex; align-items:center; gap:10px; padding:11px 12px; border:1.5px solid var(--rule); border-radius:10px; cursor:pointer; font-size:15px; background:var(--paper);}
  .opt input{accent-color:var(--navy-2);}
  .opt.is-correct{border-color:var(--success); background:var(--success-soft);}
  .opt.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .opt.locked{cursor:not-allowed;}

  .subpart-label{font-weight:700; font-size:12.5px; color:var(--accent-text); text-transform:uppercase; letter-spacing:.03em; margin:14px 0 6px;}
  .or-divider{text-align:center; font-size:11px; font-weight:700; letter-spacing:.08em; color:var(--ink-soft); margin:8px 0;}

  .steps{display:flex; flex-direction:column; gap:10px;}
  .step-line{font-size:14.5px; line-height:1.9; background:var(--paper); border:1px dashed var(--rule); border-radius:10px; padding:9px 12px;}
  .step-line.resolved{opacity:.9;}
  .blank-input{font-family:'IBM Plex Mono',monospace; font-size:14px; border:1.5px solid var(--rule); border-radius:6px; padding:3px 8px; width:120px; background:var(--card); color:var(--ink); margin:0 2px;}
  .blank-input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .blank-input.is-correct{border-color:var(--success); background:var(--success-soft);}
  .blank-input.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .blank-input[disabled]{opacity:.85;}
  .reveal-note{font-size:12px; color:var(--danger); padding-left:2px; margin-top:-2px;}

  .feedback{font-size:13.5px; padding:10px 12px; border-radius:9px; margin-top:14px; display:none;}
  .feedback.show{display:block;}
  .feedback.ok{background:var(--success-soft); color:var(--success);}
  .feedback.retry{background:var(--gold-soft); color:var(--retry-text);}
  .feedback.reveal{background:var(--danger-soft); color:var(--danger);}
  .feedback.err{background:var(--danger-soft); color:var(--danger);}
  .attempts-dots{display:inline-flex; gap:4px; margin-left:2px;}
  .attempts-dots span{width:6px; height:6px; border-radius:50%; background:var(--ink-soft); opacity:.3; display:inline-block;}
  .attempts-dots span.used{opacity:1; background:var(--danger);}

  .ar-box{background:var(--paper-2); border-radius:10px; padding:10px 12px; margin-bottom:12px; font-size:13px; color:var(--ink-soft);}

  .navbar{
    position:fixed; left:0; right:0; bottom:0; z-index:30; background:var(--paper);
    border-top:1px solid var(--rule); padding:10px 16px calc(10px + env(safe-area-inset-bottom,0px));
  }
  .navbar-inner{max-width:900px; margin:0 auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center;}
  .btn{font-family:inherit; font-size:13.5px; font-weight:700; padding:10px 14px; border-radius:9px; border:1.5px solid var(--rule); background:var(--card); color:var(--ink); cursor:pointer;}
  .btn:hover{border-color:var(--navy-2);}
  .btn:disabled{opacity:.4; cursor:not-allowed;}
  .btn-primary{background:var(--navy-2); color:#fff; border-color:var(--navy-2);}
  .navbar .spacer{flex:1;}

  .fab{position:fixed; right:16px; bottom:calc(74px + env(safe-area-inset-bottom,0px)); background:var(--gold); color:var(--navy); border:none; border-radius:999px; padding:11px 16px; font-family:inherit; font-weight:700; font-size:13px; display:flex; align-items:center; gap:7px; cursor:pointer; box-shadow:0 6px 16px rgba(0,0,0,.18); z-index:35;}
  .fab-badge{background:rgba(255,255,255,.55); border-radius:99px; padding:1px 7px; font-size:11px;}

  .overlay{position:fixed; inset:0; background:rgba(20,18,14,.45); z-index:50; display:none; align-items:flex-end; justify-content:center;}
  .overlay.show{display:flex;}
  .palette{background:var(--card); width:min(480px,100%); max-height:78vh; overflow-y:auto; border-radius:18px 18px 0 0; padding:18px 18px calc(18px + env(safe-area-inset-bottom,0px)); border:1px solid var(--rule); border-bottom:none;}
  @media (min-width:640px){ .overlay{align-items:center;} .palette{border-radius:18px; border-bottom:1px solid var(--rule); max-height:74vh;} }
  .palette-head{display:flex; align-items:center; justify-content:space-between; margin-bottom:6px;}
  .palette-head h2{font-size:16px;}
  .palette-close{background:none; border:none; font-size:20px; color:var(--ink-soft); cursor:pointer; padding:4px;}
  .palette-legend{display:flex; gap:12px; flex-wrap:wrap; font-size:11px; color:var(--ink-soft); margin:10px 0 14px;}
  .palette-legend span{display:inline-flex; align-items:center; gap:5px;}
  .dot{width:9px; height:9px; border-radius:50%; display:inline-block;}
  .dot.correct{background:var(--success);} .dot.revealed{background:var(--danger);}
  .dot.skipped{background:var(--gold);} .dot.locked{background:var(--locked);}
  .dot.current{background:var(--navy-2);}
  .chip-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(48px,1fr)); gap:8px;}
  .chip{border:1.5px solid var(--rule); border-radius:9px; padding:8px 4px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:12.5px; font-weight:600; cursor:pointer; background:var(--paper); color:var(--ink);}
  .chip[data-status="correct"]{border-color:var(--success); background:var(--success-soft); color:var(--success);}
  .chip[data-status="revealed"]{border-color:var(--danger); background:var(--danger-soft); color:var(--danger);}
  .chip[data-status="skipped"]{border-color:var(--gold); background:var(--gold-soft); color:var(--retry-text);}
  .chip[data-status="locked"]{border-color:var(--rule); color:var(--locked); cursor:not-allowed; background:var(--paper-2);}
  .chip[data-status="current"]{outline:2px solid var(--navy-2); outline-offset:1px;}

  .toast{position:fixed; left:50%; bottom:calc(140px + env(safe-area-inset-bottom,0px)); transform:translateX(-50%); background:var(--ink); color:var(--paper); padding:9px 16px; border-radius:99px; font-size:13px; opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:60;}
  .toast.show{opacity:1;}

  .done-card{text-align:center; padding:36px 20px;}
  .done-card .big{font-size:38px; margin-bottom:6px;}
  .score-pills{display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin:16px 0;}
  .score-pill{padding:8px 16px; border-radius:99px; font-size:13px; font-weight:700;}

  footer.brandfoot{max-width:900px; margin:14px auto 0; padding:0 16px calc(110px + env(safe-area-inset-bottom,0px)); text-align:center; font-size:12px; color:var(--ink-soft);}

  .mode-pill{font-family:inherit; font-size:12.5px; font-weight:700; color:var(--navy); background:var(--gold); border:none; border-radius:99px; padding:6px 14px; cursor:pointer; margin-top:12px; display:inline-flex; align-items:center; gap:6px;}
  .mode-pick{display:flex; flex-direction:column; gap:14px; padding:8px 0 24px;}
  .mode-card{background:var(--card); border:1.5px solid var(--rule); border-radius:16px; padding:22px; cursor:pointer; text-align:left;}
  .mode-card:hover{border-color:var(--navy-2);}
  .mode-card .mode-icon{font-size:26px; margin-bottom:8px;}
  .mode-card h3{font-size:18px; margin-bottom:6px;}
  .mode-card p{font-size:13.5px; color:var(--ink-soft); line-height:1.5; margin:0;}
  .quiz-hint{font-size:12.5px; color:var(--ink-soft); background:var(--paper-2); border-radius:9px; padding:8px 12px; margin-bottom:14px;}
  .review-row{border:1px solid var(--rule); border-radius:10px; padding:11px 13px; margin-bottom:10px;}
  .review-tag{font-size:11.5px; font-weight:700; margin-bottom:4px; display:block;}
  .review-tag.ok{color:var(--success);} .review-tag.bad{color:var(--danger);} .review-tag.na{color:var(--ink-soft);}
  .review-q{font-size:13.5px; margin-bottom:6px; color:var(--ink-soft);}
  .review-ans{font-size:13px; margin-bottom:2px;}

  .who-row{max-width:900px; margin:12px auto 0; display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
  .who-row .mode-pill{margin-top:0;}
  .who{display:inline-flex; flex-wrap:wrap; align-items:center; gap:6px; font-size:12.5px; color:#CFD7EA;}
  .who b{color:#F4EFDF;}
  .who button{font-family:inherit; font-size:12px; font-weight:700; color:#F4EFDF; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.22); border-radius:99px; padding:5px 11px; cursor:pointer;}
  .who button:hover{background:rgba(255,255,255,.2);}
  .login-card{max-width:460px; margin:8px auto 0; background:var(--card); border:1px solid var(--rule); border-radius:16px; padding:22px;}
  .login-card h2{font-size:21px; margin-bottom:4px;}
  .login-card p.lead{font-size:13.5px; color:var(--ink-soft); margin:0 0 16px; line-height:1.5;}
  .fld{display:flex; flex-direction:column; gap:5px; margin-bottom:12px;}
  .fld label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .fld input{font-family:inherit; font-size:15px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:9px; background:var(--paper); color:var(--ink);}
  .fld input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .fld-row{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .login-err{font-size:13px; color:var(--danger); background:var(--danger-soft); border-radius:8px; padding:8px 10px; margin-bottom:12px;}
  .login-note{font-size:12px; color:var(--ink-soft); margin-top:12px; line-height:1.5;}
  .known{margin:0 0 16px; display:flex; flex-direction:column; gap:6px;}
  .known-label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .known-btn{display:flex; justify-content:space-between; align-items:center; gap:10px; text-align:left; font-family:inherit; font-size:14.5px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:10px; background:var(--paper); color:var(--ink); cursor:pointer;}
  .known-btn:hover{border-color:var(--navy-2);}
  .known-btn small{font-size:12px; color:var(--ink-soft);}
  .rec-card{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px; margin-bottom:14px;}
  .rec-card h2{font-size:19px; margin-bottom:10px;}
  .rec-card h3{font-size:15px; margin:4px 0 8px;}
  .rec-table-wrap{overflow-x:auto;}
  .rec-table{width:100%; border-collapse:collapse; font-size:13.5px; font-variant-numeric:tabular-nums;}
  .rec-table th{text-align:left; font-size:11.5px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:6px 8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-table td{padding:8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-bar{display:inline-block; width:70px; height:6px; border-radius:99px; background:var(--rule); overflow:hidden; vertical-align:middle; margin-right:6px;}
  .rec-bar i{display:block; height:100%; background:var(--success);}
  .rec-empty{font-size:13.5px; color:var(--ink-soft);}
  .sec-sub{max-width:900px; margin:0 auto; padding:10px 16px 0; font-size:12.5px; font-weight:700; color:var(--accent-text); letter-spacing:.02em;}
  .opt{flex-wrap:wrap;}
  .opt-l{font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink-soft);}
  .opt-t{flex:1; min-width:0;}
  .opt.is-chosen:not(.is-correct):not(.is-wrong){border-color:var(--navy-2); background:var(--gold-soft);}
  .opt-tag{font-size:11px; font-weight:700; padding:2px 8px; border-radius:99px; background:var(--card); border:1px solid currentColor; white-space:nowrap;}
  .opt.is-correct .opt-tag{color:var(--success);} .opt.is-wrong .opt-tag{color:var(--danger);} .opt.is-chosen:not(.is-correct):not(.is-wrong) .opt-tag{color:var(--accent-text);}
  .chosen{font-size:13.5px; margin-top:10px; padding:8px 12px; border-radius:9px;}
  .chosen.ok{background:var(--success-soft); color:var(--success);} .chosen.bad{background:var(--danger-soft); color:var(--danger);}
  .chosen + .chosen{margin-top:6px;}
  .solution{margin-top:14px; border:1px solid var(--rule); border-left:4px solid var(--gold); background:var(--paper-2); border-radius:10px; padding:12px 14px;}
  .sol-h{font-family:'Fraunces',Georgia,serif; font-weight:700; font-size:14px; color:var(--accent-text); margin-bottom:6px;}
  .sol-line{font-size:14.5px; line-height:1.7;}
  .rev-sol summary{cursor:pointer; font-size:12.5px; font-weight:700; color:var(--accent-text); margin-top:6px;}
  .rev-sol .solution{margin-top:8px;}
  .chapter-credit{max-width:900px; margin:4px auto 0; font-size:12px; color:#CFD7EA;}
  footer.brandfoot a{color:inherit;}
  .blank-input.wide{width:260px; max-width:100%; font-family:'Source Sans 3',sans-serif;}
  .blank-input.expr{width:170px; max-width:100%;}
  /*fix-layout*/ .cp-fill,.sp-fill{width:0;} .fld{min-width:0;} .fld input{width:100%; min-width:0; box-sizing:border-box;}
  .fig{margin:6px 0 10px; display:flex; justify-content:center;}
  .figsvg{width:100%; max-width:340px; height:auto; overflow:visible;}
  .figsvg .ln,.figsvg .arm{stroke:var(--ink); stroke-width:1.6; fill:none;}
  .figsvg .arm{stroke:var(--accent-text); stroke-width:2;}
  .figsvg .pt{fill:var(--ink);}
  .figsvg .lb{fill:var(--ink); font:600 13px 'Source Sans 3',sans-serif;}
  .figsvg .al{fill:var(--accent-text); font:700 12px 'Source Sans 3',sans-serif;}
  .figsvg .wg{fill:var(--gold-soft); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .wg2{fill:rgba(199,154,62,.35); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .ra{fill:none; stroke:var(--ink); stroke-width:1.2;}
  .figsvg .ahd{fill:var(--ink);}
  .figsvg .pr{fill:var(--paper-2); stroke:var(--ink-soft); stroke-width:1.2;}
  .figsvg .tk{stroke:var(--ink-soft); stroke-width:.8;}
  .figsvg .po{fill:var(--ink); font:600 8.5px 'IBM Plex Mono',monospace;}
  .figsvg .pi{fill:var(--danger); font:600 7.5px 'IBM Plex Mono',monospace;}
  .figsvg .sh{fill:var(--gold-soft); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh2{fill:rgba(199,154,62,.38); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh3{fill:rgba(199,154,62,.22); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .none{fill:none;}
  .figsvg .hid{stroke-dasharray:5 4; fill:none;}
  .figsvg .tick{stroke:var(--ink); stroke-width:1.4; fill:none;}
  .figsvg .shd{fill:var(--accent-text); fill-opacity:.55;}
  .figsvg .cell{fill:var(--card); stroke:var(--ink); stroke-width:1.1;}
  .figsvg .dr{fill:var(--danger);} .figsvg .dw{fill:var(--card); stroke:var(--ink); stroke-width:1.2;}
  .figsvg .dotfill{fill:var(--danger);}
  .fq{display:inline-flex; flex-direction:column; vertical-align:middle; text-align:center; font-size:.82em; line-height:1.12; margin:0 2px;}
  .fq>span:first-child{border-bottom:1.5px solid currentColor; padding:0 2px;}
  .fq>span:last-child{padding:0 2px;}
  .mx{white-space:nowrap;}
  .blank-input.fr{width:110px;}
  @media (prefers-reduced-motion:reduce){ *{transition:none !important;} }
</style>
</head>
<body>
<header class="brand">
  <div class="brand-row">
    <div class="crest">BM</div>
    <div>
      <div class="brand-name">Brain &amp; Mind Academy</div>
      <div class="series-name">Sopaan <span style="font-weight:400;font-size:14px;color:#CFD7EA;">Practice Series</span></div>
    </div>
  </div>
  <div class="chapter-eyebrow">Grade 6 Mathematics · Chapter 8</div>
  <div class="chapter-title">Measurement: Introduction</div>
  <div class="chapter-sub">Exercises 8A–8C · Review Sets · Step-by-Step Practice</div><div class="chapter-credit">Follows Haese Mathematics 6 (MYP 1), Chapter 8</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · Grade 6 Mathematics<br>Exercises follow the structure of <i>Mathematics 6 (MYP 1), 3rd edition</i>, Haese Mathematics. Questions, steps and solutions written by Brain &amp; Mind Academy.</footer>

<div class="navbar"><div class="navbar-inner" id="navbarInner"></div></div>
<button class="fab" id="paletteFab"><span>Questions</span><span class="fab-badge" id="fabBadge">0/49</span></button>

<div class="overlay" id="overlay">
  <div class="palette" role="dialog" aria-label="Question palette">
    <div class="palette-head"><h2 id="paletteTitle">Question palette</h2><button class="palette-close" id="paletteClose">&times;</button></div>
    <div class="palette-legend">
      <span><i class="dot current"></i>Current</span><span><i class="dot correct"></i>Correct</span>
      <span><i class="dot revealed"></i>Revealed</span><span><i class="dot skipped"></i>Skipped</span>
      <span><i class="dot locked"></i>Locked</span>
    </div>
    <div class="chip-grid" id="paletteBody"></div>
  </div>
</div>
<div class="toast" id="toast"></div>

<script>
(function(){
"use strict";

/* ================= audio ================= */
var audioCtx=null;
function ensureAudio(){ if(!audioCtx){ try{ audioCtx=new (window.AudioContext||window.webkitAudioContext)(); }catch(e){} } return audioCtx; }
function playTone(freqs,dur,type){
  var ctx=ensureAudio(); if(!ctx) return;
  try{
    var t0=ctx.currentTime;
    freqs.forEach(function(f,i){
      var o=ctx.createOscillator(), g=ctx.createGain();
      o.type=type||'sine'; o.frequency.value=f;
      var start=t0+i*dur;
      g.gain.setValueAtTime(0.0001,start);
      g.gain.exponentialRampToValueAtTime(0.16,start+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001,start+dur);
      o.connect(g); g.connect(ctx.destination);
      o.start(start); o.stop(start+dur+0.02);
    });
  }catch(e){}
}
function playSuccess(){ playTone([523.25,659.25,783.99],0.11,'sine'); }
function playWrong(){ playTone([220,185],0.14,'square'); }
function playReveal(){ playTone([300,220],0.16,'triangle'); }

/* ================= helpers ================= */
function norm(s){
  return String(s===undefined||s===null?'':s).trim().toLowerCase().replace(/\s+/g,'')
    .replace(/[×∗*·]/g,'x').replace(/÷/g,'/').replace(/–|—|−/g,'-')
    .replace(/[²]/g,'^2').replace(/[³]/g,'^3').replace(/[⁴]/g,'^4').replace(/[⁵]/g,'^5')
    .replace(/[⁶]/g,'^6').replace(/[⁷]/g,'^7').replace(/[⁸]/g,'^8').replace(/[⁹]/g,'^9')
    .replace(/\^/g,'');
}
function parseNum(s){
  if(s===undefined||s===null) return null;
  var t=String(s).trim().replace(/,/g,'').replace(/[−–—]/g,'-').replace(/\s+/g,''); if(t==='') return null;
  var neg=false; if(t[0]==='-'){neg=true;t=t.slice(1);}
  var m=t.match(/^(\d+)\/(\d+)$/);
  if(m){ var v=parseInt(m[1],10)/parseInt(m[2],10); return neg?-v:v; }
  if(/^\d+(\.\d+)?$/.test(t)){ var v2=parseFloat(t); return neg?-v2:v2; }
  return null;
}
/* ---- expression checker: compares answers like (P-2w)/2 and P/2-w at random values ---- */
function exprPrep(s){
  return String(s).replace(/\s+/g,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/π/g,'#').replace(/pi/gi,'#').replace(/½/g,'(1/2)');
}
function exprCompile(src){
  var s=exprPrep(src), i=0, toks=[];
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length && /[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(/[a-zA-Z#]/.test(ch)){ toks.push({k:'v',v:ch}); i++; continue; }
    if('+-*/^()'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  var out=[];
  for(var t=0;t<toks.length;t++){
    var a=toks[t], b=out[out.length-1];
    if(b && (b.k==='n'||b.k==='v'||b.k===')') && (a.k==='n'||a.k==='v'||a.k==='(')) out.push({k:'&'});
    out.push(a);
  }
  var p=0;
  function peek(){ return out[p]; }
  function parseE(){ var n=parseT(); while(peek() && (peek().k==='+'||peek().k==='-')){ var o=out[p++].k, r=parseT(); n=(function(l,r,o){return function(e){ return o==='+'?l(e)+r(e):l(e)-r(e); };})(n,r,o); } return n; }
  function parseI(){ var n=parseU(); while(peek() && peek().k==='&'){ p++; var r=parseP(); n=(function(l,r){return function(e){ return l(e)*r(e); };})(n,r); } return n; }
  function parseT(){ var n=parseI(); while(peek() && (peek().k==='*'||peek().k==='/')){ var o=out[p++].k, r=parseI(); n=(function(l,r,o){return function(e){ return o==='*'?l(e)*r(e):l(e)/r(e); };})(n,r,o); } return n; }
  function parseU(){ if(peek() && peek().k==='-'){ p++; var u=parseU(); return function(e){ return -u(e); }; } if(peek() && peek().k==='+'){ p++; return parseU(); } return parseP(); }
  function parseP(){ var b=parseA(); if(peek() && peek().k==='^'){ p++; var x=parseU(); return function(e){ return Math.pow(b(e),x(e)); }; } return b; }
  function parseA(){
    var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){ return t.v; };
    if(t.k==='v') return t.v==='#' ? function(){ return Math.PI; } : function(e){ return e[t.v]; };
    if(t.k==='('){ var n=parseE(); if(!peek()||peek().k!==')') throw 0; p++; return n; }
    throw 0;
  }
  try{ var f=parseE(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function exprEqual(input,answer){
  var f=exprCompile(input), g=exprCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<8;trial++){
    var env={}; 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=1.3+Math.random()*4.1; });
    var x=f(env), y=g(env);
    if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-7*Math.max(1,Math.abs(x),Math.abs(y))) return false;
    hits++;
  }
  return hits>=3;
}
function wordsNorm(s){ return String(s||'').toLowerCase().replace(/\band\b/g,' ').replace(/[^a-z]/g,''); }
function listNorm(s){ return (String(s||'').replace(/(\d) (?=\d{3}\b)/g,'$1').match(/-?\d+(\.\d+)?/g)||[]).join(','); }
function powNorm(s){ return String(s||'').toLowerCase().replace(/\s+/g,'').replace(/[×∗*·.]/g,'x').replace(/[⁰¹²³⁴⁵⁶⁷⁸⁹]+/g,function(m){ return '^'+m.split('').map(function(c){ return '⁰¹²³⁴⁵⁶⁷⁸⁹'.indexOf(c); }).join(''); }).replace(/\^1(?!\d)/g,''); }
function fr(s){ return String(s).replace(/\{(\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>').replace(/\{(\d+)\/(\d+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); }
function gcdI(a,b){ a=Math.abs(a); b=Math.abs(b); while(b){ var t=a%b; a=b; b=t; } return a; }
function fracParse(s){ s=String(s===undefined||s===null?'':s).trim().replace(/[\u2044\u2215\u00f7]/g,'/').replace(/\s+/g,' ').replace(/\s*\/\s*/g,'/'); var m;
  if((m=s.match(/^(-?\d+)$/))) return {v:+m[1],form:'int',n:+m[1],d:1};
  if((m=s.match(/^(-?\d+)\/(\d+)$/))){ if(+m[2]===0) return null; return {v:m[1]/m[2],form:'frac',n:+m[1],d:+m[2]}; }
  if((m=s.match(/^(\d+)(?: |\+|-)(\d+)\/(\d+)$/))){ if(+m[3]===0) return null; return {v:+m[1]+m[2]/m[3],form:'mixed',w:+m[1],n:+m[2],d:+m[3]}; }
  if((m=s.match(/^-?\d*\.\d+$/))) return {v:parseFloat(s),form:'dec'};
  return null; }
function fracOK(mode,input,answer){
  if(mode==='flist'){ var A=String(input).split(/[,;]/).map(function(x){return x.trim();}).filter(Boolean), K=String(answer).split(/[,;]/).map(function(x){return x.trim();});
    if(A.length!==K.length) return false; return A.every(function(x,i){ var a=fracParse(x), k=fracParse(K[i]); return a&&k&&Math.abs(a.v-k.v)<1e-9; }); }
  var a=fracParse(input), k=fracParse(answer); if(!a||!k) return false;
  var same=Math.abs(a.v-k.v)<1e-9; if(!same) return false;
  if(mode==='fv') return true;
  if(mode==='dec') return a.form==='dec'||a.form==='int';
  if(mode==='fe') return (a.form==='frac'&&k.form==='frac'&&a.n===k.n&&a.d===k.d)||(a.form==='int'&&k.form==='int');
  if(mode==='fi') return a.form==='frac'||(a.form==='int'&&k.form==='int');
  if(mode==='fl') return a.form==='int'||(a.form==='frac'&&gcdI(a.n,a.d)===1)||(a.form==='mixed'&&a.n<a.d&&gcdI(a.n,a.d)===1);
  if(mode==='fm') return a.form==='int'||(a.form==='mixed'&&a.n>0&&a.n<a.d&&gcdI(a.n,a.d)===1);
  return false; }
function answerMatches(input,answer,accept,expr){
  if(expr==='dec'||expr==='fv'||expr==='fe'||expr==='fl'||expr==='fm'||expr==='fi'||expr==='flist'){ if(input===undefined||input===null||String(input).trim()==='') return false; return fracOK(expr,input,answer); }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  if(expr==='words'){ return [answer].concat(accept||[]).some(function(a){ return wordsNorm(a)===wordsNorm(input); }); }
  if(expr==='list'){ return [answer].concat(accept||[]).some(function(a){ return listNorm(a)===listNorm(input); }); }
  if(expr==='pow'){ return [answer].concat(accept||[]).some(function(a){ return powNorm(a)===powNorm(input); }); }
  if(expr==='dlist'){ var dn=function(x){ return (String(x).match(/-?\d*\.?\d+/g)||[]).map(Number).join(','); }; return [answer].concat(accept||[]).some(function(a){ return dn(a)===dn(input); }); }
  if(expr==='set'){ var sn=function(x){ return (String(x).match(/-?\d+/g)||[]).map(Number).sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return sn(a)===sn(input); }); }
  if(expr==='primes'){ var pn=function(x){ var t=powNorm(x).replace(/[^0-9x^]/g,''); var out=[]; t.split('x').forEach(function(tok){ if(!tok) return; var m=tok.split('^'); var b=+m[0], e=m[1]?+m[1]:1; for(var i=0;i<e;i++) out.push(b); }); return out.sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return pn(a)===pn(input); }); }
  if(expr==='angle'){ var an=function(x){ return String(x).toUpperCase().replace(/[^A-Z]/g,''); }; var k=an(answer), v=an(input); return v===k || v===k.split('').reverse().join(''); }
  if(expr==='expanded'){ var f=function(x){ return String(x).replace(/\s+/g,'').replace(/,/g,''); }; return [answer].concat(accept||[]).some(function(a){ return f(a)===f(input); }); }
  if(expr===true && input!==undefined && input!==null && String(input).trim()!==''){
    if(exprEqual(input,answer)) return true;
    return (accept||[]).some(function(a){ return exprEqual(input,a); });
  }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  var n1=parseNum(input), n2=parseNum(answer);
  if(n1!==null && n2!==null) return Math.abs(n1-n2)<1e-3;
  var cands=[answer].concat(accept||[]); var ni=norm(input);
  for(var i=0;i<cands.length;i++){ if(norm(cands[i])===ni) return true; }
  return false;
}
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;'); }

/* ================= DATA ================= */
var AR_OPTIONS = ["Both A and R are true, and R is the correct explanation of A","Both A and R are true, but R is NOT the correct explanation of A","A is true but R is false","A is false but R is true"];
var SECTIONS = [{"id": "s1", "label": "Ex 8A", "sub": "Units", "slides": [{"kind": "blank", "p": "Write the unit for each counting situation:", "tag": "", "marks": "", "flat": [{"t": "a) 7 __B1__ (a bowl of apples)", "a": {"B1": "apples"}, "expr": "words"}, {"t": "b) 4 __B1__ (fish in a tank)", "a": {"B1": "fish"}, "expr": "words"}, {"t": "c) 12 __B1__ (eggs in a tray)", "a": {"B1": "eggs"}, "expr": "words"}, {"t": "d) 30 __B1__ (children in a class)", "a": {"B1": "children"}, "expr": "words", "accept": ["students", "pupils"]}], "sol": "When we count, the unit is the thing being counted."}, {"kind": "blank", "p": "Match each statement with the correct measurement (A 80 m², B 25 minutes, C 300 g, D 15 cm, E 32 °C). Type the letter.", "tag": "", "marks": "", "flat": [{"t": "a) The mass of a rock → __B1__", "a": {"B1": "C"}}, {"t": "b) The length of a spoon → __B1__", "a": {"B1": "D"}}, {"t": "c) The maximum temperature in Chennai today → __B1__", "a": {"B1": "E"}}, {"t": "d) The time Hari spent running → __B1__", "a": {"B1": "B"}}, {"t": "e) The area of a classroom → __B1__", "a": {"B1": "A"}}], "sol": "a) mass: grams → C\nb) length: cm → D\nc) temperature: °C → E\nd) time: minutes → B\ne) area: m² → A"}, {"kind": "blank", "p": "Which type of quantity does each unit measure? (length, mass, time, temperature, area, volume, capacity or speed)", "tag": "", "marks": "", "flat": [{"t": "a) kilometre → __B1__", "a": {"B1": "length"}, "expr": "words"}, {"t": "b) tonne → __B1__", "a": {"B1": "mass"}, "expr": "words"}, {"t": "c) second → __B1__", "a": {"B1": "time"}, "expr": "words"}, {"t": "d) square metre → __B1__", "a": {"B1": "area"}, "expr": "words"}, {"t": "e) millilitre → __B1__", "a": {"B1": "capacity"}, "expr": "words"}, {"t": "f) km/h → __B1__", "a": {"B1": "speed"}, "expr": "words"}, {"t": "g) degrees Celsius → __B1__", "a": {"B1": "temperature"}, "expr": "words"}, {"t": "h) cubic centimetre → __B1__", "a": {"B1": "volume"}, "expr": "words"}], "sol": "Each type of quantity has its own units."}, {"kind": "mcq", "text": "A nail weighs 1.2 g. Why would it not be sensible to give the mass of a truck in grams?", "opts": ["The number would be huge (millions of grams), so tonnes are better", "Trucks cannot be weighed", "Grams only measure liquids", "A truck has no mass"], "correct": 0, "tag": "", "sol": "Choose a unit that gives sensibly sized numbers: a truck is about 3 t, not 3 000 000 g."}]}, {"id": "s2", "label": "Ex 8B", "sub": "Reading scales", "slides": [{"kind": "blank", "p": "Read each length measurement:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ cm", "a": {"B1": "3.4"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 80\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"12\" y=\"14\" width=\"276\" height=\"44\" rx=\"3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"22.0\" y1=\"14\" x2=\"22.0\" y2=\"28\"/><text class=\"lb\" x=\"22.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"26.3\" y1=\"14\" x2=\"26.3\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"30.5\" y1=\"14\" x2=\"30.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"34.8\" y1=\"14\" x2=\"34.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"39.1\" y1=\"14\" x2=\"39.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"43.3\" y1=\"14\" x2=\"43.3\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"47.6\" y1=\"14\" x2=\"47.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"51.9\" y1=\"14\" x2=\"51.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"56.1\" y1=\"14\" x2=\"56.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"60.4\" y1=\"14\" x2=\"60.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"64.7\" y1=\"14\" x2=\"64.7\" y2=\"28\"/><text class=\"lb\" x=\"64.7\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"68.9\" y1=\"14\" x2=\"68.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"73.2\" y1=\"14\" x2=\"73.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"14\" x2=\"77.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"81.7\" y1=\"14\" x2=\"81.7\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"86.0\" y1=\"14\" x2=\"86.0\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"90.3\" y1=\"14\" x2=\"90.3\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.5\" y1=\"14\" x2=\"94.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"98.8\" y1=\"14\" x2=\"98.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"103.1\" y1=\"14\" x2=\"103.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"107.3\" y1=\"14\" x2=\"107.3\" y2=\"28\"/><text class=\"lb\" x=\"107.3\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"111.6\" y1=\"14\" x2=\"111.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"115.9\" y1=\"14\" x2=\"115.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"120.1\" y1=\"14\" x2=\"120.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"124.4\" y1=\"14\" x2=\"124.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"128.7\" y1=\"14\" x2=\"128.7\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"132.9\" y1=\"14\" x2=\"132.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"137.2\" y1=\"14\" x2=\"137.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"141.5\" y1=\"14\" x2=\"141.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"145.7\" y1=\"14\" x2=\"145.7\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"14\" x2=\"150.0\" y2=\"28\"/><text class=\"lb\" x=\"150.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"154.3\" y1=\"14\" x2=\"154.3\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"158.5\" y1=\"14\" x2=\"158.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"162.8\" y1=\"14\" x2=\"162.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"167.1\" y1=\"14\" x2=\"167.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"171.3\" y1=\"14\" x2=\"171.3\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"175.6\" y1=\"14\" x2=\"175.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"179.9\" y1=\"14\" x2=\"179.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"184.1\" y1=\"14\" x2=\"184.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"188.4\" y1=\"14\" x2=\"188.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"192.7\" y1=\"14\" x2=\"192.7\" y2=\"28\"/><text class=\"lb\" x=\"192.7\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"196.9\" y1=\"14\" x2=\"196.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"201.2\" y1=\"14\" x2=\"201.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.5\" y1=\"14\" x2=\"205.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"209.7\" y1=\"14\" x2=\"209.7\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"214.0\" y1=\"14\" x2=\"214.0\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"218.3\" y1=\"14\" x2=\"218.3\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"14\" x2=\"222.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"226.8\" y1=\"14\" x2=\"226.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"231.1\" y1=\"14\" x2=\"231.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"235.3\" y1=\"14\" x2=\"235.3\" y2=\"28\"/><text class=\"lb\" x=\"235.3\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"239.6\" y1=\"14\" x2=\"239.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"243.9\" y1=\"14\" x2=\"243.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"248.1\" y1=\"14\" x2=\"248.1\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"252.4\" y1=\"14\" x2=\"252.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"256.7\" y1=\"14\" x2=\"256.7\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"260.9\" y1=\"14\" x2=\"260.9\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"265.2\" y1=\"14\" x2=\"265.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"269.5\" y1=\"14\" x2=\"269.5\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"273.7\" y1=\"14\" x2=\"273.7\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"278.0\" y1=\"14\" x2=\"278.0\" y2=\"28\"/><text class=\"lb\" x=\"278.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"lb\" x=\"280.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">cm</text><path class=\"dr\" d=\"M167.1,60 l-6,12 h12 z\"/></svg>", "expr": "dec"}, {"t": "b) __B1__ cm", "a": {"B1": "23"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 80\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"12\" y=\"14\" width=\"276\" height=\"44\" rx=\"3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"22.0\" y1=\"14\" x2=\"22.0\" y2=\"28\"/><text class=\"lb\" x=\"22.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"47.6\" y1=\"14\" x2=\"47.6\" y2=\"28\"/><text class=\"lb\" x=\"47.6\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">21</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"73.2\" y1=\"14\" x2=\"73.2\" y2=\"28\"/><text class=\"lb\" x=\"73.2\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">22</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"98.8\" y1=\"14\" x2=\"98.8\" y2=\"28\"/><text class=\"lb\" x=\"98.8\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">23</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"124.4\" y1=\"14\" x2=\"124.4\" y2=\"28\"/><text class=\"lb\" x=\"124.4\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">24</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"14\" x2=\"150.0\" y2=\"28\"/><text class=\"lb\" x=\"150.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">25</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"175.6\" y1=\"14\" x2=\"175.6\" y2=\"28\"/><text class=\"lb\" x=\"175.6\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">26</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"201.2\" y1=\"14\" x2=\"201.2\" y2=\"28\"/><text class=\"lb\" x=\"201.2\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">27</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"226.8\" y1=\"14\" x2=\"226.8\" y2=\"28\"/><text class=\"lb\" x=\"226.8\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">28</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"252.4\" y1=\"14\" x2=\"252.4\" y2=\"28\"/><text class=\"lb\" x=\"252.4\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">29</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"278.0\" y1=\"14\" x2=\"278.0\" y2=\"28\"/><text class=\"lb\" x=\"278.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">30</text><text class=\"lb\" x=\"280.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">cm</text><path class=\"dr\" d=\"M98.8,60 l-6,12 h12 z\"/></svg>", "expr": "dec"}, {"t": "c) __B1__ cm", "a": {"B1": "14.7"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 80\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"12\" y=\"14\" width=\"276\" height=\"44\" rx=\"3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"22.0\" y1=\"14\" x2=\"22.0\" y2=\"28\"/><text class=\"lb\" x=\"22.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">14</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"47.6\" y1=\"14\" x2=\"47.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"73.2\" y1=\"14\" x2=\"73.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"98.8\" y1=\"14\" x2=\"98.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"124.4\" y1=\"14\" x2=\"124.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"150.0\" y1=\"14\" x2=\"150.0\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"175.6\" y1=\"14\" x2=\"175.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"201.2\" y1=\"14\" x2=\"201.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"226.8\" y1=\"14\" x2=\"226.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"252.4\" y1=\"14\" x2=\"252.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"278.0\" y1=\"14\" x2=\"278.0\" y2=\"28\"/><text class=\"lb\" x=\"278.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">15</text><text class=\"lb\" x=\"280.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">cm</text><path class=\"dr\" d=\"M201.2,60 l-6,12 h12 z\"/></svg>", "expr": "dec"}, {"t": "d) __B1__ cm", "a": {"B1": "16.25"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 80\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"12\" y=\"14\" width=\"276\" height=\"44\" rx=\"3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"22.0\" y1=\"14\" x2=\"22.0\" y2=\"28\"/><text class=\"lb\" x=\"22.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">16</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"34.8\" y1=\"14\" x2=\"34.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"47.6\" y1=\"14\" x2=\"47.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"60.4\" y1=\"14\" x2=\"60.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"73.2\" y1=\"14\" x2=\"73.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"86.0\" y1=\"14\" x2=\"86.0\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"98.8\" y1=\"14\" x2=\"98.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"111.6\" y1=\"14\" x2=\"111.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"124.4\" y1=\"14\" x2=\"124.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"137.2\" y1=\"14\" x2=\"137.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"150.0\" y1=\"14\" x2=\"150.0\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"162.8\" y1=\"14\" x2=\"162.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"175.6\" y1=\"14\" x2=\"175.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"188.4\" y1=\"14\" x2=\"188.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"201.2\" y1=\"14\" x2=\"201.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"214.0\" y1=\"14\" x2=\"214.0\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"226.8\" y1=\"14\" x2=\"226.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"239.6\" y1=\"14\" x2=\"239.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"252.4\" y1=\"14\" x2=\"252.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"265.2\" y1=\"14\" x2=\"265.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"278.0\" y1=\"14\" x2=\"278.0\" y2=\"28\"/><text class=\"lb\" x=\"278.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">17</text><text class=\"lb\" x=\"280.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">cm</text><path class=\"dr\" d=\"M86.0,60 l-6,12 h12 z\"/></svg>", "expr": "dec"}], "sol": "Work out what each small division is worth first.\na) divisions of 0.1 cm: 3.4 cm\nb) divisions of 1 cm: 23 cm\nc) divisions of 0.1 cm: 14.7 cm\nd) divisions of 0.05 cm: 16.25 cm"}, {"kind": "blank", "p": "Read the temperature on each thermometer (°C):", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ °C", "a": {"B1": "36.8"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 70\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"30\" y=\"21\" width=\"250\" height=\"18\" rx=\"9\"/><circle class=\"dr\" cx=\"26\" cy=\"30\" r=\"12\"/><rect class=\"dr\" x=\"26\" y=\"26\" width=\"96.8\" height=\"8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"40.0\" y1=\"39\" x2=\"40.0\" y2=\"46\"/><text class=\"lb\" x=\"40.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">35</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"44.6\" y1=\"39\" x2=\"44.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"49.2\" y1=\"39\" x2=\"49.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"53.8\" y1=\"39\" x2=\"53.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"58.4\" y1=\"39\" x2=\"58.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"63.0\" y1=\"39\" x2=\"63.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"67.6\" y1=\"39\" x2=\"67.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"72.2\" y1=\"39\" x2=\"72.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"76.8\" y1=\"39\" x2=\"76.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"81.4\" y1=\"39\" x2=\"81.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"86.0\" y1=\"39\" x2=\"86.0\" y2=\"46\"/><text class=\"lb\" x=\"86.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">36</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"90.6\" y1=\"39\" x2=\"90.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"95.2\" y1=\"39\" x2=\"95.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"99.8\" y1=\"39\" x2=\"99.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"104.4\" y1=\"39\" x2=\"104.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"109.0\" y1=\"39\" x2=\"109.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"113.6\" y1=\"39\" x2=\"113.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"118.2\" y1=\"39\" x2=\"118.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"122.8\" y1=\"39\" x2=\"122.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"127.4\" y1=\"39\" x2=\"127.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"132.0\" y1=\"39\" x2=\"132.0\" y2=\"46\"/><text class=\"lb\" x=\"132.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">37</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"136.6\" y1=\"39\" x2=\"136.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"141.2\" y1=\"39\" x2=\"141.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"145.8\" y1=\"39\" x2=\"145.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"150.4\" y1=\"39\" x2=\"150.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"155.0\" y1=\"39\" x2=\"155.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"159.6\" y1=\"39\" x2=\"159.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"164.2\" y1=\"39\" x2=\"164.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"168.8\" y1=\"39\" x2=\"168.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"173.4\" y1=\"39\" x2=\"173.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"178.0\" y1=\"39\" x2=\"178.0\" y2=\"46\"/><text class=\"lb\" x=\"178.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">38</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"182.6\" y1=\"39\" x2=\"182.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"187.2\" y1=\"39\" x2=\"187.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"191.8\" y1=\"39\" x2=\"191.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"196.4\" y1=\"39\" x2=\"196.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"201.0\" y1=\"39\" x2=\"201.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"205.6\" y1=\"39\" x2=\"205.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"210.2\" y1=\"39\" x2=\"210.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"214.8\" y1=\"39\" x2=\"214.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"219.4\" y1=\"39\" x2=\"219.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"224.0\" y1=\"39\" x2=\"224.0\" y2=\"46\"/><text class=\"lb\" x=\"224.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">39</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"228.6\" y1=\"39\" x2=\"228.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"233.2\" y1=\"39\" x2=\"233.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"237.8\" y1=\"39\" x2=\"237.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"242.4\" y1=\"39\" x2=\"242.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"247.0\" y1=\"39\" x2=\"247.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"251.6\" y1=\"39\" x2=\"251.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"256.2\" y1=\"39\" x2=\"256.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"260.8\" y1=\"39\" x2=\"260.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"265.4\" y1=\"39\" x2=\"265.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"270.0\" y1=\"39\" x2=\"270.0\" y2=\"46\"/><text class=\"lb\" x=\"270.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><text class=\"lb\" x=\"288.0\" y=\"57.0\" text-anchor=\"end\" dominant-baseline=\"middle\">°C</text></svg>", "expr": "dec"}, {"t": "b) __B1__ °C", "a": {"B1": "38.3"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 70\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"30\" y=\"21\" width=\"250\" height=\"18\" rx=\"9\"/><circle class=\"dr\" cx=\"26\" cy=\"30\" r=\"12\"/><rect class=\"dr\" x=\"26\" y=\"26\" width=\"165.8\" height=\"8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"40.0\" y1=\"39\" x2=\"40.0\" y2=\"46\"/><text class=\"lb\" x=\"40.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">35</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"44.6\" y1=\"39\" x2=\"44.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"49.2\" y1=\"39\" x2=\"49.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"53.8\" y1=\"39\" x2=\"53.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"58.4\" y1=\"39\" x2=\"58.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"63.0\" y1=\"39\" x2=\"63.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"67.6\" y1=\"39\" x2=\"67.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"72.2\" y1=\"39\" x2=\"72.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"76.8\" y1=\"39\" x2=\"76.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"81.4\" y1=\"39\" x2=\"81.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"86.0\" y1=\"39\" x2=\"86.0\" y2=\"46\"/><text class=\"lb\" x=\"86.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">36</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"90.6\" y1=\"39\" x2=\"90.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"95.2\" y1=\"39\" x2=\"95.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"99.8\" y1=\"39\" x2=\"99.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"104.4\" y1=\"39\" x2=\"104.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"109.0\" y1=\"39\" x2=\"109.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"113.6\" y1=\"39\" x2=\"113.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"118.2\" y1=\"39\" x2=\"118.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"122.8\" y1=\"39\" x2=\"122.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"127.4\" y1=\"39\" x2=\"127.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"132.0\" y1=\"39\" x2=\"132.0\" y2=\"46\"/><text class=\"lb\" x=\"132.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">37</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"136.6\" y1=\"39\" x2=\"136.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"141.2\" y1=\"39\" x2=\"141.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"145.8\" y1=\"39\" x2=\"145.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"150.4\" y1=\"39\" x2=\"150.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"155.0\" y1=\"39\" x2=\"155.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"159.6\" y1=\"39\" x2=\"159.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"164.2\" y1=\"39\" x2=\"164.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"168.8\" y1=\"39\" x2=\"168.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"173.4\" y1=\"39\" x2=\"173.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"178.0\" y1=\"39\" x2=\"178.0\" y2=\"46\"/><text class=\"lb\" x=\"178.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">38</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"182.6\" y1=\"39\" x2=\"182.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"187.2\" y1=\"39\" x2=\"187.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"191.8\" y1=\"39\" x2=\"191.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"196.4\" y1=\"39\" x2=\"196.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"201.0\" y1=\"39\" x2=\"201.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"205.6\" y1=\"39\" x2=\"205.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"210.2\" y1=\"39\" x2=\"210.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"214.8\" y1=\"39\" x2=\"214.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"219.4\" y1=\"39\" x2=\"219.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"224.0\" y1=\"39\" x2=\"224.0\" y2=\"46\"/><text class=\"lb\" x=\"224.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">39</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"228.6\" y1=\"39\" x2=\"228.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"233.2\" y1=\"39\" x2=\"233.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"237.8\" y1=\"39\" x2=\"237.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"242.4\" y1=\"39\" x2=\"242.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"247.0\" y1=\"39\" x2=\"247.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"251.6\" y1=\"39\" x2=\"251.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"256.2\" y1=\"39\" x2=\"256.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"260.8\" y1=\"39\" x2=\"260.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"265.4\" y1=\"39\" x2=\"265.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"270.0\" y1=\"39\" x2=\"270.0\" y2=\"46\"/><text class=\"lb\" x=\"270.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><text class=\"lb\" x=\"288.0\" y=\"57.0\" text-anchor=\"end\" dominant-baseline=\"middle\">°C</text></svg>", "expr": "dec"}, {"t": "c) __B1__ °C", "a": {"B1": "37.5"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 70\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"30\" y=\"21\" width=\"250\" height=\"18\" rx=\"9\"/><circle class=\"dr\" cx=\"26\" cy=\"30\" r=\"12\"/><rect class=\"dr\" x=\"26\" y=\"26\" width=\"129.0\" height=\"8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"40.0\" y1=\"39\" x2=\"40.0\" y2=\"46\"/><text class=\"lb\" x=\"40.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">35</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"44.6\" y1=\"39\" x2=\"44.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"49.2\" y1=\"39\" x2=\"49.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"53.8\" y1=\"39\" x2=\"53.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"58.4\" y1=\"39\" x2=\"58.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"63.0\" y1=\"39\" x2=\"63.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"67.6\" y1=\"39\" x2=\"67.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"72.2\" y1=\"39\" x2=\"72.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"76.8\" y1=\"39\" x2=\"76.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"81.4\" y1=\"39\" x2=\"81.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"86.0\" y1=\"39\" x2=\"86.0\" y2=\"46\"/><text class=\"lb\" x=\"86.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">36</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"90.6\" y1=\"39\" x2=\"90.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"95.2\" y1=\"39\" x2=\"95.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"99.8\" y1=\"39\" x2=\"99.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"104.4\" y1=\"39\" x2=\"104.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"109.0\" y1=\"39\" x2=\"109.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"113.6\" y1=\"39\" x2=\"113.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"118.2\" y1=\"39\" x2=\"118.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"122.8\" y1=\"39\" x2=\"122.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"127.4\" y1=\"39\" x2=\"127.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"132.0\" y1=\"39\" x2=\"132.0\" y2=\"46\"/><text class=\"lb\" x=\"132.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">37</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"136.6\" y1=\"39\" x2=\"136.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"141.2\" y1=\"39\" x2=\"141.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"145.8\" y1=\"39\" x2=\"145.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"150.4\" y1=\"39\" x2=\"150.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"155.0\" y1=\"39\" x2=\"155.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"159.6\" y1=\"39\" x2=\"159.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"164.2\" y1=\"39\" x2=\"164.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"168.8\" y1=\"39\" x2=\"168.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"173.4\" y1=\"39\" x2=\"173.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"178.0\" y1=\"39\" x2=\"178.0\" y2=\"46\"/><text class=\"lb\" x=\"178.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">38</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"182.6\" y1=\"39\" x2=\"182.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"187.2\" y1=\"39\" x2=\"187.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"191.8\" y1=\"39\" x2=\"191.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"196.4\" y1=\"39\" x2=\"196.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"201.0\" y1=\"39\" x2=\"201.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"205.6\" y1=\"39\" x2=\"205.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"210.2\" y1=\"39\" x2=\"210.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"214.8\" y1=\"39\" x2=\"214.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"219.4\" y1=\"39\" x2=\"219.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"224.0\" y1=\"39\" x2=\"224.0\" y2=\"46\"/><text class=\"lb\" x=\"224.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">39</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"228.6\" y1=\"39\" x2=\"228.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"233.2\" y1=\"39\" x2=\"233.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"237.8\" y1=\"39\" x2=\"237.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"242.4\" y1=\"39\" x2=\"242.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"247.0\" y1=\"39\" x2=\"247.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"251.6\" y1=\"39\" x2=\"251.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"256.2\" y1=\"39\" x2=\"256.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"260.8\" y1=\"39\" x2=\"260.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"265.4\" y1=\"39\" x2=\"265.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"270.0\" y1=\"39\" x2=\"270.0\" y2=\"46\"/><text class=\"lb\" x=\"270.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><text class=\"lb\" x=\"288.0\" y=\"57.0\" text-anchor=\"end\" dominant-baseline=\"middle\">°C</text></svg>", "expr": "dec"}], "sol": "Each small division is 0.1 °C.\na) 36.8 °C\nb) 38.3 °C\nc) 37.5 °C"}, {"kind": "blank", "p": "Read the speed on each speedometer:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ km/h", "a": {"B1": "60"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">60</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">80</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">120</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">140</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">160</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">180</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"87.7\" y2=\"64.7\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">km/h</text></svg>", "expr": "dec"}, {"t": "b) __B1__ km/h", "a": {"B1": "110"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">60</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">80</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">120</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">140</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">160</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">180</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"168.0\" y2=\"35.1\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">km/h</text></svg>", "expr": "dec"}, {"t": "c) __B1__ km/h", "a": {"B1": "45"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"83.2\" y1=\"162.6\" x2=\"88.0\" y2=\"158.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"72.8\" y1=\"145.6\" x2=\"78.3\" y2=\"143.1\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"66.6\" y1=\"126.6\" x2=\"72.5\" y2=\"125.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.1\" y1=\"106.7\" x2=\"71.1\" y2=\"106.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"68.2\" y1=\"86.9\" x2=\"74.0\" y2=\"88.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"75.8\" y1=\"68.5\" x2=\"81.1\" y2=\"71.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">60</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"87.6\" y1=\"52.3\" x2=\"92.0\" y2=\"56.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"102.8\" y1=\"39.3\" x2=\"106.1\" y2=\"44.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">80</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"120.6\" y1=\"30.3\" x2=\"122.7\" y2=\"35.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"140.0\" y1=\"25.6\" x2=\"140.7\" y2=\"31.5\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"160.0\" y1=\"25.6\" x2=\"159.3\" y2=\"31.5\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"179.4\" y1=\"30.3\" x2=\"177.3\" y2=\"35.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">120</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"197.2\" y1=\"39.3\" x2=\"193.9\" y2=\"44.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"212.4\" y1=\"52.3\" x2=\"208.0\" y2=\"56.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">140</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"224.2\" y1=\"68.5\" x2=\"218.9\" y2=\"71.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"231.8\" y1=\"86.9\" x2=\"226.0\" y2=\"88.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">160</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.9\" y1=\"106.7\" x2=\"228.9\" y2=\"106.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"233.4\" y1=\"126.6\" x2=\"227.5\" y2=\"125.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">180</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"227.2\" y1=\"145.6\" x2=\"221.7\" y2=\"143.1\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"216.8\" y1=\"162.6\" x2=\"212.0\" y2=\"158.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"75.9\" y2=\"89.1\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">km/h</text></svg>", "expr": "dec"}], "sol": "Find the value of each small division (10 or 5 km/h).\na) 60 km/h\nb) 110 km/h\nc) 45 km/h"}, {"kind": "blank", "p": "Read the mass on each kitchen scale:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ g", "a": {"B1": "350"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">300</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">400</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">500</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">600</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">700</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">800</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">900</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">1000</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"100.0\" y2=\"51.4\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">g</text></svg>", "expr": "dec"}, {"t": "b) __B1__ kg", "a": {"B1": "2.4"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"79.7\" y1=\"157.8\" x2=\"84.7\" y2=\"154.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"72.0\" y1=\"143.8\" x2=\"77.5\" y2=\"141.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"67.0\" y1=\"128.5\" x2=\"72.9\" y2=\"127.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.0\" y1=\"112.7\" x2=\"71.0\" y2=\"112.5\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"70.0\" y1=\"81.2\" x2=\"75.7\" y2=\"83.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"76.8\" y1=\"66.7\" x2=\"82.0\" y2=\"69.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"86.2\" y1=\"53.8\" x2=\"90.7\" y2=\"57.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"97.9\" y1=\"42.8\" x2=\"101.6\" y2=\"47.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"126.3\" y1=\"28.4\" x2=\"128.0\" y2=\"34.1\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"142.0\" y1=\"25.4\" x2=\"142.6\" y2=\"31.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"158.0\" y1=\"25.4\" x2=\"157.4\" y2=\"31.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"173.7\" y1=\"28.4\" x2=\"172.0\" y2=\"34.1\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"202.1\" y1=\"42.8\" x2=\"198.4\" y2=\"47.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"213.8\" y1=\"53.8\" x2=\"209.3\" y2=\"57.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"223.2\" y1=\"66.7\" x2=\"218.0\" y2=\"69.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"230.0\" y1=\"81.2\" x2=\"224.3\" y2=\"83.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"235.0\" y1=\"112.7\" x2=\"229.0\" y2=\"112.5\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"233.0\" y1=\"128.5\" x2=\"227.1\" y2=\"127.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.0\" y1=\"143.8\" x2=\"222.5\" y2=\"141.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"220.3\" y1=\"157.8\" x2=\"215.3\" y2=\"154.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"142.8\" y2=\"33.3\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">kg</text></svg>", "expr": "dec"}], "sol": "a) divisions of 50 g: 350 g\nb) divisions of 0.2 kg: 2.4 kg"}, {"kind": "blank", "p": "Read the amount of water in each jug:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ mL", "a": {"B1": "300"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"shd\" style=\"fill-opacity:.35\" x=\"100\" y=\"84.0\" width=\"100\" height=\"96.0\"/><path class=\"ln\" fill=\"none\" d=\"M100,20 V180 H200 V20\"/><path class=\"ln\" fill=\"none\" d=\"M200,50 q35,5 30,45 q-3,30 -30,40\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"180.0\" x2=\"116\" y2=\"180.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"164.0\" x2=\"109\" y2=\"164.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"148.0\" x2=\"116\" y2=\"148.0\"/><text class=\"lb\" x=\"94.0\" y=\"148.0\" text-anchor=\"end\" dominant-baseline=\"middle\">100 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"132.0\" x2=\"109\" y2=\"132.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"116.0\" x2=\"116\" y2=\"116.0\"/><text class=\"lb\" x=\"94.0\" y=\"116.0\" text-anchor=\"end\" dominant-baseline=\"middle\">200 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"100.0\" x2=\"109\" y2=\"100.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"84.0\" x2=\"116\" y2=\"84.0\"/><text class=\"lb\" x=\"94.0\" y=\"84.0\" text-anchor=\"end\" dominant-baseline=\"middle\">300 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"68.0\" x2=\"109\" y2=\"68.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"52.0\" x2=\"116\" y2=\"52.0\"/><text class=\"lb\" x=\"94.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">400 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"36.0\" x2=\"109\" y2=\"36.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"20.0\" x2=\"116\" y2=\"20.0\"/><text class=\"lb\" x=\"94.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">500 mL</text></svg>", "expr": "dec"}, {"t": "b) __B1__ mL", "a": {"B1": "250"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"shd\" style=\"fill-opacity:.35\" x=\"100\" y=\"100.0\" width=\"100\" height=\"80.0\"/><path class=\"ln\" fill=\"none\" d=\"M100,20 V180 H200 V20\"/><path class=\"ln\" fill=\"none\" d=\"M200,50 q35,5 30,45 q-3,30 -30,40\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"180.0\" x2=\"116\" y2=\"180.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"164.0\" x2=\"109\" y2=\"164.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"148.0\" x2=\"116\" y2=\"148.0\"/><text class=\"lb\" x=\"94.0\" y=\"148.0\" text-anchor=\"end\" dominant-baseline=\"middle\">100 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"132.0\" x2=\"109\" y2=\"132.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"116.0\" x2=\"116\" y2=\"116.0\"/><text class=\"lb\" x=\"94.0\" y=\"116.0\" text-anchor=\"end\" dominant-baseline=\"middle\">200 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"100.0\" x2=\"109\" y2=\"100.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"84.0\" x2=\"116\" y2=\"84.0\"/><text class=\"lb\" x=\"94.0\" y=\"84.0\" text-anchor=\"end\" dominant-baseline=\"middle\">300 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"68.0\" x2=\"109\" y2=\"68.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"52.0\" x2=\"116\" y2=\"52.0\"/><text class=\"lb\" x=\"94.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">400 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"36.0\" x2=\"109\" y2=\"36.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"20.0\" x2=\"116\" y2=\"20.0\"/><text class=\"lb\" x=\"94.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">500 mL</text></svg>", "expr": "dec"}, {"t": "c) __B1__ L", "a": {"B1": "1.5"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"shd\" style=\"fill-opacity:.35\" x=\"100\" y=\"60.0\" width=\"100\" height=\"120.0\"/><path class=\"ln\" fill=\"none\" d=\"M100,20 V180 H200 V20\"/><path class=\"ln\" fill=\"none\" d=\"M200,50 q35,5 30,45 q-3,30 -30,40\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"180.0\" x2=\"116\" y2=\"180.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"160.0\" x2=\"109\" y2=\"160.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"140.0\" x2=\"109\" y2=\"140.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"120.0\" x2=\"109\" y2=\"120.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"100.0\" x2=\"116\" y2=\"100.0\"/><text class=\"lb\" x=\"94.0\" y=\"100.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1 L</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"80.0\" x2=\"109\" y2=\"80.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"60.0\" x2=\"109\" y2=\"60.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"40.0\" x2=\"109\" y2=\"40.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"20.0\" x2=\"116\" y2=\"20.0\"/><text class=\"lb\" x=\"94.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2 L</text></svg>", "expr": "dec"}, {"t": "d) __B1__ L", "a": {"B1": "0.75"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"shd\" style=\"fill-opacity:.35\" x=\"100\" y=\"120.0\" width=\"100\" height=\"60.0\"/><path class=\"ln\" fill=\"none\" d=\"M100,20 V180 H200 V20\"/><path class=\"ln\" fill=\"none\" d=\"M200,50 q35,5 30,45 q-3,30 -30,40\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"180.0\" x2=\"116\" y2=\"180.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"160.0\" x2=\"109\" y2=\"160.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"140.0\" x2=\"109\" y2=\"140.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"120.0\" x2=\"109\" y2=\"120.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"100.0\" x2=\"116\" y2=\"100.0\"/><text class=\"lb\" x=\"94.0\" y=\"100.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1 L</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"80.0\" x2=\"109\" y2=\"80.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"60.0\" x2=\"109\" y2=\"60.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"40.0\" x2=\"109\" y2=\"40.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"20.0\" x2=\"116\" y2=\"20.0\"/><text class=\"lb\" x=\"94.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2 L</text></svg>", "expr": "dec"}], "sol": "Find the value of each small division first.\na) 300 mL\nb) 250 mL\nc) 1.5 L\nd) 0.75 L"}]}, {"id": "s3", "label": "Ex 8C", "sub": "Mass", "slides": [{"kind": "blank", "p": "Which unit would you use to measure the mass of (mg, g, kg or t)?", "tag": "", "marks": "", "flat": [{"t": "a) a goat → __B1__", "a": {"B1": "kg"}}, {"t": "b) a ship → __B1__", "a": {"B1": "t"}}, {"t": "c) a book → __B1__", "a": {"B1": "g"}}, {"t": "d) a banana → __B1__", "a": {"B1": "g"}}, {"t": "e) a sofa → __B1__", "a": {"B1": "kg"}}, {"t": "f) a raindrop → __B1__", "a": {"B1": "mg"}}, {"t": "g) a refrigerator → __B1__", "a": {"B1": "kg"}}, {"t": "h) a bulldozer → __B1__", "a": {"B1": "t"}}], "sol": "mg: tiny things · g: small things · kg: people and furniture · t: vehicles and very heavy things"}, {"kind": "blank", "p": "Match each object with its mass (A 500 g, B 400 t, C 4 kg, D 1.6 t, E 5 mg, F 70 kg). Type the letter.", "tag": "", "marks": "", "flat": [{"t": "a) a car → __B1__", "a": {"B1": "D"}}, {"t": "b) a cat → __B1__", "a": {"B1": "C"}}, {"t": "c) a tin of beans → __B1__", "a": {"B1": "A"}}, {"t": "d) an ant → __B1__", "a": {"B1": "E"}}, {"t": "e) an aeroplane → __B1__", "a": {"B1": "B"}}, {"t": "f) a man → __B1__", "a": {"B1": "F"}}], "sol": "Think about which size fits each object."}, {"kind": "blank", "p": "Write in grams:", "tag": "", "marks": "", "flat": [{"t": "a) 6 kg = __B1__ g", "a": {"B1": "6000"}, "expr": "dec"}, {"t": "b) 2.5 kg = __B1__ g", "a": {"B1": "2500"}, "expr": "dec"}, {"t": "c) 0.35 kg = __B1__ g", "a": {"B1": "350"}, "expr": "dec"}, {"t": "d) 750 mg = __B1__ g", "a": {"B1": "0.75"}, "expr": "dec"}, {"t": "e) 3600 mg = __B1__ g", "a": {"B1": "3.6"}, "expr": "dec"}], "sol": "1 kg = 1000 g (× 1000); 1000 mg = 1 g (÷ 1000)."}, {"kind": "blank", "p": "Write in kilograms:", "tag": "", "marks": "", "flat": [{"t": "a) 4.2 t = __B1__ kg", "a": {"B1": "4200"}, "expr": "dec"}, {"t": "b) 0.08 t = __B1__ kg", "a": {"B1": "80"}, "expr": "dec"}, {"t": "c) 15 400 g = __B1__ kg", "a": {"B1": "15.4"}, "expr": "dec"}, {"t": "d) 625 g = __B1__ kg", "a": {"B1": "0.625"}, "expr": "dec"}, {"t": "e) 2 t = __B1__ kg", "a": {"B1": "2000"}, "expr": "dec"}], "sol": "1 t = 1000 kg (× 1000); 1000 g = 1 kg (÷ 1000)."}, {"kind": "blank", "p": "Convert:", "tag": "", "marks": "", "flat": [{"t": "a) 9 g → __B1__ mg", "a": {"B1": "9000"}, "expr": "dec"}, {"t": "b) 4800 mg → __B1__ g", "a": {"B1": "4.8"}, "expr": "dec"}, {"t": "c) 920 g → __B1__ kg", "a": {"B1": "0.92"}, "expr": "dec"}, {"t": "d) 3.7 kg → __B1__ g", "a": {"B1": "3700"}, "expr": "dec"}, {"t": "e) 1.25 t → __B1__ kg", "a": {"B1": "1250"}, "expr": "dec"}, {"t": "f) 6300 kg → __B1__ t", "a": {"B1": "6.3"}, "expr": "dec"}], "sol": "To a smaller unit: × 1000. To a larger unit: ÷ 1000."}, {"kind": "blank", "p": "Riya bought a 1.2 kg bag of rice and a 750 g bag of lentils. Find the total mass in kilograms.", "tag": "", "marks": "", "flat": [{"t": "__B1__ kg", "a": {"B1": "1.95"}, "expr": "dec"}], "sol": "750 g = 0.75 kg; 1.2 + 0.75 = 1.95 kg"}, {"kind": "blank", "p": "A biscuit has mass 15 g. Find the mass of 400 biscuits in kilograms.", "tag": "", "marks": "", "flat": [{"t": "__B1__ kg", "a": {"B1": "6"}, "expr": "dec"}], "sol": "400 × 15 = 6000 g = 6 kg"}, {"kind": "blank", "p": "250 sandbags each have mass 20 kg. Find the total mass in tonnes.", "tag": "", "marks": "", "flat": [{"t": "__B1__ t", "a": {"B1": "5"}, "expr": "dec"}], "sol": "250 × 20 = 5000 kg = 5 t"}, {"kind": "blank", "p": "A teacher has 5 g of salt. Each of 30 students needs 150 mg.", "tag": "", "marks": "", "flat": [{"t": "a) Salt needed: __B1__ mg", "a": {"B1": "4500"}, "expr": "dec"}, {"t": "b) Is there enough? (yes/no) __B1__", "a": {"B1": "yes"}}], "sol": "a) 30 × 150 = 4500 mg = 4.5 g\nb) 4.5 g < 5 g, so yes"}, {"kind": "blank", "p": "A bale of hay has mass 25 kg. A truck carries 36 bales.", "tag": "", "marks": "", "flat": [{"t": "a) Mass of hay: __B1__ kg", "a": {"B1": "900"}, "expr": "dec"}, {"t": "b) Is it more or less than a tonne? (more/less) __B1__", "a": {"B1": "less"}}], "sol": "a) 36 × 25 = 900 kg\nb) 900 kg < 1000 kg = 1 t, so less"}, {"kind": "blank", "p": "A log of mass 2.4 t is cut into 60 equal planks. Find the mass of each plank in kilograms.", "tag": "", "marks": "", "flat": [{"t": "__B1__ kg", "a": {"B1": "40"}, "expr": "dec"}], "sol": "2.4 t = 2400 kg; 2400 ÷ 60 = 40 kg"}, {"kind": "blank", "p": "An aeroplane takes off with 96 t of fuel and burns 120 kg per minute. How much fuel is left after 50 minutes (in tonnes)?", "tag": "", "marks": "", "flat": [{"t": "__B1__ t", "a": {"B1": "90"}, "expr": "dec"}], "sol": "Fuel used: 50 × 120 = 6000 kg = 6 t; 96 − 6 = 90 t"}]}, {"id": "s4", "label": "Review 8A", "sub": "Review set 8A", "slides": [{"kind": "blank", "p": "Match each statement with the correct measurement (A 50 km/h, B 4 m³, C 7 hours, D 55 °C, E 350 mL). Type the letter.", "tag": "", "marks": "", "flat": [{"t": "a) juice in a bottle → __B1__", "a": {"B1": "E"}}, {"t": "b) time slept last night → __B1__", "a": {"B1": "C"}}, {"t": "c) speed of a car → __B1__", "a": {"B1": "A"}}, {"t": "d) volume of sand in a sandpit → __B1__", "a": {"B1": "B"}}, {"t": "e) temperature of a cup of tea → __B1__", "a": {"B1": "D"}}], "sol": "a) E\nb) C\nc) A\nd) B\ne) D"}, {"kind": "blank", "p": "Read these scales:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ km/h", "a": {"B1": "90"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">60</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">80</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">120</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">140</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">160</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">180</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"132.0\" y2=\"35.1\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">km/h</text></svg>", "expr": "dec"}, {"t": "b) __B1__ mL", "a": {"B1": "1500"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"shd\" style=\"fill-opacity:.35\" x=\"100\" y=\"60.0\" width=\"100\" height=\"120.0\"/><path class=\"ln\" fill=\"none\" d=\"M100,20 V180 H200 V20\"/><path class=\"ln\" fill=\"none\" d=\"M200,50 q35,5 30,45 q-3,30 -30,40\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"180.0\" x2=\"116\" y2=\"180.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"160.0\" x2=\"109\" y2=\"160.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"140.0\" x2=\"109\" y2=\"140.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"120.0\" x2=\"109\" y2=\"120.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"100.0\" x2=\"116\" y2=\"100.0\"/><text class=\"lb\" x=\"94.0\" y=\"100.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1000 mL</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"80.0\" x2=\"109\" y2=\"80.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"60.0\" x2=\"109\" y2=\"60.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"100\" y1=\"40.0\" x2=\"109\" y2=\"40.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"100\" y1=\"20.0\" x2=\"116\" y2=\"20.0\"/><text class=\"lb\" x=\"94.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2000 mL</text></svg>", "expr": "dec"}, {"t": "c) __B1__ g", "a": {"B1": "600"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"69.2\" y1=\"136.3\" x2=\"80.6\" y2=\"132.6\"/><text class=\"po\" x=\"92.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">100</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">200</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"81.2\" y1=\"60.0\" x2=\"90.9\" y2=\"67.1\"/><text class=\"po\" x=\"100.6\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">300</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">400</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"37.0\"/><text class=\"po\" x=\"150.0\" y=\"49.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">500</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">600</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"218.8\" y1=\"60.0\" x2=\"209.1\" y2=\"67.1\"/><text class=\"po\" x=\"199.4\" y=\"74.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">700</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">800</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"230.8\" y1=\"136.3\" x2=\"219.4\" y2=\"132.6\"/><text class=\"po\" x=\"208.0\" y=\"128.9\" text-anchor=\"middle\" dominant-baseline=\"middle\">900</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">1000</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"185.0\" y2=\"41.4\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">g</text></svg>", "expr": "dec"}], "sol": "a) 90 km/h\nb) 1500 mL\nc) 600 g"}, {"kind": "blank", "p": "Which unit would you use for the mass of (mg, g, kg or t)?", "tag": "", "marks": "", "flat": [{"t": "a) a phone → __B1__", "a": {"B1": "g"}}, {"t": "b) a bus → __B1__", "a": {"B1": "t"}}, {"t": "c) a cupboard → __B1__", "a": {"B1": "kg"}}], "sol": "a) g\nb) t\nc) kg"}, {"kind": "blank", "p": "Write in kilograms:", "tag": "", "marks": "", "flat": [{"t": "a) 2.7 t = __B1__ kg", "a": {"B1": "2700"}, "expr": "dec"}, {"t": "b) 0.89 t = __B1__ kg", "a": {"B1": "890"}, "expr": "dec"}, {"t": "c) 6230 g = __B1__ kg", "a": {"B1": "6.23"}, "expr": "dec"}], "sol": "× 1000 from t; ÷ 1000 from g"}, {"kind": "blank", "p": "A suitcase has mass 21.2 kg. Write this in:", "tag": "", "marks": "", "flat": [{"t": "a) grams: __B1__ g", "a": {"B1": "21200"}, "expr": "dec"}, {"t": "b) tonnes: __B1__ t", "a": {"B1": "0.0212"}, "expr": "dec"}], "sol": "a) × 1000\nb) ÷ 1000"}, {"kind": "blank", "p": "A truck carries 800 kg of soil per load. How many tonnes are carried in 25 loads?", "tag": "", "marks": "", "flat": [{"t": "__B1__ t", "a": {"B1": "20"}, "expr": "dec"}], "sol": "25 × 800 = 20 000 kg = 20 t"}]}, {"id": "s5", "label": "Review 8B", "sub": "Review set 8B", "slides": [{"kind": "blank", "p": "Read each measurement:", "tag": "", "marks": "", "flat": [{"t": "a) __B1__ cm", "a": {"B1": "12.6"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 80\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"12\" y=\"14\" width=\"276\" height=\"44\" rx=\"3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"22.0\" y1=\"14\" x2=\"22.0\" y2=\"28\"/><text class=\"lb\" x=\"22.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">12</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"47.6\" y1=\"14\" x2=\"47.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"73.2\" y1=\"14\" x2=\"73.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"98.8\" y1=\"14\" x2=\"98.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"124.4\" y1=\"14\" x2=\"124.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"150.0\" y1=\"14\" x2=\"150.0\" y2=\"24\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"175.6\" y1=\"14\" x2=\"175.6\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"201.2\" y1=\"14\" x2=\"201.2\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"226.8\" y1=\"14\" x2=\"226.8\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"252.4\" y1=\"14\" x2=\"252.4\" y2=\"20\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"278.0\" y1=\"14\" x2=\"278.0\" y2=\"28\"/><text class=\"lb\" x=\"278.0\" y=\"40.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">13</text><text class=\"lb\" x=\"280.0\" y=\"52.0\" text-anchor=\"end\" dominant-baseline=\"middle\">cm</text><path class=\"dr\" d=\"M175.6,60 l-6,12 h12 z\"/></svg>", "expr": "dec"}, {"t": "b) __B1__ °C", "a": {"B1": "37.2"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 70\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect class=\"sh\" x=\"30\" y=\"21\" width=\"250\" height=\"18\" rx=\"9\"/><circle class=\"dr\" cx=\"26\" cy=\"30\" r=\"12\"/><rect class=\"dr\" x=\"26\" y=\"26\" width=\"115.2\" height=\"8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"40.0\" y1=\"39\" x2=\"40.0\" y2=\"46\"/><text class=\"lb\" x=\"40.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">35</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"44.6\" y1=\"39\" x2=\"44.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"49.2\" y1=\"39\" x2=\"49.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"53.8\" y1=\"39\" x2=\"53.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"58.4\" y1=\"39\" x2=\"58.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"63.0\" y1=\"39\" x2=\"63.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"67.6\" y1=\"39\" x2=\"67.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"72.2\" y1=\"39\" x2=\"72.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"76.8\" y1=\"39\" x2=\"76.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"81.4\" y1=\"39\" x2=\"81.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"86.0\" y1=\"39\" x2=\"86.0\" y2=\"46\"/><text class=\"lb\" x=\"86.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">36</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"90.6\" y1=\"39\" x2=\"90.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"95.2\" y1=\"39\" x2=\"95.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"99.8\" y1=\"39\" x2=\"99.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"104.4\" y1=\"39\" x2=\"104.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"109.0\" y1=\"39\" x2=\"109.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"113.6\" y1=\"39\" x2=\"113.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"118.2\" y1=\"39\" x2=\"118.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"122.8\" y1=\"39\" x2=\"122.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"127.4\" y1=\"39\" x2=\"127.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"132.0\" y1=\"39\" x2=\"132.0\" y2=\"46\"/><text class=\"lb\" x=\"132.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">37</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"136.6\" y1=\"39\" x2=\"136.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"141.2\" y1=\"39\" x2=\"141.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"145.8\" y1=\"39\" x2=\"145.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"150.4\" y1=\"39\" x2=\"150.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"155.0\" y1=\"39\" x2=\"155.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"159.6\" y1=\"39\" x2=\"159.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"164.2\" y1=\"39\" x2=\"164.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"168.8\" y1=\"39\" x2=\"168.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"173.4\" y1=\"39\" x2=\"173.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"178.0\" y1=\"39\" x2=\"178.0\" y2=\"46\"/><text class=\"lb\" x=\"178.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">38</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"182.6\" y1=\"39\" x2=\"182.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"187.2\" y1=\"39\" x2=\"187.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"191.8\" y1=\"39\" x2=\"191.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"196.4\" y1=\"39\" x2=\"196.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"201.0\" y1=\"39\" x2=\"201.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"205.6\" y1=\"39\" x2=\"205.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"210.2\" y1=\"39\" x2=\"210.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"214.8\" y1=\"39\" x2=\"214.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"219.4\" y1=\"39\" x2=\"219.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"224.0\" y1=\"39\" x2=\"224.0\" y2=\"46\"/><text class=\"lb\" x=\"224.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">39</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"228.6\" y1=\"39\" x2=\"228.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"233.2\" y1=\"39\" x2=\"233.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"237.8\" y1=\"39\" x2=\"237.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"242.4\" y1=\"39\" x2=\"242.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"247.0\" y1=\"39\" x2=\"247.0\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"251.6\" y1=\"39\" x2=\"251.6\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"256.2\" y1=\"39\" x2=\"256.2\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"260.8\" y1=\"39\" x2=\"260.8\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.7\" x1=\"265.4\" y1=\"39\" x2=\"265.4\" y2=\"43\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.2\" x1=\"270.0\" y1=\"39\" x2=\"270.0\" y2=\"46\"/><text class=\"lb\" x=\"270.0\" y=\"57.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><text class=\"lb\" x=\"288.0\" y=\"57.0\" text-anchor=\"end\" dominant-baseline=\"middle\">°C</text></svg>", "expr": "dec"}, {"t": "c) __B1__ kg", "a": {"B1": "3.25"}, "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle class=\"sh\" cx=\"150\" cy=\"110\" r=\"93\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"89.9\" y1=\"170.1\" x2=\"98.4\" y2=\"161.6\"/><text class=\"po\" x=\"106.9\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"77.5\" y1=\"154.4\" x2=\"82.6\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"69.2\" y1=\"136.3\" x2=\"74.9\" y2=\"134.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"65.3\" y1=\"116.7\" x2=\"71.2\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"66.0\" y1=\"96.7\" x2=\"77.9\" y2=\"98.6\"/><text class=\"po\" x=\"89.8\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"71.5\" y1=\"77.5\" x2=\"77.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"81.2\" y1=\"60.0\" x2=\"86.1\" y2=\"63.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"94.8\" y1=\"45.4\" x2=\"98.7\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"111.4\" y1=\"34.3\" x2=\"116.9\" y2=\"45.0\"/><text class=\"po\" x=\"122.3\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"130.2\" y1=\"27.3\" x2=\"131.6\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"150.0\" y1=\"25.0\" x2=\"150.0\" y2=\"31.0\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"169.8\" y1=\"27.3\" x2=\"168.4\" y2=\"33.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"188.6\" y1=\"34.3\" x2=\"183.1\" y2=\"45.0\"/><text class=\"po\" x=\"177.7\" y=\"55.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"205.2\" y1=\"45.4\" x2=\"201.3\" y2=\"49.9\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"218.8\" y1=\"60.0\" x2=\"213.9\" y2=\"63.6\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"228.5\" y1=\"77.5\" x2=\"223.0\" y2=\"79.8\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"234.0\" y1=\"96.7\" x2=\"222.1\" y2=\"98.6\"/><text class=\"po\" x=\"210.2\" y=\"100.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"234.7\" y1=\"116.7\" x2=\"228.8\" y2=\"116.2\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"230.8\" y1=\"136.3\" x2=\"225.1\" y2=\"134.4\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:0.8\" x1=\"222.5\" y1=\"154.4\" x2=\"217.4\" y2=\"151.3\"/><line class=\"tk\" style=\"stroke:var(--ink);stroke-width:1.3\" x1=\"210.1\" y1=\"170.1\" x2=\"201.6\" y2=\"161.6\"/><text class=\"po\" x=\"193.1\" y=\"153.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line class=\"arm\" style=\"stroke:var(--danger);stroke-width:2.5\" x1=\"150\" y1=\"110\" x2=\"200.0\" y2=\"51.4\"/><circle class=\"pt\" cx=\"150\" cy=\"110\" r=\"5\"/><text class=\"lb\" x=\"150.0\" y=\"142.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">kg</text></svg>", "expr": "dec"}], "sol": "a) 12.6 cm\nb) 37.2 °C\nc) 3.25 kg"}, {"kind": "blank", "p": "Match each object with its mass (A 25 kg, B 800 mg, C 40 g). Type the letter.", "tag": "", "marks": "", "flat": [{"t": "a) scissors → __B1__", "a": {"B1": "C"}}, {"t": "b) a bicycle → __B1__", "a": {"B1": "A"}}, {"t": "c) a paper clip → __B1__", "a": {"B1": "B"}}], "sol": "a) C\nb) A\nc) B"}, {"kind": "blank", "p": "Convert:", "tag": "", "marks": "", "flat": [{"t": "a) 3200 g → __B1__ kg", "a": {"B1": "3.2"}, "expr": "dec"}, {"t": "b) 4.6 g → __B1__ mg", "a": {"B1": "4600"}, "expr": "dec"}, {"t": "c) 0.7 t → __B1__ kg", "a": {"B1": "700"}, "expr": "dec"}], "sol": "a) ÷ 1000\nb) × 1000\nc) × 1000"}, {"kind": "blank", "p": "Finn posts a book of mass 1.2 kg and a scarf of mass 500 g. Find the total mass in kilograms.", "tag": "", "marks": "", "flat": [{"t": "__B1__ kg", "a": {"B1": "1.7"}, "expr": "dec"}], "sol": "500 g = 0.5 kg; 1.2 + 0.5 = 1.7 kg"}, {"kind": "blank", "p": "How many 600 g tins can be filled from 48 kg of tomatoes?", "tag": "", "marks": "", "flat": [{"t": "__B1__ tins", "a": {"B1": "80"}, "expr": "dec"}], "sol": "48 kg = 48 000 g; 48 000 ÷ 600 = 80"}, {"kind": "blank", "p": "A cricket ball has mass 160 g.", "tag": "", "marks": "", "flat": [{"t": "a) Mass of a box of 40 balls: __B1__ kg", "a": {"B1": "6.4"}, "expr": "dec"}, {"t": "b) A van can carry 1.2 t. How many boxes can it carry? __B1__", "a": {"B1": "187"}, "expr": "dec"}], "sol": "a) 40 × 160 = 6400 g = 6.4 kg\nb) 1.2 t = 1200 kg; 1200 ÷ 6.4 = 187.5, so 187 full boxes"}]}];
/* ================= build slide lists ================= */
var SLIDES = {}; SECTIONS.forEach(function(sec){ SLIDES[sec.id]=sec.slides; });
var TAB_DEFS = SECTIONS.map(function(sec){ return {id:sec.id, label:sec.label, sub:sec.sub}; });

/* ================= state ================= */
function blankItem(slide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    return {status:'unanswered', attempts:0, choice:undefined};
  }
  return {status:'unanswered', curStep:0, stepStates: slide.flat.map(function(){ return {status:'unanswered', attempts:0, inputs:{}}; })};
}
function defaultState(){
  var s={tabs:{}};
  TAB_DEFS.forEach(function(td){
    s.tabs[td.id] = { idx:0, maxReached:0, items: SLIDES[td.id].map(function(sl){ return blankItem(sl); }) };
  });
  return s;
}
var appState = {mode:null, learning:null, quiz:null};
var state = null;      // alias for appState[appState.mode]
var MODE = null;
var activeTab=TAB_DEFS[0].id;

function setMode(m){
  appState.mode = m;
  if(!appState[m]) appState[m] = defaultState();
  state = appState[m];
  MODE = m;
}
/* ================= student accounts (saved on this device) ================= */
var SHEET_KEY='sopaan-g6-ch8';
var ACC_KEY='sopaan-students-v1';
var storageOK=true;
var MEM={};
function lsGet(k){ var r=null; try{ r=localStorage.getItem(k); }catch(e){ storageOK=false; }
  if(r===null||r===undefined) r=MEM[k]||null; try{ return r?JSON.parse(r):null; }catch(e){ return null; } }
function lsSet(k,v){ var j=JSON.stringify(v); MEM[k]=j; try{ localStorage.setItem(k,j); return true; }catch(e){ storageOK=false; return false; } }
try{ localStorage.setItem('sopaan-probe','1'); localStorage.removeItem('sopaan-probe'); }catch(e){ storageOK=false; }
function hashPin(pin,salt){ var h=2166136261, str=salt+'|'+pin; for(var i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=Math.imul(h,16777619)>>>0; } return h.toString(36); }
function accKey(name,roll){ return (name.trim().toLowerCase().replace(/\s+/g,' ')+'#'+roll.trim().toLowerCase()); }
function accounts(){ return lsGet(ACC_KEY)||{students:{}}; }
var student=null; // {key,name,roll}
var records=[];   // finished-tab history for this student on this sheet
function progKey(){ return SHEET_KEY+'::'+student.key; }

function loadState(){
  appState = {mode:null, learning:null, quiz:null}; records=[]; activeTab=TAB_DEFS[0].id;
  var saved=lsGet(progKey());
  if(!saved) return;
  try{
    ['learning','quiz'].forEach(function(m){
      if(saved[m] && saved[m].tabs){
        var fresh = defaultState();
        TAB_DEFS.forEach(function(td){
          if(saved[m].tabs[td.id] && saved[m].tabs[td.id].items && saved[m].tabs[td.id].items.length===SLIDES[td.id].length){
            fresh.tabs[td.id] = saved[m].tabs[td.id];
          }
        });
        appState[m] = fresh;
      }
    });
    if(saved.mode==='learning' || saved.mode==='quiz') appState.mode = saved.mode;
    if(saved.activeTab && TAB_DEFS.some(function(t){ return t.id===saved.activeTab; })) activeTab = saved.activeTab;
    if(Array.isArray(saved.records)) records = saved.records;
  }catch(e){}
}
function saveState(){
  if(!student) return;
  lsSet(progKey(), {mode:appState.mode, learning:appState.learning, quiz:appState.quiz, activeTab:activeTab, records:records, updated:Date.now()});
  var acc=accounts(); if(acc.students[student.key]){ acc.students[student.key].last=Date.now(); lsSet(ACC_KEY,acc); }
}
function addRecord(mode, tabId, correct, revealed, skipped, total){
  records.unshift({at:Date.now(), mode:mode, tab:tabId, correct:correct, revealed:revealed, skipped:skipped, total:total});
  if(records.length>60) records.length=60;
  saveState();
}
function fmtDate(ms){ try{ return new Date(ms).toLocaleString(undefined,{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'}); }catch(e){ return ''; } }

function renderWho(){
  var el=document.getElementById('whoBar');
  if(!student){ el.hidden=true; el.innerHTML=''; return; }
  el.hidden=false;
  el.innerHTML='Signed in as <b>'+esc(student.name)+'</b> · Roll '+esc(student.roll)+
    ' <button id="btnRecord">My record</button> <button id="btnSignOut">Sign out</button>';
  document.getElementById('btnRecord').addEventListener('click', renderRecord);
  document.getElementById('btnSignOut').addEventListener('click', signOut);
}
function signOut(){
  saveState(); student=null; state=null; MODE=null;
  var acc=accounts(); delete acc.current; lsSet(ACC_KEY,acc);
  document.getElementById('modePill').hidden=true;
  renderWho(); renderLogin();
}
function signIn(key){
  var acc=accounts(); var st=acc.students[key]; if(!st) return;
  student={key:key, name:st.name, roll:st.roll};
  acc.current=key; st.last=Date.now(); lsSet(ACC_KEY,acc);
  loadState(); renderWho();
  if(appState.mode==='learning' || appState.mode==='quiz'){
    setMode(appState.mode); document.getElementById('modePill').hidden=false; updateModePill();
    showChrome(true); buildTabbar(); renderSlide();
    showToast('Welcome back, '+st.name.split(' ')[0]+'. Picking up where you left off.');
  } else {
    renderModePicker();
  }
}
function renderLogin(msg){
  showChrome(false);
  var acc=accounts(); var keys=Object.keys(acc.students).sort(function(a,b){ return (acc.students[b].last||0)-(acc.students[a].last||0); });
  var h='<div class="login-card"><h2>Student sign-in</h2>'+
    '<p class="lead">Sign in to save your answers, see your record and continue where you left off next time.</p>';
  if(!storageOK) h+='<div class="login-err">This browser is blocking saved data (for example, a private window). You can still practise, but progress will not be kept after you close the page.</div>';
  if(msg) h+='<div class="login-err">'+esc(msg)+'</div>';
  if(keys.length){
    h+='<div class="known"><span class="known-label">Continue as</span>';
    keys.slice(0,6).forEach(function(k){ var st=acc.students[k];
      h+='<button class="known-btn" data-k="'+esc(k)+'"><span>'+esc(st.name)+' <small>· Roll '+esc(st.roll)+'</small></span><small>'+(st.last?'Last active '+fmtDate(st.last):'')+'</small></button>'; });
    h+='</div>';
  }
  h+='<form id="loginForm" novalidate>'+
    '<div class="fld"><label for="lgName">Full name</label><input id="lgName" autocomplete="name" required></div>'+
    '<div class="fld-row"><div class="fld"><label for="lgRoll">Roll no.</label><input id="lgRoll" required></div>'+
    '<div class="fld"><label for="lgPin">4-digit PIN</label><input id="lgPin" type="password" inputmode="numeric" maxlength="4" autocomplete="off" required></div></div>'+
    '<button class="btn btn-primary" type="submit" style="width:100%;">Sign in</button>'+
    '<p class="login-note">New here? Enter your name, roll no. and a PIN you will remember, and your profile is created. Progress is saved on this device, so use the same device and browser to continue.</p>'+
    '</form></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  wrap.querySelectorAll('.known-btn').forEach(function(b){
    b.addEventListener('click', function(){
      var st=accounts().students[b.dataset.k];
      document.getElementById('lgName').value=st.name; document.getElementById('lgRoll').value=st.roll;
      document.getElementById('lgPin').focus();
    });
  });
  document.getElementById('loginForm').addEventListener('submit', function(e){
    e.preventDefault();
    var name=document.getElementById('lgName').value.trim(), roll=document.getElementById('lgRoll').value.trim(), pin=document.getElementById('lgPin').value.trim();
    if(!name||!roll){ renderLoginErr('Enter your name and roll no.'); return; }
    if(!/^\d{4}$/.test(pin)){ renderLoginErr('Your PIN must be exactly 4 digits.'); return; }
    var k=accKey(name,roll); var acc=accounts();
    if(acc.students[k]){
      if(acc.students[k].pin!==hashPin(pin,k)){ renderLoginErr('That PIN does not match this name and roll no. Try again.'); return; }
    } else {
      acc.students[k]={name:name.replace(/\s+/g,' '), roll:roll, pin:hashPin(pin,k), created:Date.now()};
      lsSet(ACC_KEY,acc);
    }
    signIn(k);
  });
}
function renderLoginErr(m){
  var n=document.getElementById('lgName').value, r=document.getElementById('lgRoll').value;
  renderLogin(m); document.getElementById('lgName').value=n; document.getElementById('lgRoll').value=r; document.getElementById('lgPin').focus();
}
function tabSummary(m){
  var st=appState[m]; if(!st) return null;
  return TAB_DEFS.map(function(td){
    var items=st.tabs[td.id].items, n=items.length;
    var c=items.filter(function(i){return i.status==='correct';}).length;
    var done=items.filter(function(i){return i.status!=='unanswered';}).length;
    return {label:td.label, n:n, done:done, correct:c};
  });
}
function renderRecord(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Measurement: Introduction</p>';
  ['learning','quiz'].forEach(function(m){
    var sum=tabSummary(m);
    h+='<h3>'+(m==='learning'?'📘 Learning Sheet':'📝 Quiz Mode')+'</h3>';
    if(!sum){ h+='<p class="rec-empty">Not started yet.</p>'; return; }
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>Section</th><th>Progress</th><th>Correct first time</th></tr></thead><tbody>';
    sum.forEach(function(r){ var pct=Math.round(r.done/r.n*100);
      h+='<tr><td>'+r.label+'</td><td><span class="rec-bar"><i style="width:'+pct+'%"></i></span>'+r.done+' / '+r.n+'</td><td>'+(m==='quiz'?'—':r.correct+' / '+r.n)+'</td></tr>'; });
    h+='</tbody></table></div>';
  });
  h+='</div><div class="rec-card"><h3>Finished sections</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sections finished yet. Each time you finish a tab, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>When</th><th>Mode</th><th>Section</th><th>Score</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+(r.mode==='learning'?' <span class="rec-empty">('+r.revealed+' revealed, '+r.skipped+' skipped)</span>':'')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){
    if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker();
  });
  window.scrollTo({top:0});
}

/* ================= tab bar ================= */
function buildTabbar(){
  var el=document.getElementById('tabbar');
  el.innerHTML = TAB_DEFS.map(function(t){
    return '<button class="tab-btn'+(t.id===activeTab?' active':'')+'" data-tab="'+t.id+'">'+t.label+'<span class="tab-count">'+SLIDES[t.id].length+'</span></button>';
  }).join('');
  el.querySelectorAll('.tab-btn').forEach(function(btn){
    btn.addEventListener('click', function(){ activeTab=btn.dataset.tab; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  });
}

/* ================= rendering ================= */
function canProceed(item){ return item.status==='correct'||item.status==='revealed'||item.status==='skipped'; }

function renderSlide(){
  if(!state.tabs[activeTab]){ activeTab=TAB_DEFS[0].id; }
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  if(ts.idx>=slides.length||ts.idx<0) ts.idx=0;
  var idx = ts.idx;
  var slide = slides[idx];
  var item = ts.items[idx];

  var tdef=TAB_DEFS.find(function(t){return t.id===activeTab;});
  document.getElementById('spLabel').textContent = tdef.label+' · Question '+(idx+1)+' of '+slides.length;
  document.getElementById('secSub').textContent = tdef.label+' — '+tdef.sub;
  document.getElementById('spFill').style.width = Math.round(((idx)/(Math.max(slides.length-1,1)))*100)+'%';

  var h='<div class="qcard">';
  if(slide.kind==='mcq' || slide.kind==='ar'){
    h += renderChoiceBody(slide, item, idx);
  } else {
    h += renderBlankBody(slide, item, idx);
  }
  h += '<div class="feedback" id="feedbackBox"></div>';
  if(MODE==='learning' && (item.status==='correct'||item.status==='revealed')) h += solutionHTML(slide);
  h += '</div>';

  document.getElementById('wrap').innerHTML = h;
  wireSlideEvents(slide, item, idx);
  restoreFeedback(item);
  renderNavbar(item);
  updateFab();
  saveState();
}

function solutionHTML(slide){
  if(!slide.sol) return '';
  return '<div class="solution"><div class="sol-h">Solution</div>'+slide.sol.split('\n').map(function(l){ return '<div class="sol-line">'+fr(esc(l))+'</div>'; }).join('')+'</div>';
}
var LETTERS=['a','b','c','d'];
function chosenHTML(slide,item){
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(item.choice===undefined) return '';
  var ok=item.choice===slide.correct;
  var h='<div class="chosen '+(ok?'ok':'bad')+'"><b>Your answer:</b> ('+LETTERS[item.choice]+') '+fr(esc(opts[item.choice]))+(ok?' ✓':' ✗')+'</div>';
  if(!ok) h+='<div class="chosen ok"><b>Correct answer:</b> ('+LETTERS[slide.correct]+') '+fr(esc(opts[slide.correct]))+'</div>';
  return h;
}
function renderChoiceBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div>';
  if(slide.kind==='mcq'){
    h += '<div class="qtext">'+fr(esc(slide.text))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  } else {
    h += '<div class="qtext"><span class="qtag" style="margin-left:0;margin-right:6px;">A / R</span>Assertion (A): '+fr(esc(slide.a))+'<br>Reason (R): '+fr(esc(slide.r))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  }
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(MODE==='quiz') h += '<div class="quiz-hint">Quiz mode — pick an option. The correct answer is revealed once you finish this tab.</div>';
  var locked = MODE==='learning' && (item.status==='correct' || item.status==='revealed');
  h += '<div class="options">';
  opts.forEach(function(opt,i){
    var cls='opt';
    if(locked){
      if(i===slide.correct) cls+=' is-correct';
      else if(item.choice===i) cls+=' is-wrong';
      cls+=' locked';
    }
    if(item.choice===i) cls+=' is-chosen';
    h += '<label class="'+cls+'"><input type="radio" name="choice" value="'+i+'" '+(item.choice===i?'checked':'')+' '+(locked?'disabled':'')+'> <span class="opt-l">('+LETTERS[i]+')</span> <span class="opt-t">'+fr(esc(opt))+'</span>'+(item.choice===i?'<span class="opt-tag">'+(locked?(i===slide.correct?'Your answer ✓':'Your answer ✗'):'Selected')+'</span>':'')+'</label>';
  });
  h += '</div>';
  if(locked) h += chosenHTML(slide,item);
  return h;
}

function renderBlankBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div><div class="qtext">';
  if(slide.kind==='case'){ h += '<b>'+esc(slide.title)+'.</b> '+esc(slide.body); }
  else { h += fr(esc(slide.p)); }
  h += (slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  if(slide.marks) h += '<div class="marks-pill">'+slide.marks+'</div>';
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';

  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  var blankCount=0; slide.flat.forEach(function(s){ blankCount+=Object.keys(s.a).length; });

  if(MODE==='quiz'){
    h += '<div class="step-badge">'+blankCount+' blank'+(blankCount===1?'':'s')+' in this question</div>';
    h += '<div class="quiz-hint">Quiz mode — fill in what you can. Correct answers are revealed once you finish this tab.</div>';
    if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
    if(hasExpr) h += '<div class="quiz-hint">Type expressions like <b>(P-2w)/2</b>, <b>2A/b</b> or <b>V/(pi*r^2)</b>. Use ^ for powers and pi for π. Any equivalent form is accepted.</div>';
    h += '<div class="steps">';
    for(var qi=0; qi<total; qi++){
      var qstep = slide.flat[qi];
      var qss = item.stepStates[qi];
      if(qstep.partLabel) h += '<div class="subpart-label">'+esc(qstep.partLabel)+'</div>';
      if(qstep.orDivider) h += '<div class="or-divider">OR</div>';
      var qline = fr(qstep.t);
      Object.keys(qstep.a).forEach(function(bkey){
        var val = qss.inputs[bkey]||'';
        var inp='<input class="blank-input'+(['fv','fe','fl','fm','fi','dec'].indexOf(qstep.expr)>=0?' fr':q(step.expr==='flist'||step.expr==='dlist')?' wide':qstep.expr===true?' expr':(qstep.expr==='words'||qstep.expr==='list'||qstep.expr==='expanded'||qstep.expr==='set'||qstep.expr==='primes'?' wide':''))+'" data-step="'+qi+'" data-bkey="'+bkey+'" value="'+esc(val)+'">';
        qline = qline.replace('__'+bkey+'__', inp);
      });
      if(qstep.fig) h += '<div class="fig">'+qstep.fig+'</div>';
      h += '<div class="step-line">'+qline+'</div>';
    }
    h += '</div>';
    return h;
  }

  if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
  if(hasExpr) h += '<div class="quiz-hint">Type expressions like <b>(P-2w)/2</b>, <b>2A/b</b> or <b>V/(pi*r^2)</b>. Use ^ for powers and pi for π. Any equivalent form is accepted.</div>';
  var locked = item.status==='correct' || item.status==='revealed';
  var upto = locked ? total-1 : item.curStep;
  h += '<div class="step-badge">Step '+(Math.min(item.curStep,total-1)+1)+' of '+total+'</div>';
  h += '<div class="steps">';
  for(var i=0;i<=upto;i++){
    var step = slide.flat[i];
    var ss = item.stepStates[i];
    if(step.partLabel) h += '<div class="subpart-label">'+esc(step.partLabel)+'</div>';
    if(step.orDivider) h += '<div class="or-divider">OR</div>';
    var resolved = ss.status==='correct' || ss.status==='revealed';
    var line = fr(step.t);
    Object.keys(step.a).forEach(function(bkey){
      var fs = ss.inputs['fs_'+bkey];
      var cls = fs==='correct'?'is-correct':(fs==='wrong'?'is-wrong':'');
      var val = ss.inputs[bkey]||'';
      var dis = resolved ? 'disabled':'';
      var inp='<input class="blank-input '+cls+(['fv','fe','fl','fm','fi','dec'].indexOf(step.expr)>=0?' fr':(step.expr==='flist'||step.expr==='dlist')?' wide':step.expr===true?' expr':(step.expr==='words'||step.expr==='list'||step.expr==='expanded'||step.expr==='set'||step.expr==='primes'?' wide':''))+'" data-step="'+i+'" data-bkey="'+bkey+'" value="'+esc(val)+'" '+dis+'>';
      line = line.replace('__'+bkey+'__', inp);
    });
    if(step.fig) h += '<div class="fig">'+step.fig+'</div>';
    h += '<div class="step-line'+(resolved?' resolved':'')+'">'+line+'</div>';
    if(ss.status==='revealed'){
      var reveals=[];
      Object.keys(step.a).forEach(function(bkey){ reveals.push(bkey+' = '+esc(step.a[bkey])); });
      h += '<div class="reveal-note">correct: '+reveals.join(', ')+'</div>';
    }
  }
  h += '</div>';
  return h;
}

var __flash=null;
function restoreFeedback(item){
  var fb=document.getElementById('feedbackBox'); if(!fb) return;
  if(__flash){ fb.className='feedback show '+__flash.c; fb.innerHTML=__flash.h; __flash=null; return; }
  if(MODE==='quiz'){ fb.className='feedback'; fb.innerHTML=''; return; }
  if(item.status==='correct'){ fb.className='feedback show ok'; fb.innerHTML='<b>All done — correct!</b>'; }
  else if(item.status==='revealed'){ fb.className='feedback show reveal'; fb.innerHTML='<b>Answer revealed above.</b> Move on whenever you’re ready.'; }
  else if(item.status==='skipped'){ fb.className='feedback show retry'; fb.innerHTML='Skipped — revisit it anytime from the Question Palette.'; }
  else { fb.className='feedback'; fb.innerHTML=''; }
}

function slideIsAnswered(slide,item){
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return item.stepStates.some(function(ss){ return Object.keys(ss.inputs).some(function(k){ return k.indexOf('fs_')!==0 && ss.inputs[k] && String(ss.inputs[k]).trim()!==''; }); });
}
function renderNavbar(item){
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  var slide = slides[ts.idx];
  var isLast = ts.idx === slides.length-1;
  var h='';
  h += '<button class="btn" id="btnPrev" '+(ts.idx===0?'disabled':'')+'>&larr; Previous</button>';

  if(MODE==='quiz'){
    h += '<button class="btn" id="btnSkip">Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnNext">'+(isLast?'Finish':'Next →')+'</button>';
  } else {
    h += '<button class="btn" id="btnSkip" '+(item.status!=='unanswered'?'disabled':'')+'>Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnCheck" '+(item.status!=='unanswered'?'disabled':'')+'>Check</button>';
    h += '<button class="btn btn-primary" id="btnNext" '+(canProceed(item)?'':'disabled')+'>'+(isLast?'Finish':'Next →')+'</button>';
  }
  document.getElementById('navbarInner').innerHTML = h;

  document.getElementById('btnPrev').addEventListener('click', function(){ if(ts.idx>0){ ts.idx--; renderSlide(); } });

  if(MODE==='quiz'){
    document.getElementById('btnSkip').addEventListener('click', function(){
      item.status='skipped';
      advanceQuiz(ts, slides);
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      item.status = slideIsAnswered(slide,item) ? 'answered' : 'unanswered';
      advanceQuiz(ts, slides);
    });
  } else {
    document.getElementById('btnSkip').addEventListener('click', function(){
      if(item.status==='unanswered'){ item.status='skipped'; renderSlide(); }
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      if(!canProceed(item)) return;
      if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
      else { renderFinished(); }
    });
    document.getElementById('btnCheck').addEventListener('click', function(){ handleCheck(); });
  }
}
function advanceQuiz(ts, slides){
  if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
  else { renderFinished(); }
}

function wireSlideEvents(slide, item, idx){
  document.querySelectorAll('input[type="radio"][name="choice"]').forEach(function(r){
    r.addEventListener('change', function(){ item.choice=parseInt(r.value,10); saveState();
      document.querySelectorAll('.opt').forEach(function(l){ l.classList.remove('is-chosen'); var t=l.querySelector('.opt-tag'); if(t) t.remove(); });
      var lab=r.closest('.opt'); lab.classList.add('is-chosen'); var tg=document.createElement('span'); tg.className='opt-tag'; tg.textContent='Selected'; lab.appendChild(tg); });
  });
  document.querySelectorAll('.blank-input').forEach(function(inp){
    inp.addEventListener('input', function(){
      var si=parseInt(inp.dataset.step,10), bk=inp.dataset.bkey;
      item.stepStates[si].inputs[bk]=inp.value;
      saveState();
    });
  });
}

function handleCheck(){
  var ts = state.tabs[activeTab];
  var slide = SLIDES[activeTab][ts.idx];
  var item = ts.items[ts.idx];
  var fb = document.getElementById('feedbackBox');

  if(slide.kind==='mcq' || slide.kind==='ar'){
    if(item.choice===undefined){ fb.className='feedback show err'; fb.innerHTML='Please choose an option first.'; return; }
    var ok = item.choice===slide.correct;
    if(ok){
      item.status='correct'; playSuccess();
      fb.className='feedback show ok'; fb.innerHTML='<b>Correct!</b>';
    } else {
      item.attempts=(item.attempts||0)+1;
      if(item.attempts>=2){ item.status='revealed'; playReveal(); }
      else { playWrong(); fb.className='feedback show retry'; fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'}; }
    }
    renderSlide();
    return;
  }

  // blank / case
  var step = slide.flat[item.curStep];
  var ss = item.stepStates[item.curStep];
  var blanks = Object.keys(step.a);
  var missing = blanks.some(function(k){ return !ss.inputs[k] || String(ss.inputs[k]).trim()===''; });
  if(missing){ fb.className='feedback show err'; fb.innerHTML='Fill in every blank in this step before checking.'; return; }

  var allGood=true;
  blanks.forEach(function(k){
    var good=answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr);
    ss.inputs['fs_'+k]=good?'correct':'wrong';
    if(!good) allGood=false;
  });

  if(allGood){
    ss.status='correct'; playSuccess();
    advanceStepOrFinish(item, slide);
  } else {
    ss.attempts=(ss.attempts||0)+1;
    if(ss.attempts>=2){
      ss.status='revealed'; playReveal();
      advanceStepOrFinish(item, slide);
    } else {
      playWrong();
      fb.className='feedback show retry';
      fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'};
      renderSlide();
      return;
    }
  }
  renderSlide();
}

function advanceStepOrFinish(item, slide){
  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  if(item.curStep < total-1){
    item.curStep++;
  } else {
    var anyRevealed = item.stepStates.some(function(ss){ return ss.status==='revealed'; });
    item.status = anyRevealed ? 'revealed' : 'correct';
  }
}

/* ================= palette ================= */
var overlay=document.getElementById('overlay');
function statusOf(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  return ts.items[i].status==='unanswered' ? 'locked' : ts.items[i].status;
}
function buildPalette(){
  var slides=SLIDES[activeTab];
  document.getElementById('paletteTitle').textContent = TAB_DEFS.find(function(t){return t.id===activeTab;}).label+' · Question palette';
  var body=document.getElementById('paletteBody');
  var html='';
  for(var i=0;i<slides.length;i++){
    html += '<div class="chip" data-status="'+statusOf(activeTab,i)+'" data-idx="'+i+'">'+(i+1)+'</div>';
  }
  body.innerHTML = html;
  body.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click', function(){
      var i=parseInt(chip.dataset.idx,10);
      var ts=state.tabs[activeTab];
      if(i>ts.maxReached){ showToast('Finish the earlier questions to unlock this one.'); return; }
      ts.idx=i; closePalette(); renderSlide();
    });
  });
}
function openPalette(){ buildPalette(); overlay.classList.add('show'); }
function closePalette(){ overlay.classList.remove('show'); }
var toastTimer;
function showToast(msg){
  var t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer); toastTimer=setTimeout(function(){ t.classList.remove('show'); },2200);
}
document.getElementById('paletteFab').addEventListener('click', openPalette);
document.getElementById('paletteClose').addEventListener('click', closePalette);
overlay.addEventListener('click', function(e){ if(e.target===overlay) closePalette(); });

function updateFab(){
  var slides=SLIDES[activeTab];
  var done=state.tabs[activeTab].items.filter(function(it){ return it.status==='correct'||it.status==='revealed'||it.status==='skipped'; }).length;
  document.getElementById('fabBadge').textContent = done+'/'+slides.length;
}

/* ================= overall progress + finish ================= */
function updateChapterProgress(){
  var total=0, done=0;
  TAB_DEFS.forEach(function(td){
    state.tabs[td.id].items.forEach(function(it){
      total++;
      if(it.status==='correct'||it.status==='revealed'||it.status==='skipped') done++;
    });
  });
  var pct = total>0 ? Math.round((done/total)*100) : 0;
  document.getElementById('cpFill').style.width=pct+'%';
  document.getElementById('cpLabel').textContent=pct+'% complete';
}
function isSlideCorrect(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice===slide.correct;
  return slide.flat.every(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).every(function(k){ return answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr); });
  });
}
function isSlideAttempted(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return slide.flat.some(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).some(function(k){ return ss.inputs[k] && String(ss.inputs[k]).trim()!==''; });
  });
}
function slideLabel(slide){
  var t = slide.kind==='case' ? slide.title : (slide.kind==='ar' ? slide.a : (slide.p||slide.text||''));
  t = String(t);
  return t.length>90 ? t.slice(0,90)+'…' : t;
}
function slideAnswerText(slide, item, correctSide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
    if(correctSide) return '('+LETTERS[slide.correct]+') '+opts[slide.correct];
    return item.choice!==undefined ? '('+LETTERS[item.choice]+') '+opts[item.choice] : '— not attempted —';
  }
  return slide.flat.map(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).map(function(k){
      return correctSide ? step.a[k] : (ss.inputs[k] || '—');
    }).join(', ');
  }).join('  |  ');
}

function renderFinished(){
  if(MODE==='quiz'){ renderQuizResults(); return; }
  var ts=state.tabs[activeTab];
  var correct=ts.items.filter(function(i){return i.status==='correct';}).length;
  var revealed=ts.items.filter(function(i){return i.status==='revealed';}).length;
  var skipped=ts.items.filter(function(i){return i.status==='skipped';}).length;
  var h='<div class="qcard done-card"><div class="big">✨</div><h2>Tab complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">You worked through all '+ts.items.length+' questions in this tab.</p>';
  if(!ts.recorded){ ts.recorded=true; addRecord('learning', activeTab, correct, revealed, skipped, ts.items.length); }
  h+='<div class="score-pills">'+
     '<span class="score-pill" style="background:var(--success-soft);color:var(--success);">'+correct+' correct</span>'+
     '<span class="score-pill" style="background:var(--danger-soft);color:var(--danger);">'+revealed+' revealed</span>'+
     '<span class="score-pill" style="background:var(--gold-soft);color:var(--retry-text);">'+skipped+' skipped</span></div>'+
     '<button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; ts.recorded=false; renderSlide(); });
  updateChapterProgress(); saveState();
}

function renderQuizResults(){
  var ts=state.tabs[activeTab];
  var slides=SLIDES[activeTab];
  var correctCount=0, attemptedCount=0;
  var rowsHtml = slides.map(function(slide,i){
    var item=ts.items[i];
    var ok=isSlideCorrect(activeTab,i);
    var att=isSlideAttempted(activeTab,i);
    if(ok) correctCount++;
    if(att) attemptedCount++;
    var tagCls = ok?'ok':(att?'bad':'na');
    var tagText = ok?'Correct':(att?'Incorrect':'Not attempted');
    var row='<div class="review-row">';
    row+='<span class="review-tag '+tagCls+'">Q'+(i+1)+' · '+tagText+'</span>';
    row+='<div class="review-q">'+fr(esc(slideLabel(slide)))+'</div>';
    row+='<div class="review-ans"><b>Your answer:</b> '+fr(esc(slideAnswerText(slide,item,false)))+'</div>';
    if(!ok) row+='<div class="review-ans" style="color:var(--success);"><b>Correct answer:</b> '+fr(esc(slideAnswerText(slide,item,true)))+'</div>';
    if(slide.sol) row+='<details class="rev-sol"><summary>Show solution</summary>'+solutionHTML(slide)+'</details>';
    row+='</div>';
    return row;
  }).join('');

  addRecord('quiz', activeTab, correctCount, 0, 0, slides.length);
  var h='<div class="qcard done-card" style="text-align:left;">';
  h+='<div style="text-align:center;"><div class="big">🏁</div><h2>Quiz complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">'+correctCount+' / '+slides.length+' correct · '+attemptedCount+' attempted</p></div>';
  h+='<div style="margin-top:16px;">'+rowsHtml+'</div>';
  h+='<div style="text-align:center;margin-top:6px;"><button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  h+='</div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; renderSlide(); });
  playSuccess();
  updateChapterProgress(); saveState();
}

/* ================= mode picker ================= */
function updateModePill(){
  var btn=document.getElementById('modePill');
  if(!btn) return;
  btn.textContent = MODE==='quiz' ? '📝 Quiz Mode · switch' : '📘 Learning Sheet · switch';
}
function showChrome(show){
  document.querySelector('.tabbar').style.display = show?'':'none';
  document.querySelector('.slide-progress').style.display = show?'':'none';
  document.querySelector('.navbar').style.display = show?'':'none';
  document.getElementById('paletteFab').style.display = show?'':'none';
}
function renderModePicker(){
  showChrome(false);
  var wrap=document.getElementById('wrap');
  wrap.innerHTML =
    '<div class="mode-pick">'+
      '<div class="mode-card" data-pick="learning"><div class="mode-icon">📘</div><h3>Learning Sheet</h3>'+
      '<p>Work through each question step by step with instant feedback — two tries, then the correct value is revealed right there so you can keep moving.</p></div>'+
      '<div class="mode-card" data-pick="quiz"><div class="mode-icon">📝</div><h3>Quiz Mode</h3>'+
      '<p>Attempt every question with no hints along the way. Your score and the full answer key are shown together once you finish the tab — just like the real exam.</p></div>'+
    '</div>';
  wrap.querySelectorAll('[data-pick]').forEach(function(card){
    card.addEventListener('click', function(){
      setMode(card.dataset.pick);
      document.getElementById('modePill').hidden=false;
      updateModePill();
      showChrome(true);
      buildTabbar();
      renderSlide();
    });
  });
}
document.getElementById('modePill').addEventListener('click', function(){
  if(!appState.mode){ return; }
  setMode(appState.mode==='quiz' ? 'learning' : 'quiz');
  updateModePill();
  showChrome(true);
  buildTabbar();
  renderSlide();
});

/* ================= boot ================= */
var _origRenderSlide = renderSlide;
renderSlide = function(){ _origRenderSlide(); updateChapterProgress(); updateModePill(); };

renderLogin();
})();
</script>
</body>
</html>
