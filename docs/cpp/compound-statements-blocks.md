---
title: 복합 문 (블록) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
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