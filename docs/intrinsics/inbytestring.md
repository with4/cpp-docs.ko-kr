---
title: "__inbytestring | Microsoft Docs"
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
  - "__inbytestring"
  - "__inbytestring_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep insb 명령"
  - "__inbytestring 내장 함수"
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 사용 하 여 지정 된 포트에서 데이터를 읽고 있는 `rep insb` 명령.  
  
## 구문  
  
```  
void __inbytestring(  
   unsigned short Port,  
   unsigned char* Buffer,  
   unsigned long Count  
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 읽기 포트입니다.  
  
 \[out\] `Buffer`  
 데이터 포트에서 읽기 여기에 기록 됩니다.  
  
 \[in\] `Count`  
 읽을 데이터의 바이트 수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__inbytestring`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)