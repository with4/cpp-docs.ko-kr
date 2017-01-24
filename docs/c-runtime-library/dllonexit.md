---
title: "__dllonexit | Microsoft Docs"
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
  - "__dllonexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dllonexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dllonexit"
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __dllonexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

종료 시 호출 되는 루틴을 등록 합니다.  
  
## 구문  
  
```  
_onexit_t __dllonexit(  
   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### 매개 변수  
 `func`  
 종료 시 실행할 함수에 대한 포인터입니다.  
  
 `pbegin`  
 분리 시 실행되는 함수의 리스트의 처음을 가리키는 변수의 포인터입니다.  
  
 `pend`  
 분리 시 실행되는 함수의 리스트의 끝을 가리키는 변수의 포인터입니다.  
  
## 반환 값  
 성공 하면, 사용자 함수를 가리키는 포인터입니다.  그렇지 않으면, NULL 포인터입니다.  
  
## 설명  
 `__dllonexit` 함수는 해당 함수에 의해 사용되는 전역 변수를 이 루틴에서 볼 수 없는 것을 제외하고는 [\_onexit](../c-runtime-library/reference/onexit-onexit-m.md) 함수와 유사합니다.  전역 변수를 사용하는 대신, 이 함수는 `pbegin` 및 `pend` 매개 변수를 사용합니다.  
  
 MSVCRT.LIB과 연결된 DLL 안의 `_onexit` 및 `atexit` 함수는 반드시 자체 texit\/\_onexit 목록을 유지 관리해야 합니다.  이 루틴은 이러한 DLL에서 호출하는 작업자입니다.  
  
 `_PVFV` 형식이 `typedef void (__cdecl *_PVFV)(void)`로 정의되었습니다.  
  
## 요구 사항  
  
|루틴|필수 파일|  
|--------|-----------|  
|\_\_dllonexit|onexit.c|  
  
## 참고 항목  
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)