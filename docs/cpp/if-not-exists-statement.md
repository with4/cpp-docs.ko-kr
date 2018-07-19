---
title: __if_not_exists 문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37148a3849e859d7ca77595416616cfa0b952ecf
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939951"
---
# <a name="ifnotexists-statement"></a>__if_not_exists 문
합니다 **__if_not_exists** 문은 지정된 된 식별자가 있는지 여부를 테스트 합니다. 식별자가 없는 경우 지정된 문 블록이 실행됩니다.  
  
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
>  가장 안정적인 결과 달성 하려면 사용 합니다 **__if_not_exists** 다음 제약 조건에 따라 문입니다.  
  
-   적용 된 **__if_not_exists** 문, 템플릿이 아니라 단순 형식에만 합니다.  
  
-   적용 된 **__if_not_exists** 문을 내부 또는 외부 클래스 식별자입니다. 적용 되지 않습니다 합니다 **__if_not_exists** 지역 변수에 문입니다.  
  
-   사용 된 **__if_not_exists** 문은 함수의 본문에만. 함수 본문 외부에서 **__if_not_exists** 문은 완전히 정의 된 형식만 테스트할 수 있습니다.  
  
-   오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.  
  
 보완 하는 **__if_not_exists** 문이 합니다 [__if_exists](../cpp/if-exists-statement.md) 문입니다.  
  
## <a name="example"></a>예  
 사용 하는 방법에 대 한 예로 **__if_not_exists**를 참조 하세요 [__if_exists 문](../cpp/if-exists-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선택 문](../cpp/selection-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [__if_exists 문](../cpp/if-exists-statement.md)