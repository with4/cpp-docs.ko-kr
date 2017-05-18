---
title: "컴파일러 오류 C3888 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4b85385c97f5873c1b370cd72f0866439263f787
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3888"></a>컴파일러 오류 C3888
'name': 이 리터럴 데이터 멤버와 연관된 const 식은 C++/CLI에서 지원되지 않습니다.  
  
 *이름* 선언 된 데이터 멤버는 [리터럴](../../windows/literal-cpp-component-extensions.md) 키워드 컴파일러 지원 하지 않는 값으로 초기화 됩니다. 컴파일러는 상수 정수, 열거형 또는 문자열 형식만 지원합니다. **C3888** 오류의 일반적인 원인은 데이터 멤버가 바이트 배열로 초기화되었기 때문입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  선언된 리터럴 데이터 멤버가 지원되는 형식인지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리터럴](../../windows/literal-cpp-component-extensions.md)
