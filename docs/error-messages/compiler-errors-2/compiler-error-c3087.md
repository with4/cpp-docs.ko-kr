---
title: "컴파일러 오류 C3087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
caps.latest.revision: 5
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
ms.openlocfilehash: f0f26938ae82e2d14ef9d6ca6cf944a4e396c32f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3087"></a>컴파일러 오류 C3087
'named_argument': 'attribute'에 대한 호출에서 이미 이 멤버를 초기화했습니다.  
  
 명명된 인수가 동일한 값에 대한 명명되지 않은 인수와 동일한 특성 블록에서 지정되었습니다. 명명된 인수나 명명되지 않은 인수만 지정합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3087을 생성합니다.  
  
```  
// C3087.cpp  
// compile with: /c  
[idl_quote("quote1", text="quote2")];   // C3087  
[idl_quote(text="quote3")];   // OK  
[idl_quote("quote4")];   // OK  
```
