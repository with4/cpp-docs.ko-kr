---
title: "컴파일러 오류 C3223 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f190d347ddb17e49fba92f215737fd564d04506b
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3223"></a>컴파일러 오류 C3223
'property': 속성에 'typeid'를 적용할 수 없습니다.  
  
 적용할 수 없지만 [typeid](../../windows/typeid-cpp-component-extensions.md) 속성입니다.  
  
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
