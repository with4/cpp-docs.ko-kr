---
title: "컴파일러 경고 (수준 3) C4580 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: c8cebbda1d3472a2efda43f816e7a13f2f460408
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4580"></a>컴파일러 경고(수준 3) C4580
[attribute]는 사용되지 않습니다. 대신 System::Attribute or Platform::Metadata를 기본 클래스로 지정합니다.  
  
[[특성](../../windows/attribute.md)]는 더 이상 사용자 지정 특성을 만들기 위한 기본 구문입니다. 자세한 내용은 참조 [사용자 정의 특성](../../windows/user-defined-attributes-cpp-component-extensions.md)합니다. CLR 코드의 경우 `System::Attribute`에서 특성을 파생시킵니다. Windows 런타임 코드의 경우 `Platform::Metadata`에서 특성을 파생시킵니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3454 오류가 발생하는 경우 및 이를 해결 방법을 보여 줍니다.  
  
```cpp  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```
