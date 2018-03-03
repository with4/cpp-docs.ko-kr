---
title: "컴파일러 경고 (수준 3) C4580 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed0391a1a31b4ab64efa01fc15622831de890489
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4580"></a>컴파일러 경고(수준 3) C4580
[attribute]는 사용되지 않습니다. 대신 System::Attribute or Platform::Metadata를 기본 클래스로 지정합니다.  
  
[[특성](../../windows/attribute.md)]는 더 이상 사용자 정의 특성을 만들기 위한 기본 구문입니다. 자세한 내용은 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하세요. CLR 코드의 경우 `System::Attribute`에서 특성을 파생시킵니다. Windows 런타임 코드의 경우 `Platform::Metadata`에서 특성을 파생시킵니다.  
  
## <a name="example"></a>예  
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