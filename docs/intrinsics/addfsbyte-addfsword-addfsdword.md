---
title: "__addfsbyte, __addfsword, __addfsdword | Microsoft Docs"
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
  - "__addfsbyte_cpp"
  - "__addfsdword"
  - "__addfsword_cpp"
  - "__addfsbyte"
  - "__addfsword"
  - "__addfsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__addfsdword 내장 함수"
  - "__addfsword 내장 함수"
  - "__addfsbyte 내장 함수"
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __addfsbyte, __addfsword, __addfsdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 부가가치의 시작에 상대적인 오프셋에 의해 지정 된 메모리 위치를 `FS` 세그먼트.  
  
## 구문  
  
```  
void __addfsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addfsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addfsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 시작 부분에서 오프셋 `FS`.  
  
 \[in\] `Data`  
 메모리 위치에 추가할 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__addfsbyte`|x86|  
|`__addfsword`|x86|  
|`__addfsdword`|x86|  
  
## 설명  
 이러한 루틴은 내장으로만 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_incfsbyte, \_\_incfsword, \_\_incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)   
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)