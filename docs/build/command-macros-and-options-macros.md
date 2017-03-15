---
title: "명령 매크로와 옵션 매크로 | Microsoft Docs"
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
  - "NMAKE의 명령 매크로"
  - "매크로, 명령 매크로"
  - "매크로, 옵션 매크로"
  - "옵션 매크로"
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 명령 매크로와 옵션 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft 제품에는 명령 매크로가 미리 정의되어 있습니다.  옵션 매크로는 이러한 제품에 대한 옵션을 나타내며 기본적으로 정의되어 있지 않습니다.  명령 매크로와 옵션 매크로 모두 미리 정의된 유추 규칙에 사용하며 설명 블록이나 사용자가 정의한 유추 규칙에 사용할 수 있습니다.  명령 매크로를 다시 정의하여 옵션을 포함하여 명령줄의 일부 또는 전부를 나타낼 수 있습니다.  옵션 매크로를 정의하지 않으면 null 문자열이 생성됩니다.  
  
|Microsoft 제품|명령 매크로|정의|옵션 매크로|  
|------------------|------------|--------|------------|  
|매크로 어셈블러|**As**|ml|**AFLAGS**|  
|기본 컴파일러|**BC**|bc|**BFLAGS**|  
|C 컴파일러|**CC**|cl|**CFLAGS**|  
|C\+\+ 컴파일러|**CPP**|cl|**CPPFLAGS**|  
|C\+\+ 컴파일러|**CXX**|cl|**CXXFLAGS**|  
|리소스 컴파일러|**RC**|rc|**RFLAGS**|  
  
## 참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)