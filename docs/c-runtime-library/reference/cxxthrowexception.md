---
title: "_CxxThrowException | Microsoft Docs"
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
  - "_CxxThrowException"
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
apitype: "DLLExport"
f1_keywords: 
  - "CxxThrowException"
  - "_CxxThrowException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CxxThrowException 함수"
  - "CxxThrowException 함수"
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CxxThrowException
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예외 레코드를 작성 하고 예외 처리를 시작 하려면 런타임 환경을 호출합니다.  
  
## 구문  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### 매개 변수  
 \[in\] `pExceptionObject`  
 예외를 생성한 개체입니다.  
  
 \[in\] `pThrowInfo`  
 예외를 처리 하는 데 필요한 정보입니다.  
  
## 설명  
 이 메서드는 컴파일러를 사용 하여 예외를 처리 하는 컴파일러 전용 파일에 포함 됩니다.  코드에서 직접 메서드를 호출하면 안 됩니다.  
  
## 요구 사항  
 **출처:** Throw.cpp  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)