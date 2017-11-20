---
title: "컴파일러 오류 C2158 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2158
dev_langs: C++
helpviewer_keywords: C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 84241663685ab1d12581b84bc761dcff77420fd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2158"></a>컴파일러 오류 C2158
'type': #pragma make_public 지시문은 현재 템플릿이 아닌 네이티브 형식에만 사용할 수 있습니다.  
  
 [make_public](../../preprocessor/make-public.md) pragma는 템플릿이 아닌 네이티브 형식에만 적용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2158을 생성합니다.  
  
```  
// C2158.cpp  
// compile with: /clr /c  
ref class A {};  
#pragma make_public(A)   // C2158  
  
template< typename T >  
class B {};  
#pragma make_public(B)   // C2158  
#pragma make_public(B<int>)   // C2158  
  
void C () {}  
#pragma make_public(C)   // C2158  
  
class D {};  
#pragma make_public(D)   // OK  
```