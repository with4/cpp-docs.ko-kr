---
title: "_callnewh | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_callnewh"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_callnewh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_callnewh"
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _callnewh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 설치된 *새 처리기*를 호출합니다.  
  
## 구문  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
  
```  
  
#### 매개 변수  
 `size`  
 [new 연산자](../../cpp/new-operator-cpp.md)가 할당 하려고 시도하는 메모리의 양.  
  
## 반환 값  
  
|값|설명|  
|-------|--------|  
|0|오류: 새 처리기가 설치 및 활성화되지 않았습니다.|  
|1|성공: 새 처리기가 설치 및 활성화 되어 있습니다.  메모리 할당을 다시 시도할 수 있습니다.|  
  
## 예외  
 *새 처리기*를 찾을 수 없는 경우, 이 함수는  [bad\_alloc](../../standard-library/bad-alloc-class.md)를 throw합니다.  
  
## 설명  
 [new 연산자](../../cpp/new-operator-cpp.md) 메모리 할당에 실패할 경우, *새 처리기* 는 호출됩니다.  새 처리기는 후속 할당 성공할 수 있도록 메모리를 해제하는 등 적절한 작업을 시작할 수도 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_callnewh|internal.h|  
  
## 참고 항목  
 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md)