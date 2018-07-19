---
title: 컴파일러 오류 C3846 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97d5650d1743ba379ce065d4051bfed807a1df71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268028"
---
# <a name="compiler-error-c3846"></a>컴파일러 오류 C3846
'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'assembly1' 다른 어셈블리에서 'symbol' 이미 가져왔기 대로  
  
 참조 된 어셈블리에서 이전에 가져온 때문에 참조 된 어셈블리에서에 기호를 가져올 수 없습니다.  
  
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
