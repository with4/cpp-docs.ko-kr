---
title: "컴파일러 오류 C2390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2390"
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'specifier' 저장소 클래스가 잘못되었습니다.  
  
 전역 범위 식별자에 대한 저장소 클래스가 잘못되었습니다.  잘못된 클래스 대신에 기본 저장소 클래스가 사용됩니다.  
  
 다음과 같이 해결할 수 있습니다.  
  
-   식별자가 함수이면 `extern` 저장소로 선언합니다.  
  
-   식별자가 정식 매개 변수 또는 지역 변수이면 자동 저장소로 선언합니다.  
  
-   식별자가 전역 변수이면 저장소 클래스\(자동 저장소\) 없이 선언합니다.  
  
## 예제  
  
-   다음 샘플에서는 C2390 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```