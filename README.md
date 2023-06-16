<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Directory chhunga i luh hnuah nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) install hmasak a tha a, chutah chuan `direnv allow` install a tha ( directory i luh hnuah [.envrc chu](https://github.com/xxai-art/doc/blob/main/.envrc) automatic in a execute ang).

A awmzia chu: Chinese tawng Japanese, Korean, English, English tawng dang zawng zawnga lehlin. Chinese leh English chauh support i duh chuan `zh: en` chauh i ziak thei.

A awmzia chu: Chinese tawng Japanese, Korean, English, English tawng dang zawng zawnga lehlin. Chinese leh English chauh support i duh chuan `zh: en` chauh i ziak thei.

* [hmalam atanga code awm](https://github.com/xxai-art/web)
* [Site pumpui tana ṭawng pack hrang hrang](https://github.com/xxai-art/web/tree/main/i18n)
* [Login module hrang hrang atana tawng pack hrang hrang](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Website Ṭawng hrang hranga Documentation siam](https://github.com/xxai-doc)

Front-end programming language chu [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) a ni a, hei hian coffeescript syntax hmanga feature thenkhat a dah belh a, [./coffee_plus.md](./coffee_plus.md) en rawh.

## Website leh document hrang hrangte internationalization

A hnuaia project 3 te hi siam rawh

* [@w5/mdt ah a awm bawk](https://www.npmjs.com/package/@w5/mdt)

  Suffix chu `.mdt` a ni a, pawn lam file refer nan `<+ ./coffee_plus/import.js>` ang chi syntax i hmang thei a, suffix `.md` hmangin markdown i siam thei bawk.

* [@w5/trmd ah hian a awm](https://www.npmjs.com/package/@w5/trmd)

  Markdown lehlin hian code leh link a letling dawn lo va, sentence lehlin te chu a cache ang. Lehlin chu siam danglam ni mah se, a original text chu siam danglam a nih loh chuan, execute leh chuan lehlin siam danglamna chu a overwrite lo vang.

* [@w5/i18n ah a awm](https://www.npmjs.com/package/@w5/i18n)

  `yaml` siam website lehlinna tur ṭawng file.

### Document Lehlin Automation tih dan tur

Code dahna hmun [xxai-art/doc](https://github.com/xxai-art/doc) en rawh

Directory chhunga i luh hnuah nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) install hmasak a tha a, chutah chuan `direnv allow` install a tha ( directory i luh hnuah [.envrc chu](https://github.com/xxai-art/doc/blob/main/.envrc) automatic in a execute ang).

Ṭawng za tam takah lehlin code base lian tak awm lo turin ṭawng tin atan code base hran ka siam a, code base dahna tur organization ka siam bawk

Environment variable `GITHUB_ACCESS_TOKEN` set a, chutah [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) run chuan code repository chu a siam nghal mai ang.

Dik tak chuan code base-ah pawh i dah thei bawk.

Lehlin script reference [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Script code hi hetiang hian hrilhfiah a ni:

[bunx](https://bun.sh/docs/cli/bunx) hi npx thlakna a ni a, a rang zawk. Dik tak chuan bun install i neih loh chuan `npx` i hmang zawk thei.

`bunx mdt zh` hian zh directory a `.mdt` chu `.md` tiin a render a, a hnuaia linked file 2 te hi en rawh

* [coffee_plus.mdt a ni](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md a ni](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` hi translation atana core code a ni ( `nodejs` chauh install i neih a, mahse `bun` leh `direnv` install a nih loh chuan `npx i18n` pawh i run thei bawk a, translate theih a ni).

[I18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) a parse ang a, he document-a `i18n.yml` configuration chu hetiang hi a ni:

```
en:
zh: ja ko en
```

A awmzia chu: Chinese tawng Japanese, Korean, English, English tawng dang zawng zawnga lehlin. Chinese leh English chauh support i duh chuan `zh: en` chauh i ziak thei.

A hnuhnung ber chu [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) a ni a, hei hian ṭawng tinte `README.md` main title leh subtitle hmasa ber inkara thu awmte chu extract-in entry `README.md` a siam a ni. Code hi a awlsam hle a, nangmah ngeiin i en thei ang.

Google API hi a thlawna lehlin nan hman a ni. Google i lut thei lo a nih chuan proxy configure la, set la, chu chu:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Translation script hian `.i18n` directory-ah translated cache a siam ang a, khawngaihin `git status` hmangin check la, code repository-ah add la, translation repeated a awm loh nan.

Cache update turin translation i modify apiangin `bunx i18n` kha run thin ang che.

Original text leh translation hi a ruala siam danglam a nih chuan cache a buai dawn a, chuvangin siam danglam i duh chuan pakhat chauh i siam danglam thei a, chutah chuan `bunx i18n` run la, cache chu update rawh.
