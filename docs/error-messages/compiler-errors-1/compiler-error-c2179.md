---
title: "컴파일러 오류 C2179 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2179
dev_langs: C++
helpviewer_keywords: C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c0f311bcdbbdaa721e3897eae0a90ae892cf75d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2179"></a>컴파일러 오류 C2179
'type': 특성 인수에서 형식 매개 변수를 사용할 수 없습니다  
  
 제네릭 형식 매개 변수는 런타임에 확인 됩니다. 그러나 특성 매개 변수는 컴파일 타임에 확인 되어야 합니다. 따라서 특성에 대 한 인수로 제네릭 형식 매개 변수를 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2179 오류가 발생 합니다.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```