---
title: "Windows PC에 대한 사용자-장치 연결 관리 | Microsoft Intune"
description: "Intune에서 관리되는 Windows PC에 사용자를 연결하는 방법을 알아봅니다."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 39fec6a2ea8d8c0f4b6ea1460c76a8a6c652d614


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Windows PC에 대한 사용자-장치 연결 관리
소프트웨어를 사용자에게 배포하려면 먼저 사용자를 컴퓨터에 연결해야 합니다. 여러 컴퓨터에 사용자를 연결할 수 있지만 각 컴퓨터는 한 사용자에게만 연결할 수 있습니다. 사용자는 회사 포털을 사용하여 Intune에 등록한 모든 컴퓨터에 자동으로 연결됩니다.

사용자를 컴퓨터에 연결하려면

1.  [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹** &gt; **모든 장치**(또는 사용자에게 연결하려는 컴퓨터가 포함된 다른 그룹)를 선택합니다.

2.  사용자를 연결할 컴퓨터를 선택한 후 **사용자 연결**을 선택합니다.

     **사용자 연결** 대화 상자에는 표시 이름과 함께 사용 가능한 사용자, 사용자 ID 및 각 사용자가 현재 연결되어 있는 컴퓨터 수의 목록이 표시됩니다. 사용자가 선택한 컴퓨터에 이미 연결되어 있는 경우 해당 사용자 이름과 사용자 ID가 **현재 사용자**아래에 표시됩니다. 컴퓨터가 어떤 사용자에게도 연결되지 않은 경우 **현재 사용자** 아래에 **사용자 없음**이 표시됩니다.

3.  다음 중 하나를 수행합니다.

    -   현재 사용자(있는 경우)에 연결되어 있는 컴퓨터를 그대로 두려면 **취소**를 선택합니다.

    -   현재 사용자에 대한 연결(있는 경우)을 제거하려면 **연결 제거** &gt; **확인**을 선택합니다.

    -   새 사용자와 컴퓨터를 연결하려면 **모든 사용자** 목록에서 사용자를 선택합니다. 사용자 데이터가 올바른지 확인한 후 **확인**을 선택합니다.

> [!TIP]
> 최종 사용자가 컴퓨터에 자신을 연결하는 기능을 제한하려면 **Microsoft Intune 에이전트 설정** 정책에서 **사용자와 컴퓨터를 연결하는 기능 제한** 옵션을 설정합니다.

### <a name="see-also"></a>참고 항목

[Intune 소프트웨어 클라이언트를 사용하는 일반 Windows PC 관리 작업](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->

