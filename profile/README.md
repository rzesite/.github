# Analytics on Firebase

- Firebase
- Analytics Dashboard
- View more in Google Analytics
- Strona Główna
- Aby zacząć zbierać dane, dodaj do swojej witryny tagi z identyfikatorem pomiaru: XXX
- Put this in .env.local

Put it in layout.txs

```
      <head>
        <Script
          id="google-analytics"
          strategy="lazyOnload"
          src={`https://www.googletagmanager.com/gtag/js?id=${process.env.NEXT_PUBLIC_GOOGLE_ANALYTICS}`}
        />
        <Script
          id="google-analytics-config"
          strategy="lazyOnload">
          {`
              window.dataLayer = window.dataLayer || [];
              function gtag(){dataLayer.push(arguments);}
              gtag('js', new Date());
              gtag('config', '${process.env.NEXT_PUBLIC_GOOGLE_ANALYTICS}', {
              page_path: window.location.pathname,
              });
          `}
        </Script>
      </head>
```
