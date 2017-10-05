---
title: "이항 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators
- operators [C++], binary
- binary operators
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 384ac135c7ecb63b864160723984ef5d271e1395
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="binary-operators"></a>이항 연산자
다음 표에서는 오버로드될 수 있는 연산자 목록을 보여 줍니다.  
  
### <a name="redefinable-binary-operators"></a>다시 정의 가능 이항 연산자  
  
|연산자|이름|  
|--------------|----------|  
|**,**|쉼표|  
|`!=`|같지 않음|  
|`%`|모듈러스|  
|`%=`|모듈러스/할당|  
|**&**|비트 AND|  
|**&&**|논리적 AND|  
|**&=**|비트 AND/할당|  
|**\***|곱하기|  
|**\*=**|곱하기/할당|  
|**+**|더하기|  
|`+=`|더하기/할당|  
|**-**|빼기|  
|**-=**|빼기/할당|  
|**->**|멤버 선택|  
|**->\***|멤버 포인터 선택|  
|**/**|나눗셈 기호|  
|`/=`|나누기/할당|  
|**<**|보다 작음|  
|**<<**|왼쪽 <Shift>|  
|**<<=**|왼쪽 시프트/할당|  
|**<=**|작거나 같음|  
|**=**|할당|  
|`==`|같음|  
|**>**|보다 큼|  
|**>=**|크거나 같음|  
|**>>**|오른쪽 Shift|  
|**>>=**|오른쪽 시프트/할당|  
|**^**|배타적 OR|  
|`^=`|배타적 OR/할당|  
|**&#124;**|포괄적 비트 OR|  
|`&#124;=`|포괄적 비트 OR/할당|  
|`&#124;&#124;`|논리적 OR|  
  
 이항 연산자 함수를 비정적 멤버로 선언하려면 해당 함수를 다음과 같은 형태로 선언해야 합니다.  
  
 *ret 형식이* **연산자**`op`**(** `arg` **)**  
  
 여기서 *ret 형식이* 은 반환 형식이 `op` 는 앞의 표에 나와 있는 연산자 중 하나 및 `arg` 모든 형식의 인수입니다.  
  
 이항 연산자 함수를 전역 함수로 선언하려면 해당 함수를 다음과 같은 형태로 선언해야 합니다.  
  
 *ret 형식이* **연산자**`op`**(** `arg1` **,** `arg2` **)**  
  
 여기서 *ret 형식이* 및 `op` 는 멤버 연산자 함수로 설명 되 고 `arg1` 및 `arg2` 는 인수. 인수 중 하나 이상이 클래스 형식이어야 합니다.  
  
> [!NOTE]
>  이항 연산자의 반환 형식에 대한 제한은 없지만 대부분의 사용자 정의 이항 연산자는 클래스 형식이나 클래스 형식에 대한 참조를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 오버로드](../cpp/operator-overloading.md)
