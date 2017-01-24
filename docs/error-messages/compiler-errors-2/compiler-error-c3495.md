---
title: "컴파일러 오류 C3495 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3495"
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 람다 캡처에는 자동 저장 기간이 있어야 합니다.  
  
 `static` 또는 `extern`으로 표시된 변수와 같이 자동 저장 기간이 없는 변수를 캡처할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   람다 식의 캡처 목록에 `static` 또는 `extern` 변수를 전달하지 마세요.  
  
## 예제  
 다음 예제에서는 `static` 변수 `n`이 람다 식의 캡처 목록에 나타나므로 C3495를 생성합니다.  
  
```  
// C3495.cpp int main() { static int n = 66; [&n]() { return n; }(); // C3495 }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)   
 [\(NOTINBUILD\) 저장소 클래스 지정자](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c)