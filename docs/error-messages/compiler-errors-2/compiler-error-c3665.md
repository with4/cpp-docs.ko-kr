---
title: "컴파일러 오류 C3665 | Microsoft Docs"
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
  - "C3665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3665"
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'destructor' : 재정의 지정자 'keyword'은\(는\) destructor\/finalizer에 사용할 수 없습니다.  
  
 소멸자나 종료자에 사용할 수 없는 키워드를 사용했습니다.  
  
 예를 들어 소멸자나 종료자에 대해서는 새 슬롯을 요청할 수 없습니다.  자세한 내용은 다음을 참조하십시오. [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md) 및 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 다음 샘플에서는 C3665 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3665.cpp  
// compile with: /clr  
public ref struct R {  
   virtual ~R() { }  
   virtual void a() { }  
};  
  
public ref struct S : R {  
   virtual ~S() new {}   // C3665  
   virtual void a() new {}   // OK  
};  
```