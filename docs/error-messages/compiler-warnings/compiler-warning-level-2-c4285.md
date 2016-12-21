---
title: "컴파일러 경고 (수준 2) C4285 | Microsoft Docs"
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
  - "C4285"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4285"
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4285
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier::operator –\>'의 반환 형식은 중위 표기법을 사용하여 적용할 경우 재귀적입니다.  
  
 지정된 **operator–\>\(\)** 함수에서는 정의한 형식이나 해당 형식에 대한 참조를 반환할 수 없습니다.  
  
 다음 샘플에서는 C4285 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```