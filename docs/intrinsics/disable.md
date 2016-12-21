---
title: "_disable | Microsoft Docs"
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
  - "_disable_cpp"
  - "_disable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_disable 내장"
  - "내장 사용 안 함"
  - "rsm 명령"
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _disable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 인터럽트를 사용하지 않도록 설정합니다.  
  
## 구문  
  
```  
void _disable(void);  
```  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_disable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `_disable`는 인터럽트 플래그를 지우도록 프로세서에 명령합니다.  x86 시스템에서 이 함수는 인터럽트 플래그 지우기\(`cli`\) 명령을 생성합니다.  
  
 이 함수는 커널 모드에서만 사용할 수 있습니다.  사용자 모드에서 이 함수를 사용하면 런타임에 권한 있는 명령 예외가 throw됩니다.  
  
 ARM 플랫폼에서 이 루틴은 내장 함수로만 사용할 수 있습니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)