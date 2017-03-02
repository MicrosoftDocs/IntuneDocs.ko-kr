---
title: "Intune에서 Apple DEP 인증서 가져오기 | Intune Azure 미리 보기 | Microsoft Docs"
description: "Intune Azure 미리 보기: Intune에서 Apple 장치를 관리하기 위한 필수 구성 요소인 MDM Push Certificate를 구성 및 업로드하는 지침입니다. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: c740dedebdc4afd909a8c38447f698c2724de5a1

---

# <a name="get-an-apple-dep-certificate"></a>Apple DEP 인증서 가져오기 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

회사 소유의 iOS 장치를 DEP에 등록하려면 Apple의 DEP 토큰이 필요합니다. Intune에서는 이 토큰을 통해 회사에서 소유한 DEP 참가 장치에 대한 정보를 동기화할 수 있습니다. 또한 Apple에 등록 프로필을 업로드하고 이러한 프로필에 장치를 할당할 수 있습니다.

Apple DEP(장치 등록 프로그램)로 회사 소유의 iOS 장치를 관리하려면 조직이 Apple DEP에 가입하고 해당 프로그램을 통해 장치를 받아야 합니다. 해당 프로세스의 세부 정보는 https://deploy.apple.com에서 확인할 수 있습니다. 이 프로그램의 이점 중 하나는 USB 케이블을 사용해서 각 장치를 컴퓨터에 연결하지 않고도 장치를 자동 설치할 수 있다는 것입니다.

> [!NOTE]
> 이 지침은 Intune 관리 콘솔에서 Azure Portal로 마이그레이션한 경우에만 적용됩니다. 마이그레이션 기간 동안 Intune 관리 콘솔에서 Apple DEP 토큰을 삭제한 경우에는 DEP 토큰이 Intune 계정으로 복원될 수도 있습니다. 이 경우 Azure Portal에서 DEP 토큰을 삭제하면 됩니다. 

**Apple DEP 인증서를 가져오려면**</br>
Azure Portal에서 **추가 서비스**를 선택하고 텍스트 상자에 **Intune**을 입력한 다음 **기타** > **Intune**을 선택합니다. Intune 블레이드에서 **장치 등록** > **Apple DEP 인증서**를 선택한 후 Azure Portal에서 번호가 매겨진 단계(아래 참조)를 따릅니다.

**1단계. Apple DEP 토큰을 만드는 데 필요한 Intune 공개 키 인증서를 다운로드합니다.**<br>
**공개 키 다운로드**를 선택하여 암호화 키(.pem) 파일을 다운로드하고 로컬로 저장합니다. .pem 파일은 Apple 장치 등록 프로그램 포털에서 트러스트 관계 인증서를 요청하는 데 사용됩니다.

**2단계. 적절한 Apple 웹 사이트에서 Apple DEP 토큰을 다운로드합니다.**<br>
[Apple 배포 프로그램을 통해 DEP 토큰 만들기](https://deploy.apple.com)(https://deploy.apple.com)를 선택하고 회사 Apple ID로 로그인합니다. DEP 토큰을 갱신하려면 이 Apple ID를 사용해야 합니다.

   1.  [장치 등록 프로그램 포털](https://deploy.apple.com)에서 **장치 등록 프로그램** &gt; **서버 관리**로 이동한 후 **MDM 서버 추가**를 선택합니다.

   2.  **MDM 서버 이름**을 입력하고 **다음**을 선택합니다. 서버 이름은 참조용으로 MDM(모바일 장치 관리) 서버를 식별하기 위한 것으로, Microsoft Intune 서버의 이름 또는 URL이 아닙니다.

   3.  **&lt;ServerName&gt; 추가** 대화 상자가 열립니다. **파일 선택...**을 선택하여 .pem 파일을 업로드하고 **다음**을 선택합니다.

   4.  **&lt;ServerName&gt; 추가** 대화 상자에 **내 서버 토큰** 링크가 표시됩니다. 컴퓨터에 서버 토큰(.p7m) 파일을 다운로드한 다음 **완료**를 선택합니다.

    이 인증서(.p7m) 파일은 Intune과 Apple 장치 등록 프로그램 서버 간에 트러스트 관계를 설정하는 데 사용됩니다.

**3단계. Apple DEP 토큰을 만드는 데 사용되는 Apple ID를 입력합니다. 이 ID를 사용하여 Apple DEP 토큰을 갱신할 수 있습니다.**

**4단계. 업로드할 Apple DEP 토큰으로 이동합니다. Intune에서 DEP 계정과 자동으로 동기화합니다.**<br>
인증서(.pem) 파일로 이동한 후 **열기**를 선택하고 **업로드**를 선택합니다. Push Certificate가 있으면 Intune에서 등록된 모바일 장치에 정책을 푸시하여 iOS 장치를 등록하고 관리할 수 있습니다.



<!--HONumber=Feb17_HO1-->

