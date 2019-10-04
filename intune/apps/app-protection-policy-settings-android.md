---
title: Android 앱 보호 정책 설정
titleSuffix: Microsoft Intune
description: 이 항목에서는 Android 디바이스에 대한 앱 보호 정책 설정을 설명합니다.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a71bcb8bbbd9ecb100b83323fc5eb072d176a13b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725467"
---
# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Microsoft Intune의 Android 앱 보호 정책 설정
이 문서에서는 Android 디바이스에 대한 앱 보호 정책 설정을 설명합니다. 설명하는 정책 설정은 Azure Portal의 **설정** 블레이드에서 앱 보호 정책에 대해 [구성](app-protection-policies.md)될 수 있습니다.
정책 설정의 세 가지 범주는 데이터 보호 설정, 액세스 요구 사항 및 조건부 시작입니다. 이 문서에서 *정책 관리 앱*이라는 용어는 앱 보호 정책으로 구성된 앱을 나타냅니다.

> [!IMPORTANT]
> Android 디바이스용 앱 보호 정책을 받으려면 디바이스에 Intune 회사 포털이 필요합니다. 자세한 내용은 [Intune 회사 포털 액세스 앱 요구 사항](../fundamentals/end-user-mam-apps-android.md)을 참조하세요.

## <a name="data-protection"></a>데이터 보호 
### <a name="data-transfer"></a>데이터 전송
| Setting | 사용 방법 | 기본값 |
|------|------|------|
| **Android 백업 서비스에 조직 데이터 백업** | 이 앱이 회사 또는 학교 데이터를 [Android 백업 서비스](https://developer.android.com/google/backup/index.html)로 백업하지 못하도록 하려면 **차단**을 선택합니다.<br><br> 이 앱이 회사 또는 학교 데이터를 백업하도록 허용하려면 **허용**을 선택합니다.| **허용** |
| **다른 앱에 조직 데이터 보내기** | 이 앱에서 데이터를 받을 수 있는 앱을 지정합니다. <ul><li> **정책 관리 앱**: 다른 정책 관리 앱으로만 데이터를 전송하도록 허용합니다.</li> <li>**모든 앱**: 모든 앱으로의 전송을 허용합니다. </li> <li>**없음**: 다른 정책 관리 앱을 포함한 모든 앱에 대한 데이터 전송을 허용하지 않습니다.</li></ul> <p>Intune에서 기본적으로 데이터를 전송할 수 있는 몇 가지 예외적인 앱 및 서비스가 있습니다. 또한 데이터가 Intune APP를 지원하지 않는 앱으로 전송되도록 허용해야 하는 경우 고유한 예외를 만들 수 있습니다. 자세한 내용은 [데이터 전송 예외](app-protection-policy-settings-android.md#data-transfer-exemptions)를 참조하세요.<p>이 정책은 Androidi 앱 링크에도 적용될 수 있습니다.  일반 웹 링크는 **Open app links in Intune Managed Browser**(Intune Managed Browser에서 앱 링크 열기) 정책 설정을 통해 관리됩니다.<p><div class="NOTE"><p>참고</p><p>현재 Intune은 Android 인스턴트 앱 기능을 지원하지 않습니다. Intune은 앱 간에 모든 데이터 연결을 차단합니다. 자세한 내용은 Android 개발자 설명서에서 [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html)를 참조하세요.</p><p>**다른 앱에 조직 데이터 보내기**가 **모든 앱**으로 구성된 경우, 텍스트 데이터는 계속 OS 공유를 통해 클립보드로 전송될 수 있습니다.</p></div> | **모든 앱** | 
|<ul><ui>**제외할 앱 선택** | 이 옵션은 이전 옵션에 대해 *정책 관리형 앱*을 선택한 경우 사용할 수 있습니다. | |
| **다른 앱의 데이터 받기** | 이 앱에 데이터를 전송할 수 있는 앱을 지정합니다. <ul><li>**정책 관리 앱**: 다른 정책 관리 앱에서만 데이터를 전송하도록 허용합니다.</li><li>**모든 앱**: 모든 앱에서의 데이터 전송을 허용합니다.</li><li>**없음**: 다른 정책 관리 앱을 포함한 모든 앱에서의 데이터 전송을 허용하지 않습니다. </li></ul> <p>예외적으로 intune이 데이터를 전송받을 수 있는 몇 가지 앱 및 서비스가 있습니다. 전체 앱 및 서비스 목록은 [데이터 전송 예외](app-protection-policy-settings-android.md#data-transfer-exemptions)를 참조하세요. | **모든 앱** |
| **조직 데이터 복사본 저장** | 이 앱에서 다른 이름으로 저장 옵션을 사용할 수 없도록 설정하려면 **차단**을 선택합니다. 다른 이름으로 저장을 사용할 수 있도록 설정하려면 **허용**을 선택합니다. **참고:** *이 설정은 Microsoft Excel, OneNote, PowerPoint 및 Word에 지원됩니다. 또한 타사 및 LOB 앱에서도 지원될 수 있습니다.*| **허용** |  
|<ul><ui>**선택한 서비스에 사용자가 복사본을 저장하도록 허용** |사용자가 선택한 서비스(비즈니스용 OneDrive, SharePoint 및 로컬 스토리지)에 저장할 수 있습니다. 기타 서비스는 모두 차단됩니다.  | **0개 선택됨** |
| **다른 앱 간에 잘라내기, 복사하기 및 붙여넣기 제한** | 이 앱에서 잘라내기, 복사 및 붙여넣기 동작을 사용할 수 있는 경우를 지정합니다. 다음 중에서 선택합니다. <ul><li>**차단됨**:  이 앱과 다른 앱 간에 잘라내기, 복사 및 붙여넣기 작업을 허용하지 않습니다.</li><li>**정책 관리 앱**: 이 앱과 다른 정책 관리 앱 간에만 잘라내기, 복사 및 붙여넣기 작업을 허용합니다.</li><li>**정책 관리 앱에 붙여넣기**: 이 앱과 다른 정책 관리 앱 간에 잘라내기 또는 복사를 허용합니다. 모든 앱의 데이터를 이 앱에 붙여넣을 수 있습니다.</li><li>**모든 앱**: 이 앱과 다른 앱 간의 잘라내기, 복사 및 붙여넣기에 대한 제한이 없습니다. | **모든 앱** |
| <ul><ui>**앱의 문자 제한 잘라내기 및 복사** | 조직 데이터 및 계정에서 잘라내거나 복사할 수 있는 문자 수를 지정합니다.  이렇게 하면 "다른 앱에서 잘라내기, 복사 및 붙여넣기 제한" 설정에 관계없이 지정된 문자 수를 모든 애플리케이션과 공유할 수 있습니다.<p>기본값은 0입니다.<p>**참고**: Intune 회사 포털 버전 5.0.4364.0 이상이 필요합니다.  | **0** |
| **화면 캡처 및 Google Assistant** | 이 앱을 사용할 때 디바이스의 화면 캡처 및 **Google Assistant** 기능을 차단하려면 **사용 안 함**을 선택합니다. **사용 안 함**을 선택하면 회사 또는 학교 계정으로 이 앱을 사용할 때 최근 사용 앱 미리 보기 이미지도 흐리게 표시됩니다.| **사용** |

  
### <a name="encryption"></a>암호화
| Setting | 사용 방법 | 기본값 |
|------|------|------|
| **조직 데이터 암호화** | 이 앱에서 회사 또는 학교 데이터의 암호화를 적용하려면 **필요**를 선택합니다. Intune에서는 Android 키 저장소 시스템과 함께 OpenSSL, 256비트 AES 암호화 체계를 사용하여 앱 데이터를 안전하게 암호화합니다. 데이터는 파일 I/O 작업 동안 동기적으로 암호화됩니다. 디바이스 스토리지의 콘텐츠는 항상 암호화됩니다. 새 파일은 256비트 키로 암호화됩니다. 기존 128비트 암호화된 파일은 256비트 키로 마이그레이션하려고 하지만 성공 여부는 확신할 수 없습니다. 128비트 키로 암호화된 파일도 계속 읽을 수 있습니다. <br><br> 이 암호화 방법은 FIPS 140-2 규격입니다.     |  **필요**|  
| <ul><ui>**등록된 디바이스에서 조직 데이터 암호화** | 모든 디바이스에서 Intune 앱 계층 암호화를 사용하여 조직 데이터 암호화를 적용하려면 **필요**를 선택합니다. 모든 디바이스에서 Intune 앱 계층 암호화를 사용하여 조직 데이터 암호화를 적용하지 않으려면 **필요 없음**을 선택합니다.| **필요** |


### <a name="functionality"></a>기능
| Setting | 사용 방법 | 기본값 |
|------|------|------|
| **네이티브 연락처 앱과 앱 동기화** | 앱에서 디바이스의 네이티브 연락처 앱에 데이터를 저장하지 못하도록 하려면 **사용 안 함**을 선택합니다. **사용 안 함**을 선택하면 앱에서 디바이스의 네이티브 연락처 앱에 데이터를 저장할 수 있습니다. <br><br>선택적 초기화를 수행하여 앱에서 회사 또는 학교 데이터를 제거할 경우 앱에서 네이티브 연락처 앱으로 직접 동기화된 연락처가 제거됩니다. 기본 주소록에서 다른 외부 소스에 동기화된 연락처는 초기화할 수 없습니다. 현재 Microsoft Outlook 앱에만 적용됩니다. | **사용** |
| **조직 데이터 인쇄** | 앱에서 회사 또는 학교 데이터를 인쇄하지 못하도록 하려면 **사용 안 함**을 선택합니다. 이 설정을 기본값인 **사용** 상태로 두면 사용자가 모든 조직 데이터를 내보내고 인쇄할 수 있습니다. | **사용** |
|**정책 관리형 브라우저와 웹 콘텐츠 공유** | 정책 관리 애플리케이션에서 웹 콘텐츠(http/https 링크)를 여는 방법을 지정합니다. 다음 중에서 선택합니다.<ul><li>**필요**: 정책 관리 브라우저에서만 웹 콘텐츠를 열 수 있습니다.</li><li>**비관리형 브라우저**: 웹 콘텐츠를 **비관리형 브라우저 ID** 설정으로 정의된 비관리형 브라우저에서만 열도록 허용합니다. 웹 콘텐츠가 대상 브라우저에서 관리되지 않습니다.<br>**참고**: Intune 회사 포털 버전 5.0.4415.0 이상이 필요합니다.</li><li>**구성되지 않음** 모든 앱의 웹 링크를 허용합니다. </li></ul><br><br> Intune을 사용하여 디바이스를 관리하는 경우 [Microsoft Intune에서 Managed Browser 정책을 사용하여 인터넷 액세스 관리](app-configuration-managed-browser.md)를 참조하세요.<br><br>**정책 관리 브라우저**<br>여러 정책 관리 브라우저를 배포하는 경우 하나만 시작됩니다.  시작 순서는 Intune Managed Browser 다음으로, Microsoft Edge입니다.  Android에서 최종 사용자는 Intune Managed Browser와 Microsoft Edge가 설치되지 않은 경우 http/https 링크를 지원하는 다른 정책 관리 앱에서 선택할 수 있습니다.<p>정책 관리 브라우저가 필요하지만 설치되지 않은 경우 최종 사용자에게 Intune Managed Browser를 설치하라는 메시지가 표시됩니다.<p>정책 관리 브라우저가 필요한 경우 **앱에서 다른 앱으로 데이터 전송 허용** 정책 설정에 의해 관리됩니다.<p>**Intune 디바이스 등록**<br>Intune을 사용하여 디바이스를 관리하는 경우 Microsoft Intune에서 관리되는 브라우저 정책을 사용하여 인터넷 액세스 관리를 참조하세요. <p>**정책 관리 Microsoft Edge**<br>모바일 디바이스(iOS 및 Android)용 Microsoft Edge 브라우저는 Intune 앱 보호 정책을 지원합니다. Microsoft Edge 브라우저 애플리케이션에서 회사 Azure AD 계정으로 로그인하는 사용자는 Intune에서 보호됩니다. Microsoft Edge 브라우저는 MAM SDK를 통합하고, 다음과 같은 방지를 제외하고는 모든 데이터 보호 정책을 지원합니다.<br><ul><li>**다른 이름으로 저장**: Microsoft Edge 브라우저에서 사용자가 클라우드 스토리지 공급자(예: OneDrive)에 앱 내 연결을 직접 추가할 수 없습니다.</li><li>**연락처 동기화**: Microsoft Edge 브라우저는 기본 연락처 목록에 저장하지 않습니다.</li></ul><br>**참고:** *APP SDK는 대상 앱이 브라우저인지 확인할 수 없습니다. Android 디바이스에서는 http/https 의도를 지원하는 다른 관리형 브라우저 앱이 허용됩니다.* | **구성되지 않음** |
|<ul><ui>**비관리형 브라우저 ID** | 단일 브라우저의 애플리케이션 ID를 입력합니다. 정책 관리형 애플리케이션의 웹 콘텐츠(http/https 링크)가 지정된 브라우저에서 열립니다.  웹 콘텐츠가 대상 브라우저에서 관리되지 않습니다. | **비어 있음** |
|<ul><ui>**비관리형 브라우저 이름** | **비관리형 브라우저 ID**와 연결된 브라우저의 애플리케이션 이름을 입력합니다. 지정된 브라우저가 설치되지 않은 경우 사용자에게 이 이름이 표시됩니다.  | **비어 있음** |


## <a name="data-transfer-exemptions"></a>데이터 전송 예외

  Intune 앱 보호 정책에서 데이터 송수신을 허용할 수 있는 예외적인 앱 및 플랫폼 서비스가 일부 있습니다. 예를 들어 Android의 모든 Intune 관리 앱이 Google 텍스트 음성 변환 서비스로 데이터를 전송하고 이 서비스에서 데이터를 전송받을 수 있어야 모바일 디바이스 화면의 텍스트를 소리 내어 읽어주는 기능을 사용할 수 있습니다. 이 목록은 변경될 수 있으며 생산성 보장에 유용한 서비스 및 앱을 나타냅니다.

### <a name="full-exemptions"></a>완전 예외

  다음 앱 및 서비스에서는 Intune 관리 앱으로 데이터를 전송하거나 이 앱에서 데이터 전송받는 것이 완전히 허용됩니다.

  |앱/서비스 이름 | 설명 |
  | ------ | ---- |
  | com.android.phone | 네이티브 휴대폰 앱
  | com.android.vending | Google Play 스토어 |
  | com.android.documentsui | Android 문서 선택기|
  | com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html) - Outlook을 비롯한 여러 앱에 필요합니다. |
  | com.android.webview |[Webview](https://developer.android.com/reference/android/webkit/WebView.html) - Outlook을 비롯한 여러 앱에 필요합니다.|
  | com.google.android.tts | Google 텍스트 음성 변환 |
  | com.android.providers.settings | Android 시스템 설정 |
  | com.android.settings | Android 시스템 설정 |
  | com.azure.authenticator | Azure Authenticator 앱 - 여러 시나리오에서 성공적인 인증을 위해 필요합니다. |
  | com.microsoft.windowsintune.companyportal | Intune 회사 포털|

### <a name="conditional-exemptions"></a>조건부 예외
  다음 앱 및 서비스에서는 Intune 관리 앱으로 데이터를 전송하거나 이 앱에서 데이터를 전송받는 것이 특정 조건에서만 허용됩니다.

  |앱/서비스 이름 | 설명 | 예외 조건|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome 브라우저 | Chrome은 Android 7.0 이상에서 일부 WebView 구성 요소에 사용되며 보기에서 숨겨지지 않습니다. 그러나 앱으로 들어오거나 앱에서 나가는 데이터 흐름은 항상 제한됩니다.  |
  | com.skype.raider | Skype | Skype 앱은 전화를 걸게 되는 특정 작업에 대해서만 허용됩니다. |
  | com.android.providers.media | Android 미디어 콘텐츠 공급자 | 미디어 콘텐츠 공급자는 벨소리 선택 작업에 대해서만 허용됩니다. |
  | com.google.android.gms; com.google.android.gsf | Google Play 서비스 패키지 | 이러한 패키지는 푸시 알림 등의 Google Cloud Messaging 작업에 대해서 허용됩니다. |
  | com.google.android.apps.maps | Google Maps | 탐색을 위해 주소가 허용됩니다. |

자세한 내용은 [앱에 대한 데이터 전송 정책 예외](app-protection-policies-exception.md)를 참조합니다.

## <a name="access-requirements"></a>액세스 요구 사항

| Setting | 사용 방법 |  
|------|------| 
| **액세스하려면 PIN 필요** | 이 앱을 사용하는 데 PIN을 요구하려면 **예**를 선택합니다. 회사 또는 학교 컨텍스트에서 앱을 처음으로 실행할 때 이 PIN을 설정하라는 메시지가 표시됩니다. <br><br> 기본값은 **예**입니다.<br><br> PIN 강도에 대한 다음 설정을 구성합니다. <br> <ul><li>**유형 선택:** 앱 보호 정책이 적용된 앱에 액세스하기 전에 숫자 또는 암호 유형 PIN의 요구 사항을 설정합니다. 숫자 요구 사항에는 숫자만 포함되고, 암호는 1자 이상의 알파벳 문자 **또는** 1자 이상의 특수 문자로 정의할 수 있습니다. <br><br> 기본값 = **숫자**<br><br> **참고:** 허용되는 특수 문자에는 Android 영어 키보드의 기호 및 특수 문자가 포함됩니다.</li></ul>  <ul><li>**PIN 초기화 전 시도 횟수:** 초기화하기 전까지 PIN을 성공적으로 입력하기 위해 시도할 수 있는 횟수를 지정합니다. <br><br> 기본값 = **5** </li> <br> <li> **단순 PIN 허용:** 사용자가 *1234*, *1111*, *abcd* 또는 *aaaa*와 같은 단순 PIN 시퀀스를 사용할 수 있도록 허용하려면 **예**를 선택합니다. 단순한 순서를 사용하는 것을 방지하려면 **아니요**를 선택합니다. 단순한 시퀀스는 3자 슬라이딩 윈도우로 확인됩니다. **아니요**로 구성하는 경우 1235 또는 1112는 최종 사용자가 PIN으로 설정할 수 없지만 1122는 허용됩니다. <br><br>기본값은 **예**입니다. <br><br>**참고:** 암호 형식 PIN을 구성하고, 단순 PIN 허용을 예로 설정한 경우 사용자 PIN에 1자 이상의 문자 **또는** 1자 이상의 특수 문자가 포함되어야 합니다. 암호 형식 PIN을 구성하고 단순 PIN 허용을 아니요로 설정한 경우 사용자 PIN에 하나 이상의 숫자**와** 하나 이상의 문자**와** 하나 이상의 특수 문자가 포함되어야 합니다. </li> <br> <li>  **PIN 길이:** PIN 시퀀스의 최소 자릿수를 지정합니다. <br><br>기본값은 **4**입니다. </li> <br> <li> **PIN 대신 지문 허용(Android 6.0 이상):** 앱 액세스에 PIN 대신 [지문 인증](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication)을 사용하도록 허용하려면 **예**를 선택합니다. <br><br>기본값은 **예**입니다. <br><br>**참고:** 이 기능은 Android 디바이스에서 생체 인식을 위한 일반 컨트롤을 지원합니다. Samsung Pass 같은 OEM 전용 생체 인식 설정은 *지원되지 않습니다*. <br><br>Android에서 PIN 대신 [Android 지문 인증](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication)을 사용하여 ID를 증명하도록 허용할 수 있습니다. 회사 또는 학교 계정으로 이 앱을 열려고 하면 PIN을 입력하는 대신 해당 지문 ID를 제공하라는 메시지가 표시됩니다. <br><br> Android 회사 프로필 등록 디바이스에서 **PIN 대신 지문 허용** 정책을 적용하려면 별도의 지문을 등록해야 합니다. 이 정책은 Android 회사 프로필에 설치된 정책 관리 앱에만 적용됩니다. 회사 포털에서 등록하여 Android 회사 프로필을 만든 후 별도의 지문을 디바이스에 등록해야 합니다. Android 회사 프로필을 사용하는 회사 프로필 지문에 대한 자세한 내용은 [회사 프로필 잠금](https://support.google.com/work/android/answer/7029958)을 참조하세요.<br><br><ul><li>**제한 시간 후 PIN으로 지문 재정의**: 이 설정을 사용하려면 **예**를 선택한 다음, 비활성화 시간 제한을 구성합니다. <br><br>기본값은 **예**입니다. </li></ul> <br> <ul><li>**제한 시간(분 단위 비활성 시간)** : 암호 또는 숫자(구성된 대로) PIN에서 지문 사용을 재정의할 시간(분)을 지정합니다. 이 제한 시간 값은 ‘다음 시간(분) 후에 액세스 요구 사항 다시 확인’에 지정된 값보다 커야 합니다.<br><br>기본값은 **30**입니다.  </li></ul></li></ul><br><ul><li>**디바이스 PIN을 관리하는 경우 앱 PIN 사용 안 함**: 회사 포털이 구성되어 있는 등록된 디바이스에서 디바이스 잠금이 검색되는 경우 앱 PIN을 사용하지 않도록 설정하려면 **예**를 선택합니다. <br><br> 기본값은 **아니요**입니다. </li></ul> | 
| **액세스 시 회사 자격 증명 필요** | 앱 액세스에 PIN을 입력하는 대신 해당 회사 또는 학교 계정으로 로그인하도록 요구하려면 **예**를 선택합니다. **예**로 설정하고 PIN 또는 생체 인식 프롬프트를 사용하는 경우 회사 자격 증명 및 PIN 또는 생체 인식 프롬프트가 표시됩니다. <br><br>기본값은 **아니요**입니다. |
| **액세스 요구 사항을 다시 확인할 시간(분)** | 다음 설정을 구성합니다. <ul><li>**제한 시간**: 이전에 정책에서 정의된 액세스 요구 사항이 다시 확인되기까지 걸리는 시간(분)입니다. 예를 들어 관리자가 정책에서 디바이스에 루팅된 PIN 및 블록을 설정하고, 사용자가 Intune 관리 앱을 열 때, PIN을 입력해야 하고 루팅되지 않은 디바이스에서 앱을 사용해야 합니다. 이 설정을 사용하는 경우 사용자가 구성된 값과 같은 기간에 Intune 관리 앱에서 PIN을 다시 입력하거나 또 다른 root-detection 검사를 수행할 필요가 없습니다.  <br><br>이 정책 설정 형식은 양의 정수를 지원합니다. <br><br> 기본값 = **30분** <br><br> **참고:** Android에서는 PIN이 모든 Intune 관리 앱 간에 공유됩니다. 앱이 디바이스에서 포그라운드를 나가면 PIN 타이머가 재설정됩니다. 사용자는 이 설정에서 정의한 제한 시간 동안 PIN을 공유하는 Intune 관리형 앱에 PIN을 입력할 필요가 없습니다. <br><br></li> |
| **화면 캡처 및 Android Assistant 차단** | 이 앱을 사용할 때 디바이스의 화면 캡처 및 **Android Assistant** 기능을 차단하려면 **예**를 선택합니다. **예**를 선택하면 회사 또는 학교 계정으로 이 앱을 사용할 때 최근 사용 앱 미리 보기 이미지도 흐리게 표시됩니다. <br><br>기본값은 **아니요**입니다. |

> [!NOTE]  
> 동일한 앱과 사용자 집합에 대한 액세스 섹션에서 구성된 여러 Intune 앱 보호 설정이 Android에서 작동하는 방법에 대해 자세히 알아보려면 [Intune MAM 질문과 대답](mam-faq.md) 및 [Intune에서 앱 보호 정책 액세스 작업을 사용하여 선택적으로 데이터 초기화](app-protection-policies-access-actions.md)를 참조하세요.


## <a name="conditional-launch"></a>조건부 시작
액세스 보호 정책에 대한 로그인 보안 요구 사항을 설정하도록 조건부 시작 설정을 구성합니다. 

기본적으로 미리 구성된 값과 작업이 포함된 몇 가지 설정이 제공됩니다. 이러한 설정 중 일부(예: *최소 OS 버전*)를 삭제할 수 있습니다. 또한 **항목 선택** 드롭다운에서 설정을 추가로 선택할 수도 있습니다. 

| Setting | 사용 방법 |  
|---------|------------| 
| **최대 PIN 시도 횟수** | 구성된 작업을 수행하기 전에 사용자가 PIN을 성공적으로 입력해야 하는 시도 횟수를 지정합니다. 이 정책 설정 형식은 양의 정수를 지원합니다. *작업*은 다음과 같습니다. <br><ul><li>**PIN 다시 설정** - 사용자가 해당 PIN을 다시 설정해야 합니다.</li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다.  </li></ul> </li></ul> 기본값 = **5** |
| **오프라인 유예 기간** | MAM 앱이 오프라인으로 실행할 수 있는 시간(분)입니다. 앱에 대한 액세스 요구 사항을 다시 확인하기 전의 시간(분)을 지정합니다. *작업*은 다음과 같습니다. <br><ul><li>**액세스 차단(분)** - MAM 앱이 오프라인으로 실행할 수 있는 시간(분)입니다. 앱에 대한 액세스 요구 사항을 다시 확인하기 전의 시간(분)을 지정합니다. 이 기간이 만료된 후에 앱을 계속 실행하려면 Azure AD(Azure Active Directory)에 대한 사용자 인증이 필요합니다. <br><br>이 정책 설정 형식은 양의 정수를 지원합니다. <br><br>기본값 = **720**분(12시간) </li></ul> <ul><li>**데이터 초기화(일)** - 관리자가 정의한 대로 앱이 오프라인으로 실행된 기간(일) 후에 사용자가 네트워크에 연결하고 다시 인증해야 합니다. 성공적으로 인증하고 나면 데이터에 계속 액세스할 수 있으며 오프라인 간격이 재설정됩니다.  사용자가 인증에 실패하면 앱에서 사용자 계정과 데이터를 선택적으로 초기화합니다. 자세한 내용은 [Intune 관리 앱에서 회사 데이터만 초기화하는 방법](apps-selective-wipe.md)을 참조하세요.</li></ul> 이 정책 설정 형식은 양의 정수를 지원합니다. <br><br>  기본값 = **90일** </li></ul> <br><br>  이 항목은 여러 번 나타날 수 있으며, 각 인스턴스에서 다른 작업을 지원합니다. |   
| **탈옥/루팅된 디바이스** |이 설정에는 값을 설정할 필요가 없습니다. *작업*은 다음과 같습니다. <br><ul><li>**액세스 차단** - 이 앱이 탈옥 또는 루팅된 디바이스에서 실행되지 않도록 차단합니다. 개인적인 작업에 이 앱을 계속 사용할 수 있지만 이 앱의 회사 또는 학교 데이터에 액세스하려면 다른 디바이스를 사용해야 합니다.</li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다.  </li></ul> |
| **최소 OS 버전** | 이 앱을 사용해야 하는 최소 Android 운영 체제를 지정합니다. *작업*은 다음과 같습니다. <br><ul><li>**경고** - 디바이스의 Android 버전이 요구 사항을 충족하지 않으면 사용자에게 알림이 표시됩니다. 이 알림은 무시할 수 있습니다.  </li></ul> <ul><li>**액세스 차단** - 디바이스의 Android 버전이 이 요구 사항을 충족하지 않으면 사용자 액세스가 차단됩니다.</li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다.  </li></ul> </li></ul>이 정책 설정 형식은 major.minor, major.minor.build, major.minor.build.revision을 지원합니다. |
| **최소 앱 버전** | 최소 운영 체제에 대한 값을 지정합니다. *작업*은 다음과 같습니다. <br><ul><li>**경고** - 디바이스의 앱 버전이 요구 사항을 충족하지 않으면 사용자에게 알림이 표시됩니다. 이 알림은 무시할 수 있습니다.</li></ul> <ul><li>**액세스 차단** - 디바이스의 앱 버전이 요구 사항을 충족하지 않으면 사용자 액세스가 차단됩니다. </li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다. </li></ul> </li></ul> 응용 프로그램 간에 서로 다른 버전 지정 체계를 종종 있는 하나의 앱을 대상으로 하는 하나의 최소 응용 프로그램 버전으로는 정책(예를 들어 ‘Outlook 버전 정책’)을 만듭니다. <br><br> 이 항목은 여러 번 나타날 수 있으며, 각 인스턴스에서 다른 작업을 지원합니다.<br><br> 이 정책 설정 형식은 major.minor, major.minor.build, major.minor.build.revision을 지원합니다.<br><br> 또한 최종 사용자가 LOB(기간 업무) 앱의 업데이트된 버전을 다운로드할 수 있는 **위치**를 구성할 수 있습니다. 최종 사용자는 **최소 앱 버전** 조건부 시작 대화 상자에서 이 기능을 사용할 수 있습니다. 이 대화 상자는 최종 사용자에게 최소 버전의 LOB 앱으로 업데이트할지 묻는 메시지를 표시합니다. Android에서 이 기능에는 회사 포털이 사용됩니다. 최종 사용자가 LOB 앱을 업데이트하는 방법을 구성하려면 앱에 관리형 [앱 구성 정책](app-configuration-policies-managed-app.md)과 `com.microsoft.intune.myappstore` 키가 함께 전송되어야 합니다. 전송된 값은 최종 사용자가 앱을 다운로드할 스토어를 정의합니다. 회사 포털을 통해 앱을 배포한 경우 값은 `CompanyPortal`이어야 합니다. 다른 스토어의 경우에는 전체 URL을 입력해야 합니다.|
| **최소 패치 버전** | 디바이스에 Google에서 출시된 최소 Android 보안 패치가 설치되어야 합니다.  <br><ul><li>**경고** - 디바이스의 Android 버전이 요구 사항을 충족하지 않으면 사용자에게 알림이 표시됩니다. 이 알림은 무시할 수 있습니다.  </li></ul> <ul><li>**액세스 차단** - 디바이스의 Android 버전이 이 요구 사항을 충족하지 않으면 사용자 액세스가 차단됩니다.</li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다.  </li></ul></li></ul> 이 정책 설정은 *YYYY-MM-DD* 날짜 서식을 지원합니다. |
| **디바이스 제조업체** | 세미콜론으로 구분된 제조업체 목록을 지정합니다. 여러 값의 목록에서 공백을 방지합니다. 이러한 값은 대/소문자를 구분하지 않습니다. *작업*은 다음과 같습니다. <br><ul><li>**지정됨 허용(비지정됨 차단)** - 지정된 제조업체와 일치하는 디바이스만 앱을 사용할 수 있습니다. 다른 모든 디바이스는 차단됩니다. </li></ul> <ul><li>**지정됨 허용(비지정됨 초기화)** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다. </li></ul> 이 설정 사용에 대한 자세한 내용은 [조건부 시작 작업](app-protection-policies-access-actions.md#android-policy-settings)을 참조하세요. |
| **SafetyNet 디바이스 증명** | 앱 보호 정책은 일부 Google Play Protect API를 지원합니다. 특히 이 설정은 최종 사용자 디바이스의 Google SafetyNet 증명을 구성합니다. **기본 무결성** 또는 **기본 무결성 및 인증된 디바이스**를 지정하세요. **기본 무결성**은 디바이스의 일반 무결성에 대해 알려줍니다. 변조 흔적이 있는 루팅된 디바이스, 에뮬레이터, 가상 디바이스 및 디바이스는 기본 무결성을 실패합니다. **기본 무결성 및 인증된 디바이스**는 Google 서비스를 사용하는 디바이스의 호환성을 알려줍니다. Google의 인증을 받은 수정되지 않은 디바이스만이 이 검사를 통과할 수 있습니다. *작업*은 다음과 같습니다. <br><ul><li>**경고** - 구성된 값에 따라 디바이스가 Google의 SafetyNet 증명 검사를 충족하지 않는 경우 사용자에게 알림이 표시됩니다. 이 알림은 무시할 수 있습니다. </li></ul><ul><li>**액세스 차단** - 구성된 값에 따라 디바이스가 Google의 SafetyNet 증명 검사를 충족하지 않는 경우 사용자 액세스가 차단됩니다. </li></ul> <ul><li>**데이터 초기화** - 애플리케이션과 연결된 사용자 계정이 디바이스에서 초기화됩니다. </li></ul> </li></ul> 이 설정과 관련된 자주 묻는 질문은 [MAM 및 앱 보호에 관한 질문과 대답](mam-faq.md#app-experience-on-android)을 참조하세요. |
| **앱에서 위협 검색** | 앱 보호 정책은 일부 Google Play Protect API를 지원합니다. 이 설정은 특히 최종 사용자 디바이스에 Google의 앱 확인 검사를 사용하도록 켭니다. 이 설정을 구성하면 최종 사용자가 자신의 Android 디바이스에서 Google의 앱 검사를 켤 때까지 액세스가 차단됩니다. *작업*은 다음과 같습니다. <br><ul><li>**경고** - 디바이스에서 Google의 앱 확인 검사가 꺼져 있으면 사용자에게 알림이 표시됩니다. 이 알림은 무시할 수 있습니다. </li></ul><ul><li>**액세스 차단** - 디바이스에서 Google의 앱 확인 검사가 꺼져 있으면 사용자 액세스가 차단됩니다. </li></ul></li></ul> Google의 앱 확인 검사 결과는 콘솔의 **잠재적으로 위험한 앱** 보고서에 표시됩니다. |