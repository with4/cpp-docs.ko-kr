---
title: "컴파일러 경고 (수준 3) C4159 | Microsoft Docs"
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
  - "C4159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4159"
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pragma\(pop,...\) : 이전에 푸시한 'identifier' 식별자를 팝했습니다.  
  
 소스 코드에는 pragma에 대한 식별자를 포함하는 **push** 명령 다음에 식별자를 포함하지 않는 **pop** 명령이 옵니다.  이로 인해 ***identifier***이\(가\) 팝되며, ***identifier***의 다음 사용으로 인해 예기치 않은 동작이 발생할 수도 있습니다.  
  
 이 경고를 방지하려면 **pop** 명령에 식별자를 제공하십시오.  예를 들면 다음과 같습니다.  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```