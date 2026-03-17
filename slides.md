---
theme: geist
title: 下半期 成果発表会
info: N高等学校 2年生 権代颯士の下半期成果発表
author: 権代颯士
keywords: N高,成果発表,プログラミング
transition: slide-left | slide-right
---

<div class="grid grid-cols-2 gap-6 h-full">
<div>

<div class="flex items-center gap-4 mb-1">
  <img src="/better-tab.png" class="w-28 rounded-2xl" />
  <span class="text-3xl font-bold gradient-text-blue">Better-Tab</span>
</div>
<div class="flex gap-2 ml-32 -mt-10">
  <span class="tag text-xs">#chrome-extension</span>
  <span class="tag text-xs">#new-tab</span>
</div>

<div v-click class="text-base leading-relaxed mt-4 text-white">
カスタマイズ可能な新しいタブページ。<br/>
時計、天気、カレンダー、トレンド記事を一つのページに集約した、<br/>
モダンで使いやすい新しいタブ用のページです。
</div>

</div>
<div class="flex items-center justify-center">
  <img src="/better-tab-lp.png" class="rounded-xl shadow-2xl w-full" />
</div>
</div>

<!--
1つ目は Better-Tab です。
ブラウザの新しいタブを自分好みにカスタマイズできるChrome拡張機能です。
-->

---

# Better-Tab — 技術スタック

<div class="grid grid-cols-2 gap-8 mt-2">
<div>

<TechStack :items="[
  { label: 'Framework', value: 'Next.js 16' },
  { label: 'UI', value: 'Tailwind + shadcn/ui' },
  { label: 'Language', value: 'TypeScript' },
  { label: 'Storage', value: 'IndexedDB' },
]" />

</div>
<div>

<h3 class="text-sm uppercase tracking-wider mt-0 mb-4">External APIs</h3>

<div class="grid gap-2">
  <div class="glass-card !p-3 flex items-center gap-3">
    <mdi-weather-partly-cloudy class="text-xl" />
    <div>
      <div class="text-sm font-medium">気象庁公式API</div>
      <div class="text-xs">天気予報・警報データ</div>
    </div>
  </div>
  <div class="glass-card !p-3 flex items-center gap-3">
    <mdi-post-outline class="text-xl" />
    <div>
      <div class="text-sm font-medium">Qiita公式 API</div>
      <div class="text-xs">トレンド記事</div>
    </div>
  </div>
  <div class="glass-card !p-3 flex items-center gap-3">
    <mdi-calendar class="text-xl" />
    <div>
      <div class="text-sm font-medium">holidays-jp</div>
      <div class="text-xs">日本の祝日データ</div>
    </div>
  </div>
</div>

</div>
</div>

<h3 class="text-sm uppercase tracking-wider mt-6 mb-3">
  <mdi-lightbulb-outline class="mr-1" />工夫したポイント
</h3>

<div class="grid grid-cols-2 gap-3">
  <div v-click class="glass-card !p-3 flex items-start gap-3">
    <mdi-cached class="text-xl shrink-0 mt-0.5" />
    <div>
      <div class="text-sm font-medium">APIレスポンスのキャッシュ</div>
      <div class="text-xs">外部APIから取得したデータをLocalStorageにキャッシュし、リクエスト数を削減・表示を高速化</div>
    </div>
  </div>
  <div v-click class="glass-card !p-3 flex items-start gap-3">
    <mdi-image-outline class="text-xl shrink-0 mt-0.5" />
    <div>
      <div class="text-sm font-medium">動画背景のフォールバック</div>
      <div class="text-xs">背景に動画を設定可能だが、ロードに時間がかかるため完了までサムネイルをfallback表示</div>
    </div>
  </div>
</div>

<!--
技術スタックはこのようになっています。
工夫したポイントも紹介します。
-->

---
layout: center
---

<DemoSlide title="Live Demo" subtitle="Chrome で新しいタブを開いて機能を紹介します" />

<!--
[ここで Better-Tab のデモを行う]
実際にChromeで新しいタブを開いて機能を見せます。
- 背景画像の変更
- 天気ウィジェット
- トレンド記事
-->

---

# <span class="gradient-text-blue">Spotify-CLI</span>

<div class="flex gap-2 mb-4">
  <span class="tag text-xs">#cli</span>
  <span class="tag text-xs">#spotify</span>
  <span class="tag text-xs">#blazing-fast</span>
</div>

<div class="grid grid-cols-2 gap-8">
<div>

<div v-click class="glass-card !p-4">
  <h4 class="m-0 mb-2 text-sm uppercase tracking-wider">
    <mdi-lightbulb-outline class="mr-1" />きっかけ
  </h4>
  <p class="m-0 text-sm leading-relaxed">
    Go言語の勉強として開発。<br/>
    作業中にSpotifyの画面へ切り替えるのが思考の邪魔に感じたため、<br/>
    ターミナルで完結できるツールを作った。
  </p>
</div>

</div>
<div>

<v-clicks>

<FeatureList :items="[
  'コマンドラインで再生 / 一時停止 / スキップ',
  'TUIモードで再生中の曲をリアルタイム表示',
  'WezTerm でアルバムアートワークをターミナル内に描画',
  'MSI インストーラーで簡単導入',
]" />

</v-clicks>

</div>
</div>

<!--
2つ目は Spotify-CLI です。
ターミナルから離れずに Spotify を操作できるツールです。
-->

---

# Spotify-CLI — コマンド体系

<div class="grid grid-cols-2 gap-8 mt-2">
<div>

```bash
# 基本操作
spt play      # 再生
spt pause     # 一時停止
spt next      # 次の曲
spt back      # 前の曲

# 情報表示
spt now       # 現在の曲情報
spt devices   # 接続中デバイス一覧
spt volume 80 # 音量調整

# TUIモード（引数なしで起動）
spt
```

</div>
<div>

<TechStack :items="[
  { label: 'Language', value: 'Go 1.25+' },
  { label: 'CLI', value: 'spf13/cobra' },
  { label: 'TUI', value: 'Bubbletea + Lipgloss' },
  { label: 'API Client', value: 'zmb3/spotify/v2' },
  { label: 'Auth', value: 'OAuth 2.0 + PKCE' },
]" />

</div>
</div>

<!--
コマンド体系はシンプルに設計しています。
引数なしで spt を実行すると TUI モードが起動します。
-->

---
layout: center
---

<DemoSlide title="Live Demo" subtitle="ターミナルで spt を起動して操作します" />

<!--
[ここで Spotify-CLI のデモを行う]
- spt コマンドで TUI モードを起動
- 再生/一時停止の操作
- アルバムアートワーク表示
-->

---

# <span class="gradient-text-blue">Portfolio</span> & <span class="gradient-text-blue">dotfiles</span>

<div class="grid grid-cols-2 gap-6 mt-4">

<div class="glass-card">
<h3 class="m-0 mb-3 text-lg">
  <mdi-web class="mr-2" />Portfolio(一番最初のやつ)
</h3>
<div class="text-xs mb-3 font-mono">t4ko.vercel.app</div>

<FeatureList :items="[
  'Next.jsをVercel でホスティング',
  'レスポンシブデザイン',
  'かなりデザインを意識して作りました',
]" />
</div>

<div class="glass-card">
<h3 class="m-0 mb-3 text-lg">
  <mdi-cog class="mr-2" />dotfiles(spotify cliのときのterminal)
</h3>
<div class="text-xs mb-3">Windows 11 開発環境の自動構築</div>

<div class="grid gap-2 text-sm">
  <div class="flex items-center gap-2"><span class="">▸</span> <strong class="">Neovim</strong> <span class="text-xs">エディタ</span></div>
  <div class="flex items-center gap-2"><span class="">▸</span> <strong class="">WezTerm</strong> <span class="text-xs">ターミナル</span></div>
  <div class="flex items-center gap-2"><span class="">▸</span> <strong class="">Starship</strong> <span class="text-xs">プロンプト</span></div>
  <div class="flex items-center gap-2"><span class="">▸</span> <strong class="">Lazygit</strong> <span class="text-xs">Git</span></div>
  <div class="flex items-center gap-2"><span class="">▸</span> <strong class="">yazi</strong> <span class="text-xs">ファイルマネージャ</span></div>
</div>
</div>

</div>

<!--
Portfolio と dotfiles をまとめて紹介します。
-->

---

# <span class="gradient-text">VOD.AI(仮) -- (WIP)</span>

<div class="flex gap-2 mb-4">
  <span class="tag text-xs">#remotion</span>
  <span class="tag text-xs">#react</span>
  <span class="tag text-xs">#ai-powered</span>
</div>

<div class="grid grid-cols-2 gap-8">
<div>

<div v-click class="text-sm leading-relaxed">
Remotionを軸に、<strong>Reactコードで動画編集</strong>を行うWebアプリケーション。<br/><br/>
普通の編集アプリとして利用でき、編集を重ねるにつれ<strong>クライアントの編集の癖をAIが学習</strong>。<br/>
使い込むほどAIが編集を手伝い、<strong>自動でその人らしい編集</strong>をするようになる。
</div>

</div>
<div>

<v-clicks>

<FeatureList :items="[
  'Reactコードのプリセットで簡単な編集に対応',
  'LLMとの対話でユーザーの意図を解釈',
  'AIエージェントがReactコードを自動生成',
  '編集の採用/却下からユーザーの好みをメモリに蓄積',
  '継続利用で提案品質が改善',
]" />

</v-clicks>

</div>
</div>

<!--
開発中の動画編集アプリ VODAI の紹介です。
-->

---
layout: center
---

<DemoSlide title="Live Demo" subtitle="VOD.AI の現在の開発状況を紹介します" />

<!--
[ここで VOD.AI のデモを行う]
-->

---
layout: center
---

<div class="text-center">
  <div class="section-label justify-center" style="margin-bottom: 2rem">
    <span style="letter-spacing: 0.2em; font-size: 0.6rem">END OF PRESENTATION</span>
  </div>

  <h1 class="text-5xl !mb-8" style="letter-spacing: -0.03em; color: #fff; -webkit-text-fill-color: #fff">ご清聴ありがとうございました</h1>

  <div class="divider w-64 mx-auto" />

  <div class="flex items-center justify-center gap-10 mt-8">
    <div class="flex items-center gap-2 text-sm" style="color: rgba(255, 255, 255, 0.6)">
      <mdi-github class="text-lg" />
      <span>@T4ko0522</span>
    </div>
    <div class="flex items-center gap-2 text-sm" style="color: rgba(255, 255, 255, 0.6)">
      <mdi-web class="text-lg" />
      <span>t4ko.vercel.app</span>
    </div>
    <div class="flex items-center gap-2 text-sm" style="color: rgba(255, 255, 255, 0.6)">
      <mdi-email-outline class="text-lg" />
      <span>tako.work.contact@gmail.com</span>
    </div>
  </div>

  <div class="flex items-center justify-center gap-1.5 mt-12" style="font-size: 0.7rem; color: rgba(255, 255, 255, 0.5); letter-spacing: 0.05em">
    Powered by
    <simple-icons-vercel class="text-sm" style="color: #fff" />
    <span style="color: #fff; -webkit-text-fill-color: #fff">Vercel</span>
    &
    <logos-slidev class="text-sm" />
    <span style="color: #2dd4bf; -webkit-text-fill-color: #2dd4bf">Slidev</span>
  </div>
</div>

<!--
以上で発表を終わります。ありがとうございました。
-->
