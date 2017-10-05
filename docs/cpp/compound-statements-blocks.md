---
title: "복합 문 (블록) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
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
ms.openlocfilehash: 9dc28fde0ab2cf5b21771347554d0c664b7f462d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="compound-statements-blocks"></a>복합 문(블록)
복합 문은 중괄호로 묶인 0 개 이상의 문으로 구성 (**{}**). 복합 문은 원하는 어느 곳에서든 사용할 수 있습니다. 복합 문은 일반적으로 "블록"이라고 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>설명  
 다음 예제에서는 서 복합 문을 사용 하 여는 *문을* 의 일부로 **경우** 문 (참조 [if 문을](../cpp/if-else-statement-cpp.md) 는 구문에 대 한 세부 정보에 대 한):  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  선언에 있는 문은 중 하나일 수 있습니다는 선언 문을 이기 때문에 *문 목록*합니다. 결과적으로 복합 문 내에 선언되었지만 정적으로 명시적 선언되지 않은 이름은 지역 범위와 개체의 수명을 갖습니다. 참조 [범위](../cpp/scope-visual-cpp.md) 로컬 범위를 갖는 이름 처리 하는 방법에 대 한 세부 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 문 개요](../cpp/overview-of-cpp-statements.md)
