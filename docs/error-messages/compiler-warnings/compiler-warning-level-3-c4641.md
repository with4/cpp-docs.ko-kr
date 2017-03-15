---
title: "컴파일러 경고 (수준 3) C4641 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4641"
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 문서 주석에 모호한 상호 참조가 있습니다.  
  
 컴파일러에서 참조를 명확하게 확인할 수 없습니다.  이 경고를 해결하려면 참조를 명확하게 하는 데 필요한 매개 변수 정보를 지정합니다.  
  
 자세한 내용은 [XML 문서](../../ide/xml-documentation-visual-cpp.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4641 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```