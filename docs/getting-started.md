---
id: getting-started
title: Эхлэх
---

<style>
  .toggler {
    margin-top: 2em;
  }
  .toggler li {
    display: inline-block;
    position: relative;
    top: 1px;
    padding: 10px;
    margin: 0px 2px 0px 2px;
    border: 1px solid #05A5D1;
    border-bottom-color: transparent;
    border-radius: 3px 3px 0px 0px;
    color: #05A5D1;
    background-color: transparent;
    font-size: 0.99em;
    cursor: pointer;
  }
  .toggler li:first-child {
    margin-left: 0;
  }
  .toggler li:last-child {
    margin-right: 0;
  }
  .toggler ul {
    width: 100%;
    display: inline-block;
    list-style-type: none;
    margin: 0;
    border-bottom: 1px solid #05A5D1;
    cursor: default;
  }
  @media screen and (max-width: 960px) {
    .toggler li,
    .toggler li:first-child,
    .toggler li:last-child {
      display: block;
      border-bottom-color: #05A5D1;
      border-radius: 3px;
      margin: 2px 0px 2px 0px !important;
    }
    .toggler ul {
      border-bottom: 0;
    }
  }
  .toggler a {
    display: inline-block;
    padding: 10px 5px;
    margin: 2px;
    border: 1px solid #05A5D1;
    border-radius: 3px;
    text-decoration: none !important;
  }
  .display-guide-quickstart .toggler .button-quickstart,
  .display-guide-native .toggler .button-native,
  .display-os-mac .toggler .button-mac,
  .display-os-linux .toggler .button-linux,
  .display-os-windows .toggler .button-windows,
  .display-platform-ios .toggler .button-ios,
  .display-platform-android .toggler .button-android {
    background-color: #05A5D1;
    color: white;
  }
  block { display: none; }
  .display-guide-quickstart.display-platform-ios.display-os-mac .quickstart.ios.mac,
  .display-guide-quickstart.display-platform-ios.display-os-linux .quickstart.ios.linux,
  .display-guide-quickstart.display-platform-ios.display-os-windows .quickstart.ios.windows,
  .display-guide-quickstart.display-platform-android.display-os-mac .quickstart.android.mac,
  .display-guide-quickstart.display-platform-android.display-os-linux .quickstart.android.linux,
  .display-guide-quickstart.display-platform-android.display-os-windows .quickstart.android.windows,    .display-guide-native.display-platform-ios.display-os-mac .native.ios.mac,
  .display-guide-native.display-platform-ios.display-os-linux .native.ios.linux,
  .display-guide-native.display-platform-ios.display-os-windows .native.ios.windows,
  .display-guide-native.display-platform-android.display-os-mac .native.android.mac,
  .display-guide-native.display-platform-android.display-os-linux .native.android.linux,
  .display-guide-native.display-platform-android.display-os-windows .native.android.windows {
    display: block;
  }
</style>

Энэ хуудас дээрх мэдээллийн тусламжтай та React Native дээр эхний аппаа хийж, суулгах болно. Хэрэв та аль хэдийн React Native суулгасан бол шууд [Tutorial](tutorial.md) хэсэг рүү шилжээрэй.

<strong>Та вэб хийх талаар туршлагатай</strong> бол Expo tools-тэй React Native-ийг ашиглах нь зүйтэй. Учир нь та Xcode эвсэл Android Studio суулгаж, тохиргоо хийхгүйгээр ажлаа эхлүүлэх боломжтой юм. Expo CLI нь таны төхөөрөмж дээр хөгжүүлэлтийн орчныг бий болгож өгөх бөгөөд та React Native аппаа хэдхэн минутын дотор л бичих боломжтой. Даруй хөгжүүлэхийг хүсвэл та интернэт хөтчөөрөө [Snack](https://snack.expo.io/)-руу орж, React Native-ийг ашиглаж үзэх боломжтой.

<strong> Хэрэв та натив апп хөгжүүүлэлтийн талаар мэдлэгтэй бол</strong> та React Native CLI-ийг ашиглах нь зүйтэй, гэхдээ Xcode эсвэл Android Studio шаардлагатай. Эдгээрийн аль нэгийг нь суулгасан байгаа бол та хэдэн минутын дотор л аппаа ажиллуулах боломжтой. Хэрэв суулгаагүй бол суулгах, тохиргоо хийхэд нэг цаг орчим хугацаа шаардлагатай.

<div class="toggler">
  <ul role="tablist" >
    <li id="quickstart" class="button-quickstart" aria-selected="false" role="tab" tabindex="0" aria-controls="quickstarttab" onclick="displayTab('guide', 'quickstart')">
      Expo CLI Түргэн эхлэх
    </li>
    <li id="native" class="button-native" aria-selected="false" role="tab" tabindex="-1" aria-controls="nativetab" onclick="displayTab('guide', 'native')">
      React Native CLI Түргэн эхлэх
    </li>
  </ul>
</div>

<block class="quickstart mac windows linux ios android" />
Та [Node 10+](https://nodejs.org/en/download/) суулгасан бол  npm ашиглан  Expo CLI-ийг командын мөрт оруулан суулгах боломжтой :

```sh
npm install -g expo-cli
```

Тэгээд доорх командыг өгч, "Awesomeproject" гэсэн нэртэй React Native дээрх шинэ аппаа бүтээнэ:

```sh
expo init AwesomeProject

cd AwesomeProject
npm start # you can also use: expo start
```

Ингэснээр та хөгжүүлэлтийн сервер асна.

## React Native дээрх аппаа ажиллуулах

Та iOS эсвэл Android утсан дээрээ [Expo](https://expo.io) суулгаад, өөрийн компьютер холбогдсонтой ижил wifi-гаар холбогдоно. Android дээр Expo аппыг ашиглан терминалаасаа QR код уншуулж, аппаа нээнэ. iOS дээр холбоос авахын тулд дэлгэц дээрх зааврыг дагана.

### Аппдаа өөрчлөлт оруулах

Апп тань амжилттай болсон болохоор одоо өөрчлөлт оруулая. Хүссэн текст янзлагч дээрээ `App.js` -ийг нээн зарим мөрийг өөрчлөөд хадгал, аппликейшн автоматаар дахин ачаалах учиртай.

### Ингээд боллоо!

Танд баяр mhj! Та хамгийн анхны React Native аппаа ажиллуулж, өөрчлөлт хийж үзлээ.

<center><img src="/react-native/docs/assets/GettingStartedCongratulations.png" width="150"></img></center>

## Одоо яах вэ?

Хэрэв та Expo-той холбоотой асуух зүйл байвал [docs](https://docs.expo.io)-ээс харах боломжтой. Мөн [Expo forums](https://forums.expo.io) форумаас туслалцаа авч болно.

Эдгээр хэрэгсэл нь таныг ажлаа хурдан эхлүүлэхэд туслах болно. Expo CLI ашиглан апп хийхээсээ өмнө, [юу хийх боломжгүй](https://docs.expo.io/versions/latest/introduction/why-not-expo) тухай уншаарай.

Хэрэв Expo-ийг ашиглах явцад ямар нэг асуудал гарвал дахин шинээр асуулт үүсгэхийн оронд энэ тухай өмнө асуусан эсэхийг хараарай:

- [Expo CLI асуулт](https://github.com/expo/expo-cli/issues) дотор ( Expo CLI-той холбоотой асуудлууд), эсвэл
- [Expo асуудлууд](https://github.com/expo/expo/issues) гэсэн рүү орж (Expo client эсвэл SDK-тай холбоотой мэдээлэл харж болно).

React Native-ийн тухай илүү ихийг мэдэхийг хүсэж байвал [Хичээл](tutorial.md) гэсэн рүү ороорой.

### Аппаа симулятор эсвэл виртуал төхөөрөмж дээр ажиллуулах

Expo CLI-ийн тусламжтай та React Native аппаа биет төхөөрөмж дээр хөгжүүлэлтийн орчин үүсгэхгүйгээр хялбархан ажиллуулах боломжтой. Хэрэв та аппаа iOS симулятор эсвэл Android виртуал төхөөрөмж дээр ажиллуулахыг хүсвэл Xcode хэрхэн суулгах, Android хөгжүүлэлтийг орчинг хэрхэн үүсгэх тухай судлах зорилгоор натив код ашиглан апп хийх заавартай танилцаарай.

Үүний дараа та `npm run android` командаар Android виртуал төхөөрөмж дээр аппаа нээх боломжтой. iOS симулятор дээр ажиллуулах бол `npm run ios` гэж бичнэ. (Зөвхөн macOS)

### Анхаарах зүйлс

Expo ашиглах үед натив код үүсгэдэггүй тул React Native API, Expo апп дээрх компонентүүдаас өөр тусгай натив модуль багтаах боломжгүй.

Та аяндаа өөрийн натив кодыг оруулах хэрэгтэй болсон ч энэ нь Expo ашиглахгүй байх шалтгаан биш юм. Энэ тохиолдолд та "[цуцалж](https://docs.expo.io/versions/latest/expokit/eject)" өөрийн натив кодоо оруулж хийх боломжтой. Хэрэв цуцалсан бол та "Натив код ашиглан апп хийх" заавартай танилцах шаардлагатай.

Expo CLI нь таны аппад Expo client аппыг дэмжих React Native-ийн хамгийн сүүлийн үеийн хувилбарыг ашиглах боломжийг бүрдүүлнэ. The Expo client апп нь React Native-ийн хувилбар байнгын тогтвортой гарсан үеэс долоо хоног орчмын дотор тухайн хувилбарыг дэмжих боломжтой болдог. Ямар хувилбаруудыг дэмждэгийг мэдэхийг хүсвэл [үүнийг](https://docs.expo.io/versions/latest/sdk/#sdk-version) уншаарай.

Хэрэв та React Native-ийг бэлэн байгаа төсөлдөө ашиглахыг хүсвэл Expo CLI ашиглахгүйгээр аппаа хийх тусгай орчныг нь тохируулж эхлэх боломжтой. "Натив кодоор апп хийх" гэснийг сонгон дээрх зааврыг даган React Native-т нийцсэн натив кодоор үүсгээрэй.

<block class="native mac windows linux ios android" />

<p>Хэрэв та натив код бичих шаардлагатай бол энэ зааврыг дагана уу. Жишээ нь та React Native-ийг одоо байгаа апптай нэгтгэхийг хүсэх эсвэл <a href="getting-started.html" onclick="displayTab('guide', 'quickstart')">Expo</a> "салгасан" эсвэл React Native апп хийхийг хүсэж байгаа бол танд энэ хэсэг туслах болно.</p>

Хөгжүүлэгчийн системээс шалтгаалан, мөн iOS эсвэл Android-д зориулж хийж байгаагаас шалтгаалан заавар нь бага зэрэг өөр байх боломжтой. Хэрэв та iOS, Android хоёрт хоёуланд нь зориулж апп хийхийг хүсэж байвал тэгсэн ч болно. Та зөвхөн аль нэгнээс нь эхлэхэд хангалттай бөгөөд тохируулах нь бага зэрэг өөр байна.

<div class="toggler">
  <span>Хөгжүүлэлтийн ҮС:</span>
  <a href="javascript:void(0);" class="button-mac" onclick="displayTab('os', 'mac')">macOS</a>
  <a href="javascript:void(0);" class="button-windows" onclick="displayTab('os', 'windows')">Windows</a>
  <a href="javascript:void(0);" class="button-linux" onclick="displayTab('os', 'linux')">Linux</a>
  <span>Ашиглах ҮС:</span>
  <a href="javascript:void(0);" class="button-ios" onclick="displayTab('platform', 'ios')">iOS</a>
  <a href="javascript:void(0);" class="button-android" onclick="displayTab('platform', 'android')">Android</a>
</div>

<block class="native linux windows ios" />

## Дэмжихгүй

<blockquote><p>iOS-т зориулсан натив код ашиглан апп хийхэд Mac компьютер шаардлагатай. Та <a href="getting-started.html" onclick="displayTab('guide', 'quickstart')">Түргэн Эхлэх</a> гэсэн рүү орж оронд нь Expo ашиглан хэрхэн аппаа хийх тухай мэдээлэлтэй танилцана уу.</p></blockquote>

<block class="native mac ios" />

## Хамаарал бүхий програмуудыг суулгах

Танд Node, Watchman, React Native команд мөрийн интерфейс болон Xcode хэрэгтэй.

Та аппаа хөгжүүлэхдээ хүссэн засварлах програмаа ашиглах боломжтой ч iOS-д зориулсан React Native апп хийхэд Xcode-ийг суулгаж, шаардлагатай програмуудаа тохируулах хэрэгтэй.

<block class="native mac android" />

## Хамаарал бүхий програмуудыг суулгах

Танд Node, Watchman, React Native команд мөрийн интерфейс, JDK, болон Android Studio хэрэгтэй.

<block class="native linux android" />

## Хамаарал бүхий програмуудыг суулгах

Танд Node, React Native команд мөрийн интерфейс, JDK, болон Android Studio хэрэгтэй.

<block class="native windows android" />

## Хамаарал бүхий програмуудыг суулгах

Танд Node, React Native команд мөрийн интерфейс, Python2, JDK, болон Android Studio хэрэгтэй.

<block class="native mac windows linux android" />

Та аппаа хөгжүүлэхдээ хүссэн засварлах програмаа ашиглах боломжтой ч Аndroid-д зориулсан React Native апп хийхэд Android Studio-г суулгаж шаардлагатай програмуудаа тохируулах хэрэгтэй.

<block class="native mac ios android" />

### Node, Watchman

Бид танд [Homebrew](http://brew.sh/) ашиглан Node, Watchman суулгахыг санал болгож байна. Терминал дотроо Homebrew суулгасны дараа доорх кодыг уншуулна уу:

```
brew install node
brew install watchman
```

Хэрэв та аль хэдийн Node суулгасан бол Node 8.3 юм уу, сүүлийн хувилбар мөн эсэхийг шалгаарай.

[Watchman](https://facebook.github.io/watchman) нь Facebook-ийн файлын систем дэх өөрчлөлтийг хянах зориулалттай юм. Ажиллагаагаа сайжруулахын тулд үүнийг суулгахыг танд зөвлөх байна.

<block class="native linux android" />

### Node

Node 8.3 эсвэл сүүлийн үеийн хувилбарыг суулгах бол [installation instructions for your Linux distribution](https://nodejs.org/en/download/package-manager/) -рүү орно уу.

<block class='native windows android' />

### Node, Python2, JDK

Node, Python2-ийг суулгахдаа Windows зориулсан, түгээмэл ашиглагддаг package manager-ээс татахыг танд зөвлөж байна. [Chocolatey](https://chocolatey.org)

React Native-т мөн [Java SE Development Kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)-ийн сүүлийн үеийн хувилбар шаардлагатай. Мөн Python 2 ч бас. Аль алиныг нь Chocolatey ашиглан суулгаж болно..

Administrator Command Prompt-ийг нээн (right click Command Prompt and select "Run as Administrator"), доорх командыг өгнө:

```powershell
choco install -y nodejs.install python2 jdk8
```

Хэрэв та аль хэдийн Node-ийг суулгасан бол Node 8.3 юм уу, сүүлийн үеийн хувилбар эсэхийг шалгаарай. Хэрэв JDK суулгасан бол 8 юм уу сүүлийн шинэ хувилбар эсэхийг шалгаарай.

> Програм суулгахтай холбоотой нэмэлт мэдээллийг та [Node's Downloads page](https://nodejs.org/en/download/) эндээс харж болно.

<block class="native mac ios android" />

### The React Native CLI

Node нь npm-тэй ирдэг бөгөөд үүнийг ашиглан React Native суулгах команд мөрийн интерфейс боломжтой.

Терминал дотроо доорх командыг өгөөрэй:

```
npm install -g react-native-cli
```

> Хэрэв `Cannot find module 'npmlog'` алдаа зааж байвал шууд npm суулгаад үзээрэй : `curl -0 -L https://npmjs.org/install.sh | sudo sh`.

<block class="native windows linux android" />

### The React Native CLI

Node нь npm-тэй ирдэг бөгөөд үүнийг ашиглан React Native суулгах команд мөрийн интерфейс боломжтой.

Command Prompt эсвэл shell-д доорх командыг өгөөрэй:

```powershell
npm install -g react-native-cli
```

> Хэрэв`Cannot find module 'npmlog'` гэсэн алдаа өгч байвал npm-ийг шууд суулгаад үзээрэй: `curl -0 -L https://npmjs.org/install.sh | sudo sh`.

<block class="native mac ios" />

### Xcode

Xcode суулгах хамгийн хялбар арга бол [Mac App Store](https://itunes.apple.com/us/app/xcode/id497799835?mt=12) ашиглах юм. Xcode суулгаснаар давхар iOS Simulator болон iOS апп хийхэд шаардлагатай бусад програмуудыг суулгах юм.

Хэрэв та аль хэдийн Xcode суулгасан бол 9.4 эсвэл үүнээс сүүлийн үеийн хувилбар мөн эсэхийг шалгаарай.

#### Команд мөрийн хэрэгслүүд

Мөн та Xcode Command Line Tools-ийг суулгах шаардлагатай. Xcode-ийг нээгээд, Xcode цэсээс "Preferences..." гэснийг сонгоно. Locations panel гэсэн рүү очин хамгийн сүүлийн үеийн Command Line Tools-ийг сонгон суулгана.

![Xcode Command Line Tools](/react-native/docs/assets/GettingStartedXcodeCommandLineTools.png)

<block class="native mac linux android" />

### Java Хөгжүүлэлтийн багц

React Native нь сүүлийн үеийн Java SE Development Kit (JDK)-ыг шаарддаг. [Download and install Oracle JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html). Мөн та [OpenJDK 8](http://openjdk.java.net/install/)-ийг ашиглах боломжтой.

<block class="native mac linux windows android" />

### Android хөгжүүлэлтийн орчин

Хэрэв та анхлан Android апп хөгжүүлж байгаа бол хөгжүүлэлтийн орчноо тохируулах нь зарим талаараа уйтгартай мэт санагдаж магад. Харин Android хөгжүүлэлтийн талаар мэдлэгтэй бол цөөн хэдэн зүйлийг хангасан байх ёстой. Аль ч тохиолдолд доорх алхмуудыг нэг бүрчлэн дагахыг зөвлөе.

<block class="native mac windows linux android" />

#### 1. Android Studio суулгах

[Android Studio татах ба суулгах](https://developer.android.com/studio/index.html). Суулгах төрлөө сонгох хэрэгтэй болох үеэд "Custom" гэснийг сонгоорой. Доорх нэрсийн хажууд байгаа дөрвөлжин нүдийг зөвлөөрэй:

<block class="native mac windows android" />

- `Android SDK`
- `Android SDK Platform`
- `Performance (Intel ® HAXM)` ([AMD CPU бол эндээс хар](https://android-developers.googleblog.com/2018/07/android-emulator-amd-processor-hyper-v.html))
- `Android Virtual Device`

<block class="native linux android" />

- `Android SDK`
- `Android SDK Platform`
- `Android Virtual Device`

<block class="native mac windows linux android" />

Тэгээд "Next" гэсэн руу орж эдгээр компонентүүдийг суулгаарай.

> Хэрэв дөрвөлжин нүднүүд нь саарал өнгөтэй байвал та эдгээр бүрэлдэхүүн хэсгүүдийг дараа суулгах боломжтой гэсэн үг.

Тохиргоо хийсний дараа Тавтай морилно уу гэсэн дэлгэц гарах бөгөөд дараагийн шат руу шилжиж болно.

#### 2. Android SDK суулгах

Android Studio нь Android SDK-ийн сүүлийн үеийн хувилбарыг автоматаар суулгадаг. Натив код ашиглан React Native апп хийж байгаа үед `Android 9 (Pie)` SDK тусгайлан хэрэг болдог. Android Studio дотор SDK Manager-ыг ашиглан нэмэлт Android SDKs суулгах боломжтой.

"Welcome to Android Studio" дэлгэц дээрээс SDK Manager -рүү хандаж болно. "Тохиргоо хийх" гэснийг дараад "SDK Manager" гэснийг сонгоорой.

<block class="native mac android" />

![Android Studio Welcome](/react-native/docs/assets/GettingStartedAndroidStudioWelcomeMacOS.png)

<block class="native windows android" />

![Android Studio Welcome](/react-native/docs/assets/GettingStartedAndroidStudioWelcomeWindows.png)

<block class="native mac windows linux android" />

> Мөн Android Studio дотор "Preferences" гэсэн хэсгээс **Appearance & Behavior** → **System Settings** → **Android SDK** гэж орон SDK Manager -г олох боломжтой.

SDK Manager дотроосоо "SDK Platforms" гэснийг сонгоно. Тэгээд баруун доод буланд байх "Show Package Details" гэсэн дээр дарна. `Android 9 (Pie)` гэснийг хайж, нээгээд доорх зүйлсийг зөвлөсөн эсэхийг шалгана:

- `Android SDK Platform 28`
- `Intel x86 Atom_64 System Image` or `Google APIs Intel x86 Atom System Image`

Дараа нь "SDK Tools" гэсэн рүү орж "Show Package Details" гэснийг харна. "Android SDK Build-Tools" гэсэн хайж олон, дэлгэж хараад `28.0.3` гэснийг сонгосон эсэхийг шалгана.

Эцэст нь "Apply" гэдгийг дарж, Android SDK болон бусад хэрэгслүүдээ татаж аван суулгана.

#### 3. ANDROID_HOME орчны хувьсагч

React Native нь натив код ашиглан апп хийхийн тулд орчны зарим хувьсагчийг тохируулахыг шаарддаг.

<block class="native mac linux android" />

Тохиргоо хийх файл дотор үүнийг нэмнэ үү `$HOME/.bash_profile` эсвэл `$HOME/.bashrc`:

<block class="native mac android" />

```
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

<block class="native linux android" />

```
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

<block class="native mac linux android" />

> `.bash_profile` гэдэг нь тусгайлан `bash`-д зориулсан гэсэн үг. Хэрэв та өөр шэлл ашиглаж байгаа бол тохиргооны файл дээрээ тухайн шэллд засвар оруулах шаардлагатай.

`source $HOME/.bash_profile` гэж бичээд одоогийн бүрхүүлдээ тохиргоогоо оруулна. `echo $PATH` гэж уншуулан ANDROID_HOME хувьсагч байгаа эсэхийг нягтална уу.

> Зөв Android SDK байршил ашиглаж байгаа эсэхээ шалгаарай. Android Studio дотор SDK-ийн бодит байршлыг олохын тулд "Preferences" гэж ороод **Appearance & Behavior** → **System Settings** → **Android SDK** гэсэн дарааллаар орно.

<block class="native windows android" />

Windows Control Panel дотор **System and Security** гэсний доор System pane гэсэн руу орно. Тэгээд **Change settings...** гэснийг дараад **Advanced** гэснийг нээн **Environment Variables...** гэсэн дээр дарна. **New...** гэснийг дарж, Android SDK байршлыг заах `ANDROID_HOME` хэрэглэгчийн хувьсагчийг шинээр үүсгэнэ.

![ANDROID_HOME Environment Variable](/react-native/docs/assets/GettingStartedAndroidEnvironmentVariableANDROID_HOME.png)

SDK нь автоматаар доорх байршилд суудаг:

```powershell
c:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk
```

Android Studio дотор SDK-ийн одоогийн байршлыг олохдоо "Preferences" гэдэг дээр дараад **Appearance & Behavior** → **System Settings** → **Android SDK** дарааллаар орно.

Шинээр Command Prompt цонхыг нээн дараагийн шатанд шилжихийн өмнө шинэ орчны хувьсагч уншиж байгаа эсэхийг шалгана.

#### 4. Замд платформ хэрэгслүүд нэмэх

Windows Control Panel​ дотор **System and Security** гэсний доорх System pane гэсэн дээр дарна. Тэгээд **Change settings...** гэж дарна. **Advanced** гэснийг нээн and **Environment Variables...** гэснийг сонгоно. **Path** хувьсагч гэснийг нээн, **Edit** гэснийг дарна. **New** гэсэн дээр дарж платформ хэрэгслүүдийн жагсаалтыг харна.

Энэхүү хавтас нь автоматаар доорх байрлалд байдаг:

```powershell
c:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk\platform-tools
```

<block class="native linux android" />

### Watchman

Watchman суулгахыг хүсвэл [Watchman суулгах заавар](https://facebook.github.io/watchman/docs/install.html#buildinstall)-ыг дагана уу.

> [Watchman](https://facebook.github.io/watchman/docs/install.html) нь файл систем дэх өөрчлөлтийг харах зорилготой Facebook-ийн гаргасан хэрэгсэл юм. Ажиллагаагаа илүү сайжруулж, тодорхой асуудалтай хүнд үед илүү боломжтой байхыг хүсэж байгаа бол танд үүнийг суулгахыг зөвлөх байна. (Үүнийг суулгахгүй ч байсан болно. Хүртэх ашиг тус нь янз бүр байх боломжтой. Одоо суулгавал дараа нь төвөг учрах нь бага байна).

<block class="native mac ios" />

## Шинэ аппликейшн бүтээх

React Native команд мөрийн интерфейсийг ашиглан "AwesomeProject" нэртэй шинэ апп үүсгэх:

```
react-native init AwesomeProject
```

Хэрэв та одоо байгаа аппыг React Native-тай нэгтгэж байгаа бол ингэх шаардлагагүй. Хэрэв та Expo-гоос "ejected" болсон ( эсвэл React Native апп хийх), эсвэл одоо байгаа React Native төсөл дээрээ iOS дэмждэг болгох гэж байгаа бол (үүнийг харна уу [Platform Specific Code](platform-specific-code.md)). Мөн та гуравдагч CLI ашиглан React Native аппаа эхлүүлэх боломжтой, Тухайлбал, [Ignite CLI](https://github.com/infinitered/ignite).

### [Нэмэлт] Онцгойлон аль нэг хувилбарыг ашиглах

Хэрэв та React Native-ийн аль нэг хувилбарыг ашиглан шинэ апп хийх гэж байгаа бол `--version` нэмэлтийг ашиглах боломжтой:

```
react-native init AwesomeProject --version X.XX.X
```

```
react-native init AwesomeProject --version react-native@next
```

<block class="native mac windows linux android" />

## Шинэ аппликейшн бүтээх

React Native командын мөрийн интерфейсийг ашиглан "AwesomeProject" нэртэй шинэ төслөө эхлүүлэх:

```
react-native init AwesomeProject
```

Хэрэв та одоо байгаа аппыг React Native-тай нэгтгэж байгаа бол ингэх шаардлагагүй. Хэрэв та Create React Native App "ejected" болсон ( эсвэл React Native апп хийх), эсвэл одоо байгаа React Native төсөл дээрээ Android дэмждэг болгох гэж байгаа бол (үүнийг харна уу [Platform Specific Code](platform-specific-code.md)). Мөн та гуравдагч CLI ашиглан React Native аппаа эхлүүлэх боломжтой, Тухайлбал, [Ignite CLI](https://github.com/infinitered/ignite).

### [Нэмэлт] Онцгойлон аль нэг хувилбарыг ашиглах

Хэрэв та React Native-ийн аль нэг хувилбарыг ашиглан шинэ апп хийх гэж байгаа бол `--version` нэмэлтийг ашиглах боломжтой:

```
react-native init AwesomeProject --version X.XX.X
```

```
react-native init AwesomeProject --version react-native@next
```

<block class="native mac windows linux android" />

## Android төхөөрөмжийг бэлдэх

React Native Android аппаа ашиглахын тулд танд Android төхөөрөмж хэрэг болно. Ингэхдээ бодит Android төхөөрөмж байж болохоос гадна Android төхөөрөмжийг компьютер дээр дуурайн ажилладаг виртуал Android төхөөрөмжийг ашиглах боломжтой. Аль нь ч бай та Android апп хөгжүүлж байгаа бол аппаа ажиллуулах төхөөрөмж хэрэгтэй.

### Бодит төхөөрөмж ашиглах

Хэрэв танд Android-ийн төхөөрөмж биетээрээ байгаа бол Android виртуал төхөөрөмжийн оронд төхөөрөмжөө компьютертойгоо USB каблиар холбон доорх зааврыг дагахад болно. [энд](running-on-device.md).

### Виртуал төхөөрөмж ашиглах

Хэрэв та Android Studio ашиглах бол `./AwesomeProject/android`-ийг нээгээд, Android Studio дотроо "AVD Manager" гэснийг нээн ашиглах боломжтой Android виртуал төхөөрөмжүүдийн жагсаалтыг харж болно. Үүн шиг тэмдэглэгээг олж харна уу:

![Android Studio AVD Manager](/react-native/docs/assets/GettingStartedAndroidStudioAVD.png)

Хэрэв та Android Studio-ийг дөнгөж суулгасан бол [Шинээр Android Виртуал Төхөөрөмж үүсгэх](https://developer.android.com/studio/run/managing-avds.html) хэрэгтэй. "Виртуал төхөөрөмж үүсгэх..." гэснийг сонгоод жагсаалт дундаас аль нэг утсыг сонгон "Дараа нь" гэснийг дарна. Ингээд **Pie** Аппликейшн програмчлалын интерфейс үе 28 гэснийг сонгоно.

<block class="native linux android" />

> Ажиллагааг сайжруулахын тулд [VM acceleration](https://developer.android.com/studio/run/emulator-acceleration.html#vm-linux)-ийг тохируулахыг бид зөвлөж байна. Зааврыг дагуу хийсний дараа AVD Manager гэсэн рүү эргээд очоорой.

<block class="native windows android" />

> Хэрэв HAXM суулгаагүй байгаа бол,"Install HAXM" гэсэн дээр дарах эсвэл [энэхүү заавар](https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows)-ыг дагаарай. Тохиргоо хийсний дараа AVD Manager гэсэн рүү эргээд очоорой.

<block class="native mac android" />

> Хэрэв HAXM суулгаагүй бол [энэхүү заавар](https://github.com/intel/haxm/wiki/Installation-Instructions-on-macOS)-ыг дагаарай. Тохиргоо хийсний дараа AVD Manager рүү эргээд очоорой.

<block class="native mac windows linux android" />

"Дараа нь" гэдгийг дараад "Дуусгах" гэснийг дарж Android виртуал төхөөрөмжөө үүсгээрэй. Одоо та Android виртуал төхөөрөмжийн дэргэдэх гурвалжин ногоон товч дээр дарж, ажиллуулах боломжтой болсон байна. Эндээс дараагийн алхам руу шилжээрэй.

<block class="native mac ios" />

## React Native аппликейшнаа ажиллуулах

React Native хавтас дотор `react-native run-ios` командыг уншуулах:

```
cd AwesomeProject
react-native run-ios
```

Удахгүй та iOS Simulator дээр шинэ апп тань ажиллаж байгааг харах болно.

![AwesomeProject on iOS](/react-native/docs/assets/GettingStartediOSSuccess.png)

`react-native run-ios` команд нь аппаа ажиллуулах олон аргуудын нэг юм. Та Xcode-с шууд ажиллуулах эсвэл [Nuclide](https://nuclide.io/) ашиглах боломжтой.

> Хэрэв болохгүй бол [Troubleshooting](troubleshooting.md#content) гэснийг уншина уу.

### Төхөөрөмж дээр ажиллуулах

Дээрх команд нь автоматаар таны аппыг iOS Simulator дээр ажиллуулна. Хэрэв та бодит iOS төхөөрөмж дээр ажиллуулахыг хүсвэл [энэ заавар](running-on-device.md)-ыг уншина уу.

<block class="native mac windows linux android" />

## React Native аппликейшнаа ажиллуулах

React Native хавтас дотор `react-native run-android` командыг уншуулах:

```
cd AwesomeProject
react-native run-android
```

Хэрэв бүх тохиргоо зөв бол таны апп удахгүй Android emulator дээр ажиллана.

<block class="native mac android" />

![AwesomeProject on Android](/react-native/docs/assets/GettingStartedAndroidSuccessMacOS.png)

<block class="native windows android" />

![AwesomeProject on Android](/react-native/docs/assets/GettingStartedAndroidSuccessWindows.png)

<block class="native mac windows linux android" />

`react-native run-android` команд нь аппаа ажиллуулах олон аргуудын нэг юм. Та Android Studio-с шууд ажиллуулах эсвэл [Nuclide](https://nuclide.io/) ашиглах боломжтой.

> Хэрэв болохгүй бол [Troubleshooting](troubleshooting.md#content) гэснийг уншина уу.

<block class="native mac ios android" />

### Аппдаа өөрчлөлт оруулах

Апп тань амжилттай ажиллаж байгаа тул хэрхэн өөрчлөлт оруулахыг харцгаая.

<block class="native mac ios" />

- Хүссэн текст засварлагч дотроо `App.js` гэснийг нээн зарим мөрөнд өөрчлөлт оруулна.
- iOS Simulator дотор `⌘R` гэснийг даран аппаа дахин уншуулаад өөрчлөгдсөн эсэхийг харна уу!

<block class="native mac android" />

- Хүссэн текст засварлагч дотроо `App.js` гэснийг нээн зарим мөрөнд өөрчлөлт оруулна.
- `R` товчийг хоёр дарах эсвэл хөгжүүлэгчийн цэсээс (`⌘M`) дахин уншуулах гэснийг даран хийсэн өөрчлөлтөө харна уу!

<block class="native windows linux android" />

### Аппдаа өөрчлөлт оруулах

Апп тань амжилттай ажиллаж байгаа тул хэрхэн өөрчлөлт оруулахыг харцгаая.

- Хүссэн текст засварлагч дотроо `App.js` гэснийг нээн зарим мөрөнд өөрчлөлт оруулна.
- `R` товчийг хоёр дарах эсвэл хөгжүүлэгчийн цэсээс (`⌘M`) дахин уншуулах гэснийг даран хийсэн өөрчлөлтөө харна уу!

<block class="native mac ios android" />

### That's it!

Баяр хүргэе! Та анхны React Native аппаа амжилттай хийж, өөрчлөлт оруулж чадлаа.

<center><img src="/react-native/docs/assets/GettingStartedCongratulations.png" width="150"></img></center>

<block class="native windows linux android" />

### That's it!

Баяр хүргэе! Та анхны React Native аппаа амжилттай хийж, өөрчлөлт оруулж чадлаа.

<center><img src="/react-native/docs/assets/GettingStartedCongratulations.png" width="150"></img></center>

<block class="native mac ios" />

## Одоо яах вэ?

- Хөгжүүлэгчийн цэс доторх [Live Reload](debugging.md#reloading-javascript) гэснийг дарна. Та ямар нэг өөрчлөлт оруулсан тухай бүрт апп тань автоматаар шинэчлэгдэх болно!

- Хэрэв та React Native дээрх шинэ кодоо одоо байгаа аппликейшнд хуулахыг хүсвэл [Нэгтгэх заавар](integration-with-existing-apps.md) уншина уу.

React Native-ийн тухай илүү ихийг сурахыг хүсэж байвал [Хичээл](tutorial.md) гэсэн дээр дараарай.

<block class="native windows linux mac android" />

## Одоо яах вэ?

- Хөгжүүлэгчийн цэс доторх [Live Reload](debugging.md#reloading-javascript) гэснийг дарна. Та ямар нэг өөрчлөлт оруулсан тухай бүрт апп тань автоматаар шинэчлэгдэх болно!

- Хэрэв та React Native дээрх шинэ кодоо одоо байгаа аппликейшнд хуулахыг хүсвэл [Нэгтгэх заавар](integration-with-existing-apps.md) уншина уу.

React Native-ийн тухай илүү ихийг сурахыг хүсэж байвал [Хичээл](tutorial.md) гэсэн дээр дараарай.

<script>
  function displayTab(type, value) {
    var container = document.getElementsByTagName('block')[0].parentNode;
    container.className = 'display-' + type + '-' + value + ' ' +
      container.className.replace(RegExp('display-' + type + '-[a-z]+ ?'), '');
  }
  function convertBlocks() {
    // Convert <div>...<span><block /></span>...</div>
    // Into <div>...<block />...</div>
    var blocks = document.querySelectorAll('block');
    for (var i = 0; i < blocks.length; ++i) {
      var block = blocks[i];
      var span = blocks[i].parentNode;
      var container = span.parentNode;
      container.insertBefore(block, span);
      container.removeChild(span);
    }
    // Convert <div>...<block />content<block />...</div>
    // Into <div>...<block>content</block><block />...</div>
    blocks = document.querySelectorAll('block');
    for (var i = 0; i < blocks.length; ++i) {
      var block = blocks[i];
      while (
        block.nextSibling &&
        block.nextSibling.tagName !== 'BLOCK'
      ) {
        block.appendChild(block.nextSibling);
      }
    }
  }
  function guessPlatformAndOS() {
    if (!document.querySelector('block')) {
      return;
    }
    // If we are coming to the page with a hash in it (i.e. from a search, for example), try to get
    // us as close as possible to the correct platform and dev os using the hashtag and block walk up.
    var foundHash = false;
    if (
      window.location.hash !== '' &&
      window.location.hash !== 'content'
    ) {
      // content is default
      var hashLinks = document.querySelectorAll(
        'a.hash-link'
      );
      for (
        var i = 0;
        i < hashLinks.length && !foundHash;
        ++i
      ) {
        if (hashLinks[i].hash === window.location.hash) {
          var parent = hashLinks[i].parentElement;
          while (parent) {
            if (parent.tagName === 'BLOCK') {
              // Could be more than one target os and dev platform, but just choose some sort of order
              // of priority here.
              // Dev OS
              if (parent.className.indexOf('mac') > -1) {
                displayTab('os', 'mac');
                foundHash = true;
              } else if (
                parent.className.indexOf('linux') > -1
              ) {
                displayTab('os', 'linux');
                foundHash = true;
              } else if (
                parent.className.indexOf('windows') > -1
              ) {
                displayTab('os', 'windows');
                foundHash = true;
              } else {
                break;
              }
              // Target Platform
              if (parent.className.indexOf('ios') > -1) {
                displayTab('platform', 'ios');
                foundHash = true;
              } else if (
                parent.className.indexOf('android') > -1
              ) {
                displayTab('platform', 'android');
                foundHash = true;
              } else {
                break;
              }
              // Guide
              if (parent.className.indexOf('native') > -1) {
                displayTab('guide', 'native');
                foundHash = true;
              } else if (
                parent.className.indexOf('quickstart') > -1
              ) {
                displayTab('guide', 'quickstart');
                foundHash = true;
              } else {
                break;
              }
              break;
            }
            parent = parent.parentElement;
          }
        }
      }
    }
    // Do the default if there is no matching hash
    if (!foundHash) {
      var isMac = navigator.platform === 'MacIntel';
      var isWindows = navigator.platform === 'Win32';
      displayTab('platform', isMac ? 'ios' : 'android');
      displayTab(
        'os',
        isMac ? 'mac' : isWindows ? 'windows' : 'linux'
      );
      displayTab('guide', 'quickstart');
      displayTab('language', 'objc');
    }
  }
  convertBlocks();
  guessPlatformAndOS();
</script>
