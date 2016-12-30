---
title: "Intune에서 macOS 장치 등록 | Microsoft Intune"
description: "Intune에서 macOS 장치를 등록하는 방법을 설명합니다."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 650e9b0700971e626e4062c312111ef60e74badc


---

# <a name="enroll-your-macos-device-in-intune"></a>Intune에서 macOS 장치 등록

조직의 앱, 데이터 및 리소스에 액세스할 수 있으면 업무를 수행할 수 있습니다. 회사에서 macOS 장치를 사용하는 경우에는 이를 위해 __관리 프로필__을 설치해야 합니다. 관리 프로필은 설정 및 액세스 정보를 Mac으로 로드하는 파일로 IT 관리자가 설정합니다. 자세히 알고 싶으세요? [Intune에서 회사 포털 앱을 설치하고 장치를 등록하면 어떻게 되는지](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md) 알아보세요.

  > [!NOTE]
  > 실제로 iPhone 또는 iPad 같은 iOS 장치를 등록하려면 [대신 이 지침을 따르세요](enroll-your-device-in-intune-ios.md).

1. __Dock__에서 __Safari__를 찾고 새 창을 연 다음 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)를 엽니다.
2. 회사 또는 학교 계정으로 회사 포털 웹 사이트에 로그인합니다.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. 로그인하면 사용 가능한 __앱__, __내 장치__ 및 IT 직원의 사용 가능한 __연락처 정보__가 표시됩니다. 페이지 위쪽에 다음과 같은 알림이 표시됩니다. **이 장치가 등록되지 않았거나 회사 포털 앱이 이 장치를 식별할 수 없습니다. <u>여기를 탭</u>하여 다른 장치를 선택합니다.** __여기를 탭하세요__를 클릭합니다.

 ![회사 포털 macOS 시작 페이지](./media/macOS_enroll_001_landing_page.png)

4. 팝업 창에 __이 장치를 식별 또는 등록__하는 이유를 간단히 설명하는 메시지가 표시됩니다. 내용을 검토한 다음 __등록__을 클릭합니다.

 ![이 장치 macOS 식별 또는 등록](./media/macOS_enroll_002_IDenroll_popup.png)

5. 두 번째 팝업 창에 __이 장치를 등록__하면 어떻게 되는지 간단히 설명하는 메시지가 표시됩니다. 내용은 검토한 다음 __설치__를 클릭하여 진행합니다.

 ![이 장치 macOS 등록](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > 장치가 조직의 리소스에 액세스해도 안전한지 확인하기 위해 Intune에서 컴퓨터에 액세스해야 합니다. [Intune에서 장치를 등록하면 어떻게 되는지](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) 알아보세요.

6. __시스템 환경설정__이 열리고 __"관리 프로필"을 설치할까요?__ 메시지가 표시됩니다. __설치__를 클릭하여 진행하거나 __프로필 표시__를 클릭하여 자세한 내용을 확인합니다.

 ![관리 프로필 설치](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. macOS 팝업 창이 표시됩니다. 컴퓨터의 __사용자 이름__과 __암호__를 입력한 다음 __확인__을 클릭하여 변경하도록 확인합니다. 그러면 관리 프로필이 Mac에 설치됩니다.

 ![macOS 프로필 설치 팝업](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Mac에서 프로필에 대한 자세한 정보가 포함된 메시지나 __설치__할지 여부를 묻는 메시지가 추가로 표시될 수 있습니다. __계속__ 및 __설치__를 클릭하여 진행합니다. 설치가 완료되면 __장치 프로필__ 목록에서 새로 설치된 __관리 프로필__을 볼 수 있습니다.

 ![macOS 프로필 설치됨](./media/macOS_enroll_006_sysprefs_installed_profile.png)

여전히 도움이 필요하세요? IT 관리자에게 문의하세요. 연락처 정보는 [회사 포털 웹 사이트](http://portal.manage.microsoft.com)에서 찾을 수 있습니다.



<!--HONumber=Dec16_HO2-->

