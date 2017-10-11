---
title: "컴파일러 경고 C4355 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 061ad3df17cf9c86fbc5ac98048932aff8b0b25b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4355"></a>컴파일러 경고 C4355
'this' : 기본 멤버 이니셜라이저 목록에서 사용되었습니다.  
  
 **이** 포인터는 비정적 멤버 함수 내 에서만 유효 합니다. 기본 클래스에 대 한 이니셜라이저 목록에서 사용할 수 없습니다.  
  
 기본 클래스 생성자와 클래스 멤버 생성자 전에 호출 됩니다 **이** 생성자입니다. 실제로 다른 생성자에 생성 되지 않은 개체에 대 한 포인터를 전달 했습니다. 이러한 다른 생성자는 모든 멤버에 액세스할 또는이 멤버 함수를 호출을 하는 경우 결과가 정의 되지 것입니다. 사용 하지 않아야는 **이** 모든 생성이 완료 될 때까지 포인터입니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4355 오류가 생성 됩니다.  
  
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
