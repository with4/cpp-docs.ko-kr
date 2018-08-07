---
title: jitintrinsic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0b114089567de06a71f15b69c556e08d1e4e9c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404082"
---
# <a name="jitintrinsic"></a>jitintrinsic
64비트 공용 언어 런타임에 중요한 항목으로 함수를 표시합니다. 이는 Microsoft에서 제공하는 라이브러리의 특정 함수에서 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>설명  
 **jitintrinsic** 추가 MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>)를 함수 서명에 합니다.  
  
 사용자가이 사용 하 여 권장 되지 않습니다 **__declspec** 한정자, 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)