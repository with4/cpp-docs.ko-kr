---
title: "__outbyte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outbyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out 명령"
  - "__outbyte 내장 함수"
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성은 `out` 1 지정 된 바이트를 전송 하는 명령 `Data` 가 지정한 I\/O 포트가 아웃 `Port`.  
  
## 구문  
  
```  
void __outbyte(   
   unsigned short Port,   
   unsigned char Data   
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 데이터를 보낼 포트입니다.  
  
 \[in\] `Data`  
 지정 된 포트로 보낼 바이트입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__outbyte`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)