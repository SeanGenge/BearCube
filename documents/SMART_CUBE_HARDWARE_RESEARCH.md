# Smart Cube Hardware Ecosystem & Technology Research

**Research Date:** 2026-02-22
**Confidence Scale:** HIGH (multiple corroborating sources) | MEDIUM (single reliable source) | LOW (inferred/incomplete data)

---

## Table of Contents

1. [Smart Cube Brands & Models](#1-smart-cube-brands--models)
2. [Technical Specifications](#2-technical-specifications)
3. [SDKs and APIs](#3-sdks-and-apis)
4. [Data Exposed by Smart Cubes](#4-data-exposed-by-smart-cubes)
5. [Market Trends](#5-market-trends)
6. [Web Bluetooth API Compatibility](#6-web-bluetooth-api-compatibility)
7. [Community Tools & Libraries](#7-community-tools--libraries)
8. [WCA Stance on Smart Cubes](#8-wca-stance-on-smart-cubes)

---

## 1. Smart Cube Brands & Models

**Confidence: HIGH**

There are four major smart cube manufacturers, plus two notable white-label partnerships:

### GAN (Ganyuan Intelligent Technology Co. Ltd)
The premium/flagship smart cube brand. Most advanced encryption and protocol.

| Model | Type | Key Features | Price (approx.) | Battery |
|-------|------|-------------|------------------|---------|
| GAN 356 i3 V2 | 3x3 | Magnetic, advanced tracking, Hall sensors | ~$60 | Rechargeable, ~30hr |
| GAN 356 i Carry 2 | 3x3 | Magnetic, UV Coated, replaceable battery | ~$50 | Replaceable, ~700hr |
| GAN i Carry 4 | 3x3 | Matte finish, replaceable button batteries | ~$40 | Replaceable, ~150hr |
| GAN 356 i Carry 2 (CNY Edition) | 3x3 | Limited edition matte finish | ~$50 | Replaceable, ~150hr |

- **Companion App:** CubeStation
- **Protocol:** Proprietary, AES-encrypted using MAC-address-derived keys
- **Source:** [GANCUBE Official](https://www.gancube.com/collections/gan-smart-speeding-cube), [SpeedCubeShop](https://speedcubeshop.com/products/gan-356-i-carry-2-3x3-bluetooth-smart-cube-magnetic-uv-coated)

### MoYu (Moyu Culture Co., Ltd.)
Rapidly growing competitor with flagship-quality smart cubes.

| Model | Type | Key Features | Price (approx.) | Battery |
|-------|------|-------------|------------------|---------|
| WeiLong AI V10 (Standard) | 3x3 | Ball-core, gyroscope, 76 magnets | ~$45-55 | Rechargeable, ~30hr |
| WeiLong AI V10 (MagLev) | 3x3 | MagLev + Ball-core, gyroscope, UV Coated | ~$55-65 | Rechargeable, ~30hr |
| WeiLong AI V10 (Lite) | 3x3 | Budget variant, extended battery | ~$30-35 | ~365hr battery |
| MoYu AI Cube V2 | 3x3 | Mid-range, medium magnets | ~$25-35 | Rechargeable |

- **Companion App:** WCU Cube
- **Protocol:** Proprietary (decoded in csTimer open-source project)
- **Source:** [SpeedCubeShop - WeiLong V10](https://speedcubeshop.com/products/moyu-weilong-v10-ai-3x3-bluetooth-smart-cube-standard), [MasterCubeStore](https://mastercubestore.com/smart-cubes/2183-moyu-ai-cube-3x3-v2-m-stickerless-6970647060726.html)

### GoCube / Particula
Pioneer in gamified smart cube experience. Manufacturer behind Rubik's Connected.

| Model | Type | Key Features | Price (approx.) | Battery |
|-------|------|-------------|------------------|---------|
| GoCube Edge | 3x3 | Pillowed design, IMU/3D tracking, LED indicators | ~$70-80 | LiPo rechargeable, ~2hr charge |
| Rubik's Connected | 3x3 | Rubik's branding, no IMU, no LED, stickered | ~$50-60 | Rechargeable |

- **Companion App:** GoCube app
- **Sensors:** Bluetooth 5.0, IMU (GoCube only), 0.001s tracking accuracy
- **Source:** [Particula - GoCube](https://particula-tech.com/products/gocube), [Particula - Rubik's Connected](https://particula-tech.com/products/rubik-s-connected), [AppleInsider Review](https://appleinsider.com/articles/21/02/02/review-rubiks-connected-is-a-smart-cube-for-nostalgia-lovers)

### Giiker (Xiaomi ecosystem)
Early smart cube pioneer. Xiaomi's smart cube is a white-labeled Giiker.

| Model | Type | Key Features | Price (approx.) | Battery |
|-------|------|-------------|------------------|---------|
| Giiker i3S | 3x3 | Magnetic, encrypted state (newer models) | ~$30-40 | Rechargeable |
| Xiaomi Giiker | 3x3 | Xiaomi-branded Giiker | ~$25-35 | Rechargeable |

- **Companion App:** Giiker SuperCube
- **Protocol:** Newer i3S models use encrypted state (unlike original i3)
- **Source:** [Tinkerman - Smart Cubes](https://tinkerman.cat/post/smart-cubes-and-wisblock/), [SpeedSolving](https://www.speedsolving.com/threads/which-bluetooth-cube-is-the-best.78857/)

### QiYi
Newer entrant with budget-friendly smart cubes.

| Model | Type | Key Features | Price (approx.) | Battery |
|-------|------|-------------|------------------|---------|
| QiYi AI 3x3 | 3x3 | Magnetic, 48 magnets, no gyroscope | ~$20-30 | Replaceable, ~800hr |
| QiYi AI 3x3 (UV Coated) | 3x3 | UV surface treatment | ~$25-35 | Replaceable, ~800hr |

- **Companion App:** Smart Player Pro (iOS/Android, English/Chinese only)
- **Note:** No gyroscope means orientation may not always display correctly
- **Source:** [SpeedCubeShop - QiYi AI](https://speedcubeshop.com/products/qiyi-ai-3x3-magnetic-bluetooth-smart-cube), [Cuboss](https://cuboss.com/shop/qiyi-smart-cube-3x3/)

---

## 2. Technical Specifications

**Confidence: HIGH**

### Sensor Technology

Smart cubes use two main sensor approaches:

1. **Hall Effect / Magnetic Position Sensors (GAN, MoYu premium)**
   - Non-contact magnetic induction at the core
   - Detects precise face alignments via magnetic field changes
   - GAN's 2x2-exclusive 21mm core with Hall sensors provides "zero missed turns"
   - **Confidence: HIGH** - Source: [SpeedCubing.org](https://speedcubing.org/blogs/news/how-does-a-smartcube-work)

2. **Gyroscope + Accelerometer (GoCube, MoYu AI V10)**
   - Inertial Measurement Unit (IMU) for full 3D orientation tracking
   - Measures angular motion and direction
   - Required for accurate on-screen orientation display
   - Some budget cubes (QiYi) omit the gyroscope
   - **Confidence: HIGH** - Source: [SpeedCubing.org](https://speedcubing.org/blogs/news/how-does-a-smartcube-work), [SpeedCubeShop](https://speedcubeshop.com/products/moyu-weilong-v10-ai-3x3-bluetooth-smart-cube-standard)

### Bluetooth Specifications

| Specification | Details |
|--------------|---------|
| Protocol | Bluetooth Low Energy (BLE) / Bluetooth 5.0 |
| Frequency Band | 2402-2480 MHz |
| Max RF Power | <10 dBm |
| Range | Up to ~10m practical (100m theoretical for BT 5.0) |
| GATT | Custom GATT services and characteristics per manufacturer |
| Compatibility | iOS 9.0+, Android 4.4+ |

- **Source:** [Particula - Rubik's Connected](https://particula-tech.com/products/rubik-s-connected), [Wikipedia - BLE](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)

### Internal Architecture

1. **Microcontroller** - Processes sensor data, maintains internal cube state model
2. **Sensors** - Hall effect sensors or gyro/accelerometer array
3. **BLE Radio** - Bluetooth Low Energy transceiver
4. **Battery** - LiPo rechargeable (20-30hr typical) or replaceable coin cell (150-800hr)
5. **Magnets** - 48-76 positioning magnets depending on model

- **Confidence: HIGH** - Source: [SpeedCubing.org](https://speedcubing.org/blogs/news/how-does-a-smartcube-work)

### Power / Battery Comparison

| Brand/Model | Battery Type | Life | Charging |
|-------------|-------------|------|----------|
| GAN 356 i3 | Rechargeable LiPo | ~30hr active | USB-C |
| GAN i Carry 2 | Replaceable coin cell | ~700hr | N/A (battery swap) |
| MoYu WeiLong AI V10 | Rechargeable | ~30hr active | Charging storage box |
| MoYu WeiLong AI V10 Lite | Replaceable | ~365hr | N/A |
| GoCube Edge | Rechargeable LiPo | ~8hr active | USB, ~2hr charge |
| QiYi AI 3x3 | Replaceable | ~800hr | N/A |

- **Confidence: MEDIUM-HIGH** (battery life claims are manufacturer-stated)

---

## 3. SDKs and APIs

**Confidence: HIGH**

### Official / First-Party SDKs

#### GAN - CubeStation SDK
- **Platform:** Proprietary, no public SDK
- **App:** CubeStation (iOS/Android)
- **Protocol:** AES-encrypted, MAC-address-derived keys
- **Source:** [GANCUBE](https://www.gancube.com/)

#### MoYu - WCU Cube
- **Platform:** Proprietary, no public SDK
- **App:** WCU Cube (iOS/Android)
- **Source:** [SpeedSolving - MoYu App Thread](https://www.speedsolving.com/threads/moyu-smartcube-app.93584/)

#### QiYi - Smart Player
- **Platform:** Proprietary, no public SDK
- **App:** Smart Player Pro (iOS/Android)
- **Source:** [SpeedCubeShop - QiYi](https://speedcubeshop.com/products/qiyi-ai-3x3-magnetic-bluetooth-smart-cube)

### Third-Party / Open-Source SDKs & Libraries

#### gan-web-bluetooth (Primary GAN library)
- **GitHub:** [afedotov/gan-web-bluetooth](https://github.com/afedotov/gan-web-bluetooth)
- **npm:** [gan-web-bluetooth](https://www.npmjs.com/package/gan-web-bluetooth)
- **Language:** TypeScript/JavaScript
- **Dependency:** RxJS (event-driven Observable pattern)
- **Supports:** GAN Smart Cubes + GAN Smart Timers
- **API Pattern:**
  ```typescript
  import { connectGanCube } from 'gan-web-bluetooth';

  var conn = await connectGanCube();
  conn.events$.subscribe((event) => {
    if (event.type == "FACELETS") {
      console.log("Cube facelets state", event.facelets);
    } else if (event.type == "MOVE") {
      console.log("Cube move", event.move, event.timestamp);
    }
  });
  await conn.sendCubeCommand({ type: "REQUEST_FACELETS" });
  ```
- **Events exposed:** FACELETS, MOVE (with timestamps), GYRO, BATTERY, DISCONNECT
- **Utility:** `cubeTimestampLinearFit()` for clock synchronization
- **Limitation:** GAN i3 newer encryption scheme may not work with all versions
- **Confidence: HIGH** - Source: [GitHub](https://github.com/afedotov/gan-web-bluetooth), [npm](https://www.npmjs.com/package/gan-web-bluetooth)

#### cubing.js (Multi-brand support)
- **GitHub:** [cubing/cubing.js](https://github.com/cubing/cubing.js)
- **Language:** TypeScript/JavaScript
- **Supports:** GoCube, Giiker, GAN (older models), MoYu
- **Features:** Alg manipulation, puzzle animation, scrambles, Bluetooth puzzle connectivity
- **Limitation:** Newer GAN 356 i3 not supported due to changed API/encryption
- **Confidence: HIGH** - Source: [GitHub](https://github.com/cubing/cubing.js/issues/289), [cubing.js API](https://js.cubing.net/cubing/api/classes/bluetooth.GoCube.html)

#### giiker (Giiker-specific libraries)
- **GitHub (hakatashi):** [hakatashi/giiker](https://github.com/hakatashi/giiker) - npm: `giiker`
- **GitHub (Scarygami):** [Scarygami/giiker](https://github.com/Scarygami/giiker) - npm: `@scarygami/giiker` v3.0.0
- **GitHub (kabelbinder):** [kabelbinder/giiker](https://github.com/kabelbinder/giiker) - supports i3SE encrypted state
- **Language:** JavaScript
- **Source:** [GitHub](https://github.com/hakatashi/giiker)

#### qy-cube (QiYi-specific)
- **GitHub:** [agolovchuk/qy-cube](https://github.com/agolovchuk/qy-cube)
- **Language:** JavaScript
- **Protocol Reverse Engineering:** [Flying-Toast/qiyi_smartcube_protocol](https://github.com/Flying-Toast/qiyi_smartcube_protocol)
- **Source:** [GitHub](https://github.com/agolovchuk/qy-cube)

#### react-native-giiker (React Native)
- **GitHub:** [juniorerico/react-native-giiker](https://github.com/juniorerico/react-native-giiker)
- **Platform:** React Native (iOS/Android native apps)
- **Source:** [GitHub](https://github.com/juniorerico/react-native-giiker)

#### ESP32 Smart Cube Interface
- **GitHub:** [playfultechnology/esp32-smartcube](https://github.com/playfultechnology/esp32-smartcube)
- **Platform:** ESP32 microcontroller, connects to BLE smart cubes
- **Source:** [GitHub](https://github.com/playfultechnology/esp32-smartcube)

---

## 4. Data Exposed by Smart Cubes

**Confidence: HIGH**

### Data Categories

| Data Type | Description | Available From | Notes |
|-----------|-------------|----------------|-------|
| **Move Events** | Face turned (U, D, L, R, F, B) and direction (CW/CCW/180) | All smart cubes | Core functionality |
| **Move Timestamps** | Time of each individual move from cube's internal clock | All smart cubes | Clock drift requires linear fit correction |
| **Cube State (Facelets)** | Complete 54-facelet state representing all sticker positions | All smart cubes | Can be requested on-demand |
| **Gyroscope/Orientation** | 3D orientation of the cube in physical space | GoCube, MoYu V10 (with gyro) | Not available on QiYi, budget models |
| **Battery Level** | Current battery percentage | All smart cubes | Periodic updates |
| **Move Count** | Total number of moves in a solve | Derived from move events | Computed by app |
| **TPS (Turns Per Second)** | Speed metric | Derived from moves + timestamps | Computed by app |
| **Connection Status** | Bluetooth connected/disconnected events | All smart cubes | Standard BLE |

### Data Flow Architecture

```
[Physical Cube Turn]
       |
       v
[Hall Sensors / IMU detect rotation]
       |
       v
[Microcontroller updates internal cube state model]
       |
       v
[BLE GATT notification sent to connected device]
       |
       v
[App/Library decodes event (possibly decrypts for GAN)]
       |
       v
[Event emitted: move notation, timestamp, facelets state]
```

### Timestamp Synchronization

GAN smart cubes have imprecise internal clocks that introduce noticeable time skew with the host device clock. Best practice is to:
1. Record timestamps from both host device and cube clocks during a solve
2. Apply linear regression to fit cube timestamp values
3. Use the `cubeTimestampLinearFit()` utility from gan-web-bluetooth

- **Source:** [gan-web-bluetooth GitHub](https://github.com/afedotov/gan-web-bluetooth), [GAN MAC FAQ Gist](https://gist.github.com/afedotov/52057533a8b27a0277598160c384ae71)

---

## 5. Market Trends

**Confidence: MEDIUM-HIGH**

### Market Size & Growth

- Global Rubik's Cube market CAGR: **4.20%** (2023-2030)
- Smart Rubik's Cube segment estimated CAGR: **~15%** (rapidly evolving tech toy)
- Estimated 2025 smart cube market size: **~$172.5 million** (projected)
- Rubik's brand alone: **350M+ total units sold** historically
- **Source:** [Cognitive Market Research](https://www.cognitivemarketresearch.com/rubiks-cube-market-report), [Data Insights Market](https://www.datainsightsmarket.com/reports/smart-rubiks-cube-428838), [Alibaba Insights](https://www.alibaba.com/product-insights/the-rubik-s-cube-unraveling-the-350m-sales-phenomenon-market-dominance-in-2026.html)

### Key Technology Trends

1. **MagLev Technology** - Replacing springs with magnetic levitation for smoother turning. Major differentiator for premium cubes.
2. **Replaceable Batteries** - Trend away from rechargeable toward coin-cell batteries for longer life (GAN i Carry series, QiYi)
3. **Ball-Core Design** - MoYu's ball-core mechanism for enhanced stability and auto-alignment
4. **UV Coating** - Premium surface treatment becoming standard on flagship models
5. **Smart + Performance Convergence** - Smart cubes now matching non-smart flagships in turning quality

### Brand Positioning

| Brand | Position | Trend | Key Strengths |
|-------|----------|-------|---------------|
| **GAN** | Premium leader | Stable/growing | Best encryption, flagship quality, wide ecosystem |
| **MoYu** | Premium challenger | Rapidly growing | WeiLong V10 AI highly competitive, aggressive pricing |
| **QiYi** | Budget/mid-range | Growing | Extremely long battery life, affordable entry point |
| **GoCube/Particula** | Gamification leader | Stable | Best beginner/learning experience, Rubik's brand partnership |
| **Giiker** | Pioneer/legacy | Declining | Xiaomi ecosystem, but less competitive hardware |

### Pricing Tiers (2025-2026)

| Tier | Price Range | Examples |
|------|------------|---------|
| Budget | $20-35 | QiYi AI, Giiker, MoYu AI V2 |
| Mid-range | $35-55 | GAN i Carry 2, MoYu WeiLong V10 Standard |
| Premium | $55-80 | GAN 356 i3, MoYu V10 MagLev UV, GoCube Edge |

- **Source:** [SpeedCubeShop](https://speedcubeshop.com/collections/bluetooth-smart-cubes), [TheCubicle](https://www.thecubicle.com/collections/smart-cubes-and-bluetooth), [Accio Trends](https://www.accio.com/business/cube-3x3-trends)

---

## 6. Web Bluetooth API Compatibility

**Confidence: HIGH**

### Browser Support Matrix

| Browser | Desktop | Android | iOS |
|---------|---------|---------|-----|
| **Chrome** | YES (v56+) | YES | NO (WebKit limitation) |
| **Edge** | YES | YES | NO |
| **Opera** | YES | YES | NO |
| **Safari** | NO | N/A | NO |
| **Firefox** | NO | NO | NO |
| **Bluefy** (iOS) | N/A | N/A | YES (workaround) |

- **Source:** [Can I Use - Web Bluetooth](https://caniuse.com/web-bluetooth), [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API), [WebBluetoothCG Implementation Status](https://github.com/WebBluetoothCG/web-bluetooth/blob/main/implementation-status.md)

### Key Limitations

1. **No Safari/Firefox Support** - Major gap; Safari has no implementation planned. This blocks all iOS browsers (which must use WebKit).
2. **iOS Workaround** - [Bluefy](https://apps.apple.com/us/app/bluefy-web-ble-browser/id1492822055) is a dedicated BLE browser for iOS that supports Web Bluetooth.
3. **User Gesture Required** - Bluetooth device discovery must be initiated by a user gesture (click/tap).
4. **MAC Address Discovery** - Some apps (csTimer) can read MAC addresses automatically, but requires properly configured Chrome on macOS/Windows/Android.
5. **GAN Encryption Challenge** - GAN cubes require MAC address to derive AES decryption keys. Getting MAC varies by platform.
6. **Clock Drift** - GAN cube internal clocks are not ideally calibrated; timestamp linear fit correction required.
7. **HTTPS Required** - Web Bluetooth API only works on secure contexts (HTTPS or localhost).

### Platform-Specific Notes

- **Windows/macOS/Linux (Chrome):** Full support, best experience
- **Android (Chrome):** Full support, good experience
- **iOS:** No native support; must use Bluefy browser app or native app approach
- **ChromeOS:** Full support

- **Source:** [Medium - Web Bluetooth](https://medium.com/@kamresh485/exploring-the-web-bluetooth-api-use-cases-advantages-and-limitations-6f3f85946e44), [GAN MAC FAQ](https://gist.github.com/afedotov/52057533a8b27a0277598160c384ae71)

---

## 7. Community Tools & Libraries

**Confidence: HIGH**

### Web-Based Applications

| Tool | Description | Smart Cube Support | Source |
|------|-------------|-------------------|--------|
| **csTimer** | Professional speedcubing timer, open source | Giiker, GAN, GoCube, MoYu | [csTimer](https://cstimer.net/), [GitHub](https://github.com/cs0x7f/cstimer) |
| **Cubeast** | Smart cube timer with solve analysis | All 3x3 Bluetooth cubes | [cubeast.com](https://www.cubeast.com/) |
| **acubemy** | Universal smart cube trainer/timer/PvP | All brand smart cubes | [acubemy.com](https://acubemy.com/) |
| **Cubedex** | Algorithm drilling app with smart cube | GAN (via gan-web-bluetooth + cubing.js) | [SpeedSolving Thread](https://www.speedsolving.com/threads/%F0%9F%9A%80-just-launched-cubedex-a-new-app-to-drill-your-algs-like-a-pro.93373/) |

### Key Open-Source Libraries

| Library | Purpose | Cubes Supported | GitHub |
|---------|---------|----------------|--------|
| **gan-web-bluetooth** | GAN cube + timer Web Bluetooth | GAN cubes & timers | [afedotov/gan-web-bluetooth](https://github.com/afedotov/gan-web-bluetooth) |
| **cubing.js** | Full cubing toolkit + Bluetooth | GoCube, Giiker, GAN (older), MoYu | [cubing/cubing.js](https://github.com/cubing/cubing.js) |
| **giiker** (hakatashi) | Giiker cube Bluetooth wrapper | Giiker i3 | [hakatashi/giiker](https://github.com/hakatashi/giiker) |
| **@scarygami/giiker** | Giiker cube Bluetooth wrapper v3 | Giiker | [Scarygami/giiker](https://github.com/Scarygami/giiker) |
| **giiker** (kabelbinder) | Giiker i3SE encrypted support | Giiker i3SE | [kabelbinder/giiker](https://github.com/kabelbinder/giiker) |
| **qy-cube** | QiYi cube Bluetooth communicator | QiYi | [agolovchuk/qy-cube](https://github.com/agolovchuk/qy-cube) |
| **qiyi_smartcube_protocol** | QiYi protocol reverse engineering | QiYi | [Flying-Toast/qiyi_smartcube_protocol](https://github.com/Flying-Toast/qiyi_smartcube_protocol) |
| **esp32-smartcube** | ESP32 hardware BLE interface | Giiker, Xiaomi | [playfultechnology/esp32-smartcube](https://github.com/playfultechnology/esp32-smartcube) |
| **react-native-giiker** | React Native BLE interface | Giiker/Xiaomi | [juniorerico/react-native-giiker](https://github.com/juniorerico/react-native-giiker) |

### Protocol Reference (csTimer bluetooth.js)

The csTimer project at `src/js/bluetooth.js` contains reverse-engineered protocol decodings for all major manufacturers (Giiker, GAN, GoCube, MoYu) and serves as the de facto reference implementation for smart cube Bluetooth protocols.

- **Source:** [Tinkerman](https://tinkerman.cat/post/smart-cubes-and-wisblock/), [csTimer GitHub Wiki](https://github.com/cs0x7f/cstimer/wiki/Use-csTimer-to-connect-to-smart-cubes---%E4%BD%BF%E7%94%A8csTimer%E8%BF%9E%E6%8E%A5%E6%99%BA%E8%83%BD%E9%AD%94%E6%96%B9)

### Hardware Projects

- **ESP32 Bluetooth Timer** - Building a standalone speedcubing timer with ESP32 that connects to smart cubes via BLE
  - Source: [ojdip.net](https://ojdip.net/2020/11/esp32-cube-timer/)
- **WisBlock Smart Cube Integration** - RAK Wireless WisBlock IoT platform interfacing with smart cubes
  - Source: [Tinkerman](https://tinkerman.cat/post/smart-cubes-and-wisblock/)

---

## 8. WCA Stance on Smart Cubes

**Confidence: HIGH**

### Official Position: BANNED in Competition

The World Cube Association (WCA) explicitly **prohibits** smart cubes in official competitions.

**WCA Regulation (Article 3):**
> "Puzzles must not have electronic components such as Bluetooth or Wi-Fi capabilities, motors, sensors, or lights."

### Rationale
- Electronic components could be used maliciously (e.g., computer-assisted solving hints)
- Ensures fair competition with standardized equipment
- Maintains integrity of results

### Exceptions / Unofficial Use
- Smart cubes may be used in **unofficial events** under judge supervision for move counting
- Some unofficial online competitions (e.g., cubingcontests.com) explicitly support smart cubes for verified results
- The cubing community widely uses smart cubes for **training purposes** outside competition

### Supported Cubes in Unofficial Contexts
For unofficial competitions that do allow smart cubes, commonly supported models include: GiiKER, GoCube, Rubik's Connected, HeyKube, and earlier GAN smart cubes.

- **Source:** [WCA Regulations](https://www.worldcubeassociation.org/regulations/), [SpeedCubing.org - Are Smart Cubes Allowed](https://speedcubing.org/blogs/news/are-smart-cubes-allowed-in-wca-competitions), [CubingContests Rules](https://cubingcontests.com/rules)

---

## Summary & Recommendations for BearCube Project

### Most Developer-Friendly Smart Cubes
1. **GAN 356 i Carry 2** - Best library support (gan-web-bluetooth), widely documented protocol
2. **GoCube / Rubik's Connected** - Supported by cubing.js, simpler protocol
3. **Giiker** - Multiple open-source libraries, well-documented protocol
4. **MoYu WeiLong AI V10** - Growing support in csTimer, competitive hardware

### Recommended Libraries for Web Integration
1. **gan-web-bluetooth** - Best for GAN cubes, clean RxJS Observable API
2. **cubing.js** - Best multi-brand support, includes puzzle visualization
3. **csTimer bluetooth.js** - Best reference for all protocol implementations

### Key Technical Considerations
- Web Bluetooth API is Chrome/Edge only; no Safari/Firefox support
- iOS requires native app or Bluefy browser workaround
- GAN cubes use AES encryption requiring MAC address for key derivation
- Cube clock drift requires timestamp linear regression correction
- Each manufacturer has a proprietary protocol (no standard exists)
- csTimer's open-source bluetooth.js is the best protocol reference

### Architecture Recommendation
For a web-based application targeting smart cube integration:
- Use **gan-web-bluetooth** for GAN cube support (most popular brand)
- Use **cubing.js** Bluetooth module for GoCube/Giiker/older GAN support
- Reference **csTimer bluetooth.js** for MoYu and QiYi protocol details
- Plan for **native app wrapper** (React Native, Capacitor, etc.) for iOS support
- Implement **timestamp linear fit** for accurate timing
- Consider **Progressive Web App (PWA)** approach with Web Bluetooth on supported platforms
