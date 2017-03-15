---
title: "CriticalSection::CriticalSection 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection, 생성자"
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::CriticalSection 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

뮤텍스 개체와 유사하지만 단일 프로세스에서 스레드에서 사용할 수 있는 동기화 개체를 초기화 합니다.  
  
## 구문  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### 매개 변수  
 `spincount`  
 임계 셕션 개체의 회전 수를 설정합니다.  기본값은 0입니다.  
  
## 설명  
 섹션 crticial 및 spincounts에 대한 자세한 내용은 **InitializeCriticalSectionAndSpinCount**함수 Windows API documenation 동기화 섹션을 참조합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)