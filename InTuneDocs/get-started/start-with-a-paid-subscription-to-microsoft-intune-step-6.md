---
title: "정책 및 앱 배포 | Microsoft Intune"
description: "정책 설정을 사용하도록 설정하고 장치가 관리에 등록되면 즉시 적용되는 앱을 배포할 수 있습니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 56f7d1578ba6b193c6547686675e0fd4fde5f378


---

# <a name="create-policies-and-publish-apps"></a>정책 만들기 및 앱 게시
Intune에 앱을 등록하기 전에 이러한 장치가 관리에 등록되는 즉시 배포되는 앱 및 정책 설정을 사용하도록 설정할 수 있습니다. Intune 정책은 모바일 장치에 대한 보안 설정을 제어하고, 컴퓨터에 대한 Windows 방화벽 및 Endpoint Protection 설정을 유지하고, 응용 프로그램을 배포하는 데 사용할 수 있는 설정을 제공합니다. 장치에 Intune에 등록되는 즉시 설정 및 앱을 받도록 정책을 구성하고 앱을 추가하고 이러한 앱을 배포할 수 있습니다.

정책 및 앱은 플랫폼마다 다릅니다.

## <a name="manage-device-settings"></a>장치 설정 관리

 장치 정책 설정은 플랫폼별로 구성하고 관리합니다. 다음 플랫폼에 대한 정책을 구성할 수 있습니다.

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android 및 Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10(PC 및 모바일)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows 팀](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Intune 소프트웨어 클라이언트를 실행하는 Windows PC](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

[Microsoft Intune 정책을 사용하여 장치의 설정 및 기능을 관리](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)하는 방법에 대해 자세히 알아볼 수 있습니다.

## <a name="add-and-deploy-apps"></a>앱 추가 및 배포

다음의 두 가지 방법으로 Intune에 앱을 추가한 다음 관리되는 장치에 배포할 수 있습니다.
- **필수 설치** - 앱에서 관리되는 장치에 앱을 자동으로 설치합니다.
- **사용 가능한 설치** - 앱이 Intune 회사 포털 앱에 표시되므로 사용자가 장치에 앱을 설치할지 여부를 선택할 수 있습니다.

### <a name="add-apps"></a>앱 추가

먼저 다음 방법 중 하나로 앱을 Intune에서 사용할 수 있게 만들어야 합니다.
- [등록된 장치용 앱 추가](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Intune 소프트웨어 클라이언트 PC용 앱 추가](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>앱 배포

Intune에서 앱을 사용할 수 있으므로 관리되는 장치에 앱을 배포할 수 있습니다.
- [Deploy apps to devices](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)(장치에 앱 배포)
- 대량 구매 앱 배포:
    - [iOS - 대량 구매 프로그램](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [비즈니스용 Windows 스토어](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    배포용 앱을 구성했으면 [앱을 구성](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune)하고 [앱을 모니터링](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune)할 수 있습니다.

>[!div class="step-by-step"]

>[&larr; **사용자 및 장치 구성**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**회사 포털 사용자 지정** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->

