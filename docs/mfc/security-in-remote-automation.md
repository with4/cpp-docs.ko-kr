---
title: "원격 자동화의 보안 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- AllowRemoteActivation [MFC]
- Remote Automation [MFC], security
- activating objects [MFC]
- security [MFC]
- Automation objects [MFC], security options
- object activation [MFC]
- security [MFC], Remote Automation
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e535fac6330d6268629e8e3681fec47c7b0d65d3
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="security-in-remote-automation"></a>원격 자동화의 보안
원격 자동화는 서버 응용 프로그램 작성기(또는 해당 관리자)를 통해 특정 개체를 원격으로 활성화할 수 있는 방법을 지정할 수 있도록 기본적인 수준의 보안을 지원합니다. 지정된 시스템의 모든 자동화 개체는 전역적으로 "원격 활성화 허용 안 함" 또는 "원격 활성화 허용"으로 설정될 수 있습니다. 또한 개별 개체에 이러한 기능이 더욱 자주 제공될 수 있습니다. 원격 자동화는 키를 사용 하 여 각 개체의 레지스트리 설정에 **AllowRemoteActivation**, 지정된 된 서버를 원격으로 활성화할 수 있는지 여부를 확인 하려면. 시스템 전역 설정에서 이 모드가 사용될 경우 이 키가 레지스트리 내의 각 개체에 할당될 수 있으며 각 개체의 개별 상태는 "예" 또는 "아니요"로 적절하게 설정될 수 있습니다.  
  
 서버 시스템에서 Windows NT 또는 Windows 2000을 실행하는 경우 보안의 대체 형식이 허용됩니다. 이 경우 원격 자동화는 지정된 서버를 원격으로 활성화할 수 있는 사용자, 그룹 또는 사용자 그룹을 지정하는 NT ACL(액세스 제어 목록)을 사용합니다.  
  
 보안 옵션은 전체 개체에 적용되며 특정 인터페이스의 특성이나 개별 속성 또는 해당 개체의 메서드를 설정할 수 없습니다.  
  
 RAC(원격 자동화 연결) 관리자를 통해 모든 보안 옵션을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화](../mfc/remote-automation.md)

