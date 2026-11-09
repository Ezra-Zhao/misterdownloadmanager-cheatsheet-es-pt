# Mister Download Manager 速查表 | MDM Cheatsheet | Guía rápida de Mister Download Manager

**免费平替 IDM 的 Rust 下载器 —— 先分清下哪个文件、再谈快不快**

> 一页看懂 Mister Download Manager（MDM）：纯 Rust 从零写的开源下载管理器，操作习惯照着 IDM 来——多连接分片加速、断点续传、浏览器接管下载、视频与种子/magnet 下载、夜间队列调度，还带一个 MCP 服务，能让 Claude、Cursor 这些 AI 助手管你的下载列表。Windows、Linux、macOS 三平台，免费、无广告、无试用期、不用注册。这张速查不卖翻译（它的界面本来就有 86 种语言），卖的是新手最容易卡住的两件事：下对文件、安全装上。

- 上游项目：[anefzaoui/misterdownloadmanager](https://github.com/anefzaoui/misterdownloadmanager)（2026-11-09 实测 3,652 ★ / 253 forks，GPL-3.0；2026-10-29 建仓，7 个 release）
- 平台：Windows 10 / 11；Linux（Ubuntu、Debian、Fedora 等）；macOS（Apple Silicon 与 Intel，实验版，见诚实标注区）
- 本页结构：中文主文 → English → Español → Português

---

Apoyo y más: [GitHub Sponsors](https://github.com/sponsors/Ezra-Zhao) · [Gumroad — plantillas y cuadernos que uso](https://ezraflow28.gumroad.com) · [Ko-fi](https://ko-fi.com/ezra777zhao)

## 四个安装文件，先选哪个（下错是新手第一大坑）

下载只去一个地方：原仓的 GitHub Releases 页。Windows 会看到这四个文件，先对号入座：

| 文件 | 选它当 |
|---|---|
| `...-setup.exe` | **不确定就选它。** 它负责装好程序、连上浏览器、问你用哪种语言，一步到位 |
| `...-portable.zip` | 想放 U 盘随身带、或者不想安装：解压就能跑，所有东西都留在它自己的文件夹里 |
| `...-x64.zip` | 只想要纯程序包、不要安装器 |
| `...-extension-chromium.zip` | 想手动给浏览器装扩展（Chrome、Edge、Brave、Opera、Vivaldi）；其实从官方商店装更省事，见下面扩展那张卡 |

Linux 另有四种：deb（Ubuntu、Debian、Mint、Pop!_OS）、rpm（Fedora、openSUSE、RHEL）、AppImage（任何发行版）、tar.gz（纯程序包），按自己的发行版选。

## 未签名放行卡（被 SmartScreen 拦住，不等于中毒）

- MDM 这个早期版本**还没有做代码签名**（原仓自述），第一次在 Windows 上运行，系统可能弹出 "Windows protected your PC"。这是没签名的固定待遇，不是报毒。
- 放行走法（原仓原文的步骤）：点 **More info**，再点 **Run anyway**。
- 安全底线：**只从原仓 GitHub Releases 官方页下载**，别下第三方下载站的包。未签名的软件最容易被塞私货，你还没法验。

## 浏览器扩展差异卡

| 浏览器 | 情况 |
|---|---|
| Firefox（附加组件站版） | 功能最全：YouTube 页面上有下载按钮（原仓截图口径），普通下载也由它接管 |
| Chrome（网上应用店版） | 受商店政策限制，YouTube 上的下载按钮被禁（社区口径，证据 B）；普通下载接管不受这条影响 |
| Brave / Edge / Opera / Vivaldi 等 Chromium 系 | 与 Chrome 商店版同一限制（社区口径，证据 B）；也可以绕开商店，手动装 Releases 里的 `extension-chromium.zip` |

装好扩展后，浏览器里的下载会被 MDM 接住；MDM 没在运行时，下载会还给浏览器自己处理。

## 与 IDM 四行对照

| 项 | Mister Download Manager | IDM |
|---|---|---|
| 价格 | 免费，永久 | 付费，30 天试用之后买授权 |
| 开源 | 是，GPL-3.0 | 否 |
| 种子支持 | 支持 magnet 与 .torrent，还能做种 | 无此功能 |
| 界面语言 | 86 种（含西班牙语墨西哥/西班牙、葡萄牙语巴西/葡萄牙） | 40 种 |

（对照基准为原仓与 IDM 6.42 的对比表；它还顺手保留了 IDM 的命令行开关习惯，从 IDM 迁过来的人不用重学。）

## 它还会什么（够用就好，别当选购清单）

- 断了能续：崩溃、重启、断网之后接着下，不用从头来。
- 视频与图包：网页上的视频有按钮可点（含播放列表、字幕、只要声音），图片画廊能整包抓。
- 夜间队列：排好队列和时间表，可以把电脑唤醒下完再关机。
- AI 助手接入：自带 MCP 服务，Claude、Cursor、VS Code 能列出、添加、暂停、删除你的下载。
- 限速与 VPN 绑定：能给单个或全部下载限速，也能把流量锁死在一块网卡上、带 kill switch。

## 诚实标注区（这一栏是这张速查的命）

- **这张不卖翻译**：MDM 界面已有 86 种语言，西班牙语（墨西哥、西班牙）和葡萄牙语（巴西、葡萄牙）都在里面，第一次启动就问你用哪种，之后在 View → Language 里改。本页卖的是选文件和安全装法这两步。
- **速度数字是作者同机自测**：「比 IDM 快 5 倍、1 GB 文件 1 秒对 5.5 秒」出自原仓对照表——作者在同一台机器、同一个本地测试服务器、两边都用默认设置测的，七个场景全胜，方法与原始数据都公开在原仓里；仓里还带了那台测试服务器（labserver），不信可以自己复跑。但你的网络环境测不出这个数，标证据 B。
- **macOS 版是实验版**：作者自述还没在真 Mac 上试过，原仓就是挂出来招募人试的。先别拿它当主力下载器。
- **Linux 两个已知缺口**（原仓自述）：Flatpak 版浏览器接不到 MDM；屏幕阅读器（Orca）还读不了它的窗口。Windows 那边的 Narrator、NVDA 是支持的，别混为一谈。
- **势头数据**：3,652 ★ / 253 forks（2026-11-09 原仓实测，证据 A）；2026-10-29 才建仓，十来天冲到这个数（第三方新仓榜口径，证据 B）。项目年轻，作者自述引擎、主窗口和浏览器集成在 Windows 与 Linux 上已稳，一些边角还停在「够用」阶段。

---

## English (summary)

Mister Download Manager (3,652 stars / 253 forks as of 2026-11-09, GPL-3.0, created 2026-10-29) is a clean-room, open-source download manager written in Rust that keeps IDM's familiar workflow: multi-connection segmented downloads, resume after crashes or dropped connections, browser capture, video and torrent/magnet downloads, overnight queue scheduling, and an MCP server so Claude, Cursor or VS Code can manage your download list. It is free, with no ads, no trial and no sign-up, on Windows, Linux and macOS. This cheatsheet does not sell translation — the app already ships 86 UI languages — it sells the two steps where newcomers get stuck. First, pick the right file on the GitHub Releases page: `...-setup.exe` if you are not sure (it installs, connects the browser and asks your language), `...-portable.zip` for a USB stick or no-install use, `...-x64.zip` for the plain programs, and `...-extension-chromium.zip` only if you want to install the browser extension by hand. Second, the SmartScreen moment: this early version is not code-signed yet (upstream says so), so Windows may show "Windows protected your PC" — click More info, then Run anyway, and only ever download from the official Releases page. Extension differences: the Firefox add-on is the full-featured one, with a download button on YouTube pages; the Chrome Web Store version is limited by store policy and the YouTube button is banned there (community reports, evidence B), and Chromium browsers such as Brave, Edge, Opera and Vivaldi share that limit. Against IDM: free forever vs paid after a 30-day trial, open source (GPL-3.0) vs closed, full torrent support vs none, 86 UI languages vs IDM's 40. Honest notes: the "5× faster, 1 GB in 1 second vs 5.5" figures are the author's own same-machine benchmarks against a local test server that ships in the repo so anyone can rerun them (evidence B); the macOS builds are experimental and untested on a real Mac by the author's own admission; on Linux, Flatpak browsers cannot reach it and the Orca screen reader cannot read its windows yet.

---

## Español (guía rápida — traducción de estudio, pendiente de revisión por un hablante nativo)

**La alternativa gratuita a IDM, escrita en Rust: primero acierta con el archivo, después hablamos de velocidad.**

Mister Download Manager (3.652 estrellas / 253 forks a 9 de noviembre de 2026, GPL-3.0, creado el 29 de octubre de 2026) es un gestor de descargas de código abierto, escrito desde cero en Rust, que conserva la forma de trabajar de IDM: descargas por segmentos con varias conexiones, reanudación tras un corte, captura de descargas del navegador, vídeo y torrents/magnet, colas programadas para la noche y un servidor MCP para que Claude o Cursor gestionen tu lista. Es gratis, sin anuncios, sin periodo de prueba y sin registro, en Windows, Linux y macOS. Su interfaz ya viene en 86 idiomas, español incluido; esta guía no vende traducción, vende los dos pasos donde casi todo el mundo se atasca.

En la página de Releases de GitHub hay cuatro archivos para Windows y hay que elegir bien: `...-setup.exe` si no lo tienes claro (instala el programa, lo conecta con el navegador y te pregunta el idioma); `...-portable.zip` si lo quieres en un USB o sin instalar, descomprimir y listo; `...-x64.zip` si solo quieres los programas, sin instalador; y `...-extension-chromium.zip` solo si prefieres instalar la extensión del navegador a mano. Segundo paso: esta versión temprana aún no tiene firma de código, así que Windows puede mostrar «Windows protected your PC». No es un virus: pulsa «More info» y luego «Run anyway», y descarga únicamente desde la página oficial de Releases, nunca desde sitios de terceros.

Con las extensiones hay diferencias que conviene saber: la de Firefox es la completa, con botón de descarga sobre los vídeos de YouTube; la de la Chrome Web Store está limitada por las políticas de la tienda y ese botón está prohibido ahí (reportes de la comunidad, evidencia B), y lo mismo vale para Brave, Edge, Opera y Vivaldi. Frente a IDM: gratis para siempre frente a pago tras 30 días de prueba; código abierto (GPL-3.0) frente a cerrado; soporte completo de torrents frente a ninguno; 86 idiomas de interfaz frente a 40. Notas honestas: las cifras de velocidad («5 veces más rápido, 1 GB en 1 segundo frente a 5,5») son mediciones del propio autor, en la misma máquina y contra un servidor de pruebas local que viene en el repositorio para que cualquiera las repita (evidencia B); las versiones de macOS son experimentales y el autor admite que aún no las ha probado en un Mac real; y en Linux los navegadores Flatpak no pueden conectar con el programa y el lector de pantalla Orca aún no lee sus ventanas.

---

## Português (guia rápido — tradução de estudo, aguardando revisão de um falante nativo)

**A alternativa gratuita ao IDM, escrita em Rust: primeiro acerte o arquivo, depois a gente fala de velocidade.**

O Mister Download Manager (3.652 estrelas / 253 forks em 9 de novembro de 2026, GPL-3.0, criado em 29 de outubro de 2026) é um gerenciador de downloads de código aberto, escrito do zero em Rust, que mantém o jeito de trabalhar do IDM: downloads segmentados com várias conexões, retomada depois de uma queda, captura das descargas do navegador, vídeo e torrents/magnet, filas programadas para a noite e um servidor MCP para o Claude ou o Cursor cuidarem da sua lista. É grátis, sem anúncios, sem período de teste e sem cadastro, no Windows, no Linux e no macOS. A interface já vem em 86 idiomas, português do Brasil e de Portugal incluídos; este guia não vende tradução, vende os dois passos onde quase todo mundo trava.

Na página de Releases do GitHub há quatro arquivos para Windows, e é preciso escolher direito: `...-setup.exe` se você não tiver certeza (instala o programa, conecta com o navegador e pergunta o idioma); `...-portable.zip` se quiser levar num pen drive ou usar sem instalar, é só descompactar; `...-x64.zip` se quiser só os programas, sem instalador; e `...-extension-chromium.zip` só se preferir instalar a extensão do navegador na mão. Segundo passo: esta versão inicial ainda não tem assinatura de código, então o Windows pode mostrar «Windows protected your PC». Não é vírus: clique em «More info» e depois em «Run anyway», e baixe apenas da página oficial de Releases, nunca de sites de terceiros.

Nas extensões há diferenças que vale saber: a do Firefox é a completa, com botão de download sobre os vídeos do YouTube; a da Chrome Web Store é limitada pelas políticas da loja e esse botão é proibido lá (relatos da comunidade, evidência B), e o mesmo vale para Brave, Edge, Opera e Vivaldi. Contra o IDM: grátis para sempre contra pagamento depois de 30 dias de teste; código aberto (GPL-3.0) contra fechado; suporte completo a torrents contra nenhum; 86 idiomas de interface contra 40. Notas honestas: os números de velocidade («5 vezes mais rápido, 1 GB em 1 segundo contra 5,5») são medições do próprio autor, na mesma máquina e contra um servidor de testes local que vem no repositório para qualquer um repetir (evidência B); as versões de macOS são experimentais e o autor admite que ainda não as testou num Mac de verdade; e no Linux os navegadores em Flatpak não conseguem alcançar o programa e o leitor de tela Orca ainda não lê as janelas dele.

---

## 来源与声明

- 灵感来源 / Source / Fuente / Fonte: [anefzaoui/misterdownloadmanager](https://github.com/anefzaoui/misterdownloadmanager)（2026-11-09 实测 3,652 ★ / 253 forks；文件选择、SmartScreen 步骤与对照表均以当日上游 README 为准）
- 本仓是个人学习整理：内容用我自己的话总结自上游公开文档，不搬运原文；速度数字为上游作者自测口径并已标注，引用时请同时核对上游 README 的基准测试一节。
- 西语、葡语部分为学习译稿，待母语校对。Las secciones en español y portugués son traducciones de estudio pendientes de revisión nativa.
- License: MIT © 2026 Guangyi Zhao（注：本速查仓自身的许可；上游 MDM 本体为 GPL-3.0，与本仓无关）
