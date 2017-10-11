---
title: "__if_not_exists 문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5eff74bd6405d7ec63b3cc8fbea968df984fddb8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="ifnotexists-statement"></a>__if_not_exists 문
`__if_not_exists` 문은 지정된 식별자가 있는지 여부를 테스트합니다. 식별자가 없는 경우 지정된 문 블록이 실행됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`identifier`|존재 여부를 테스트할 식별자입니다.|  
|`statements`|경우에 실행할 하나 이상의 문을 `identifier` 존재 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
  
> [!CAUTION]
>  가장 안정적인 결과를 얻으려면 다음 제약 조건에서 `__if_not_exists` 문을 사용합니다.  
  
-   템플릿이 아니라 단순 형식에만 `__if_not_exists` 문을 적용합니다.  
  
-   클래스 내부 또는 외부 모두에서 `__if_not_exists` 문을 식별자에 적용합니다. 지역 변수에 `__if_not_exists` 문을 적용하지 마십시오.  
  
-   `__if_not_exists` 문은 함수의 본문에서만 사용합니다. 함수 본문 외부에서 `__if_not_exists` 문은 완전히 정의된 형식만 테스트할 수 있습니다.  
  
-   오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.  
  
 보완 하는 `__if_not_exists` 문이 [__if_exists](../cpp/if-exists-statement.md) 문.  
  
## <a name="example"></a>예제  
 사용 하는 방법에 대 한 예제를 보려면 `__if_not_exists`, 참조 [__if_exists 문](../cpp/if-exists-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선택 문](../cpp/selection-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [__if_exists 문](../cpp/if-exists-statement.md)
