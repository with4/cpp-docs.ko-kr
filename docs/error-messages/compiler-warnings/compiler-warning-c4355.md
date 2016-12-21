---
title: "컴파일러 경고 C4355 | Microsoft Docs"
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
  - "C4355"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4355"
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4355
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' : 기본 멤버 이니셜라이저 목록에서 사용되었습니다.  
  
 **this** 포인터는 비정적 멤버 함수에만 사용할 수 있으며  기본 클래스의 이니셜라이저 목록에는 사용할 수 없습니다.  
  
 기본 클래스 생성자와 클래스 멤버 생성자는 **this** 생성자 전에 호출됩니다.  여기서는 포인터를 다른 생성자에 대해 생성되지 않은 개체로 전달했습니다.  이러한 다른 생성자가 이에 대한 멤버에 액세스하거나 해당 멤버 함수를 호출하면 결과가 정의되지 않으므로  모든 생성이 완료될 때까지 **this** 포인터를 사용하지 말아야 합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4355 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```