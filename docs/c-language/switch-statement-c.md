---
title: "switch 문 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- switch
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 3ff740fe76a52c94ed084c6f9f975c950502424e
ms.lasthandoff: 04/01/2017

---
# <a name="switch-statement-c"></a>switch 문 (C)
`switch` 및 **case** 문은 복잡한 조건부 및 분기 작업을 제어하는 데 도움이 됩니다. `switch` 문은 해당 본문 내의 문으로 제어를 전달합니다.  
  
## <a name="syntax"></a>구문  
 *selection-statement*:  
 **switch(** *expression* **)** *statement*  
  
 *labeled-statement*:  
 **case**  *constant-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 **case** *constant-expression*이 **switch(** *expression* **)**의 값과 일치하는 문으로 제어가 전달됩니다. `switch` 문에는 **case** 인스턴스가 개수에 제한 없이 포함될 수 있지만 동일한 `switch` 문 내에 값이 같은 두 case 상수가 존재할 수는 없습니다. 문 본문의 실행은 선택된 문에서 시작되고 본문의 끝에 도달하거나 **break** 문이 본문 밖으로 제어를 전달할 때까지 계속됩니다.  
  
 `switch` 문의 사용은 대개 다음과 같습니다.  
  
 `switch` ( *expression* )  
  
 **{**  
  
 *declarations*  
  
 입니다.  
  
 을 발생시킵니다.  
  
 입니다.  
  
 **case** *constant-expression* **:**  
  
 *statements executed if the expression equals the*  
  
 *value of this constant-expression*  
  
 입니다.  
  
 을 발생시킵니다.  
  
 입니다.  
  
 **break;**  
  
 **default :**  
  
 *statements executed if expression does not equal*  
  
 *any case constant-expression*  
  
 **}**  
  
 **break** 문을 사용하여 `switch` 문 내의 특정 case 처리를 종료하고 `switch` 문의 끝으로 분기할 수 있습니다. **break**가 없는 경우 프로그램은 다음 case로 지속되어 **break** 또는 문의 끝에 도달할 때까지 문을 실행합니다. 어떤 상황에서는 이러한 지속이 바람직할 수 있습니다.  
  
 **default** 문은 **case** *constant-expression*이 **switch(** *expression* **)**의 값과 같지 않은 경우 실행됩니다. **default** 문이 생략되는 경우 **case** 일치가 발견되지 않으면 `switch` 본문의 문이 실행되지 않습니다. **default** 문은 하나만 존재할 수 있습니다. **default** 문은 끝에 와야 할 필요가 없으며 `switch` 문의 본문 어느 위치에나 나타날 수 있습니다. **case** 또는 **default** 레이블은 `switch` 문 안에서만 나타날 수 있습니다.  
  
 `switch` *expression* 및 **case** *constant-expression*의 형식은 정수여야 합니다. 각 **case** *constant-expression*의 값은 문 본문 내에서 고유해야 합니다.  
  
 `switch` 문 본문의 **case** 및 **default** 레이블은 문 본문에서 실행이 시작되는 위치를 결정하는 초기 테스트에서만 의미가 있습니다. switch 문은 중첩될 수 있습니다. `switch` 문을 실행하기 전에 모든 정적 변수가 초기화됩니다.  
  
> [!NOTE]
>  선언은 `switch` 본문을 형성하는 복합 문의 위쪽에 나타날 수 있지만 선언에 포함된 초기화는 수행되지 않습니다. `switch` 문은 초기화가 포함된 줄을 우회하여 본문 내의 실행 문으로 제어를 직접 전달합니다.  
  
 다음 예제에서는 `switch` 문을 보여 줍니다.  
  
```  
switch( c )   
{  
    case 'A':  
        capa++;  
    case 'a':  
        lettera++;  
    default :  
        total++;  
}  
```  
  
 이 예제에서는 **break** 문이 다음 case 앞에 나타나지 않으므로 `c`가 `'A'`와 같은 경우 `switch` 본문의 모든 세 문이 실행됩니다. 실행 제어는 첫 번째 문(`capa++;`)으로 전달되고 본문의 나머지 부분에서 순서대로 계속됩니다. `c`가 `'a'`와 같은 경우 `lettera` 및 `total`이 증가합니다. `total`가 `c` 또는 `'A'`와 같지 않은 경우 `'a'`만 증가합니다.  
  
```  
switch( i )   
{  
    case -1:  
        n++;  
        break;  
    case 0 :  
        z++;  
        break;  
    case 1 :  
        p++;  
        break;  
}  
```  
  
 이 예제에서 **break** 문은 `switch` 본문의 각 문 뒤에 나옵니다. **break** 문은 한 문이 실행된 후 문 본문에서 강제로 빠져나옵니다. `i`가 –1과 같은 경우 `n`만 증가합니다. `n++;` 문 다음에 오는 **break**는 실행 제어가 문 본문 밖으로 전달되고 나머지 문들을 우회하도록 합니다. 이와 마찬가지로 `i`가 0과 같은 경우 `z`만 증가하고, `i`가 1과 같은 경우에는 `p`만 증가합니다. 제어가 복합 문의 끝에서 본문 밖으로 전달되므로 마지막 **break** 문은 반드시 필요하지는 않지만 일관성을 위해 포함되었습니다.  
  
 다음 예제와 같이 단일 문이 여러 **case** 레이블을 수행할 수 있습니다.  
  
```  
case 'a' :  
case 'b' :  
case 'c' :  
case 'd' :  
case 'e' :  
case 'f' :  hexcvt(c);  
```  
  
 이 예제에서 *constant-expression*이 `'a'`와 `'f'` 사이의 문자와 같은 경우 `hexcvt` 함수가 호출됩니다.  
  
 **Microsoft 전용**  
  
 Microsoft C는 `switch` 문의 case 값 수를 제한하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C의 경우 `switch` 문에서 257개 이상의 case 레이블이 허용되어야 합니다.  
  
 기본적으로 Microsoft C에는 Microsoft 확장을 사용하도록 설정되어 있습니다. 이러한 확장을 사용하지 않도록 설정하려면 /Za 컴파일러 옵션을 사용하십시오.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [switch 문(C++)](../cpp/switch-statement-cpp.md)
