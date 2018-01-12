---
title: jitintrinsic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 451f9e534284a2daa69ddc11495f6ecc8af1ee13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="jitintrinsic"></a>jitintrinsic
64비트 공용 언어 런타임에 중요한 항목으로 함수를 표시합니다. 이는 Microsoft에서 제공하는 라이브러리의 특정 함수에서 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>설명  
 `jitintrinsic`는 MODOPT(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>)를 함수 서명에 추가합니다.  
  
 예기치 않은 결과가 발생할 수 있기 때문에 이 `__declspec` 한정자는 사용하지 않도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)