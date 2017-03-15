---
title: "컴파일러 경고(수준 1) C4376 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4376"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4376"
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 1) C4376
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액세스 지정자 'old\_specifier:'은\(는\) 더 이상 지원되지 않습니다. 대신 'new\_specifier:'을\(를\) 사용하십시오.  
  
 형식 및 멤버 액세스를 지정 하는 메타 데이터에 대한 자세한 내용은 다음을 참조 하십시오.  [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 및 [멤버 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility). 이것은 [방법: 클래스 및 구조체 정의 및 사용](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)에 있습니다.  
  
## 예제  
 다음 샘플에서는 C4376 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```