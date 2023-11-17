---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: true
info: |
  # 進化したWeb技術でPWAを<br>ネイティブアプリに近づける

  [フロントエンドカンファレンス沖縄2023](https://frontend-conf.okinawa.jp/)
drawings:
  persist: false
transition: slide-left
title: 進化したWeb技術でPWAをネイティブアプリに近づける
author: Yuhei FUJITA
keywords:
  - PWA
  - フロントエンドカンファレンス沖縄2023
favicon: https://github.com/YuheiFUJITA.png
---

# 進化したWeb技術でPWAを<br>ネイティブアプリに近づける

2023-11-18@ZORKS沖縄

Yuhei FUJITA

---

# 自己紹介

<div class="grid grid-cols-2 gap-4">

<div>

![icon](https://github.com/YuheiFUJITA.png)

</div>

<div>

- 名前：Yuhei FUJITA
- X：[@Yuhei_FUJITA](https://twitter.com/Yuhei_FUJITA)
- コミュニティ運営
  - [Vue Fes](https://vuefes.jp/)
  - [PWA Night](https://pwanight.connpass.com/)
  - [VS Code Meetup](https://vscode.connpass.com/)
- 趣味
  - キャンプ
  - フィルムカメラ

</div>
</div>

---

# 一昨日から沖縄満喫してた人です

<div class="grid grid-cols-2 gap-4">

<div>

<Tweet id="1725113409874940318" scale="0.9"/>

</div>

<div>

<Tweet id="1725355368216404332" scale="0.9"/>

</div>

</div>

---

# 今日の話

![PWA Logo](https://raw.githubusercontent.com/webmaxru/progressive-web-apps-logo/master/pwalogo-inverse.svg)

---

# Progressive Web Apps（PWA）

<div class="grid grid-cols-3 gap-4">

<div class="col-span-1">

<img src="https://web.dev/articles/what-are-pwas/image/a-graph-illustrating-rel-8f0fbfba2c3e8.svg" alt="PWAの立ち位置" style="background-color: white; padding: 10px;">

</div>

<div class="col-span-2">

## 改めてPWAとは

**Using the latest web features** to bring enhanced <span class="blue">capabilities</span> and <span class="yellow">reliability</span>, Progressive Web Apps allow what you build to be <span class="green">installed</span> **by anyone, anywhere, on any device with a single codebase**.

## 翻訳
プログレッシブウェブアプリは、**最新のWeb機能を使用して**<span class="blue">機能</span>と<span class="yellow">信頼性</span>を強化し、構築したものを**誰でも、どこでも、どのデバイスでも、単一のコードベースで**<span class="green">インストールできる</span>ようにします。

</div>

</div>

<hr>

<small>[What are Progressive Web Apps?  \|  Articles  \|  web\.dev](https://web.dev/articles/what-are-pwas)</small>

---

# 3つの柱

<div class="grid grid-cols-3 gap-4">

<div>

## <span class="blue">Capable / 機能性</span>

- Web API
  - Web Push
  - geoLocation
  - WebRTC

</div>

<div>

## <span class="yellow">Reliable / 信頼性</span>

- オフライン動作
  - Service Worker
- 高速な読み込み
  - Pre Cache
- 安全な通信
  - HTTPS

</div>

<div>

## <span class="green">Installable / <br>インストール可能</span>

- アプリ化
  - Standalone
- ホーム画面に追加
  - アプリアイコン

</div>

</div>

<hr>

<small>[What are Progressive Web Apps?  \|  Articles  \|  web\.dev](https://web.dev/articles/what-are-pwas)</small>

---

# なぜネイティブアプリにするのか？

- よりパワフルなアプリを作れる
  - 処理速度・OSの提供するAPI
- モバイルSafariのサポート
  - 使えないAPI・わかりにくいインストール手順
- ユーザーの認知度が高い
  - アプリストア・インストールの導線

---

# Google Trendsで見るPWA

上が日本、下が世界

![Alt text](/images/google-trends-japan.png)

![Alt text](/images/google-trends-global.png)

---
layout: statement
---

# より良いPWAにするには？

---

# 今回はPWA化の話は割愛

<div class="grid grid-cols-2 gap-4">

<div>

![Alt text](/images/frontend-conf-okinawa-2022.png)

</div>

<div>

去年の「PWAをインストールしやすくするための実装 by まぁし（知念）さん」がわかりやすいのでそちらを参照してください。

</div>

</div>

<hr>

<small>[PWAをインストールしやすくするための実装 by まぁし（知念）さん](https://speakerdeck.com/chinen/frontend-conf-okinawa-2022)</small><br>
<small> [フロントエンドカンファレンス沖縄2022 - YouTube](https://www.youtube.com/live/JnNlmakDtAs?si=LlCD0eaM8YCCwOCl&t=3760) </small>

---

# maskable icon

<div class="grid grid-cols-3 gap-4">

<div>

<video src="https://web.dev/articles/maskable-icon/video/tcFciHGuF3MxnTr1y5ue01OGLBn2/mx1PEstODUy6b5TXjo4S.webm?hl=ja" autoplay loop muted></video>

</div>

<div class="col-span-2">

さまざまな形のアイコンに対応できる。

```json {all|8|all}
// manifest.json
{
  "icons": [
    {
      "src": "maskable_icon.png",
      "sizes": "196x196",
      "type": "image/png",
      "purpose": "maskable"
    },
  ],
}
```

</div>
</div>

<hr>

<span class="reference"><https://web.dev/articles/maskable-icon?hl=ja></span>

---
layout: statement
---

# より良いユーザー体験を<br>提供するために

---

# PWAのチェックリスト<br>Core Progressive Web App checklist

- <span class="yellow">Starts fast, stays fast（すばやく起動、常に高速で快適）</span>
- <span class="green">Works in any browser（どのブラウザでも動作）</span>
- <span class="green">Responsive to any screen size（あらゆる画面サイズに応答）</span>
- <span class="yellow">Provides a custom offline page（カスタムのオフライン ページを用意）</span>
- Is installable（インストール可能）

<span class="yellow">より良いWeb体験で重要なこと</span>

<span class="green">ネイティブアプリでも重要なこと</span>

<hr>

<small> [What makes a good Progressive Web App?  \|  Articles  \|  web\.dev](https://web.dev/articles/pwa-checklist) </small>

---

# PWAのチェックリスト<br>Optimal Progressive Web App checklist

- Provides an offline experience（オフライン機能を利用できる）
- <span class="yellow">Is fully accessible（完全にアクセス可能）</span>
- Can be discovered through search（検索で見つけられる）
- <span class="yellow">Works with any input type（すべての入力タイプに対応）</span>
- <span class="yellow">Provides context for permission requests<br>（権限リクエストのコンテキストを提供する）</span>
- Follows best practices for healthy code<br>（正常なコードのためのベスト プラクティスにしたがっている）

<hr>

<small> [What makes a good Progressive Web App?  \|  Articles  \|  web\.dev](https://web.dev/articles/pwa-checklist) </small>

---
layout: statement
---

# PWAを<br>ネイティブアプリに<br>近づける

（タイトル回収）

---

# ネイティブアプリならある「あの機能」を<br>PWAで提供する

- 共有する機能を提供する<span class="yellow">Web Share API</span>
- 共有される機能を提供する<span class="yellow">Web Share Target API</span>
- 特定機能を瞬時に呼び出す<span class="yellow">Shortcuts API</span>

---
layout: statement
---

# Web Share API

PWAから共有する

---

# Web Share API

<div class="grid grid-cols-3 gap-4">

<div>

<img src="/images/web-share-api.gif" alt="Web Share API" style="max-width: 100%; height: 450px;">

</div>

<div class="col-span-2">

- 共有機能を提供するAPI
- OS標準の共有メニューを呼び出せる
  - 統一されたUIを提供可能
- さまざまなファイルを共有可能
  - pdf
  - audio
  - image
  - text
  - video

<hr>

<small> [Web Share API \- Web APIs \| MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Share_API) </small>

</div>

</div>

---

# Web Share API

```ts {all|11,18,20|19|12,15,17|13-14|1-6,9,13|16|all} {maxHeight:'400px'}
type ShareData = {
  title?: string,
  text?: string,
  url?: string,
  files? :File[],
}

const shareContent = async (
  data: ShareData
): Promise<void> => {
  if(navigator.share) {
    try {
      await navigator.share(data);
      console.log("success")
    } catch (err) {
      console.log("failed")
    }
  } else {
    console.log("Web Share API not support")
  }
};
```

---

# For Android Developers

これがないとAndroidアプリはPWAからの共有を受け取れない。

```xml {all|9-11|all}
<!-- AndroidManifest.xml -->
<activity ...>
  <intent-filter>
    <action android:name="android.intent.action.VIEW" />
    <data android:scheme="http" android:host="www.example.com" />
    <category
      android:name="android.intent.category.DEFAULT"
    />
    <category
      android:name="android.intent.category.BROWSABLE"
    />
  </intent-filter>
</activity>
```

<hr>

<small> [Intent  \|  Android Developers](https://developer.android.com/reference/android/content/Intent#CATEGORY_BROWSABLE) </small>

---
layout: statement
---

# Web Share Target API

PWAに共有する

---

# Web Share Target API

<div class="grid grid-cols-3 gap-4">

<div>

<img src="/images/web-share-target-api.gif" alt="Web Share API" style="max-width: 100%; height: 450px;">
</div>

<div class="col-span-2">

- 他アプリからの共有を受け取るAPI
  - Web Share APIとは役割が逆
- `GET` or `POST` リクエストで受け取る
  - `GET` の場合は `query` で受け取る
  - `POST` の場合は `body` で受け取る
- `manifest.json` で定義
  - 受け取れる共有内容や受け取り方を記述
- 要インストール
  - インストールしていない場合は利用不可

<hr>

<small> [share\_target \- Web app manifests \| MDN](https://developer.mozilla.org/en-US/docs/Web/Manifest/share_target) </small>

</div>

</div>

---

# Web Share Target API `GET` の場合

```json {all|2,10|3|4|5-9|all}
// manifest.json
{
  "share_target": {
    "action": "/receiver/",
    "method": "GET",
    "params": {
      "title": "name",
      "text": "description",
      "url": "link"
    }
  }
}

```

```bash
curl 'https://example.com/receiver/'\
  ?name=foo\
  &description=bar\
  &link=piyo
```

---

# Web Share Target API `POST` の場合

```json {all|4|5|6-20|10-19|all} {maxHeight:'250px'}
// manifest.json
{
  "share_target": {
    "action": "/receiver/",
    "method": "POST",
    "enctype": "multipart/form-data",
    "params": {
      "title": "name",
      "text": "description",
      "url": "link",
      "files": [
        {
          "name": "lists",
          "accept": ["text/csv", ".csv"]
        },
        {
          "name": "photos",
          "accept": ["image/svg+xml", ".svg"]
        }
      ]
    }
  }
}
```

```bash
curl 'https://example.com/receiver/' \
  --form 'name="foo"' \
  --form 'description="bar"' \
  --form 'link="https://example.com"' \
  --form 'files=@"/path/to/file.csv"'
```

---
layout: statement
---

# Shortcuts API

---

# Shortcuts API

<div class="grid grid-cols-3 gap-4">

<div>

<img src="/images/shortcuts-api.gif" alt="Shortcuts API" style="max-width: 100%; height: 450px;">

</div>

<div class="col-span-2">

- ショートカットメニューを追加するAPI
  - アプリアイコン長押し時に最大4つ表示可能
- 任意の機能の呼び出し
  - アプリを開くことなく直接機能を呼び出せる
- `manifest.json` で定義
  - ショートカットの内容を記述

<hr>

<small> [shortcuts \- Web app manifests \| MDN](https://developer.mozilla.org/en-US/docs/Web/Manifest/shortcuts) </small>

</div>

</div>

---

# Shortcuts API

```json {all|3,16|4-15|5|6|7|8|9-14|all}
// manifest.json
{
  "shortcuts": [
    {
      "name": "Open Play Later",
      "short_name": "Play Later",
      "description": "View the list of podcasts you saved for later",
      "url": "/play-later?utm_source=homescreen",
      "icons": [
        {
          "src": "/icons/play-later.png",
          "sizes": "192x192"
        }
      ]
    }
  ]
}
```

---

# ネイティブアプリっぽくなったPWA

<div class="grid grid-cols-3 gap-4">

<div>

Web Share API

<img src="/images/web-share-api.gif" alt="Web Share API" style="max-width: 100%; height: 400px;">

</div>

<div>

Web Share Target API

<img src="/images/web-share-target-api.gif" alt="Web Share Target API" style="max-width: 100%; height: 400px;">

</div>

<div>

Shortcuts API

<img src="/images/shortcuts-api.gif" alt="Shortcuts API" style="max-width: 100%; height: 400px;">

</div>

</div>

---

# 各ブラウザ対応状況

| API | Desktop Chrome | Desktop Safari | Mobile Chrome | Mobile Safari |
| --- | :-: | :-: | :-: | :-: |
| [Web Share API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share#browser_compatibility) | Yes<br>Chrome OS<br>Windows | Yes | Yes | Yes |
| [Web Share Target API](https://developer.mozilla.org/en-US/docs/Web/Manifest/share_target#browser_compatibility) | Yes | No | Yes | No |
| [Shortcuts API](https://developer.mozilla.org/en-US/docs/Web/Manifest/shortcuts#browser_compatibility) | Yes | No | Yes | No |
---

# まとめ

- PWAの復習
  - PWAはWebの最新技術を利用したWebアプリ
  - 3つの柱を中心に構築する
- PWAチェックリスト
  - PWAをより良いものにするためのチェックリスト
  - PWAに限らずWebのチェックリスト
- Web APIによる機能拡張
  - Web APIを駆使すればネイティブアプリに近づけられる
  - とはいえすべてのブラウザで対応しているわけではない

---

# 参考

- [What are Progressive Web Apps?  \|  Articles  \|  web\.dev](https://web.dev/articles/what-are-pwas)
- [Adaptive icon support in PWAs with maskable icons  \|  Articles  \|  web\.dev](https://web.dev/articles/maskable-icon)
- [What makes a good Progressive Web App?  \|  Articles  \|  web\.dev](https://web.dev/articles/pwa-checklist)
- [Web Share API \- Web APIs \| MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Share_API)
- [Integrate with the OS sharing UI with the Web Share API  \|  Articles  \|  web\.dev](https://web.dev/articles/web-share)
- [Intent  \|  Android Developers](https://developer.android.com/reference/android/content/Intent#CATEGORY_BROWSABLE)
- [share\_target \- Web app manifests \| MDN](https://developer.mozilla.org/en-US/docs/Web/Manifest/share_target)
- [Receiving shared data with the Web Share Target API \- Chrome for Developers](https://developer.chrome.com/articles/web-share-target/)
- [shortcuts \- Web app manifests \| MDN](https://developer.mozilla.org/en-US/docs/Web/Manifest/shortcuts)
- [Web Share APIでPWAに共有機能を実装する](https://zenn.dev/yuhei_fujita/articles/adventcalendar-web-share-target)
