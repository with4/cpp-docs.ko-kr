---
title: "컴파일러 경고(수준 3) C4635 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4635"
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고(수준 3) C4635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 문서 주석 대상: 잘못된 형식의 XML: 이유  
  
 컴파일러가 XML 태그에서 일부 문제를 발견했습니다.  문제를 수정하고 다시 컴파일합니다.  
  
 다음 샘플에서는 C4635를 생성합니다.  
  
```  
// C4635.cpp // compile with: /doc /clr /W3 /c /// <summary> /// The contents of the folder have changed. /// <summary/>   // C4635 // try the following line instead // /// </summary> public ref class Test {};  
```  
  
 이 샘플은 **끝 태그 'member'가 시작 태그 'summary'와 일치하지 않습니다**를 출력합니다.  
  
 이 샘플의 문제는 \<summary\>에 대한 끝 태그가 잘못 구성되어 컴파일러가 \<summary\> 끝 태그로 인식하지 못하는 것입니다.  모든 \/doc 컴파일에서 컴파일러가 \<member\> 태그를 .xdc 파일에 포함합니다.  따라서 이 문제는 끝 태그 \<\/member\>가 컴파일러가 처리한 이전의 시작 태그 \<summary\>와 일치하지 않는다는 것입니다.