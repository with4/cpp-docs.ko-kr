---
title: "정적 저장소 클래스 지정자 | Microsoft Docs"
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
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 34f60570d18882ddfb7ebef78977d6b2f5c82000
ms.lasthandoff: 02/24/2017

---
# <a name="static-storage-class-specifier"></a>정적 저장소 클래스 지정자
**정적** 저장소 클래스 지정자를 사용하여 내부 수준에서 선언된 변수는 global 수명을 갖지만 선언된 블록 안에만 표시됩니다. 상수 문자열의 경우**static**을 사용하면 자주 호출된 함수에서 빈번한 초기화 부담이 줄어들어 도움이 됩니다.  
  
## <a name="remarks"></a>설명  
**static** 변수를 명시적으로 초기화하지 않으면 기본적으로 0으로 초기화됩니다. 함수 안에서 **static**은 저장소를 할당되게 하며 정의로 사용됩니다. 내부 정적 변수는 단일 함수에만 표시되는 전용 영구 저장소를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
[C 저장소 클래스](c-storage-classes.md)  
[저장소 클래스(C++)](../cpp/storage-classes-cpp.md)  
