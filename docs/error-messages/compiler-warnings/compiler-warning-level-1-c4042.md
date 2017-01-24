---
title: "컴파일러 경고 (수준 1) C4042 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4042"
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 저장소 클래스가 잘못되었습니다.  
  
 이 컨텍스트에서는 지정된 저장소 클래스를 이 식별자와 함께 사용할 수 없습니다.  컴파일러는 대신에 기본 저장소 클래스를 사용합니다.  
  
-   `extern`: *identifier*가 함수인 경우  
  
-   **auto**: *identifier*가 정식 매개 변수나 지역 변수인 경우  
  
-   저장소 클래스 없음: *identifier*가 전역 변수인 경우  
  
 이 경고는 매개 변수 선언에서 **register** 이외의 저장소 클래스를 지정하는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C4042 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```