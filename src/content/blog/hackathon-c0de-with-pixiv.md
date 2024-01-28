---
author: mznms
pubDatetime: 2024-01-28T23:17:00+09:00
title: 「第1回 C0deハッカソン with ピクシブ」参加記
slug: hackathon-c0de-with-pixiv
featured: true
draft: false
description: 2023-24年に開催された「第1回 C0deハッカソン with ピクシブ」に，チーム「身体でプログラミング」として参加した記録です。
---

大学の所属団体で開催されたハッカソンに参加した。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">ピクシブさんとのハッカソン、キックオフです！<br>参加者だけで40人近いビックイベントです！<br>ここから約1ヶ月、走りきりましょう！ <a href="https://t.co/HPHqYpSdqq">pic.twitter.com/HPHqYpSdqq</a></p>&mdash; 名工大プログラミング部C0de (@c0demattari) <a href="https://twitter.com/c0demattari/status/1737429752515105230?ref_src=twsrc%5Etfw">December 20, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

ハッカソンといっても本イベントはふつうのハッカソンとは様相が異なる。

まず，ハッカソンというと1週間程度のものが通常であるが，今回はなんと**狂気の1か月開催**である。

そして，協賛としてあの天にも轟く有名企業，**ピクシブ株式会社様**にご支援をいただいているのである。

これは熱い。

## 作ったもの

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">チーム名: 🏃‍♀️身体でプログラミング <br>製作物: PhysiCode <br><br>カメラと姿勢検知により、身体でプログラミングできるWebアプリを作成しました。 頭だけでなく、身体も使ってプログラミング、そんななさそうでなかった体験をしてみませんか？ <br>言語はBrainf**kです。<br>(続) <a href="https://t.co/bqNIcXR5Ff">pic.twitter.com/bqNIcXR5Ff</a></p>&mdash; 名工大プログラミング部C0de (@c0demattari) <a href="https://twitter.com/c0demattari/status/1748262070251143284?ref_src=twsrc%5Etfw">January 19, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

今回は「**PhysiCode**」というWebアプリを作成した。
言ってしまえば，これは[Brainf\*ck方言](https://dic.nicovideo.jp/a/brainfuck%E6%96%B9%E8%A8%80)のひとつである。
ただほかの方言と違い，本アプリでは，定められたポーズをとりWebカメラに映すことで，トークンを入力することができる。
理論上は，どんな計算でもポージングの組み合わせだけで実行可能なのである。

<img src="https://img.mamizu.jp/pose.png" alt="作成したアプリで使うポーズの表">

作成したものはVercelにデプロイされているので，ぜひ遊んでみてほしい。
十分に大きな部屋で。

https://physi-code.vercel.app/

念のために言っておくと，本アプリはWebカメラの画像をTensorFlowの姿勢検知ライブラリにより解析するためだけに使用しており，画像は一切外部に流されない。
むしろ，すべての処理はクライアントのブラウザが担うため，ある程度スペックのある端末で試してもらうとストレスがない。

## チーム

今回のハッカソンはあらかじめやりたいアイデアのある人が提案を行い，それに対して一緒にやりたいと思った人が乗っかるという形式でチームが組まれた。

筆者は「ポージングを撮影してプログラミングをする」というアイデアを出してみたところ，一緒にやってくれるメンバが見つかった。

実質的に開発を行った者としては，筆者を含め3人であった。
ひとりは学内最高のWebフロントサイドエンジニアである。
もうひとりは学内屈指の競技プログラマである。
他のチームと比べれば実働人数が少ない方ではあるが，これ以上ないといっても嘘にならないほどの強力なパーティである。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">ハッカソン、キックオフ… <a href="https://t.co/5neDxwXNv8">pic.twitter.com/5neDxwXNv8</a></p>&mdash; 名工大プログラミング部C0de (@c0demattari) <a href="https://twitter.com/c0demattari/status/1737429729689711089?ref_src=twsrc%5Etfw">December 20, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## 開発

開催期間の最序盤に，筆者の私事により，チームとしての出だしが数日遅れてしまった。
しかしながら，その間にもチームには姿勢検知ライブラリの選定を行ってもらい，その後の動き出しがスムーズに行った。

その後の開発は，大まかにやる分野を振り分ける形で進んでいった。

- UI作成，各機能の結合
- 姿勢検知・判定部分，文字入力部分の実装
- プログラム処理系，その他ドキュメントの作成（筆者）

まず姿勢検知担当の彼には大きく助けられた。
最初の会議の翌日には，ライブラリを実際に用いてカメラで身体の各パーツ位置を表示するアプリが爆誕していた。
これはのちの機能を細かく詰めていく時イメージを固めるのに大きく役立った。

そしてゴッドWebフロントエンジニアの彼には最初から最後まで助けられた。
1日ごとにUIは実装されていき，我々が書き散らした各機能部のコンポーネントは彼の手により鮮やかに結合されていくのである。
そして何より恐ろしいことに，彼は本ハッカソンの運営長である。
もはや私はハッカソン期間中，もはや彼におんぶに抱っこどころではなく，彼のバスにずっと乗っていた。

## 感想

開発期間中間の時点，具体的にはまだ処理系が実装されておらず，カメラとキャンバス機能（身体の各キーパーツが表示される部分）がある程度実装されているのみの段階では，正直に申し上げて，本当に作っているものが面白くなるのかがさっぱりわからなかった。

しかし実際にポーズに応じてトークンが入力できる機能が追加できた段階では，プロダクトの完成への実感が大きく湧いてきたのを覚えている。

ああ，自分の妄想が自分の手（とチームメンバの手）によって形となり，手に取ることができるようになることのなんたる喜びか。

## 結果

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">🎉ピクシブ最優秀賞🎉<br>🎉学生メンター最優秀賞🎉<br><br>「🏃‍♀️身体でプログラミング」<a href="https://t.co/gFmUUtAF8d">https://t.co/gFmUUtAF8d</a></p>&mdash; 名工大プログラミング部C0de (@c0demattari) <a href="https://twitter.com/c0demattari/status/1750108308529381759?ref_src=twsrc%5Etfw">January 24, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

このハッカソンでは最終日に，各作品は，ピクシブ社員の方々や，C0deのOBから審査いただいた。
そしてわれらがPhysiCodeは「ピクシブ最優秀賞」と「学生メンター最優秀賞」のダブル受賞をした。
ありがとうございます。

ピクシブCTOの方からコメントいただき，特にアイデアの部分を褒めていただいたことがとてもうれしい。

## おわりに

どのチームも力作を制作した中，最優秀賞×2をいただき光栄です。

共同開発の難しさと楽しさをたくさん感じた1か月弱でした。

次はもう少し腕を上げて，またどこかで誰かと何かを作りたいですね。
アイデアを練っておきます。

## 余談

第一候補の「Brain and Body f\*ck」じゃなくて「PhysiCode」っていうかっこいい名前にしといて正解だったかもしれん
