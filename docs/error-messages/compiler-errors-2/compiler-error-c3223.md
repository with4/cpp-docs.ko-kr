---
title: "컴파일러 오류 C3223 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3223
dev_langs:
- C++
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 40d433c600dd560a4642aac1832fe94b60917fa0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3223"></a>컴파일러 오류 C3223
'property': 속성에 'typeid'를 적용할 수 없습니다.  
  
 속성에 [typeid](../../windows/typeid-cpp-component-extensions.md) 를 적용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3223을 생성합니다.  
  
```  
// C3223.cpp  
// compile with: /clr  
ref class R {  
public:  
   property int myprop;  
};  
  
int main() {  
   System::Type^ type2 = R::myprop::typeid;   // C3223  
}  
```
