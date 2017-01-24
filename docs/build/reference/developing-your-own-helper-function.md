---
title: "사용자 도우미 함수 개발 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "도우미 함수"
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 사용자 도우미 함수 개발
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL이나 가져오기의 이름을 기준으로 특정 처리를 수행하는 루틴을 직접 작성할 수 있습니다.  제공된 코드를 기준으로 사용자가 직접 코드를 작성하는 방법과 앞에서 설명한 알림 후크를 사용하여 제공된 버전을 후크하는 방법이 있습니다.  
  
 직접 코드 작성  
 이 방법은 새 코드의 지침으로 제공되는 코드를 사용할 수 있기 때문에 비교적 간단합니다.  물론 호출 규칙을 지켜야 하고, 링커가 생성한 썽크로 제어를 반환할 경우 적절한 함수 포인터를 반환해야 합니다.  직접 코드를 작성하면 호출을 충족시키거나 호출에서 나가기 위해 다양한 작업을 수행할 수 있습니다.  
  
 처리 시작 알림 후크 사용  
 dliStartProcessing 알림의 기본 도우미와 동일한 값을 받는 사용자 제공 알림 후크 함수에 간단하게 새 포인터를 제공하는 것이 가장 편리한 방법입니다.  이 때 기본 도우미로 제어가 반환되면 기본 도우미의 모든 추가 처리가 생략되기 때문에 후크 함수는 반드시 새 도우미 함수여야 합니다.  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)