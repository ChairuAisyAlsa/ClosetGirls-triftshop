````markdown
<!-- ========================================================= -->
<!--                 CLOSETGIRLS TRIFTSHOP                    -->
<!-- ========================================================= -->

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=D88C9A&height=220&section=header&text=CLOSETGIRLS%20TRIFTSHOP&fontSize=38&fontColor=FFFFFF&animation=fadeIn&fontAlignY=38"/>

<img src="https://readme-typing-svg.demolab.com?font=Playfair+Display&size=22&pause=1000&color=D88C9A&center=true&vCenter=true&width=650&lines=Welcome+to+Our+Digital+Closet;Thrift+Fashion+Online+Store;Pre-Loved+Pieces%2C+New+Stories;Find+Your+Style+with+ClosetGirls+%F0%9F%91%97" />

<br>

![Project](https://img.shields.io/badge/PROJECT-ClosetGirls%20TriftShop-D88C9A?style=for-the-badge)
![Status](https://img.shields.io/badge/STATUS-IN%20DEVELOPMENT-3E302B?style=for-the-badge)
![Team](https://img.shields.io/badge/TEAM-3%20MEMBERS-F8F1E7?style=for-the-badge)

</div>

---

# 👗 WELCOME TO OUR CLOSET

> **ClosetGirls TriftShop** adalah konsep toko thrift fashion online
> yang membantu pengguna menemukan pakaian pre-loved dengan mudah,
> mulai dari melihat produk, memilih barang, memasukkan ke keranjang,
> melakukan checkout, hingga melihat riwayat pesanan.

### ✨ Our Concept

ClosetGirls membawa konsep **digital closet** sebagai tempat untuk
menjelajahi berbagai pilihan fashion thrift dalam satu platform.

```text
        ┌───────────────────────────┐
        │     👗 DIGITAL CLOSET     │
        └─────────────┬─────────────┘
                      │
              ┌───────▼───────┐
              │  Browse Style │
              └───────┬───────┘
                      │
              ┌───────▼───────┐
              │ Choose Pieces │
              └───────┬───────┘
                      │
              ┌───────▼───────┐
              │ Add to Cart   │
              └───────┬───────┘
                      │
              ┌───────▼───────┐
              │   Checkout    │
              └───────┬───────┘
                      │
              ┌───────▼───────┐
              │  New Story ✨ │
              └───────────────┘
````

---

# 🌷 THE GIRLS BEHIND THE CLOSET

<div align="center">

| 👩🏻   | Member    | Contribution                          |
| ---- | --------- | --------------------------------     |
| 🎀   | **Dinar** | Project Chapter & Function Point     |
| 👜   | **Anisa** | Flowchart                            |
| 👗   | **Aisy**  | UI/UX Design,ERD,Arsitektur & Dokumen|

</div>

> *Three girls, one closet, one project.*

---

# 🛍️ ABOUT THE PROJECT

### What is ClosetGirls?

ClosetGirls TriftShop merupakan rancangan sistem toko thrift
fashion online yang dibuat untuk mempermudah pengguna dalam
mencari dan membeli produk fashion pre-loved.

### 🎯 Project Goals

* 🛍️ Menampilkan katalog produk thrift
* 🔎 Mempermudah pencarian dan filter produk
* 👗 Menampilkan detail produk
* 🛒 Menyediakan keranjang belanja
* 💳 Menyediakan proses checkout dan pembayaran
* 📦 Menyimpan informasi pesanan
* 👩🏻‍💻 Membantu admin mengelola produk dan pesanan

---

# 🧩 PROJECT STRUCTURE

```text
ClosetGirls-TriftShop/
│
├── README.md
│
├── agile_methodology/
│
├── project_chapter/
│
├── function_point/
│
├── flowchart/
│
├── erd/
│
├── architecture/
│
├── ui_ux/
│
└── setup_code/
```

---

# 🔄 AGILE METHODOLOGY

ClosetGirls menggunakan pendekatan **Agile** untuk membantu
pengembangan project dilakukan secara bertahap.

```mermaid
graph LR
    A["💡 Planning"] --> B["🎨 Design"]
    B --> C["💻 Development"]
    C --> D["🧪 Testing"]
    D --> E["🔍 Review"]
    E --> A
```

### Sprint Flow

```text
Planning
   ↓
Design
   ↓
Development
   ↓
Testing
   ↓
Review
   ↓
Improvement
   ↺
```

---

# 🏗️ SYSTEM ARCHITECTURE

```mermaid
graph TB

    A["👤 USER / ADMIN"]

    B["🖥️ PRESENTATION LAYER<br/>HTML • CSS • JavaScript"]

    C["⚙️ APPLICATION LAYER<br/>Authentication<br/>Product & Category<br/>Cart & Order<br/>Payment"]

    D["🗄️ DATA LAYER<br/>Users<br/>Categories<br/>Products<br/>Orders<br/>Order Details<br/>Payments"]

    E["🌐 EXTERNAL SERVICES<br/>Payment Simulation<br/>Future Notification"]

    A --> B
    B --> C
    C --> D
    C --> E
```

### Architecture Layers

| Layer            | Function                                      |
| ---------------- | --------------------------------------------- |
| 🖥️ Presentation | Tampilan yang digunakan user dan admin        |
| ⚙️ Application   | Menjalankan logika utama sistem               |
| 🗄️ Data         | Menyimpan data pengguna, produk dan transaksi |
| 🌐 External      | Terhubung dengan layanan eksternal            |

---

# 🗃️ DATABASE / ERD

```mermaid
erDiagram

    USERS ||--o{ ORDERS : membuat
    CATEGORIES ||--o{ PRODUCTS : memiliki
    ORDERS ||--|{ ORDER_DETAILS : memiliki
    PRODUCTS ||--o{ ORDER_DETAILS : dipesan
    ORDERS ||--o| PAYMENTS : memiliki

    USERS {
        int id PK
        string username
        string email
        string password_hash
        string role
    }

    CATEGORIES {
        int id PK
        string nama_kategori
        string deskripsi
    }

    PRODUCTS {
        int id PK
        int category_id FK
        string nama_produk
        string deskripsi
        decimal harga
        int stok
        string ukuran
        string kondisi
        string foto
    }

    ORDERS {
        int id PK
        int user_id FK
        decimal total_harga
        string alamat
        string status
        datetime created_at
    }

    ORDER_DETAILS {
        int id PK
        int order_id FK
        int product_id FK
        int jumlah
        decimal harga
    }

    PAYMENTS {
        int id PK
        int order_id FK
        string metode
        decimal jumlah
        string status
        datetime paid_at
    }
```

---

# 🛒 MAIN USER FLOW

```mermaid
graph TD

    A["🏠 Home"] --> B["🔐 Login"]
    B --> C["🛍️ Catalog"]
    C --> D["🔎 Search / Filter"]
    D --> E["👗 Product Detail"]
    E --> F{"Stock Available?"}

    F -- "No" --> C
    F -- "Yes" --> G["🛒 Add to Cart"]

    G --> H["🧺 Cart"]
    H --> I["💳 Checkout"]
    I --> J["📍 Address & Order Data"]
    J --> K["💰 Payment"]

    K --> L{"Payment Successful?"}

    L -- "No" --> K
    L -- "Yes" --> M["📦 Order Confirmed"]
    M --> N["📋 Order History"]
    N --> O["🚪 Logout"]
```

---

# 👩🏻‍💻 ADMIN FLOW

```mermaid
graph LR

    A["🔐 Admin Login"]
    B["📊 Dashboard"]
    C["👗 Manage Products"]
    D["🏷️ Manage Categories"]
    E["📦 Manage Orders"]

    A --> B
    B --> C
    B --> D
    B --> E
```

---

# 🎨 UX/UI DESIGN

### User Journey

```mermaid
graph LR

    A["Login"] --> B["Home"]
    B --> C["Catalog"]
    C --> D["Product Detail"]
    D --> E["Cart"]
    E --> F["Checkout"]
    F --> G["Payment"]
    G --> H["Confirmation"]
    H --> I["Order History"]
```

### Main Screens

| Screen             | Description                 |
| ------------------ | --------------------------- |
| 🔐 Login           | Halaman masuk pengguna      |
| 🏠 Home            | Halaman utama toko          |
| 🛍️ Catalog        | Daftar produk thrift        |
| 👗 Product Detail  | Informasi lengkap produk    |
| 🛒 Cart            | Produk yang dipilih         |
| 💳 Checkout        | Data pesanan dan pembayaran |
| 📦 Order History   | Riwayat pesanan             |
| 📊 Admin Dashboard | Pengelolaan sistem          |

---

# 🎀 DESIGN THEME

### Color Palette

| Color         | Hex       | Usage      |
| ------------- | --------- | ---------- |
| 🌸 Dusty Pink | `#D88C9A` | Primary    |
| 🤍 Cream      | `#F8F1E7` | Background |
| 🤎 Dark Brown | `#3E302B` | Text       |
| 🟢 Green      | `#28A745` | Success    |
| 🟡 Yellow     | `#FFC107` | Warning    |
| 🔴 Red        | `#DC3545` | Error      |

### Design Direction

```text
        ┌──────────────────────────┐
        │       CLOSETGIRLS        │
        │                          │
        │    👗  👜  👚  👖       │
        │                          │
        │   Search your style...   │
        │                          │
        │  [ Vintage ] [ Casual ]  │
        │                          │
        │   🛍️ Explore the Closet  │
        └──────────────────────────┘
```

---

# 🧰 CLOSET TOOLKIT

### Frontend

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge\&logo=css3\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)

### Backend

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge\&logo=flask\&logoColor=white)

### Database

![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge\&logo=sqlite\&logoColor=white)

### Design & Documentation

![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge\&logo=figma\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge\&logo=github\&logoColor=white)

---

# ✨ MAIN FEATURES

```text
┌─────────────────────────────────────────────┐
│              CLOSETGIRLS FEATURES           │
├─────────────────────────────────────────────┤
│                                             │
│  🔐 Authentication                          │
│  🛍️ Product Catalog                         │
│  🔎 Search & Filter                          │
│  👗 Product Detail                           │
│  🛒 Shopping Cart                            │
│  💳 Checkout & Payment                       │
│  📦 Order Management                         │
│  📋 Order History                            │
│  👩🏻‍💻 Admin Dashboard                        │
│                                             │
└─────────────────────────────────────────────┘
```

---

# 📚 PROJECT DOCUMENTATION

| Documentation      | Status         |
| ------------------ | -------------- |
| 📖 Project Chapter | ✅ Available    |
| 📊 Function Point  | ✅ Available    |
| 🔄 Flowchart       | ✅ Available    |
| 🗃️ ERD            | ✅ Available    |
| 🏗️ Architecture   | ✅ Available    |
| 🎨 UX/UI           | ✅ Available    |
| ⚙️ Setup Code      | ✅ Available    |
| 💻 Implementation  | 🚧 Development |

---

# 🌱 PROJECT PROGRESS

```text
Project Chapter      ████████████████████ 100%
Function Point       ████████████████████ 100%
Flowchart            ████████████████████ 100%
ERD                  ████████████████████ 100%
Architecture         ████████████████████ 100%
UX/UI                ████████████████████ 100%
Setup Code            ████████████████████ 100%
Implementation        ████░░░░░░░░░░░░░░░░ 20%
Testing               ░░░░░░░░░░░░░░░░░░░░ 0%
```

---

# 🧵 DEVELOPMENT ROADMAP

```mermaid
graph LR

    A["📋 Planning"] --> B["🎨 UI/UX"]
    B --> C["🏗️ Architecture"]
    C --> D["⚙️ Setup Code"]
    D --> E["💻 Development"]
    E --> F["🧪 Testing"]
    F --> G["🚀 Final Project"]
```

---

# 📌 CLOSET RULES

> 👗 Every piece has a story.

> 🛍️ Keep the closet organized.

> ✨ Make the interface simple and comfortable.

> 🧵 Build step by step.

> 💻 Document every progress.

---

# 💭 OUR PROJECT IDEA

ClosetGirls TriftShop dibuat dengan konsep sederhana:

```text
       PRE-LOVED FASHION
              ↓
       DIGITAL CLOSET
              ↓
        EASY BROWSING
              ↓
       EASY SHOPPING
              ↓
       NEW OWNER ✨
```

Kami ingin membuat pengalaman belanja thrift
yang sederhana, terorganisir, dan mudah digunakan.

---

# 👩🏻‍💻 THE TEAM

<div align="center">

### 🎀 DINAR

**Project Chapter & Function Point**

### 👜 ANISA

**Flowchart**

### 👗 AISY

**UI/UX Design,ERD,Arsitektur & Dokumen**

</div>

---

# 🌷 CLOSING

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Playfair+Display&size=22&pause=1000&color=D88C9A&center=true&vCenter=true&width=650&lines=Thank+you+for+visiting+our+closet+%F0%9F%8C%B7;ClosetGirls+TriftShop;Every+piece+deserves+a+new+story+%E2%9C%A8" />

<br><br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=D88C9A&height=120&section=footer"/>

</div>
```
