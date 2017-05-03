---
title: "Agile::operator-&gt; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator->"
ms.assetid: 570f4b0b-1735-49b3-8a30-4a302ac57074
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator-&gt; 연산자
현재 Agile 개체가 나타내는 개체에 대한 핸들을 검색합니다.  
  
## 구문  
  
```cpp  
  
       T^ operator->()   
const throw();  
```  
  
## 반환 값  
 현재 Agile 개체가 나타내는 개체에 대한 핸들입니다.  
  
 이 연산자는 실제로 알려지지 않은 내부 형식을 반환합니다. 반환 값을 보유하는 편리한 방법은 [auto](../Topic/auto%20\(C++\).md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)