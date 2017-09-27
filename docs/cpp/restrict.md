---
title: "제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- restrict
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
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
ms.openlocfilehash: 2d1cdbff84966e7926b30ef70c40581cc3801a93
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="restrict"></a>restrict
**Microsoft 전용**  
  
 포인터 형식을 반환하는 함수 선언 또는 정의에 적용되며, 함수가 다른 포인터를 사용하여 별칭이 지정되지 않을 개체를 반환함을 컴파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>설명  
 컴파일러는 `__declspec(restrict)`를 전파합니다. 예를 들어 CRT `malloc` 함수는 `__declspec(restrict)`로 데코레이팅되므로 `malloc`를 사용하여 메모리 위치로 초기화된 포인터도 별칭이 지정되지 않습니다.  
  
 컴파일러는 포인터가 실제로 별칭이 지정되지 않았는지 확인하지 않습니다. 프로그램에서 `restrict __declspec` 한정자로 표시된 포인터에 별칭을 지정하지 않도록 확인하는 것은 개발자의 책임입니다.  
  
 변수에서와 유사한 의미 체계에 대 한 참조 [__restrict](../cpp/extension-restrict.md)합니다.  
  
## <a name="example"></a>예제  
 참조 [noalias](../cpp/noalias.md) 사용 하는 예제 `restrict`합니다.  
  
 C + + AMP의 일부인 restrict 키워드에 대 한 정보를 참조 하십시오. [제한 (c + + AMP)](../cpp/restrict-cpp-amp.md)합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)
