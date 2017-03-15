---
title: "컴파일러 오류 C3286 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3286"
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier': 반복 변수에는 저장소 클래스 지정자를 사용할 수 없습니다.  
  
 자세한 내용은 [\(NOTINBUILD\)저장소 클래스 지정자](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c)를 참조하세요.  
  
 자세한 내용은 [for each, in](../../dotnet/for-each-in.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3286을 생성합니다.  
  
```  
// C3286.cpp // compile with: /clr int main() { array<int> ^p = { 1, 2, 3 }; for each (static int i in p) {}   // C3286 for each (int j in p) {}   // OK }  
```