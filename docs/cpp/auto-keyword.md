---
title: "auto 키워드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0413fd47b486cf1613b7c249b93e6a3507a5577c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="auto-keyword"></a>auto 키워드
`auto` 키워드는 선언 지정자입니다. 그러나 C++ 표준에는 이 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다. Visual c + + 2010 이전는 `auto` 에 변수를 선언 하는 키워드는 *자동* 저장소 클래스, 즉 변수 지역 변수입니다. Visual c + + 2010부터는 `auto` 키워드로 선언 된 변수 선언에 초기화 식에서 해당 형식이 추론 됩니다. [/zc: auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션의 의미를 제어는 `auto` 키워드입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>설명  
 `auto` 키워드 정의는 C 프로그래밍 언어가 아닌 C++ 프로그래밍 언어로 변경됩니다.  
  
 다음 항목에서는 `auto` 키워드 및 해당 컴파일러 옵션을 설명합니다.  
  
-   [자동](../cpp/auto-cpp.md) 설명의 새 정의 `auto` 키워드입니다.  
  
  
-   [/Zc: auto (변수 형식 추론)](../build/reference/zc-auto-deduce-variable-type.md) 의 정의 컴파일러에 알리는 컴파일러 옵션에 설명 된 `auto` 키워드를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)
