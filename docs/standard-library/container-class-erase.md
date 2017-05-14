---
title: "컨테이너 Class::erase | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: aeb81554bdc50db44e9e8d4ee66369149eceb875
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="container-classerase"></a>Container Class::erase
> [!NOTE]
>  이 항목은 C++ 표준 라이브러리에서 사용되는 작동하지 않는 컨테이너 예제로 Visual C++ 설명서에 포함되어 있습니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.  
  
 요소를 지웁니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,  
    iterator last);
```  
  
## <a name="remarks"></a>설명  
 첫 번째 멤버 함수에서 가리키는 제어 된 시퀀스의 요소를 제거 *_Where*합니다. 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 둘 다 제거된 요소 다음에 남아 있는 첫 번째 요소를 지정하는 반복기를 반환하거나, 이러한 요소가 없는 경우 [end](../standard-library/container-class-end.md)를 반환합니다.  
  
 복사 작업에서 예외를 throw하는 경우에만 멤버 함수는 예외를 throw합니다.  
  
## <a name="see-also"></a>참고 항목  
 [샘플 컨테이너 클래스](../standard-library/sample-container-class.md)

