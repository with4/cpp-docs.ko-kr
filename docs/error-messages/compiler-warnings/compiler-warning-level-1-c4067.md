---
title: "컴파일러 경고 (수준 1) C4067 | Microsoft Docs"
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
  - "C4067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4067"
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리기 지시문 다음에 예기치 않은 토큰이 있습니다. 줄 바꿈 문자가 필요합니다.  
  
 컴파일러가 전처리기 지시문 다음에서 추가 문자를 발견하여 무시했습니다.  이 경고는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서만 표시됩니다.  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### 이 경고를 해결하려면 다음 중 하나를 수행하십시오.  
  
1.  **\/Ze**로 컴파일합니다.  
  
2.  주석 구분 기호를 사용합니다.  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```