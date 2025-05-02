# VISIOSCAN AI - MVP Repository

This monorepo contains three modules for the VISIOSCAN AI MVP:
1. **Inference Engine** – real-time pathology detection on CXR & Head CT
2. **Radiologist Web UI** – OHIF extension inside PACS (React, MVVM)
3. **Patient & Trainee Portal** – bilingual 3D explainer (Next.js SSR, CDN-first)

---

## 1. Inference Engine

```
visioscan_mvp_inference/
├── README.md
├── requirements.txt
├── setup.py
├── inference_engine/
│   ├── inference.py
│   ├── models/
│   │   ├── cnn_ensemble.py
│   │   ├── unet3d.py
│   │   └── utils.py
│   ├── kernels/
│   │   ├── CMakeLists.txt
│   │   ├── cuda_kernel.cu
│   │   └── cuda_module.cpp
│   └── services/
│       └── api.py
```

_(See previous section for full code)_

---

## 2. Radiologist Web UI

```
visioscan_webui/
├── README.md
├── package.json
├── webpack.config.js
├── public/
│   └── index.html
├── src/
│   ├── index.jsx
│   ├── App.jsx
│   ├── viewmodels/
│   │   └── ImageViewerViewModel.js
│   ├── components/
│   │   └── ImageViewer.jsx
│   ├── services/
│   │   └── api.js
│   └── extensions/
│       └── visioscan-extension/
│           ├── manifest.json
│           ├── index.js
│           └── extensionConfig.js
```

_(See previous section for full code)_

---

## 3. Patient & Trainee Portal

A bilingual (English/Finland) server-rendered website showcasing a 3D explainer model via CDN. Built with Next.js for SEO and performance.

```
visioscan_portal/
├── README.md
├── package.json
├── next.config.js
├── public/
│   ├── locales/
│   │   ├── en/common.json
│   │   └── fi/common.json
│   ├── model/
│   │   └── explainer.glb
│   └── favicon.ico
├── pages/
│   ├── _app.js
│   ├── index.js
│   └── [locale]/
│       └── index.js
├── components/
│   ├── Layout.js
│   └── Explainer3D.js
└── utils/
    └── i18n.js
```

--- README.md ---
```markdown
# VISIOSCAN AI - Patient & Trainee Portal

A bilingual (English/Finnish) server-side rendered portal with a 3D explainer. Assets (3D model, translations) served via CDN for low-latency.

## Features
- Next.js SSR with dynamic locale routing
- `react-three-fiber` for loading a glTF explainer model
- `next-i18next` for translation management
- CDN-first for `/public/model` and `/public/locales`

## Tech Stack
- Node.js 18+
- Next.js 13
- React 18
- React Three Fiber
- next-i18next

## Installation

```bash
git clone https://github.com/your-org/visioscan_portal.git
cd visioscan_portal
npm install
npm run dev  # http://localhost:3000
```

## Build & Deploy
```bash
npm run build
npm run start  # production
