<!-- 1. 引入 Design System 指定的三款字体与图标 -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=JetBrains+Mono:wght@600&family=Manrope:wght@600;700;800&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1" rel="stylesheet">

<!-- 2. 注入 Precision & Insight 完整的 Design System 配置 -->
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
<script id="tailwind-config">
  tailwind.config = {
    darkMode: 'class',
    theme: {
      extend: {
        colors: {
          surface: '#f9f9ff',
          'surface-dim': '#d3daea',
          'surface-bright': '#f9f9ff',
          'surface-container-lowest': '#ffffff',
          'surface-container-low': '#f0f3ff',
          'surface-container': '#e7eefe',
          'surface-container-high': '#e2e8f8',
          'surface-container-highest': '#dce2f3',
          'on-surface': '#151c27',
          'on-surface-variant': '#444748',
          'inverse-surface': '#2a313d',
          'inverse-on-surface': '#ebf1ff',
          outline: '#747878',
          'outline-variant': '#c4c7c7',
          'surface-tint': '#5f5e5e',
          primary: '#000000',
          'on-primary': '#ffffff',
          'primary-container': '#1c1b1b',
          'on-primary-container': '#858383',
          'inverse-primary': '#c8c6c5',
          secondary: '#4b41e1',
          'on-secondary': '#ffffff',
          'secondary-container': '#645efb',
          'on-secondary-container': '#fffbff',
          tertiary: '#000000',
          'on-tertiary': '#ffffff',
          'tertiary-container': '#191c1d',
          'on-tertiary-container': '#828485',
          error: '#ba1a1a',
          'on-error': '#ffffff',
          'error-container': '#ffdad6',
          'on-error-container': '#93000a',
          background: '#f9f9ff',
          'on-background': '#151c27',
          'surface-variant': '#dce2f3',
        },
        fontFamily: {
          sans: ['Inter', 'sans-serif'],
          display: ['Manrope', 'sans-serif'],
          mono: ['JetBrains Mono', 'monospace'],
        },
        borderRadius: {
          sm: '0.125rem',
          DEFAULT: '0.25rem',
          md: '0.375rem',
          lg: '0.5rem',
          xl: '0.75rem',
          full: '9999px',
        },
        spacing: {
          'container-max': '1200px',
          'section-lg': '160px',
          'section-sm': '80px',
          gutter: '32px',
        }
      }
    }
  }
</script>
