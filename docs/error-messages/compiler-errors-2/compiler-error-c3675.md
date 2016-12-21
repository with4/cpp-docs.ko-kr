---
title: "컴파일러 오류 C3675 | Microsoft Docs"
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
  - "C3675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3675"
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 'property'이\(가\) 정의되어서 예약어입니다.  
  
 사용자가 간단한 속성을 정의하면 컴파일러는 get 및 set 접근자 메서드를 생성하고 이들 이름이 프로그램의 범위에 표시됩니다.  컴파일러에서 생성한 이름은 속성 이름 앞에 get\_ 및 set\_가 추가되어 구성됩니다.  따라서 컴파일러가 생성한 접근자와 이름이 동일한 함수는 선언할 수 없습니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3675 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```