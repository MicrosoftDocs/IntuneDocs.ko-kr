---
title: "Windows 10용 앱 보호 정책 구성 준비 | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Azure AD에서 MAM(모바일 응용 프로그램 관리) 공급자 설치"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 9490951b2953f8b8c6fe3d38824053bbe75f9af1
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10용 앱 보호 정책 구성 준비

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Windows 10 앱 보호 정책을 만들려면 Azure AD에서 MAM(모바일 응용 프로그램 관리) 공급자를 설치하여 Windows 10용 MAM을 사용하도록 설정해야 합니다. 이와 같이 구성하면 Intune을 사용하여 새 WIP(Windows Information Protection) 정책을 만들 때 등록 상태를 정의할 수 있습니다.

> [!NOTE]
> 등록 상태는 MAM 또는 MDM(모바일 장치 관리)일 수 있습니다.

## <a name="to-configure-the-mam-provider"></a>MAM 공급자를 구성하려면

1.  [Azure Portal](https://portal.azure.com/)로 이동한 다음 Intune 자격 증명을 사용하여 로그인합니다.

2.  왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

    ![MAM 공급자 구성](../media/AppManagement/mam-provider-sc-1.png)

3.  **Azure AD** 블레이드가 열리면 **모바일(MDM 및 MAM)**을 선택한 다음 **Microsoft Intune**을 클릭합니다.

    ![모바일 MDM 및 MAM](../media/AppManagement/mam-provider-sc-1.png)

4.  구성 블레이드가 열리면 먼저 **기본 MAM URL 복원**을 선택한 후에 다음 항목을 구성합니다.

    a.  MAM 사용자 범위: MAM을 사용하여 Windows 10 장치를 사용하는 특정 사용자 그룹 또는 모든 사용자에 대한 회사 데이터를 보호할 수 있습니다.

    b.  MAM 사용 약관 URL: MAM 서비스 사용 약관 끝점의 URL입니다. 최종 사용자에게 MAM 서비스 약관을 표시하는 데 사용됩니다.

    c.  MAM 검색 URL: 장치가 앱 보호 정책을 적용해야 할 때 검색하는 URL 장치입니다.

    d.  MDM 준수 URL:

5.  이러한 설정을 구성한 후에 **저장**을 선택합니다.

## <a name="next-steps"></a>다음 단계

[WIP 앱 보호 정책 만들기](https://docs.microsoft.comcreate-windows-information-protection-policy-with-intune.md)
