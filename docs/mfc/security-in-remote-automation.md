---
title: "원격 자동화의 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "개체 활성화"
  - "AllowRemoteActivation"
  - "자동화 개체, 보안 옵션"
  - "개체 활성화"
  - "원격 자동화, 보안"
  - "보안[MFC]"
  - "보안[MFC], 원격 자동화"
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 원격 자동화의 보안
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

원격 자동화는 특정 개체를 원격으로 활성화 할 수있는 방법을 지정 \(또는 오히려, 그 관리자\) 서버 응용 프로그램 작가를 할 수 있도록 기본적인 수준의 보안을 지원합니다.  주어진 시스템의 모든 자동화 개체는 세계적으로 "원격 작동을 허용"하거나 "원격 작동을 허용"으로 설정될 수 있습니다.  또한, 더 자주, 개별 개체와 같은 기능을 제공할 수 있습니다.  원격 자동화는 특정 서버를 원격으로 활성화 할 수 있는지 여부를 결정하기 위해 각 개체의 레지스트리 설정의 키 **AllowRemoteActivation**를 사용합니다.  시스템 범위 설정이 모드를 사용할 경우, 레지스트리 내의 각 객체는이 키를 할당 할 수 있으며, 각각의 개별 상태가 적절하게 "예"또는 "아니오"로 설정 될 수 있습니다.  
  
 서버 시스템에서 Windows NT 또는 Windows 2000을 실행하는 경우, 보안의 또 다른 형태는 허용됩니다.  이 경우, 원격 자동화는 사용자 또는 그룹 또는 사용자 그룹 원격 관련 서버를 활성화 할 수있는 지정 NT 액세스 제어리스트 \(ACL\)를 사용합니다.  
  
 보안 옵션은 전체 개체에 적용됩니다; 그것은 또는 개별 속성 또는 해당 개체의 메서드, 특정 인터페이스의 속성을 설정할 수 없습니다.  
  
 연결 RAC \(원격 자동화\) 관리자를 통해 모든 보안 옵션을 설정할 수 있습니다.  
  
## 참고 항목  
 [원격 자동화](../mfc/remote-automation.md)