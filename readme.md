## Dashboard App

### 1.

### 2.

### 3. Mengoptimalkan Font dan Gambar

Berikut adalah topik yang akan kami bahas:

#### A. Cara menambahkan font khusus dengan next/font.

Impor `Inter` font dari `next/font/google` modul - ini akan menjadi font utama Anda. Lalu, tentukan apa bagian Anda ingin memuat. Dalam hal ini, `latin`:

`/app/ui/fonts.ts`

```tsx
import { Inter } from "next/font/google";

export const inter = Inter({ subsets: ["latin"] });
```

Terakhir, tambahkan font ke `<body>` elemen dalam `/app/layout.tsx`:
`/app/layout.tsx`

```tsx
import "@/app/ui/global.css";
import { inter } from "@/app/ui/fonts";

export default function RootLayout({
	children,
}: {
	children: React.ReactNode;
}) {
	return (
		<html lang="en">
			<body className={`${inter.className} antialiased`}>{children}</body>
		</html>
	);
}
```

#### B. Cara menambahkan gambar dengan next/image.

Next.js dapat melayani aset statis, seperti gambar, di bawah tingkat atas `/public` folder. File di dalamnya `/public` dapat dirujuk dalam aplikasi Anda.

Dengan HTML biasa, Anda akan menambahkan gambar sebagai berikut:

```html
<img
	src="/hero.png"
	alt="Screenshots of the dashboard project showing desktop version"
/>
```

Gunakan komponen `<Image/>`:

```tsx
import Image from "next/image";
```

```tsx
<Image
	src="/hero-desktop.png"
	width={1000}
	height={760}
	className="hidden md:block"
	alt="Screenshots of the dashboard project showing desktop version"
/>
```

### 4. Membuat Tata Letak dan Halaman
