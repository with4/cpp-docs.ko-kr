---
title: "단순 변수 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 03d3939ef04a6a1a8bc5e3cd3ec5bfe56236ca0f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="simple-variable-declarations"></a>단순 변수 선언
직접 선언자의 가장 간단한 형태로 단순 변수를 선언하여 변수의 이름 및 형식을 지정합니다. 이 선언에서 변수의 저장소 클래스와 데이터 형식도 지정합니다.  
  
 변수 선언에는 저장소 클래스나 형식 또는 둘 다 필요합니다. 형식화되지 않은 변수(예: `var;`)는 경고를 생성합니다.  
  
## <a name="syntax"></a>구문  
 `declarator`:  
 *pointer* opt  
  
 *direct-declarator*  
  
 *direct-declarator*:  
 *identifier*  
  
 *identifier*:  
 *nondigit*  
  
 *identifier nondigit*  
  
 *identifier digit*  
  
 산술, 구조체, 공용 구조체, 열거형 및 void 형식과 `typedef` 이름으로 나타내는 형식의 경우 형식 지정자가 모든 형식 정보를 제공하므로 선언에 단순 선언자를 사용할 수 있습니다. 포인터, 배열 및 함수 형식에는 복잡한 선언자가 필요합니다.  
  
 쉼표(**,**)로 구분된 식별자 목록을 사용하여 같은 선언에 여러 변수를 지정할 수 있습니다. 선언에 정의된 모든 변수의 기본 형식은 같습니다. 예:  
  
```  
int x, y;        /* Declares two simple variables of type int */  
int const z = 1; /* Declares a constant value of type int */  
```  
  
 `x` 및 `y` 변수는 특정 구현에 대해 `int` 형식으로 정의된 집합에 값을 보유할 수 있습니다. 단순 개체 `z`가 값 1로 초기화되며 수정할 수 없습니다.  
  
 `z`의 선언이 초기화되지 않은 정적 변수용이거나 파일 범위에 있을 경우 초기 값 0을 수신하고 이 값은 수정할 수 없습니다.  
  
```  
unsigned long reply, flag; /* Declares two variables  
                              named reply and flag     */  
```  
  
 이 예제에서 `reply` 변수와 `flag` 변수 모두 `unsigned long` 형식이고 부호 없는 정수 값을 갖습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언자 및 변수 선언](../c-language/declarators-and-variable-declarations.md)
