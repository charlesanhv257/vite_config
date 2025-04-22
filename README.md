# ⚡ Vite React + TypeScript Starter

Một bộ cấu hình Vite nâng cao, tối ưu cho mọi dự án sử dụng React + TypeScript. Dễ dàng mở rộng, maintain, và tích hợp tốt với monorepo (Turbo, pnpm workspaces).

---

## 🚀 Tính năng nổi bật

- ⚛️ React 19 (JSX automatic runtime)
- ✅ TypeScript support
- 📦 Alias paths từ `tsconfig.json` (`@` → `src/`)
- 🧱 Cấu trúc module hoá, dễ bảo trì
- 🔍 Bundle analyzer (Rollup visualizer)
- 🧠 CSS Modules + SCSS hỗ trợ biến toàn cục
- 🌍 Quản lý biến môi trường với `.env`
- 🧩 Hỗ trợ proxy API trong dev server
- 🔥 Tốc độ build cực nhanh với esbuild

---

## 📁 Cấu trúc thư mục đề xuất

```
src/
  assets/       # Ảnh, fonts, media
  components/   # Component dùng chung
  features/     # Tính năng theo domain
  hooks/        # Custom hooks
  pages/        # Route pages
  stores/       # State management (Zustand, Redux, v.v.)
  styles/       # SCSS / CSS Modules
  types/        # Global types/interfaces
  utils/        # Hàm tiện ích
```

---

## 🛠️ Cài đặt

```bash
pnpm install
```

> Hỗ trợ tốt `pnpm`, `yarn`, hoặc `npm`.

---

## 📦 Scripts

| Lệnh            | Mô tả                                  |
|------------------|------------------------------------------|
| `pnpm dev`       | Chạy server phát triển                  |
| `pnpm build`     | Build production                        |
| `pnpm preview`   | Xem thử bản build production            |
| `pnpm analyze`   | Phân tích bundle bằng Rollup visualizer |

---

## 🔐 Biến môi trường

Tạo file `.env` ở root:

```
VITE_API_BASE_URL=https://api.example.com
APP_ENV=development
```

Và trong `vite.config.ts` bạn có thể sử dụng: `env.VITE_API_BASE_URL`, `env.APP_ENV`

---

## 🔧 Plugin tích hợp

| Plugin                     | Chức năng                                               |
|----------------------------|----------------------------------------------------------|
| `@vitejs/plugin-react`     | React + Fast Refresh                                    |
| `vite-tsconfig-paths`      | Tự động import alias từ `tsconfig.json`                |
| `rollup-plugin-visualizer` | Phân tích bundle khi build                              |

---

## 📦 Tối ưu build

```ts
build: {
  target: 'esnext',
  sourcemap: mode !== 'production',
  outDir: 'dist',
  assetsDir: 'assets',
  minify: 'esbuild',
  rollupOptions: {
    output: {
      manualChunks: {
        react: ['react', 'react-dom'],
      },
    },
  },
}
```

---

## 🌐 Proxy API dev server

```ts
server: {
  proxy: {
    '/api': {
      target: env.VITE_API_BASE_URL,
      changeOrigin: true,
      rewrite: path => path.replace(/^\/api/, ''),
    },
  },
}
```

---

## 🔎 Phân tích bundle

```bash
pnpm analyze
```

---

## 📜 Giấy phép

MIT License – Tự do sử dụng, tùy chỉnh và chia sẻ.

---

## ✨ Tác giả

**Vũ Tuấn Anh (CharlesAnhV)**  
🔗 [linkedin.com/in/charlesanhv]([https://linkedin.com/in/charlesanhv](https://www.linkedin.com/in/perserver-anh-245649196/))  
📁 [github.com/charlesanhv257](https://github.com/charlesanhv257)
