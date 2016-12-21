---
title: "_setjmp3 | Microsoft Docs"
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
  - "_setjmp3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "setjmp3"
  - "_setjmp3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setjmp3 함수"
  - "setjmp3 함수"
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setjmp3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내부 CRT 함수입니다.  `setjmp` 함수의 새로운 구현입니다.  
  
## 구문  
  
```  
int _setjmp3(    OUT jmp_buf env,    int count,    (optional parameters) );  
```  
  
#### 매개 변수  
 \[out\] `env`  
 상태 정보 저장을 위한 버퍼 주소입니다.  
  
 \[in\] `count`  
 `optional parameters`에 저장된 정보의 추가 `DWORD` 수입니다.  
  
 \[in\] `optional parameters`  
 `setjmp` 내장 함수가 적용한 추가 데이터입니다.  첫 번째 `DWORD`는 추가 데이터를 해제한 다음 비휘발성 등록 상태로 반환하는 데 사용되는 함수 포인터입니다.  두 번째 `DWORD`는 복원할 시도 수준입니다.  모든 추가 데이터는 `jmp_buf`의 제네릭 데이터 배열에 저장됩니다.  
  
## 반환 값  
 항상 0을 반환합니다.  
  
## 설명  
 이 함수는 C\+\+ 프로그램에서는 사용하지 마세요.  C\+\+을 지원하지 않는 내장 함수입니다.  `setjmp`를 사용하는 방법에 대한 자세한 내용은 [setjmp\/longjmp 사용](../cpp/using-setjmp-longjmp.md)를 참조하십시오.  
  
## 요구 사항  
  
## 참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)