# 设计系统与全面交互规范 (Design System & Interactive Spec)

---
name: Precision & Insight
colors:
  surface: '#f9f9ff'
  surface-dim: '#d3daea'
  surface-bright: '#f9f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f0f3ff'
  surface-container: '#e7eefe'
  surface-container-high: '#e2e8f8'
  surface-container-highest: '#dce2f3'
  on-surface: '#151c27'
  on-surface-variant: '#444748'
  inverse-surface: '#2a313d'
  inverse-on-surface: '#ebf1ff'
  outline: '#747878'
  outline-variant: '#c4c7c7'
  surface-tint: '#5f5e5e'
  primary: '#000000'
  on-primary: '#ffffff'
  primary-container: '#1c1b1b'
  on-primary-container: '#858383'
  inverse-primary: '#c8c6c5'
  secondary: '#4b41e1'
  on-secondary: '#ffffff'
  secondary-container: '#645efb'
  on-secondary-container: '#fffbff'
  tertiary: '#000000'
  on-tertiary: '#ffffff'
  tertiary-container: '#191c1d'
  on-tertiary-container: '#828485'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e5e2e1'
  primary-fixed-dim: '#c8c6c5'
  on-primary-fixed: '#1c1b1b'
  on-primary-fixed-variant: '#474646'
  secondary-fixed: '#e2dfff'
  secondary-fixed-dim: '#c3c0ff'
  on-secondary-fixed: '#0f0069'
  on-secondary-fixed-variant: '#3323cc'
  tertiary-fixed: '#e1e3e4'
  tertiary-fixed-dim: '#c5c7c8'
  on-tertiary-fixed: '#191c1d'
  on-tertiary-fixed-variant: '#454748'
  background: '#f9f9ff'
  on-background: '#151c27'
  surface-variant: '#dce2f3'
typography:
  display-lg:
    fontFamily: Manrope
    fontSize: 64px
    fontWeight: '800'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Manrope
    fontSize: 40px
    fontWeight: '800'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Manrope
    fontSize: 32px
    fontWeight: '700'
    lineHeight: '1.3'
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Manrope
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.4'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  label-caps:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: '600'
    lineHeight: '1.0'
    letterSpacing: 0.1em
  metric-value:
    fontFamily: Manrope
    fontSize: 48px
    fontWeight: '700'
    lineHeight: '1.0'
    letterSpacing: -0.03em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  container-max: 1200px
  section-gap-lg: 160px
  section-gap-sm: 80px
  gutter: 32px
  stack-xs: 4px
  stack-sm: 8px
  stack-md: 16px
  stack-lg: 24px
---

## 1. 按钮与交互路由逻辑 (Interaction Specification)

* **顶部导航栏 (Navbar)**:
  * 点击 LOGO `Beiran Wu` 或 `首页`: 跳转至【首页】（展示 Hero 级个人介绍与精选作品）。
  * 点击 `作品`: 跳转至【作品集中页】，展示精选案例列表。
  * 点击 `关于我`: 跳转至【关于我页】，展示设计哲学与流程。
  * 点击 `简历`: 跳转至【简历页】，支持在线浏览与下载 PDF。
  * 点击 `Contact Me`: 唤醒全局联系弹窗。
* **页面内部按钮**:
  * 【首页/关于我】中的 `查看作品`: 动态无缝切换至【作品】视图。
  * 【作品页】中的卡片或 `查看案例`: 弹出作品详情模态框。
  * 【简历页】中的 `下载 PDF 简历`: 触发文件下载。
  * 【底部 CTA】的 `联系我`: 打开联系弹窗。

---

## 2. 完整前端全交互代码 (`index.html`)

```html
<!DOCTYPE html>
<html class="light" lang="zh-CN">
<head>
<meta charset="utf-8">
<meta content="width=device-width, initial-scale=1.0" name="viewport">
<title>Beiran Wu - UI/UX Designer & Product Manager</title>
<!-- Fonts -->
<link href="[https://fonts.googleapis.com](https://fonts.googleapis.com)" rel="preconnect">
<link crossorigin="" href="[https://fonts.gstatic.com](https://fonts.gstatic.com)" rel="preconnect">
<link href="[https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&amp;family=JetBrains+Mono:wght@600&amp;family=Manrope:wght@600;700;800&amp;display=swap](https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&amp;family=JetBrains+Mono:wght@600&amp;family=Manrope:wght@600;700;800&amp;display=swap)" rel="stylesheet">
<!-- Material Symbols -->
<link href="[https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap](https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&amp;display=swap)" rel="stylesheet">
<style>
  .material-symbols-outlined {
    font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
  }
</style>
<!-- Tailwind CSS -->
<script src="[https://cdn.tailwindcss.com?plugins=forms,container-queries](https://cdn.tailwindcss.com?plugins=forms,container-queries)"></script>
<script id="tailwind-config">
  tailwind.config = {
    darkMode: "class",
    theme: {
      extend: {
        "colors": {
          "secondary-container": "#645efb",
          "inverse-on-surface": "#ebf1ff",
          "surface": "#f9f9ff",
          "outline": "#747878",
          "on-secondary-fixed": "#0f0069",
          "on-tertiary-fixed": "#191c1d",
          "on-error": "#ffffff",
          "secondary-fixed-dim": "#c3c0ff",
          "on-primary-container": "#858383",
          "surface-container-high": "#e2e8f8",
          "on-surface-variant": "#444748",
          "primary": "#000000",
          "tertiary-container": "#191c1d",
          "on-tertiary": "#ffffff",
          "tertiary": "#000000",
          "primary-container": "#1c1b1b",
          "surface-variant": "#dce2f3",
          "error-container": "#ffdad6",
          "on-primary-fixed": "#1c1b1b",
          "inverse-surface": "#2a313d",
          "on-tertiary-container": "#828485",
          "tertiary-fixed": "#e1e3e4",
          "secondary": "#4b41e1",
          "on-secondary-container": "#fffbff",
          "surface-dim": "#d3daea",
          "on-secondary": "#ffffff",
          "surface-tint": "#5f5e5e",
          "surface-container-highest": "#dce2f3",
          "on-tertiary-fixed-variant": "#454748",
          "surface-container-low": "#f0f3ff",
          "surface-bright": "#f9f9ff",
          "background": "#f9f9ff"
        },
        "borderRadius": {
          "DEFAULT": "0.125rem",
          "sm": "0.125rem",
          "md": "0.375rem",
          "lg": "0.5rem",
          "xl": "0.75rem",
          "full": "9999px"
        },
        "spacing": {
          "stack-xs": "4px",
          "stack-sm": "8px",
          "stack-md": "16px",
          "stack-lg": "24px",
          "section-gap-sm": "80px",
          "section-gap-lg": "160px",
          "gutter": "32px",
          "container-max": "1200px"
        },
        "fontFamily": {
          "label-caps": ["JetBrains Mono"],
          "metric-value": ["Manrope"],
          "headline-sm": ["Manrope"],
          "display-lg-mobile": ["Manrope"],
          "body-md": ["Inter"],
          "body-lg": ["Inter"],
          "headline-md": ["Manrope"],
          "display-lg": ["Manrope"]
        },
        "fontSize": {
          "label-caps": ["12px", { "lineHeight": "1.0", "letterSpacing": "0.1em", "fontWeight": "600" }],
          "metric-value": ["48px", { "lineHeight": "1.0", "letterSpacing": "-0.03em", "fontWeight": "700" }],
          "headline-sm": ["24px", { "lineHeight": "1.4", "fontWeight": "600" }],
          "display-lg-mobile": ["40px", { "lineHeight": "1.2", "letterSpacing": "-0.02em", "fontWeight": "800" }],
          "body-md": ["16px", { "lineHeight": "1.6", "fontWeight": "400" }],
          "body-lg": ["18px", { "lineHeight": "1.6", "fontWeight": "400" }],
          "headline-md": ["32px", { "lineHeight": "1.3", "letterSpacing": "-0.01em", "fontWeight": "700" }],
          "display-lg": ["64px", { "lineHeight": "1.1", "letterSpacing": "-0.02em", "fontWeight": "800" }]
        }
      }
    }
  }
</script>
</head>
<body class="bg-background text-on-surface font-body-md antialiased selection:bg-secondary-container selection:text-inverse-on-surface">

  <!-- Sticky Global Navigation -->
  <header class="bg-surface/80 backdrop-blur-md top-0 z-40 sticky border-b border-outline-variant/30 shadow-sm">
    <div class="flex justify-between items-center h-20 px-gutter max-w-container-max mx-auto relative">
      <a class="font-headline-sm text-headline-sm tracking-tighter text-primary cursor-pointer hover:opacity-80 transition-opacity" onclick="navigateTo('home')">Beiran Wu</a>
      
      <!-- Desktop Menu -->
      <nav class="hidden md:flex gap-stack-lg items-center h-full font-label-caps text-label-caps">
        <button id="nav-home" class="nav-btn text-secondary border-b-2 border-secondary pb-1 h-full flex items-center mt-1" onclick="navigateTo('home')">首页</button>
        <button id="nav-works" class="nav-btn text-on-surface-variant hover:text-primary transition-colors h-full flex items-center" onclick="navigateTo('works')">作品</button>
        <button id="nav-about" class="nav-btn text-on-surface-variant hover:text-primary transition-colors h-full flex items-center" onclick="navigateTo('about')">关于我</button>
        <button id="nav-resume" class="nav-btn text-on-surface-variant hover:text-primary transition-colors h-full flex items-center" onclick="navigateTo('resume')">简历</button>
      </nav>
      
      <button class="hidden md:flex items-center justify-center bg-tertiary text-on-tertiary rounded-sm px-6 py-3 font-label-caps text-label-caps hover:bg-surface-tint transition-all shadow-sm" onclick="openContactModal()">
        Contact Me
      </button>

      <!-- Mobile Menu Button -->
      <button class="md:hidden flex items-center text-on-surface p-2" onclick="toggleMobileMenu()">
        <span class="material-symbols-outlined text-[24px]">menu</span>
      </button>

      <!-- Mobile Drawer Menu -->
      <div id="mobile-menu" class="hidden absolute top-20 left-0 w-full bg-surface border-b border-outline-variant/30 flex-col p-6 gap-4 font-label-caps text-label-caps md:hidden shadow-lg z-50">
        <button class="text-left py-2 text-on-surface" onclick="navigateTo('home'); toggleMobileMenu();">首页</button>
        <button class="text-left py-2 text-on-surface" onclick="navigateTo('works'); toggleMobileMenu();">作品</button>
        <button class="text-left py-2 text-on-surface" onclick="navigateTo('about'); toggleMobileMenu();">关于我</button>
        <button class="text-left py-2 text-on-surface" onclick="navigateTo('resume'); toggleMobileMenu();">简历</button>
        <button class="bg-tertiary text-on-tertiary rounded-sm py-3 mt-2 text-center" onclick="openContactModal(); toggleMobileMenu();">Contact Me</button>
      </div>
    </div>
  </header>

  <!-- Main Dynamic Views Container -->
  <main class="w-full">
    
    <!-- Page 1: 首页 (Home) -->
    <div id="view-home" class="page-view transition-opacity duration-300">
      <section class="md:py-section-gap-lg px-gutter max-w-container-max mx-auto grid grid-cols-1 lg:grid-cols-12 gap-gutter items-center pt-stack-lg">
        <div class="lg:col-span-7 flex flex-col gap-stack-lg order-2 lg:order-1">
          <h1 class="text-7xl font-bold text-primary tracking-tighter">吴贝然</h1>
          <div class="inline-flex items-center gap-2 font-label-caps text-label-caps text-on-surface-variant bg-surface-container-low px-4 py-2 rounded-full w-fit">
            <span class="w-2 h-2 rounded-full bg-secondary"></span>
            UI/UX 设计师 &amp; 产品经理
          </div>
          <h2 class="font-display-lg-mobile md:font-display-lg text-primary tracking-tight">
            专注与洞察 <br><span class="text-secondary">(Precision &amp; Insight)</span>
          </h2>
          <p class="font-body-lg text-on-surface-variant max-w-2xl leading-relaxed">
            融合严谨的系统思维与直觉化的视觉设计，专注打造高转化率与极佳体验的数字产品。
          </p>
          <div class="flex flex-wrap gap-stack-md pt-stack-sm">
            <button class="bg-primary text-on-primary rounded-sm px-8 py-4 font-label-caps text-label-caps hover:bg-surface-tint transition-all" onclick="navigateTo('works')">
              查看精选作品
            </button>
            <button class="border border-outline-variant text-primary rounded-sm px-8 py-4 font-label-caps text-label-caps hover:bg-surface-container-low transition-all" onclick="navigateTo('about')">
              了解设计理念
            </button>
          </div>
        </div>
        <div class="lg:col-span-5 order-1 lg:order-2 flex justify-center lg:justify-end relative">
          <div class="rounded-lg overflow-hidden border border-outline-variant/30 shadow-sm w-full max-w-[400px] aspect-[4/5]">
            <img alt="Profile Photo" class="w-full h-full object-cover" src="[https://lh3.googleusercontent.com/aida-public/AB6AXuA2x4c3SQnKrZRiq88VnenJajlupiyU-LStF_l-XfXNHs26GJ2e0LbT4-UCJhwamZSVwzDg5IBceSAnqenZTxwVqPI3YkYK6tU2VGhglI-pkbINPC-vhdVp7LxQT7OXdNvDiFsxAS_G28JfpgNwOofqLy1Ipx5Vd_5nnS6TlNSTrxTaWPKACjdOx7GLykhar4Qrji4SJQM5VWbYTSfWvoOLlorZAEu8yg3pezhBg4qOSqECmPnRrzUVKQFCrzd9kt-Zow](https://lh3.googleusercontent.com/aida-public/AB6AXuA2x4c3SQnKrZRiq88VnenJajlupiyU-LStF_l-XfXNHs26GJ2e0LbT4-UCJhwamZSVwzDg5IBceSAnqenZTxwVqPI3YkYK6tU2VGhglI-pkbINPC-vhdVp7LxQT7OXdNvDiFsxAS_G28JfpgNwOofqLy1Ipx5Vd_5nnS6TlNSTrxTaWPKACjdOx7GLykhar4Qrji4SJQM5VWbYTSfWvoOLlorZAEu8yg3pezhBg4qOSqECmPnRrzUVKQFCrzd9kt-Zow)">
          </div>
        </div>
      </section>
    </div>

    <!-- Page 2: 作品页 (Works) -->
    <div id="view-works" class="page-view hidden transition-opacity duration-300">
      <section class="py-section-gap-sm px-gutter max-w-container-max mx-auto">
        <div class="flex flex-col gap-stack-sm mb-stack-lg">
          <h2 class="font-headline-md text-headline-md text-primary">精选作品集 (Selected Works)</h2>
          <p class="font-body-lg text-on-surface-variant max-w-3xl">包含了设计系统、B端复杂工具与C端产品的项目案例。</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-gutter">
          <!-- Work Card 1 -->
          <div class="bg-surface-container-lowest border border-outline-variant/50 rounded-lg p-6 flex flex-col gap-4 hover:border-secondary transition-all cursor-pointer group" onclick="openProjectDetails('企业级 AI 数据分析平台', '通过重构复杂的数据展现逻辑，使用户完成关键指标决策的时间缩短 35%。')">
            <div class="w-full aspect-video bg-surface-container-high rounded-md overflow-hidden relative">
              <div class="absolute inset-0 flex items-center justify-center text-secondary font-headline-md">Case Study #01</div>
            </div>
            <div class="flex justify-between items-start pt-2">
              <div>
                <h3 class="font-headline-sm text-primary group-hover:text-secondary transition-colors">企业级 AI 数据分析平台</h3>
                <p class="font-body-md text-on-surface-variant mt-1">数据可视化 · 信息架构优化</p>
              </div>
              <span class="font-metric-value text-secondary text-2xl">+35%</span>
            </div>
            <button class="bg-surface-container-low text-primary py-2 px-4 rounded-sm font-label-caps text-label-caps w-fit group-hover:bg-secondary group-hover:text-on-secondary transition-colors">查看案例</button>
          </div>

          <!-- Work Card 2 -->
          <div class="bg-surface-container-lowest border border-outline-variant/50 rounded-lg p-6 flex flex-col gap-4 hover:border-secondary transition-all cursor-pointer group" onclick="openProjectDetails('Smart Design System 2.0', '为跨团队合作建立的响应式设计规范系统，大幅提升研发一致性。')">
            <div class="w-full aspect-video bg-surface-container-high rounded-md overflow-hidden relative">
              <div class="absolute inset-0 flex items-center justify-center text-secondary font-headline-md">Case Study #02</div>
            </div>
            <div class="flex justify-between items-start pt-2">
              <div>
                <h3 class="font-headline-sm text-primary group-hover:text-secondary transition-colors">Smart Design System 2.0</h3>
                <p class="font-body-md text-on-surface-variant mt-1">组件库 · 跨平台设计规范</p>
              </div>
              <span class="font-metric-value text-secondary text-2xl">2.0</span>
            </div>
            <button class="bg-surface-container-low text-primary py-2 px-4 rounded-sm font-label-caps text-label-caps w-fit group-hover:bg-secondary group-hover:text-on-secondary transition-colors">查看案例</button>
          </div>
        </div>
      </section>
    </div>

    <!-- Page 3: 关于我页 (About) -->
    <div id="view-about" class="page-view hidden transition-opacity duration-300">
      <section class="py-section-gap-sm px-gutter max-w-container-max mx-auto">
        <div class="flex flex-col gap-stack-sm mb-stack-lg">
          <h2 class="font-headline-md text-headline-md text-primary">设计哲学</h2>
          <p class="font-body-lg text-on-surface-variant max-w-3xl">平衡分析严谨性与创意直觉，坚持以人为本的设计原则。</p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div class="bg-surface-container-lowest border border-outline-variant/50 rounded-lg p-8 flex flex-col gap-stack-md lg:col-span-2">
            <div class="w-12 h-12 rounded bg-surface-container-low flex items-center justify-center text-secondary">
              <span class="material-symbols-outlined text-[24px]">architecture</span>
            </div>
            <h3 class="font-headline-sm text-headline-sm text-primary">结构化思考</h3>
            <p class="font-body-md text-on-surface-variant">从底层架构出发理清逻辑线索，建立清晰信息层级，减少认知负荷。</p>
          </div>
          <div class="bg-surface-container-lowest border border-outline-variant/50 rounded-lg p-8 flex flex-col gap-stack-md">
            <div class="w-12 h-12 rounded bg-surface-container-low flex items-center justify-center text-secondary">
              <span class="material-symbols-outlined text-[24px]">visibility</span>
            </div>
            <h3 class="font-headline-sm text-headline-sm text-primary">视觉精确</h3>
            <p class="font-body-md text-on-surface-variant">精准地把控留白与字号对比，突出核心目标。</p>
          </div>
        </div>
      </section>
    </div>

    <!-- Page 4: 简历页 (Resume) -->
    <div id="view-resume" class="page-view hidden transition-opacity duration-300">
      <section class="py-section-gap-sm px-gutter max-w-container-max mx-auto">
        <div class="flex justify-between items-center mb-stack-lg">
          <div>
            <h2 class="font-headline-md text-headline-md text-primary">个人简历</h2>
            <p class="font-body-lg text-on-surface-variant">教育背景、专业经历与技能矩阵。</p>
          </div>
          <button class="bg-primary text-on-primary rounded-sm px-6 py-3 font-label-caps text-label-caps hover:bg-surface-tint flex items-center gap-2" onclick="downloadResume()">
            <span class="material-symbols-outlined text-[18px]">download</span> 下载 PDF 简历
          </button>
        </div>
        
        <div class="bg-surface-container-lowest border border-outline-variant/50 rounded-lg p-8 space-y-6">
          <div>
            <h3 class="font-headline-sm text-secondary">工作经历</h3>
            <div class="mt-4 border-l-2 border-outline-variant pl-4 space-y-4">
              <div>
                <h4 class="font-body-lg font-bold">高级 UI/UX 设计师 & 产品经理</h4>
                <p class="font-label-caps text-on-surface-variant">2023 - 至今</p>
                <p class="font-body-md text-on-surface-variant mt-1">主导产品原型规划与用户体验升级。</p>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

    <!-- Universal Bottom Call to Action Section -->
    <section class="py-section-gap-sm px-gutter max-w-container-max mx-auto flex flex-col items-center justify-center text-center gap-stack-lg border-t border-outline-variant/20">
      <h2 class="font-display-lg-mobile md:font-display-lg text-primary max-w-4xl tracking-tight">
        准备好一起创造<br>影响力了吗？
      </h2>
      <button class="bg-primary text-on-primary rounded-sm px-8 py-4 font-label-caps text-label-caps hover:bg-surface-tint transition-all inline-flex items-center gap-2" onclick="openContactModal()">
        联系我 <span class="material-symbols-outlined text-[18px]">arrow_forward</span>
      </button>
    </section>
  </main>

  <!-- Modal 1: Global Contact Modal -->
  <div id="contact-modal" class="hidden fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center p-4">
    <div class="bg-surface rounded-lg p-8 max-w-md w-full border border-outline-variant/30 shadow-2xl relative">
      <button class="absolute top-4 right-4 text-on-surface-variant hover:text-primary" onclick="closeContactModal()">
        <span class="material-symbols-outlined">close</span>
      </button>
      <h3 class="font-headline-sm text-headline-sm text-primary mb-2">联系吴贝然</h3>
      <p class="font-body-md text-on-surface-variant mb-6">期待与您探讨关于产品设计与合作的机会！</p>
      <a href="mailto:beiran.wu@example.com" class="block w-full bg-primary text-on-primary text-center rounded-sm py-3 font-label-caps text-label-caps hover:bg-surface-tint transition-colors">
        发送邮件：beiran.wu@example.com
      </a>
    </div>
  </div>

  <!-- Modal 2: Project Detail Modal -->
  <div id="project-modal" class="hidden fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center p-4">
    <div class="bg-surface rounded-lg p-8 max-w-2xl w-full border border-outline-variant/30 shadow-2xl relative max-h-[90vh] overflow-y-auto">
      <button class="absolute top-4 right-4 text-on-surface-variant hover:text-primary" onclick="closeProjectModal()">
        <span class="material-symbols-outlined">close</span>
      </button>
      <h3 id="project-title" class="font-headline-md text-primary mb-2">项目详情</h3>
      <p id="project-desc" class="font-body-lg text-on-surface-variant mb-6">加载中...</p>
      <div class="bg-surface-container-low p-6 rounded-md mb-6">
        <p class="font-body-md text-on-surface">此处为项目详细描述、设计流程、数据复盘与相关展示界面。</p>
      </div>
      <button class="bg-tertiary text-on-tertiary px-6 py-3 rounded-sm font-label-caps text-label-caps" onclick="closeProjectModal()">关闭面板</button>
    </div>
  </div>

  <!-- JS Interaction Controller -->
  <script>
    // SPA Router Engine
    function navigateTo(viewName) {
      document.querySelectorAll('.page-view').forEach(view => {
        view.classList.add('hidden');
      });
      
      const targetView = document.getElementById(`view-${viewName}`);
      if (targetView) {
        targetView.classList.remove('hidden');
      } else {
        document.getElementById('view-home').classList.remove('hidden');
      }

      // Update Navigation Styles
      document.querySelectorAll('.nav-btn').forEach(btn => {
        btn.className = "nav-btn text-on-surface-variant hover:text-primary transition-colors h-full flex items-center";
      });
      
      const activeNav = document.getElementById(`nav-${viewName}`);
      if (activeNav) {
        activeNav.className = "nav-btn text-secondary border-b-2 border-secondary pb-1 h-full flex items-center mt-1";
      }

      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // Mobile Menu Drawer Toggle
    function toggleMobileMenu() {
      const menu = document.getElementById('mobile-menu');
      menu.classList.toggle('hidden');
      menu.classList.toggle('flex');
    }

    // Contact Modal Controller
    function openContactModal() {
      document.getElementById('contact-modal').classList.remove('hidden');
    }
    function closeContactModal() {
      document.getElementById('contact-modal').classList.add('hidden');
    }

    // Project Details Modal Controller
    function openProjectDetails(title, description) {
      document.getElementById('project-title').innerText = title;
      document.getElementById('project-desc').innerText = description;
      document.getElementById('project-modal').classList.remove('hidden');
    }
    function closeProjectModal() {
      document.getElementById('project-modal').classList.add('hidden');
    }

    // Resume Download Mock Handler
    function downloadResume() {
      alert('正在启动简历下载过程...');
    }
  </script>
</body>
</html>
