---
title: "_ 활성화 | Microsoft Docs"
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
  - "_enable"
  - "_enable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "내장 _ 활성화"
  - "내장 가능"
  - "ssm 명령"
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ 활성화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 인터럽트를 사용하도록 설정합니다.  
  
## 구문  
  
```  
void _enable(void);  
```  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_enable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `_enable`은 인터럽트 플래그를 설정하도록 프로세서에 명령합니다.  x86 시스템에서 이 함수는 인터럽트 플래그 설정\(`sti`\) 명령을 생성합니다.  
  
 이 함수는 커널 모드에서만 사용할 수 있습니다.  사용자 모드에서 이 함수를 사용하면 권한 있는 명령 예외가 throw됩니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)