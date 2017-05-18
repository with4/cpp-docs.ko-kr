---
title: "컴파일러 오류 C3846 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 04807182611beed23bf388d1f42a4fba0a3acea7
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3846"></a>컴파일러 오류 C3846
'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'symbol' 'assembly1' 다른 어셈블리에서 이미 가져온 대로  
  
 참조 된 어셈블리에서 이전에 가져온 참조 된 어셈블리에서 심볼을 가져올 수 없습니다.  
  
## <a name="example"></a>예제
다음 샘플에서는 C3846 오류가 생성 됩니다.  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 하 고이 컴파일합니다.  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  

