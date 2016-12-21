---
title: "Charizing 연산자 (#@) | Microsoft Docs"
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
  - "#@"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#@ 전처리 연산자"
  - "charizing 연산자"
  - "전처리기, 연산자"
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Charizing 연산자 (#@)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 charizing 연산자는 매크로의 인수에만 사용할 수 있습니다.  매크로 정의에서 **\#@**이 형식 매개 변수 앞에 오는 경우 실제 인수는 매크로가 확장될 때 작은따옴표로 묶이고 문자로 취급됩니다.  예를 들면 다음과 같습니다.  
  
```  
#define makechar(x)  #@x  
```  
  
 위의 정의는 다음 문이  
  
```  
a = makechar(b);  
```  
  
 다음과 같이 확장되게 합니다.  
  
```  
a = 'b';  
```  
  
 작은따옴표는 charizing 연산자와 함께 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [전처리 연산자](../preprocessor/preprocessor-operators.md)