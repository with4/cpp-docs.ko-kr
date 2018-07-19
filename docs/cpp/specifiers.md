---
title: 지정자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d437b70148fdaba4c8eb4d7aa855e7d75f6f2487
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953749"
---
# <a name="specifiers"></a>지정자
이 항목에 설명 합니다 *-specifiers* (선언 지정자) 구성 요소를 [선언](declarations-and-definitions-cpp.md).  
  
 다음 자리 표시자 및 언어 키워드는 선언 지정자입니다.  
  
 *저장소 클래스 지정자*  
  
 *형식 지정자*  
  
 *함수 지정자*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef] ( [typedef](http://msdn.microsod) `(` *확장-선언-한정자-seq* `)`  
  
## <a name="remarks"></a>설명  
 합니다 *-specifiers* 선언의 부분은의 가장 긴 시퀀스 *-specifiers* 또는 참조 한정자는 포인터를 포함 하지 않는 형식 이름을 의미 하기 위해 사용할 수 있는 합니다. 선언의 나머지 부분은 합니다 *선언 자*에 소개 된 이름을 포함 하는 합니다.  
  
 다음 표에서 4 개의 선언을 목록과 후 각 선언의 *선언 지정자* 하 고 *declarator* 구성 요소 개별적으로 합니다.  
  
|선언|*선언 지정자*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|**char**|`*lpszAppName`|  
|`typedef char * LPSTR;`|**char**|`*LPSTR`|  
|`const int func1();`|**const int**|`func1`|  
|`volatile void *pvvObj;`|**volatile void**|`*pvvObj`|  
  
 때문에 **서명**, **부호 없는**합니다 **긴**, 및 **짧은** 의미 모든 **int**,  **typedef** 의 구성원으로 만들어진 다음이 키워드 중 하나로 다음 이름을 *declarator-list* 아닌 *-specifiers*합니다.  
  
> [!NOTE]
>  이름은 다시 선언할 수 있기 때문에 현재 범위에서 최신 선언에 해석이 적용됩니다. 재선언은 특히 `typedef` 이름이 컴파일러에 의해 해석되는 방법에 영향을 줄 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 정의](declarations-and-definitions-cpp.md)