---
title: "__outbytestring | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outbytestring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep outsb 명령"
  - "__outbytestring 내장 함수"
  - "outsb 명령"
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성은 `rep outsb` 첫 번째 전송 명령, `Count` 에 데이터 바이트를 가리키는 의해 `Buffer` 지정 된 포트 `Port`.  
  
## 구문  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 데이터를 보낼 포트입니다.  
  
 \[in\] `Buffer`  
 지정 된 포트를 통해 전송 될 데이터입니다.  
  
 \[in\] `Count`  
 보낼 데이터의 바이트 수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__outbytestring`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)