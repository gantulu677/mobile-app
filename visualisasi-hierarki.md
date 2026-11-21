# Visualisasi Hierarki App

Dokumen ini mendefinisikan hierarki layout untuk aplikasi React mobile-only.

## 1. Hierarki Komponen

```text
App
│
├── AppShell
│   ├── AppHeader
│   ├── MainContent
│   │   ├── HomePage
│   │   ├── ProductsPage
│   │   ├── LiveChatPage
│   │   ├── NotificationPage
│   │   ├── CartPage
│   │   └── ProfilePage
│   └── BottomNavigation
│
├── StandalonePages
│   ├── CheckoutPage
│   │   ├── StandaloneHeader
│   │   ├── StandaloneContent
│   │   └── StandaloneBottomAction
│   │
│   └── PaymentResultPage
│       ├── StandaloneHeader
│       ├── StandaloneContent
│       └── StandaloneBottomAction
│
└── Overlay
    └── OverlayHost
        ├── Modal
        ├── Drawer
        ├── Dialog
        └── Toast
```

## 2. Aturan Layout

| Komponen | Aturan |
|---|---|
| `AppShell` | `display: flex; flex-direction: column` |
| `MainContent` | `flex: 1; overflow-y: auto` |
| `StandalonePages` | `display: flex; flex-direction: column` |
| `StandaloneContent` | `flex: 1; overflow-y: auto` |

## 3. Visualisasi Flex Layout

### AppShell

```text
AppShell
  display: flex
  flex-direction: column
  │
  ├── AppHeader
  ├── MainContent
  │     flex: 1
  │     overflow-y: auto
  └── BottomNavigation
```

### StandalonePages

```text
StandalonePages
  display: flex
  flex-direction: column
  │
  ├── StandaloneHeader
  ├── StandaloneContent
  │     flex: 1
  │     overflow-y: auto
  └── StandaloneBottomAction
```

## 4. Ketentuan Struktur

1. `AppShell` dan `StandalonePages` masing-masing menggunakan layout flex column.
2. `MainContent` dan `StandaloneContent` menggunakan `flex-1` serta dapat di-scroll secara vertikal.
3. `AppHeader` dan `BottomNavigation` merupakan bagian dari `AppShell`.
4. `StandalonePages` tidak menggunakan `AppHeader` atau `BottomNavigation` milik `AppShell`.
5. Setiap halaman standalone memiliki `StandaloneHeader`, `StandaloneContent`, dan `StandaloneBottomAction`.
6. `OverlayHost` menjadi tempat pengelolaan overlay global dan terpisah dari kelompok halaman.

## 5. Status

Dokumen ini adalah spesifikasi struktur dan layout. Dokumen ini belum menyatakan bahwa struktur tersebut telah diimplementasikan ke dalam repository.
