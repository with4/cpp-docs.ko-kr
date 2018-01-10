---
title: "지정자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 352ef898c9380c55e90205129ba6fe48bf352856
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifiers"></a>지정자
이 항목에 설명 된 *decl 지정자* 의 (선언 지정자) 구성 요소는 [선언](declarations-and-definitions-cpp.md)합니다.  
  
 다음 자리 표시자 및 언어 키워드는 선언 지정자입니다.  
  
 *저장소 클래스 지정자*  
  
 *형식 지정자*  
  
 *함수 지정자*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [__declspec](../cpp/declspec.md) `(` *확장-decl-한정자-seq*`)`  
  
## <a name="remarks"></a>설명  
 *decl 지정자* 선언의 부분은의 가장 긴 시퀀스 *decl 지정자* 또는 참조 한정자를 포인터를 포함 하지 않고 형식 이름을 의미 하기 위해 취할 수입니다. 선언의 나머지는 *선언 자*, 도입 된 이름이 포함 된 합니다.  
  
 다음 표에서 4 개의 선언을 목록과 다음 각 선언 *decl 지정자* 및 *선언 자* 구성 요소 별도로 합니다.  
  
|선언|*decl 지정자*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 때문에 `signed`, `unsigned`, `long`, 및 `short` 모든 의미 `int`, `typedef` 의 구성원 이어야 만들어지며이 키워드 중 하나는 다음 이름을 *선언 자 목록* 의*decl 지정자*합니다.  
  
> [!NOTE]
>  이름은 다시 선언할 수 있기 때문에 현재 범위에서 최신 선언에 해석이 적용됩니다. 재선언은 특히 `typedef` 이름이 컴파일러에 의해 해석되는 방법에 영향을 줄 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 정의](declarations-and-definitions-cpp.md)