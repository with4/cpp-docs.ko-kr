---
title: "__readdr | Microsoft Docs"
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
  - "__readdr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readdr 내장 함수"
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readdr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 디버그 레지스터의 값을 읽습니다.  
  
## 구문  
  
```  
unsigned         __readdr(unsigned int DebugRegister);  
unsigned __int64 __readdr(unsigned int DebugRegister);  
```  
  
#### 매개 변수  
 \[in\] `DebugRegister`  
 디버그를 식별 하는 0부터 7 상수를 등록 합니다.  
  
## 반환 값  
 지정 된 디버그 레지스터의 값입니다.  
  
## 설명  
 이러한 내장 커널 모드에서 사용할 수 있으며 루틴을 내장으로만 사용할 수 있습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readdr`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_readeflags](../intrinsics/readeflags.md)