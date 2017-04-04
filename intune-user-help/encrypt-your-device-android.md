---
title: "암호화를 사용하여 Android 장치를 보호하는 방법 | Microsoft 문서"
description: "Android 장치 보호"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 8ba85e15fb55a4de1b2f1db53bc5b9962de84394
ms.lasthandoff: 03/13/2017


---


# <a name="how-to-protect-your-android-device-using-encryption"></a>암호화를 사용하여 Android 장치를 보호하는 방법

장치를 암호화하면 장치의 정보를 보호 코드의 계층에 래핑하여 권한이 없는 사용자가 해당 정보에 액세스하는 것을 방지합니다. 정보 보안을 보장하기 위한 단계로서, 조직에서는 회사 파일, 메일 또는 데이터에 액세스하기 전에 Android 장치를 암호화할 것을 요구합니다.

> [!Note]
> IT 관리자가 요구하는 경우 암호화하기 전에 PIN 또는 암호를 설정하라는 메시지가 표시될 수 있습니다.

휴대폰의 등록을 취소한 경우 휴대폰이 암호화된 상태로 유지됩니다.

1.  장치에 대해 화면 잠금 PIN 또는 암호가 설정되어 있는지 확인합니다.

2.  **설정**에서 **보안** &gt; **Encrypt Device**(장치 암호화)를 선택합니다.
    일부 휴대폰에서는 **저장소** &gt; **저장소 암호화** 또는 **저장소** &gt; **잠금 화면 및 보안** &gt; **기타 보안 설정**을 선택하여 "암호화" 옵션을 찾아야 합니다.

3.  화면의 지시를 따릅니다. 암호화가 진행되는 동안 장치가 여러 번 다시 시작될 수 있습니다.

> [!Note]
> 특정 Android 장치는 암호화할 수 없습니다. 자세한 내용은 [여기](your-device-appears-encrypted-but-cp-says-otherwise-android.md)를 참조하세요.

### <a name="what-to-do-if-you-have-issues"></a>문제가 있는 경우 수행할 작업
**문제**: 장치를 이미 암호화한 경우에는 다음 중 하나가 발생합니다.

- 암호화 단추를 사용할 수 없습니다.
- 여전히 암호화해야 한다는 메시지가 표시됩니다.
- 회사 포털 앱을 사용하려고 할 때 오류가 발생합니다.

**시도할 작업**

- 장치가 충전되었고 전원에 연결되어 있는지 확인합니다.
- 장치에서 PIN 또는 암호를 설정했는지 확인합니다.
- 장치에서 이미 PIN 또는 암호를 설정한 경우 다음 단계를 시도해 볼 수 있습니다. IT 관리자가 장치를 더 안전하게 하기 위해 이러한 단계를 요구할 수 있습니다. 표시되는 메뉴 이름은 보유한 Android 장치의 유형에 따라 단계에 있는 메뉴 이름과 약간 다를 수 있습니다.

    1. **설정** > **보안** > **화면 잠금**으로 이동합니다. 현재 PIN 또는 암호를 확인합니다.

    2. **화면 잠금 선택** 화면에서 사용할 화면 잠금 유형을 선택합니다.

    3. **보안 시작** 화면에서 **기기 시작 시 PIN 요청**을 탭하고 **계속**을 탭합니다.

    4. PIN(이전에 입력한 것과 같은 PIN을 입력할 수 있음)을 선택하고 **PIN 확인**을 탭합니다.

    5. 회사 포털 앱을 열고 장치를 선택하고 **준수 확인**을 탭합니다.

여전히 도움이 필요하세요? IT 관리자에게 문의하거나(연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com) 확인) <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android 팀</a>으로 메일을 보내세요.
