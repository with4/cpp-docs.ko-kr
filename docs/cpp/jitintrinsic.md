---
title: "jitintrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "jitintrinsic"
  - "jitintrinsic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], jitintrinsic"
  - "jitintrinsic __declspec 한정자"
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# jitintrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

64비트 공용 언어 런타임에 중요한 항목으로 함수를 표시합니다.  이는 Microsoft에서 제공하는 라이브러리의 특정 함수에서 사용됩니다.  
  
## 구문  
  
```  
__declspec(jitintrinsic)  
```  
  
## 설명  
 `jitintrinsic`는 MODOPT\(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>\)를 함수 서명에 추가합니다.  
  
 예기치 않은 결과가 발생할 수 있기 때문에 이 `__declspec` 한정자는 사용하지 않도록 합니다.  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)