---
title: "__max | Microsoft Docs"
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
  - "__max"
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
  - "max"
  - "__max"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__max 매크로"
  - "max 매크로"
  - "최대값 매크로"
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __max
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 값 중 더 큰 값을 반환합니다.  
  
## 구문  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### 매개 변수  
 `type`  
 숫자 데이터 형식  
  
 `a, b`  
 비교 되는 숫자 형식의 값입니다.  
  
## 반환 값  
 `__max` 은 인수 중 더 큰 숫자를 반환합니다.  
  
## 설명  
 `__max` 매크로는 두 값을 비교 하고 더 큰 값을 반환 합니다.  서명 되거나 서명 되지 않은 데이터 형식은 모든 숫자 인수가 될 수 있습니다.  인수와 반환 값은 동일한 데이터 형식 이어야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`__max`|\<stdlib.h\>|  
  
## 예제  
 자세한 내용은 [\_\_min](../../c-runtime-library/reference/min.md) 의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Math::Max](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_\_min](../../c-runtime-library/reference/min.md)