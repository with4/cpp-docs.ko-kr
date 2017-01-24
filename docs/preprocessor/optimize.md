---
title: "최적화 | Microsoft Docs"
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
  - "vc-pragma.optimize"
  - "optimize_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "최적화 pragma"
  - "pragma, 최적화"
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 최적화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수별로 수행할 최적화를 지정합니다.  
  
## 구문  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## 설명  
 **optimize** pragma는 함수 외부에 나타나야 하며, pragma가 표시된 후 정의된 첫 번째 함수에서 적용됩니다.  **on** 및 **off** 인수는 *optimization\-list*에서 지정된 옵션을 설정하거나 해제합니다.  
  
 *optimization\-list*는 다음 표에 나와 있는 0개 이상의 매개 변수일 수 있습니다.  
  
### optimize Pragma의 매개 변수  
  
|매개 변수|최적화 형식|  
|-----------|------------|  
|**g**|전역 최적화를 활성화합니다.|  
|**s** 또는 **t**|짧거나 빠른 기계어 코드 시퀀스를 지정합니다.|  
|**y**|프로그램 스택에서 프레임 포인터를 생성합니다.|  
  
 이러한 문자는 [\/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션과 함께 사용되는 동일한 문자입니다.  예를 들어 다음 pragma는 **\/Os** 컴파일러 옵션과 동일합니다.  
  
```  
#pragma optimize( "ts", on )  
```  
  
 빈 문자열\(**""**\)과 함께 사용된 **optimize** pragma는 특별한 형태의 지시문입니다.  
  
 **off** 매개 변수를 사용하는 경우 이 항목 앞부분의 표에 나와 있는 최적화가 해제됩니다.  
  
 **on** 매개 변수를 사용하는 경우 [\/O](../build/reference/o-options-optimize-code.md) 컴파일러 옵션으로 지정한 항목에 대해 최적화가 다시 설정됩니다.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)