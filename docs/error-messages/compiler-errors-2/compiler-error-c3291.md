---
title: "컴파일러 오류 C3291 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: da6145b3a3aecd5f550a58c009020fb24280349e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3291"></a>컴파일러 오류 C3291
'default' : trivial 속성의 이름이 될 수 없습니다.  
  
 trivial 속성은 `default`로 이름을 바꿀 수 없습니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3291을 생성합니다.  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```
