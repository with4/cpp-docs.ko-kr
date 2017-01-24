---
title: "__RTDynamicCast | Microsoft Docs"
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
  - "__RTDynamicCast"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__RTDynamicCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__RTDynamicCast"
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __RTDynamicCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[dynamic\_cast](../cpp/dynamic-cast-operator.md) 연산자의 런타임 구현입니다.  
  
## 구문  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### 매개 변수  
 `inptr`  
 다형성 개체에 대한 포인터입니다.  
  
 `VfDelta`  
 개체 내 가상 함수 포인터의 오프셋입니다.  
  
 `SrcType`  
 `inptr` 매개 변수에 의해 가리켜지는 개체의 정적 형식입니다.  
  
 `TargetType`  
 캐스트의 의도된 결과입니다.  
  
 `isReference`  
 입력이 참조인 경우 `true`이며, 입력이 포인터인 경우 `false`입니다.  
  
## 반환 값  
 성공한 경우, 적절한 하위 개체에 대한 포인터입니다. 그렇지 않으면 NULL입니다.  
  
## 예외  
 `dynamic_cast<>`의 입력이 참조이고 캐스팅이 실패한 경우 `bad_cast()`입니다.  
  
## 설명  
 `inptr` 형식의 개체를 `TargetType`로 변환합니다.  만약 `TargetType`이 포인터이거나 l\-값이라면, 만약 `TargetType`이 참조라면, `inptr`의 유형은 포인터가 되어야 합니다.  `TargetType`는 포인터나 앞서 정의한 클래스 유형이나 "빈 공간에 대한 포인터"에 대한 참조가 되어야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_RTDynamicCast|rtti.h|