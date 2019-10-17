---
title: Microsoft Intune - Azure의 macOS에서 엔드포인트 보호 추가 | Microsoft Docs
description: MacOS 디바이스에서 게이트키퍼를 사용하여 mac 앱 스토어를 포함해 앱을 설치할 수 있는 위치를 결정합니다. 또한 Microsoft Intune을 사용하여 방화벽이 특정 앱을 허용하도록 구성하거나 사용하도록 설정하고, 특정 앱을 차단하고, 은폐 모드를 사용하고 특정 유형의 들어오는 연결을 차단합니다.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6090d329eee6f27da21b6133a2b7ccdc7072feb3
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814122"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune에서 macOS 엔드포인트 보호 설정  

이 문서에서는 macOS를 실행하는 디바이스에 대해 구성할 수 있는 엔드포인트 보호 설정을 보여줍니다. Intune에서 [endpoint protection](endpoint-protection-configure.md) 에 대 한 macos 장치 구성 프로필을 사용 하 여 이러한 설정을 구성할 수 있습니다.  

## <a name="gatekeeper"></a>게이트키퍼  

- **이러한 위치에서 다운로드 한 앱 허용**  
  앱이 다운로드 된 위치에 따라 장치를 시작할 수 있는 앱을 제한 합니다. 맬웨어에서 디바이스를 보호하고 신뢰하는 소스로부터만 앱을 허용하기 위함입니다.  

  - **구성되지 않음**  
  - **Mac 앱 스토어**  
  - **Mac 앱 스토어 및 확인된 개발자**  
  - **Anywhere**  

  **기본값**: 구성되지 않음  

- **사용자가 게이트 키퍼를 재정의할 수 있음**  
  사용자가 게이트키퍼 설정을 재정의하는 것을 금지하고 앱을 설치하기 위해 컨트롤 클릭을 금지합니다. 사용하도록 설정되면 사용자가 앱을 컨트롤 클릭하여 설치할 수 있습니다.  
 
  - **구성 되지 않음** -사용자가 앱을 설치 하려면 클릭 하 여 클릭 합니다.  
  - **차단** -사용자가 컨트롤을 사용 하 여 앱을 설치할 수 없습니다.  

  **기본값**: 구성되지 않음  

## <a name="firewall"></a>방화벽  

방화벽을 사용하여 포트별이 아닌 애플리케이션별 연결을 제어합니다. 애플리케이션별 설정을 사용하면 방화벽 보호의 이점을 더욱 쉽게 얻을 수 있습니다. 또한 합법적인 앱에 대해 열려있는 네트워크 포트를 원하지 않는 앱이 제어하는 것을 방지해줍니다.  

**일반**
- **방화벽**  
  들어오는 연결을 사용자 환경에서 처리하는 방법을 구성하려면 방화벽을 사용하도록 설정합니다.  
  - **구성되지 않음**  
  - **사용**  

  **기본값**: 구성되지 않음  

- **들어오는 연결**  
  DHCP, Bonjour, IPSec 등의 기본 인터넷 서비스에 필요한 연결을 제외하고 들어오는 모든 연결을 차단합니다. 또한 이 기능은 모든 공유 서비스(예: 파일 공유, 화면 공유)를 차단합니다. 공유 서비스를 사용하는 경우 이 설정을 *구성되지 않음*으로 유지합니다.  
  - **구성되지 않음**  
  - **차단**  

  **기본값**: 구성되지 않음  

**특정 앱에 대한 들어오는 연결을 허용하거나 차단합니다.**  

  - **허용 된 앱**  
    들어오는 연결을 수신하도록 명시적으로 허용된 앱을 선택합니다.  

  - **차단 된 앱**  
    들어오는 연결을 차단해야 하는 앱을 선택합니다.  

  - **은폐 모드**  
    컴퓨터가 검색 요청에 응답하지 않게 하려면 은폐 모드를 사용하도록 설정합니다. 디바이스는 권한이 부여된 앱에 대해 들어오는 요청에 계속 응답합니다. ICMP(ping)와 같은 예기치 않은 요청은 무시합니다.  
    - **구성되지 않음**  
    - **사용**  

    **기본값**: 구성되지 않음  

## <a name="filevault"></a>FileVault  
Apple 대해 filevault 켭니다 설정에 대 한 자세한 내용은 Apple developer 콘텐츠에서 [FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault) 를 참조 하세요. 

> [!IMPORTANT]  
> MacOS 10.15을 통해 대해 filevault 켭니다 구성에는 사용자 승인 MDM 등록이 필요 합니다. 

- **FileVault**  
  MacOS 10.13 이상을 실행 하는 장치에서 대해 filevault 켭니다로 XTS-AES 128를 사용 하 여 전체 디스크 암호화를 *사용 하도록 설정할* 수 있습니다.  
  - **구성되지 않음**  
  - **사용**  

  **기본값**: 구성되지 않음  

  - **복구 키 유형**  
    장치에 대해 *개인 키* 복구 키가 생성 됩니다. 개인 키에 대 한 다음 설정을 구성 합니다.  

    - **개인 복구 키의 위치** -사용자에 게 개인 복구 키를 검색할 수 있는 방법과 위치를 설명 하는 짧은 메시지를 지정 합니다. 암호를 잊어버린 경우 개인 복구 키를 입력 하 라는 메시지가 표시 되 면 사용자가 화면에 표시 되는 메시지에이 텍스트가 삽입 됩니다.  
      
    - **개인 복구 키 회전** -장치의 개인 복구 키를 회전 하는 빈도를 지정 합니다. **구성 되지 않음**의 기본값 또는 **1** ~ **12** 개월 값을 선택할 수 있습니다.  

  - **로그 아웃 시 프롬프트 사용 안 함**  
    사용자가 로그 아웃할 때 대해 filevault 켭니다을 허용 하도록 요청 하는 메시지를 표시 하지 않습니다.  사용 안 함으로 설정 하면 로그 아웃 시 프롬프트가 비활성화 되 고 대신 사용자가 로그인 할 때 사용자에 게 메시지가 표시 됩니다.  
    - **구성되지 않음**  
    - **비활성화** -로그 아웃 시 프롬프트를 사용 하지 않도록 설정 합니다.

    **기본값**: 구성되지 않음  

  - **바이패스에 허용 되는 횟수**  
  사용자가 로그인 하는 데 대해 filevault 켭니다가 필요 하기 전에 사용자가 대해 filevault 켭니다를 사용 하도록 설정 하 라는 메시지를 무시할 수 있는 횟수를 설정 합니다. 

    - **구성 되지 않음** -다음 로그인이 허용 되기 전에 장치에서 암호화가 필요 합니다.  
    - **1** ~ **10** -사용자가 장치에서 암호화를 요구 하기 전에 1 ~ 10 번의 프롬프트를 무시할 수 있습니다.  
    - **제한이 없음, 항상 묻기** -사용자에 게 대해 filevault 켭니다를 사용 하도록 설정 하 라는 메시지가 표시 되지만 암호화가 필요 하지 않습니다.  
 
    **기본값**: *다름* - *로그 아웃 시 프롬프트 사용 안 함* 설정이 **구성 되지 않음**으로 설정 된 경우이 설정은 기본적으로 **구성 되지 않음**으로 설정 됩니다. *로그 아웃 시 메시지 표시 안* 함이 **사용 안 함**으로 설정 되 면이 설정은 기본적으로 **1** 이 고, **구성 되지 않음** 값은 옵션이 아닙니다.

Intune을 사용 하는 대해 filevault 켭니다에 대 한 자세한 내용은 [대해 filevault 켭니다 recovery keys](encryption-monitor.md#filevault-recovery-keys)를 참조 하세요.
