[index.html](https://github.com/user-attachments/files/26937842/index.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>南九州4天3夜自驾行程</title>
  <meta name="description" content="南九州4天3夜自驾中文旅游网页，包含每日路线、景点卡片、地图链接与住宿信息，手机端优先。" />
  <style>
    :root{
      --bg:#f5f7fb;
      --card:#ffffff;
      --text:#18212f;
      --muted:#667085;
      --line:#e7ecf3;
      --brand:#1677ff;
      --brand-2:#19b5fe;
      --accent:#00b894;
      --warn:#ff9f43;
      --shadow:0 10px 30px rgba(18,38,63,.08);
      --radius:20px;
      --radius-sm:14px;
      --max:1100px;
    }

    *{box-sizing:border-box;}
    html{scroll-behavior:smooth;}
    body{
      margin:0;
      font-family:-apple-system,BlinkMacSystemFont,"Segoe UI","PingFang SC","Hiragino Sans GB","Microsoft YaHei",sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at top right, rgba(25,181,254,.10), transparent 25%),
        radial-gradient(circle at top left, rgba(22,119,255,.08), transparent 20%),
        var(--bg);
      line-height:1.65;
    }

    a{color:inherit;text-decoration:none;}
    img{max-width:100%;display:block;}

    .container{
      width:min(100% - 28px, var(--max));
      margin:0 auto;
    }

    .hero{
      padding:22px 0 14px;
    }

    .hero-card{
      background:linear-gradient(135deg, #1677ff 0%, #19b5fe 100%);
      color:#fff;
      border-radius:28px;
      padding:24px 18px 22px;
      box-shadow:var(--shadow);
      position:relative;
      overflow:hidden;
    }

    .hero-card::after{
      content:"";
      position:absolute;
      right:-30px;
      top:-30px;
      width:140px;
      height:140px;
      border-radius:50%;
      background:rgba(255,255,255,.12);
    }

    .eyebrow{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:6px 12px;
      border-radius:999px;
      background:rgba(255,255,255,.15);
      font-size:12px;
      letter-spacing:.3px;
      margin-bottom:12px;
      backdrop-filter: blur(6px);
    }

    h1{
      margin:0 0 10px;
      font-size:30px;
      line-height:1.2;
    }

    .hero-desc{
      margin:0;
      font-size:14px;
      opacity:.96;
      max-width:720px;
    }

    .hero-meta{
      display:grid;
      grid-template-columns:repeat(2,1fr);
      gap:10px;
      margin-top:18px;
    }

    .meta-box{
      background:rgba(255,255,255,.14);
      border:1px solid rgba(255,255,255,.16);
      border-radius:18px;
      padding:12px;
      backdrop-filter: blur(6px);
    }

    .meta-label{
      font-size:12px;
      opacity:.88;
      margin-bottom:4px;
    }

    .meta-value{
      font-size:15px;
      font-weight:700;
    }

    .top-nav-wrap{
      position:sticky;
      top:0;
      z-index:20;
      backdrop-filter: blur(12px);
      background:rgba(245,247,251,.72);
      border-bottom:1px solid rgba(231,236,243,.8);
    }

    .top-nav{
      display:flex;
      gap:10px;
      overflow:auto;
      padding:12px 0;
      scrollbar-width:none;
    }

    .top-nav::-webkit-scrollbar{display:none;}

    .nav-pill{
      white-space:nowrap;
      padding:10px 14px;
      border-radius:999px;
      background:#fff;
      border:1px solid var(--line);
      box-shadow:0 4px 14px rgba(18,38,63,.05);
      font-size:14px;
      color:#334155;
      flex:0 0 auto;
    }

    .section{
      padding:18px 0;
    }

    .summary{
      display:grid;
      gap:14px;
    }

    .card{
      background:var(--card);
      border:1px solid var(--line);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
    }

    .card-body{padding:18px;}

    .section-title{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      margin-bottom:12px;
    }

    .section-title h2{
      margin:0;
      font-size:22px;
      line-height:1.25;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:6px;
      padding:6px 10px;
      border-radius:999px;
      background:#eef5ff;
      color:var(--brand);
      font-size:12px;
      font-weight:700;
      white-space:nowrap;
    }

    .route-line{
      display:flex;
      flex-wrap:wrap;
      gap:8px;
      margin-top:12px;
    }

    .route-chip{
      padding:8px 12px;
      border-radius:999px;
      background:#f8fafc;
      border:1px solid var(--line);
      color:#334155;
      font-size:13px;
    }

    .grid{
      display:grid;
      gap:14px;
    }

    .day-card{
      overflow:hidden;
    }

    .day-head{
      padding:18px 18px 14px;
      border-bottom:1px solid var(--line);
      background:linear-gradient(180deg,#ffffff 0%, #fbfdff 100%);
    }

    .day-kicker{
      display:inline-block;
      font-size:12px;
      font-weight:700;
      color:var(--brand);
      margin-bottom:6px;
    }

    .day-title{
      margin:0;
      font-size:24px;
      line-height:1.25;
    }

    .day-sub{
      margin:8px 0 0;
      color:var(--muted);
      font-size:14px;
    }

    .day-body{
      padding:18px;
    }

    .timeline{
      display:grid;
      gap:12px;
    }

    .spot{
      position:relative;
      background:#fff;
      border:1px solid var(--line);
      border-radius:18px;
      padding:15px;
    }

    .spot-header{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:12px;
      margin-bottom:8px;
    }

    .spot-title{
      margin:0;
      font-size:18px;
      line-height:1.3;
    }

    .spot-type{
      display:inline-flex;
      align-items:center;
      padding:5px 9px;
      border-radius:999px;
      background:#f1f5f9;
      color:#475569;
      font-size:12px;
      white-space:nowrap;
    }

    .spot-desc{
      margin:0 0 10px;
      color:#475467;
      font-size:14px;
    }

    .spot-meta{
      display:grid;
      gap:8px;
      margin:10px 0 12px;
    }

    .meta-row{
      font-size:13px;
      color:#5b6472;
      background:#f8fafc;
      border:1px solid #eef2f6;
      border-radius:12px;
      padding:9px 10px;
    }

    .actions{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin-top:8px;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:11px 14px;
      border-radius:12px;
      font-size:14px;
      font-weight:700;
      transition:.2s ease;
    }

    .btn-primary{
      background:var(--brand);
      color:#fff;
    }

    .btn-primary:hover{filter:brightness(.96);}

    .btn-light{
      background:#f5f8fc;
      color:#314056;
      border:1px solid var(--line);
    }

    .btn-light:hover{
      background:#eef4fb;
    }

    .hotel{
      border:1px solid #dceef0;
      background:linear-gradient(180deg,#ffffff 0%, #f5fffd 100%);
    }

    .hotel .spot-type{
      background:#e9fbf4;
      color:#108a63;
    }

    .note{
      margin-top:12px;
      padding:12px 14px;
      border-radius:14px;
      background:#fff8ef;
      border:1px solid #ffe3bf;
      color:#8a5a1f;
      font-size:13px;
    }

    .tips{
      display:grid;
      gap:12px;
    }

    .tip-box{
      border:1px dashed #cfe0ff;
      background:#f7fbff;
      border-radius:16px;
      padding:14px;
    }

    .tip-box h3{
      margin:0 0 8px;
      font-size:16px;
    }

    .tip-box p{
      margin:0;
      color:#526071;
      font-size:14px;
    }

    .footer{
      padding:24px 0 40px;
      color:#667085;
      font-size:13px;
      text-align:center;
    }

    @media (min-width: 768px){
      .hero-card{
        padding:34px 30px 28px;
      }
      h1{font-size:42px;}
      .hero-desc{font-size:16px;}
      .hero-meta{
        grid-template-columns:repeat(4,1fr);
      }
      .grid-2{
        display:grid;
        grid-template-columns:1.2fr .8fr;
        gap:16px;
      }
      .timeline{
        grid-template-columns:repeat(2,1fr);
      }
      .full-span{
        grid-column:1 / -1;
      }
    }
  </style>
</head>
<body>

  <div class="top-nav-wrap">
    <div class="container">
      <nav class="top-nav">
        <a class="nav-pill" href="#overview">行程总览</a>
        <a class="nav-pill" href="#day1">Day 1</a>
        <a class="nav-pill" href="#day2">Day 2</a>
        <a class="nav-pill" href="#day3">Day 3</a>
        <a class="nav-pill" href="#day4">Day 4</a>
        <a class="nav-pill" href="#tips">出行提醒</a>
      </nav>
    </div>
  </div>

  <header class="hero">
    <div class="container">
      <div class="hero-card">
        <div class="eyebrow">🚗 手机端优先 · 可点击旅游网页</div>
        <h1>南九州 4 天 3 夜自驾行程</h1>
        <p class="hero-desc">
          这是一条兼顾风景质量、路线顺畅度与驾驶舒适度的南九州自驾方案。
          重点优化思路是：Day 1 沿日南海岸由南向北游览，Day 2 不重复海岸线，
          Day 3 使用樱岛单程渡轮后直接前往雾岛，Day 4 轻松返机场。
        </p>

        <div class="hero-meta">
          <div class="meta-box">
            <div class="meta-label">旅行天数</div>
            <div class="meta-value">4天3夜</div>
          </div>
          <div class="meta-box">
            <div class="meta-label">建议方式</div>
            <div class="meta-value">自驾 / 租车</div>
          </div>
          <div class="meta-box">
            <div class="meta-label">出发地</div>
            <div class="meta-value">鹿儿岛机场</div>
          </div>
          <div class="meta-box">
            <div class="meta-label">结束地</div>
            <div class="meta-value">鹿儿岛机场还车</div>
          </div>
        </div>
      </div>
    </div>
  </header>

  <main>
    <section id="overview" class="section">
      <div class="container">
        <div class="card">
          <div class="card-body">
            <div class="section-title">
              <h2>行程总览</h2>
              <span class="badge">优化版路线</span>
            </div>

            <div class="summary">
              <div class="route-line">
                <span class="route-chip">D1 鹿儿岛机场 → 鹈户神宫 → 青岛 → 宫崎市</span>
                <span class="route-chip">D2 宫崎市 → 鹿儿岛市 → 仙岩园 → 鸭池</span>
                <span class="route-chip">D3 鸭池 → 樱岛 → 雾岛</span>
                <span class="route-chip">D4 雾岛 → 鹿儿岛机场还车</span>
              </div>

              <div class="grid-2">
                <div class="tip-box">
                  <h3>为什么这样排最顺</h3>
                  <p>
                    第一天把日南海岸景点按南到北串联，最后从青岛自然进入宫崎市区；
                    第二天直接高速前往鹿儿岛，把观光重心集中到仙岩园；
                    第三天采用“鹿儿岛港 → 樱岛单程渡轮 → 陆路前往雾岛”的方式，
                    避免多余折返，整体驾驶体验更轻松。
                  </p>
                </div>
                <div class="tip-box">
                  <h3>适合什么样的旅行者</h3>
                  <p>
                    适合第一次玩南九州、希望兼顾自然海景、火山景观、庭园文化，
                    同时又不想每天赶路太累的人。整体路线偏稳、偏顺、偏实用。
                  </p>
                </div>
              </div>

            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="day1" class="section">
      <div class="container">
        <article class="card day-card">
          <div class="day-head">
            <div class="day-kicker">Day 1 · 5月3日</div>
            <h2 class="day-title">鹿儿岛机场 → 日南海岸 → 青岛 → 宫崎市</h2>
            <p class="day-sub">关键词：神话海岸、海景驱车、青岛收尾、宫崎入住</p>
          </div>

          <div class="day-body">
            <div class="route-line" style="margin-bottom:16px;">
              <span class="route-chip">鹿儿岛机场</span>
              <span class="route-chip">鹈户神宫</span>
              <span class="route-chip">Sun Messe 日南 / 道之站 Phoenix（二选一）</span>
              <span class="route-chip">青岛</span>
              <span class="route-chip">宫崎市住宿</span>
            </div>

            <div class="timeline">
              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">鹿儿岛机场（抵达 / 取车）</h3>
                  <span class="spot-type">起点</span>
                </div>
                <p class="spot-desc">建议抵达后先完成租车手续，再直接进入第一天海岸观光路线。</p>
                <div class="spot-meta">
                  <div class="meta-row">建议时间：10:30 抵达后办理租车</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E9%B9%BF%E5%84%BF%E5%B2%9B%E6%9C%BA%E5%9C%BA">打开地图</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">鹈户神宫</h3>
                  <span class="spot-type">景点</span>
                </div>
                <p class="spot-desc">建在海边天然洞穴中的神宫，是南九州海岸线非常有代表性的祈福景点，可体验“投运玉”。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：宫崎县日南市大字宫浦 3232</div>
                  <div class="meta-row">建议停留：45–60 分钟</div>
                  <div class="meta-row">开放参考：06:00–18:00</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E9%B9%88%E6%88%B7%E7%A5%9E%E5%AE%AB%20%E5%AE%AB%E5%B4%8E%E5%8E%BF%E6%97%A5%E5%8D%97%E5%B8%82%E5%A4%A7%E5%AD%97%E5%AE%AE%E6%B5%A63232">打开地图</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">Sun Messe 日南</h3>
                  <span class="spot-type">可选景点</span>
                </div>
                <p class="spot-desc">海边摩艾石像是这条线上最适合拍照的点之一，适合想保留“照片感”的旅客。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：宫崎县日南市大字宫浦 2650</div>
                  <div class="meta-row">建议停留：45–60 分钟</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Sun%20Messe%20%E6%97%A5%E5%8D%97%20%E5%AE%AB%E5%B4%8E%E5%8E%BF%E6%97%A5%E5%8D%97%E5%B8%82%E5%A4%A7%E5%AD%97%E5%AE%AE%E6%B5%A62650">打开地图</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">道之站 Phoenix</h3>
                  <span class="spot-type">可选景点</span>
                </div>
                <p class="spot-desc">如果更重视效率，这里比正式景区更适合短暂停留，可俯瞰太平洋与“鬼之洗衣板”海岸地貌。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：381-1 Uchiumi, Miyazaki, 889-2301</div>
                  <div class="meta-row">建议停留：10–20 分钟</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Station%20Phoenix%20381-1%20Uchiumi%20Miyazaki%20889-2301">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="http://michinoekiphoenix.jp/">官方网站</a>
                </div>
              </div>

              <div class="spot full-span">
                <div class="spot-header">
                  <h3 class="spot-title">青岛神社 / 青岛海岸</h3>
                  <span class="spot-type">景点</span>
                </div>
                <p class="spot-desc">这一天建议把青岛放在最后，作为海岸线收尾。可看“鬼之洗衣板”地貌，也能顺路步行参拜青岛神社。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：宫崎县宫崎市青岛 2-13-1</div>
                  <div class="meta-row">建议停留：60–90 分钟</div>
                  <div class="meta-row">提示：车辆不能开进岛内，请停在参道入口附近停车场后步行进入</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E9%9D%92%E5%B2%9B%E7%A5%9E%E7%A4%BE%20%E5%AE%AB%E5%B4%8E%E5%8E%BF%E5%AE%AB%E5%B4%8E%E5%B8%82%E9%9D%92%E5%B2%9B2-13-1">打开地图</a>
                </div>
              </div>

              <div class="spot hotel full-span">
                <div class="spot-header">
                  <h3 class="spot-title">住宿：t25（宫崎）</h3>
                  <span class="spot-type">住宿</span>
                </div>
                <p class="spot-desc">建议第一晚入住宫崎市区，便于第二天一早直接上高速前往鹿儿岛市。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：宫崎市上野町 9-17</div>
                  <div class="meta-row">入住参考：15:00–19:00</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E5%AE%AB%E5%B4%8E%E5%B8%82%E4%B8%8A%E9%87%8E%E7%94%BA9-17">打开地图</a>
                </div>
                <div class="note">⚠️ 关键提醒：建议最晚 18:00 前到达办理入住，避免影响 check-in。</div>
              </div>
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="day2" class="section">
      <div class="container">
        <article class="card day-card">
          <div class="day-head">
            <div class="day-kicker">Day 2 · 5月4日</div>
            <h2 class="day-title">宫崎市 → 鹿儿岛市 → 仙岩园 → 鸭池</h2>
            <p class="day-sub">关键词：高速直行、萨摩庭园、鹿儿岛市内住宿</p>
          </div>

          <div class="day-body">
            <div class="route-line" style="margin-bottom:16px;">
              <span class="route-chip">宫崎市出发</span>
              <span class="route-chip">高速直达鹿儿岛市</span>
              <span class="route-chip">仙岩园</span>
              <span class="route-chip">鸭池住宿</span>
            </div>

            <div class="timeline">
              <div class="spot full-span">
                <div class="spot-header">
                  <h3 class="spot-title">仙岩园（矶庭园）</h3>
                  <span class="spot-type">核心景点</span>
                </div>
                <p class="spot-desc">第二天最推荐把观光重点集中在仙岩园。这里是鹿儿岛代表性的历史庭园，以樱岛和锦江湾为借景，极具地方特色。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：鹿儿岛县鹿儿岛市吉野町 9700-1</div>
                  <div class="meta-row">建议停留：2–3 小时</div>
                  <div class="meta-row">开放参考：09:00–17:00（最晚入场 16:30）</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E4%BB%99%E5%B2%A9%E5%9B%AD%20%E9%B9%BF%E5%84%BF%E5%B2%9B%E5%8E%BF%E9%B9%BF%E5%84%BF%E5%B2%9B%E5%B8%82%E5%90%89%E9%87%8E%E7%94%BA9700-1">打开地图</a>
                </div>
              </div>

              <div class="spot hotel full-span">
                <div class="spot-header">
                  <h3 class="spot-title">住宿：Art Hotel Kagoshima</h3>
                  <span class="spot-type">住宿</span>
                </div>
                <p class="spot-desc">建议第二晚住在鹿儿岛市鸭池一带，方便第三天前往鹿儿岛港搭乘樱岛渡轮。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：鹿儿岛市鸭池新町 22-1</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Art%20Hotel%20Kagoshima%20%E9%B9%BF%E5%84%BF%E5%B2%9B%E5%B8%82%E9%B8%AD%E6%B1%A0%E6%96%B0%E7%94%BA22-1">打开地图</a>
                </div>
              </div>
            </div>

            <div class="note">
              建议这一天不要再重复安排海岸观光点。因为 Day 1 已经看过日南海岸，把时间集中留给鹿儿岛市区会更合理。
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="day3" class="section">
      <div class="container">
        <article class="card day-card">
          <div class="day-head">
            <div class="day-kicker">Day 3 · 5月5日</div>
            <h2 class="day-title">鸭池 → 鹿儿岛港 → 樱岛 → 雾岛</h2>
            <p class="day-sub">关键词：单程渡轮、火山展望、黑醋午餐、雾岛入住</p>
          </div>

          <div class="day-body">
            <div class="route-line" style="margin-bottom:16px;">
              <span class="route-chip">鸭池</span>
              <span class="route-chip">鹿儿岛港</span>
              <span class="route-chip">樱岛单程渡轮</span>
              <span class="route-chip">汤之平展望所</span>
              <span class="route-chip">有余力加有村熔岩展望所</span>
              <span class="route-chip">桷志田午餐</span>
              <span class="route-chip">雾岛住宿</span>
            </div>

            <div class="timeline">
              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">鹿儿岛港（樱岛渡轮乘船点）</h3>
                  <span class="spot-type">交通节点</span>
                </div>
                <p class="spot-desc">建议从鹿儿岛港搭乘前往樱岛的单程渡轮，避免玩完再折返回市区，整体路线更顺。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：4-1 Honkoshinmachi, Kagoshima, 892-0814</div>
                  <div class="meta-row">说明：适合“去程乘船，返程走陆路”</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Ferry%20Boarding%20to%20Sakurajima%204-1%20Honkoshinmachi%20Kagoshima%20892-0814">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="https://www.city.kagoshima.lg.jp/sakurajima-ferry/index.html">渡轮官网</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">汤之平展望所</h3>
                  <span class="spot-type">推荐景点</span>
                </div>
                <p class="spot-desc">如果樱岛只停留一个地方，优先推荐这里。视野开阔，很适合感受樱岛火山的整体气势。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：1025 Sakurajimakoikecho, Kagoshima, 891-1418</div>
                  <div class="meta-row">建议停留：20–30 分钟</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Yunohira%20Observation%20Deck%201025%20Sakurajimakoikecho%20Kagoshima%20891-1418">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="http://www.sakurajima.gr.jp/tourism/000350.html">景点信息</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">有村熔岩展望所</h3>
                  <span class="spot-type">可选景点</span>
                </div>
                <p class="spot-desc">如果当天时间宽裕，可增加这一站。这里更适合近距离感受熔岩地形和火山地貌的力量感。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：952 Arimuracho, Kagoshima, 891-1545</div>
                  <div class="meta-row">建议停留：20–30 分钟</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Arimura%20Lava%20Observation%20Deck%20952%20Arimuracho%20Kagoshima%20891-1545">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="https://www.sakurajima.gr.jp/spot/4090.html">景点信息</a>
                </div>
              </div>

              <div class="spot">
                <div class="spot-header">
                  <h3 class="spot-title">黑醋餐厅 桷志田</h3>
                  <span class="spot-type">午餐推荐</span>
                </div>
                <p class="spot-desc">把午餐安排在这里很顺路。离开樱岛后往福山方向前进时可自然接上，同时兼顾用餐与轻观光。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：311-2 Fukuyamacho Fukuyama, Kirishima, Kagoshima 899-4501</div>
                  <div class="meta-row">建议停留：60–90 分钟</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Kurozu%20Restaurant%20Kakuida%20311-2%20Fukuyamacho%20Fukuyama%20Kirishima%20Kagoshima%20899-4501">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="http://kurozurestaurant.com/">官方网站</a>
                </div>
              </div>

              <div class="spot hotel full-span">
                <div class="spot-header">
                  <h3 class="spot-title">住宿：Hotel Kyocera（雾岛）</h3>
                  <span class="spot-type">住宿</span>
                </div>
                <p class="spot-desc">第三晚建议住在雾岛，方便最后一天轻松前往鹿儿岛机场还车。</p>
                <div class="spot-meta">
                  <div class="meta-row">地址：1409-1 Hayatocho Mitsugi, Kirishima, Kagoshima 899-5117</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=Hotel%20Kyocera%201409-1%20Hayatocho%20Mitsugi%20Kirishima%20Kagoshima%20899-5117">打开地图</a>
                  <a class="btn btn-light" target="_blank" href="https://www.h-kyocera.co.jp/">官方网站</a>
                </div>
              </div>
            </div>

            <div class="note">
              Day 3 的核心优化点是：不要坐樱岛往返渡轮。单程上岛后直接往雾岛方向开，是这条路线最省折返的走法。
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="day4" class="section">
      <div class="container">
        <article class="card day-card">
          <div class="day-head">
            <div class="day-kicker">Day 4 · 5月6日</div>
            <h2 class="day-title">雾岛 → 鹿儿岛机场还车</h2>
            <p class="day-sub">关键词：轻松收尾、预留加油和还车时间</p>
          </div>

          <div class="day-body">
            <div class="timeline">
              <div class="spot full-span">
                <div class="spot-header">
                  <h3 class="spot-title">酒店出发 → 鹿儿岛机场还车</h3>
                  <span class="spot-type">返程</span>
                </div>
                <p class="spot-desc">最后一天建议不再安排额外景点，把时间留给早餐、退房、加油、还车和机场手续，整体会更安心。</p>
                <div class="spot-meta">
                  <div class="meta-row">建议：至少预留 2–3 小时用于加油、还车与登机前准备</div>
                </div>
                <div class="actions">
                  <a class="btn btn-primary" target="_blank" href="https://www.google.com/maps/search/?api=1&query=%E9%B9%BF%E5%84%BF%E5%B2%9B%E6%9C%BA%E5%9C%BA">打开机场地图</a>
                </div>
              </div>
            </div>

            <div class="note">
              最后一天最怕的是还车时间估算过短。即使路线不远，也建议保守安排，避免因为加油或排队影响节奏。
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="tips" class="section">
      <div class="container">
        <div class="card">
          <div class="card-body">
            <div class="section-title">
              <h2>出行提醒</h2>
              <span class="badge">实用建议</span>
            </div>

            <div class="tips">
              <div class="tip-box">
                <h3>1. 第一天尽量按南 → 北顺序玩</h3>
                <p>这样青岛会自然成为海岸观光的最后一站，结束后直接进宫崎市区，路线最干净。</p>
              </div>
              <div class="tip-box">
                <h3>2. 第二天不要重复海岸观光</h3>
                <p>既然 Day 1 已看过海景，Day 2 直接把重心留给鹿儿岛市内的仙岩园会更划算。</p>
              </div>
              <div class="tip-box">
                <h3>3. 樱岛建议单程渡轮</h3>
                <p>“去程坐船，上岛后一路往雾岛开”比往返渡轮更省时间，也更符合整体动线。</p>
              </div>
              <div class="tip-box">
                <h3>4. 最后一天不要塞景点</h3>
                <p>还车、加油、机场流程都可能比想象中更耗时，最后一天保守安排是最安全的。</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="container">
      本页为南九州 4 天 3 夜中文行程网页示例，适合直接保存为 HTML 使用，也可继续扩展为更完整的旅游网站。
    </div>
  </footer>

</body>
</html>
