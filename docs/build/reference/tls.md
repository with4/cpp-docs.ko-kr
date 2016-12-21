---
title: "/TLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/TLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TLS dumpbin 옵션"
  - "-TLS dumpbin 옵션"
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 파일에서 IMAGE\_TLS\_DIRECTORY 구조체를 표시합니다.  
  
## 설명  
 \/TLS는 TLS 구조체의 필드와 TLS 콜백 함수의 주소를 표시합니다.  
  
 프로그램에서 스레드 지역 저장소를 사용하지 않는 경우 해당 이미지에는 TLS 구조체가 포함되지 않습니다.  자세한 내용은 [스레드](../../cpp/thread.md)를 참조하십시오.  
  
 IMAGE\_TLS\_DIRECTORY는 winnt.h에 정의됩니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)