# 타사 고지 (Third-Party Notices)

NURIMO 는 아래의 공개 소프트웨어를 사용합니다. 각 구성 요소의 저작권은 해당 저작권자에게 있습니다.

> **확인 시점**: 2026-09-15 · **NURIMO 판**: 1.10.0
>
> 라이선스는 **버전을 올릴 때마다 다시 확인한다**. ImageSharp 처럼 도중에 라이선스가
> 바뀐 전례가 있다(PLAN.md 17장).

---

## 함께 배포되는 것

| 구성 요소 | 버전 | 라이선스 | 저작권 |
|---|---|---|---|
| .NET / WPF | 10.0 | MIT | © .NET Foundation and Contributors |
| WPF-UI | 4.3.0 | MIT | © lepoco |
| CommunityToolkit.Mvvm | 8.4.2 | MIT | © .NET Foundation and Contributors |
| Microsoft.Extensions.* | 10.0.11 | MIT | © Microsoft Corporation |
| SkiaSharp | 4.151.2 | MIT | © Microsoft Corporation, Xamarin Inc. |
| Skia | (SkiaSharp 내장) | BSD-3-Clause | © Google Inc. |
| PDFsharp | 6.2.4 | MIT | © empira Software GmbH |
| PDFtoImage | 5.4.0 | MIT | © David Sungaila |
| **PDFium** | (PDFtoImage 내장) | **BSD-3-Clause** | © 2014 The PDFium Authors |
| **BitMiracle.LibTiff.NET** | 2.4.660 | **BSD-3-Clause** | © Bit Miracle |
| **Svg.Skia** | 5.2.3 | MIT | © Wiesław Šoltés |
| HarfBuzzSharp | 14.2.0 | MIT | © Microsoft Corporation, Xamarin Inc. |
| HarfBuzz | (HarfBuzzSharp 내장) | MIT | © HarfBuzz Project Authors |
| H.NotifyIcon.Wpf | 2.4.1 | MIT | © Konstantin S., Philipp Sumi |
| Serilog | 4.4.0 | Apache-2.0 | © Serilog Contributors |

## 만들 때만 쓰는 것 (배포본에 들어가지 않음)

| 구성 요소 | 버전 | 라이선스 |
|---|---|---|
| xUnit | 2.9.3 | Apache-2.0 |
| Inno Setup | 6.7.3 | Inno Setup License |

## 함께 배포하지 않는 것

### 그림 갈래를 읽는 것 — HEIC · AVIF · Raw(CR2·NEF·ARW·DNG·RAF)

NURIMO 는 이 갈래들의 **해석기를 함께 배포하지 않습니다.**

**제약 없는 라이선스로 가는 길이 없기 때문입니다.** HEIC 는 `libheif`(LGPL)에 더해
속이 HEVC 라 **특허 로열티**가 따라붙고, Raw 는 사실상 `LibRaw`(LGPL/CDDL)뿐입니다.
정적으로 묶은 단일 DLL 로 LGPL 을 재배포하려면 「받는 사람이 다시 링크할 수 있게」 하는
의무가 생기는데, 소스를 공개하지 않는 배포본과는 맞지 않습니다.
**FFmpeg 을 담지 않기로 한 것과 같은 줄기입니다.**

`Magick.NET`(Apache-2.0)이 이 모두를 한 번에 읽어 주지만, 그 안에 든 네이티브
24MB 에 위의 카피레프트 부품들이 함께 들어 있어 같은 문제를 그대로 안고 옵니다.

**대신 Windows 에게 맡깁니다.** 사용자가 Microsoft Store 에서 「HEIF 이미지 확장」·
「AV1 비디오 확장」·「Raw 이미지 확장」을 설치해 두었다면 NURIMO 가 그것을 통해 읽고,
없으면 **무엇을 설치하면 되는지 말해 줍니다.** 우리가 아무것도 재배포하지 않으므로
라이선스도 특허도 사용자의 코덱 쪽에 남습니다.

### FFmpeg

NURIMO 는 **FFmpeg 을 함께 배포하지 않습니다.**

영상·음성 기능을 쓰려면 사용자가 직접 준비해야 하며, NURIMO 는 이미 설치된 것을 찾거나
사용자의 동의를 받아 공식 출처에서 내려받아 `%LOCALAPPDATA%\NURIMO\tools\ffmpeg`
(포터블은 `data\tools\ffmpeg`)에 둡니다.

이렇게 하는 이유는 다음과 같습니다(PLAN.md 18장).

- FFmpeg 은 기본적으로 **LGPL v2.1 이상**이지만, 널리 쓰이는 Windows 빌드는
  x264·x265 를 포함해 **GPL v2 이상**입니다.
- H.264 · HEVC · AAC 는 **특허** 대상이며, 인코더를 배포하는 경우 별도의 고려가 필요합니다.

따라서 NURIMO 자체는 FFmpeg 을 재배포하지 않으며, 사용자가 설치한 빌드의 이름·판·라이선스는
**설정 > 타사 고지**에서 확인할 수 있습니다.

---

## 라이선스 전문

### MIT License

```
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### BSD 3-Clause License (PDFium, Skia)

```
Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above
copyright notice, this list of conditions and the following disclaimer
in the documentation and/or other materials provided with the
distribution.
    * Neither the name of Google Inc. nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### Apache License 2.0 (Serilog)

전문: <https://www.apache.org/licenses/LICENSE-2.0>

```
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

## 참고 대상에 대하여

NURIMO 는 ShareX · File Converter · PDF24 의 **공개된 기능 구성과 작업 흐름을 참고**했으나,
소스 코드 · UI 리소스 · 문구 · 아이콘을 가져오지 않았습니다. 화면 배치 · 명명 · 상호작용은
NURIMO 가 독자적으로 설계한 것입니다.
