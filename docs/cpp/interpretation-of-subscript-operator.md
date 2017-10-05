---
title: "첨자 연산자의 해석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator, interpretation of
- arrays [C++], subscripting
- interpreting subscript operators
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>첨자 연산자의 해석
다른 연산자와 달리 첨자 연산자 (****) 사용자가 다시 정의할 수 있습니다. 첨자 연산자의 기본 동작은 다음 메서드를 사용하여 배열 이름과 첨자를 결합하는 것입니다.  
  
 \*((*배열 이름*) + (*아래 첨자*))  
  
 포인터 형식을 비롯한 모든 추가에서와 마찬가지로 형식 크기를 조정하기 위해 크기 조정이 자동으로 수행됩니다. 따라서 결과 값은 *아래 첨자* 의 원점부터 바이트 *배열 이름*아니라는 *아래 첨자*th 요소는 배열입니다. (이 변환에 대 한 자세한 내용은 참조 [덧셈 연산자](../cpp/additive-operators-plus-and.md).)  
  
 다차원 배열에서도 다음 메서드를 사용하여 주소가 파생됩니다.  
  
 **((**   
 ***배열 이름은* ) + (**   
 ***아래 첨자* 1***max*2 * \* max*3*...max*n) ** + ** *아래 첨자*2 * \* max*3*...max*n).   입니다. 입니다. *+**아래 첨자*n))  
  
## <a name="see-also"></a>참고 항목  
 [배열](../cpp/arrays-cpp.md)
